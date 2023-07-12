---
layout: post
title: 비동기 데이터 매칭 작업
subtitle: 2023-01-20 ~ 2023-02-01 (1주)
categories: 2022.Co.Marvrus
tags: 
---

## 주 프로젝트
- 서비스 중인 [메타버스 학습 플랫폼 MEEMZ](https://seunghyeon-hong.github.io/co.gnflex/2022/08/02/live-service-client-dev.html) 참조  
  데이터 뿐 아니라 이미지도 서버에 저장하는 것으로 추가 기획되어 작업함
<table>
  <tr>
    <td>프로젝트명</td>
    <td>비동기 데이터 매칭 작업</td>
    <td>기간</td>
    <td>2023-01-20 ~ 2023-02-01 (1주)</td>
  </tr>
  <tr>
    <td>개요</td>
    <td>Input 이미지와 비동기 분석결과의 매칭 필요</td>
    <td>팀원</td>
    <td>2명</td>
  </tr>
  <tr>
    <td>주요 역할 및 담당</td>
    <td colspan="3">SDK 로직 수정과 클라이언트 적용</td>
  </tr>
  <tr>
    <td>성과</td>
    <td colspan="3">분석 결과와 리소스가 되는 이미지를 매칭함<br>
    Formdata로 이미지 저장 구현</td>
  </tr>
</table>

- **인원**  
  클라이언트1, 서버1
<br>

## 개발이슈  
1. 이미지 분석 기술은 리소스를 많이 점유하여 기본적으로 **비동기**이다. 이미지를 분석 시작하는 시점과 분석이 종료되는 시점이 다르다.  
2. 카메라로 촬영한 이미지를 모듈에서 분석하기 위해서 **Mat이라는 자료형**태로 변환을 시킨다.  
3. 서버에 저장할 데이터는 카메라에 찍힌 이미지 데이터를 jpg 등으로 인코딩한 파일형태이다.  
4. 한 번 Mat으로 변환한 데이터는 원래대로 되돌릴 수 없다.
<br>

분석 결과만 저장하던 이전 기획에서는 분석 시작 시 이미지 데이터가 릴리즈 되어도 문제가 없었다. 하지만 바뀐 기획에서는 SDK의 상당부분을 바꾸지 않는 이상 효율적인 매칭이 어려웠다.  

### 기존 구현 방식  
- 순서 :  
이미지 리소스 -> Mat데이터로 변환(이미지 리소스 릴리즈) -> 큐 적재 -> 분석시작 -> 분석완료 -> 분석결과 저장(Mat데이터 릴리즈)
<br>

[![기존 구현 방식](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20230120_async_sturucture1.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20230120_async_sturucture1.png)  
<!-- (https://mermaid.live/edit#pako:eNqNUk1v2zAM_SuETiuQBumwXowhQ4Dk1Bbb6nQnXWiJtjVYkqePZlnR_z7KabOkvewgQHp85HsU-SSU1yQqEelXJqdobbALaKUbMSSjzIguAQJGqNc352hT0Duv80DnAfUvAHVutn0g1NJJ53wi8I8UAKuOEhjbQRu8BYWWAp4Smur7w-ZhU7IG70cgBvcQR1KmNaQhGUufm7Ck3xdszxqXE7vAy-WyqSI5PdVOHrirzAFG_qvU1WJh46kPVZkI6HDY_zGuA-d3X17CA7UJfMuMPXFKc8naqhpZoEgjW1jff_32jux84b6l1tvV_RZWkw6d6x_F5_O5dOrQIT4SBIp5SKAx4bHB0x9WOAynpNLjricHajDEY9o5TNIFUglC13z4eH09u_q0KOfiYHEaUsm6XdVbqFc_Nuv39Yzqgb-IhSHmwOJtwS0mxncm9ZB6Km0WNPXIQ4efOTKZHZN-MS5mghfAotG8ik_SAUjBeZakqPiqqUVWlUK6Z6ZiTr7eOyWqFodIM5FH9vO6um_QjTbJhyNI0_PusPTT7j__BRrHEfs) -->
 

### 바뀐 구현 방식  
1. 이미지 데이터와 함께 프레임 id를 관리 (릴리즈 하지 않음)
2. 변환한 Mat데이터와 id를 모듈에 보내 분석
3. 분석이 완료되면 id로 리소스 이미지를 찾아 매칭
4. 매칭된 결과 데이터는 기존API를 통해 저장
5. 이미지는 S3 Form데이터로 저장
6. 리스트에 적재했던 그 동안의 이미지 데이터는 일괄 삭제
7. 반복
<br>

많은 이미지 데이터를 가지고 있어야 하기에 자원을 소모하지만 서비스중인 코드를 가장 적게 수정하는 방법이어서 선택했다.<br>
연구개발에 사용되는 기능으로, 초상권 사용 동의 UI까지 추가한 후 배포될 예정이다.

<p><br></p>

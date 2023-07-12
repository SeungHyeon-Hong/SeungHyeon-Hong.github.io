---
layout: post
title: (B2B)PlayTango 기술 제휴 RnD
subtitle: 2022-10-05 ~ 2022-11-30 (2개월)
categories: 2022.Co.Marvrus
tags: 
---

## 주 프로젝트
- **타사 앱에 자사 모듈 탑재**  
<table>
  <tr>
    <td>프로젝트명</td>
    <td>PlayTango 기술 제휴 RnD</td>
    <td>기간</td>
    <td>2022-10-05 ~ 2022-11-30 (2개월)</td>
  </tr>
  <tr>
    <td>개요</td>
    <td>타사 앱에 자사 모듈 탑재</td>
    <td>팀원</td>
    <td>3명</td>
  </tr>
  <tr>
    <td>주요 역할 및 담당</td>
    <td colspan="3">클라이언트 개발 전반</td>
  </tr>
  <tr>
    <td>성과</td>
    <td colspan="3">
    개발중인 앱에 자사 모듈(MEE Engine, 얼굴인식)을 탑재한 버젼 전달<br>
    추후 개발진행 시 요구되는 선행 작업을 확인
    </td>
  </tr>
</table>

- **개발툴**  
  Unity, Android Studio
<br>

- **인원**  
  기획1, 클라이언트1, 아트1
<br>

- **소통**  
Figma, Atlassian
<br>

- **산출**  
  제공받은 타사 앱에 얼굴인식 기능 구현
<br>

## 개발 이슈  
1. Unity로 개발을 진행.  
2. **Unity에서 Android 모듈은 단 1개를 사용**할 수 있다.  
3. 제공받은 앱은 전용기기와 통신에 필요한 블루투스 모듈을 사용한다.  
4. 자사 모듈 역시, 안드로이드 플랫폼 용으로 포팅된 Java 코드를 모듈화하여 사용한다.  
5. 타사 앱의 기능과 자사 모듈을 동시에 사용하기 위해서는 2개의 모듈 모두 필요하다.  

Unity 작업 시 1개의 안드로이드 모듈만 사용할 수 있으나, 사용해야 하는 모듈이 2개인 상황이다. 이런 경우, 안드로이드 모듈을 1개로 합쳐 제작한 후 Unity에 넣어 사용해야 한다.<br>
다만, 시간 제약과 안드로이드 개발에 대한 기술 부족으로 모듈을 합치는 작업은 이번 프로젝트 범위에서 제외되었고, 양 측의 모듈 중 어느 쪽을 사용하더라도 앱이 정상 동작하도록 2가지 버젼을 제작 후 RnD를 종료했다.
<br>

<p><br></p>

<hr>

## 서비스 간략 소개  
<a href="https://playtango.co.kr/" target="_blank"><span style="font-size:2em; font-weight:bold;">PlayTango</span></a> 는 전용기기와 전용블록을 사용하는 유아대상 학습서비스이다.  
전용 블록이 필요 없는 태블릿 버젼을 개발중에 자사의 얼굴인식 기능을 접목하는 B2B RnD를 진행했다.

<p><br></p>
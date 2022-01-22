---
layout: post
title: Unity 파이프라인 교체
subtitle: 2021-07-01 ~ 2021-08-31 (2개월)
categories: Co.GnFlex
tags: 
---

## 주 프로젝트
- **Unity 3D에서 URP로 환경 변경**
<table>
  <tr>
    <td>프로젝트명</td>
    <td>URP 환경 셋팅</td>
    <td>기간</td>
    <td>2021-07-01 ~ 2021-08-31 (2개월)</td>
  </tr>
  <tr>
    <td>개요</td>
    <td>작업환경 셋팅을 변경</td>
    <td>팀원</td>
    <td>3명</td>
  </tr>
  <tr>
    <td>주요 역할 및 담당</td>
    <td colspan="3">프로젝트 환경 조성. 기능 검증.</td>
  </tr>
  <tr>
    <td>성과</td>
    <td colspan="3">Unity 3D에서 URP로 프로젝트 환경 변경 완료.<br>변경된 환경에서 컨텐츠 3편 제작.<br>컨텐츠에 3D오브젝트와 라이트를 적용하여 시각적인 퀄리티 향상을 확인함.</td>
  </tr>
</table>


## Art파트의 요청 사항  
- **Unity 셰이더 그래프 사용 희망**   
    셰이더 그래프(Visual Effect Graph) 사용을 위해 **Scriptable Render Pipeline(SRP)**이 요구됨.   
- Spine 애니메이션 리소스에 **normal map(노멀맵) 적용을 희망**   
    노멀맵이 적용된 이미지를 시각적으로 확인하기 위하여 **2D라이트**가 요구됨.  
<p>Scriptable Render Pipeline(SRP)에는 URP와 HDRP가 있다. 완제품의 서비스환경이 미니PC 기준이어서 고사양의 작업은 필요치 않기에, 비교적 가벼운 작업에 적합한 URP환경을 최종적으로 선택하였다. 또, SRP는 2DLight도 지원한다.
</p>
<p>차후 제작되는 컨텐츠는 2D와 3D리소스가 혼합 사용될 예정이다. 3D오브젝트를 자유롭게 사용하기 위해서 무엇보다도 셰이더가 중요하기에 관련 설정에 초점을 맞췄다. 그래서 특정 Unity 버젼에서 셰이더 그래프가 안정적으로 동작한다는 이펙터의 요청을 수렴하여, 가급적 교체하지 않는 Unity Editor의 버젼을 업그레이드 하였다. 
</p>

## 기능 검증 내용  
- 셰이더 그래프로 제작한 이펙트와 컨텐츠 리소스 조합테스트  
- Spine 4.0에서 제작한 리소스의 URP 2D Render Pipeline 환경 테스트  
- 2D/3D환경의 동시사용불가 이슈가 있기에, 기획단계에서 결정하기로 협의  
<br>

URP는 비교적 최근에 만들어졌지만, 아트 파트에서 사용하는 애니메이션 툴인 [Spine에서 URP를 지원하는 라이브러리를 제공](http://en.esotericsoftware.com/spine-unity-download#Installing-Extension-UPM-Packages)했기에 문제는 없었다. 다만 최신버젼의 사용을 희망했기에 2021년 7월 기준, 최신 버젼인 spine-unity 4.0 으로 버젼업하였다.  

공식아카이브에서 제공하는 패키지의 Example.  
[![스파인 공식 제공 2D샘플](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20210701_urp_2drenderer_officialsample.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20210701_urp_2drenderer_officialsample.png)

Unity URP 2D 기본 셋팅 시의 라이트 적용 차이.  
[![스파인 공식 제공 2D샘플](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20210701_urp_2drenderer_default_render_setting.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20210701_urp_2drenderer_default_render_setting.png)

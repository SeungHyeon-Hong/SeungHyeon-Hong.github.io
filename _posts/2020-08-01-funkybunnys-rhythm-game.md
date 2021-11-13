---
layout: post
title: FunkyBunnys
subtitle: 2020-08-01 ~ 2020-12-01(4개월)
categories: zest.Activities  
tags: [Unity, PC, 3D, RhythmGame, Package]  
---

## 개요  
- 제목_ FunkyBunnys  
- 기간_ 2020-08-01 ~ 2020-12-01(4개월) 
- 팀원_ 모델러1, 플머1  
- 결과_ 2020 BuStar PC데모 출품  
<br>

<iframe style="displey:block; width:100%; hetght:100%;" width="640" height="360" src="https://www.youtube.com/embed/8Ijv0P6j-Pg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 기획의도  
- 3D  
- 스토리 형 리듬게임  
- 패키지 게임  
- 레벨업, 상점이용 등 약간의 RPG 기획 첨가.  

## 이야기  
<p>우연히 인연이 닿아 고퀄리티의 맵에서 프로그래밍을 해 볼 수 있었다. 데모는 모든 리소스가 빌드인(Build-in)이었지만, 스팀 출시를 상정하고 있었기에 <b>많은 리소스를 관리</b>하는 것이 큰 과제였다. 리소스 자체의 용량, 특히 맵의 용량이 컸기때문에 나눠서 로드해도 <b>런타임 로딩시간</b>이 1초를 넘기는 일이 다반사였기 때문이다. 여러 맵을 돌아다니며 스토리를 진행하는 것이 기획의 골자이기 때문에 더욱 고민이 깊었다.</p>
<p>결론적으로, 최적화를 진행하면 예쁘게 만들어 둔 맵의 퀄리티가 떨어져 게임의 매력이 줄어드니, 고용량 패키지인 것을 감수하고 더욱 고퀄리티의 게임을 만드는 방향으로 이야기를 진행했다. 데이터는 챕터별로 나눠서 올릴 수 있도록 패키징하고, 로딩 페이지를 따로 제작해서 로딩 화면에서도 볼거리를 제공하기로 했다.
</p>


## 다이어그램  
- 스토리형 게임이기 때문에 많은 대사를 소화할 수 있도록 구성했다.  
추후 컨텐츠 추가를 상정한 클래스 구조이다.  
Json, XML 등의 외부 스크립트로 대사칩을 작업할 수 있도록 설계했다.  


[![Lines&Stories](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20200801_classdiagram_lineinfo.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20200801_classdiagram_lineinfo.png)
<br>

- 다양한 미션의 RPG적 요소가 기획되어 있었다.  
추후에 추가 가능한 요소로써 특정위치 찾기, 특정 키 누르기, 대화 시 배경설정, 씬 전환 이벤트까지 작업했다.  


[![Events&Missions](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20200801_classdiagram_events.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20200801_classdiagram_events.png)

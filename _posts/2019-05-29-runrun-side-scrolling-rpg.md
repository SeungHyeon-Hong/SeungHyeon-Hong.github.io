---
layout: post
title: RUNRUN
subtitle: 2019-05-29 ~ 2019-08-20 (3개월)
categories: zest.Activities  
tags: [Unity, PC, Android, Side-scrolling, RPG]  
---

## 개요  
- 제목_ RUNRUN  
- 기간_ 2019-05-29 ~ 2019-08-20 (3개월)  
- 팀원_ 1인개발  
- 결과_ PC/Mobile 크로스플랫폼 지원 빌드  
<br>

<iframe style="displey:block; width:100%; hetght:100%;" width="640" height="360" src="https://www.youtube.com/embed/-gJSakY-isQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 기획의도  
- 2D 횡스크롤 RPG.  
- 다양한 난이도의 맵을 제공.  

## Code  
<div style="font-size: 1.2em; font-weight: bold;">무한히 반복하는 맵</div>   
1. 충분히 긴 맵을 2개 준비한다.
2. 캐릭터의 이동속도에 맞추어 지나온 맵을 앞쪽으로 이동시킨다.

``` csharp
//반복시킬 맵2개를 넣어둘 슬롯  
GameObject[] m_StageMap = new GameObject[2];  
int m_MapIdx = 0; //현재 맵번호 확인
float m_MapSizeX = 0.0f; //맵의 총 길이 
float m_NextMapReady = 150.0f; //맵 위치 변경 조건
```  
<br>

``` csharp
//맵 생성과 위치초기화.
for (int ii = 0; ii < m_StageMap.Length; ii++)
{
    m_StageMap[ii] = (GameObject)Instantiate(m_Map1Prefab);
}
m_MapSizeX = m_StageMap[0].GetComponent<Map1_PrefabCtrl>().m_MapSize;
m_StageMap[0].transform.position = new Vector3(0, 0, 0); //기본위치
m_StageMap[1].transform.position = new Vector3(-m_MapSizeX, 0, 0); //두번째 맵 기본위치.
```  
<br>

``` csharp
void Update()
{
    //맵 이동 조건 확인
    if (m_MapSizeX * m_MapIdx + m_NextMapReady < m_Hero.transform.position.x)
    {
        m_MapIdx++;  
        //맵 이동  
        m_StageMap[(m_MapIdx % 2)].transform.position = new Vector3(m_MapSizeX * m_MapIdx, 0, 0);  
        //이동시킨 맵의 아이템 리셋  
        m_StageMap[(m_MapIdx % 2)].GetComponent<Map1_PrefabCtrl>().ResetItems();  
    }
}
```  

---
layout: post
title: SDK 사용 편의성 향상
subtitle: 2022-07-27 ~ 2022-08-01 (4일)
categories: 2022.Co.Marvrus
tags: 
---

## 주 프로젝트
- **SDK 랩핑 클래스 제작**
<table>
  <tr>
    <td>프로젝트명</td>
    <td>SDK 사용 편의성 향상</td>
    <td>기간</td>
    <td>2022-07-27 ~ 2022-08-01 (4일)</td>
  </tr>
  <tr>
    <td>개요</td>
    <td>클라이언트 파트 지원</td>
    <td>팀원</td>
    <td>1명</td>
  </tr>
  <tr>
    <td>주요 역할 및 담당</td>
    <td colspan="3">클라이언트에서 SDK를 더욱 쉽게 사용할 수 있도록 코드 랩핑</td>
  </tr>
  <tr>
    <td>성과</td>
    <td colspan="3">전용 SDK 제작 지원으로 작업 능률 향상</td>
  </tr>
</table>

## 사용 편의성 향상 요청  
<p>SDK 사용 시, 비동기 동작이 많고 매칭해야 하는 데이터가 다수 존재하여 개발 난이도가 다소 높음.<br>
조금 더 쉽게 사용할 수 있도록 추가 작업을 요청.</p>

### 제약사항
- B2B서비스를 전제로 제작된 SDK이기 때문에 특정 클라이언트를 위해 전체 SDK구조를 바꿀 수 없어, 전용 SDK로 제작 필요.  
- 비동기 동작을 대기하지 않도록 구현.  
- 클라이언트에서 사용하는 데이터 형태로 리턴 필요.  

## 구현  
SDK 사용 FlowChart 변경내용  
[![SDK 사용 FlowChart 변경내용](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220727_flowchart.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220727_flowchart.png)  
<!-- (https://mermaid.live/edit#pako:eNqVlE1P4zAQhv9KFC5BaiqSFihRxYk97Z6WI0HWxJ4Qi8SObJdSqv73tWOnmxaxHz207uvnnfGMP_YxlQzjIq5buaUNKBP9-FmKyH70pnpR0DcRbTkK40XIEuh7oo0lL4MEkO33mr0SLrghtEH6ejgURUE3Rtb1CGXJE5VCIDXESPL48J3gmw2rny8tCoxpg31g88RFO8uR-xyD-mWS_EkhRf6G60rduxwDjsznev6UCRZTAwhod5rrv7pgsd8zMEDwnesvV7NMXtAQx7ng2wYF8a0kWxDHyq5DsbIPCgpWirMtsKV4pcqSsdMBr_Kkk2zT4iByaPkH-hWNwGIEph2tlifqqcOuCUHRhtCNUm7HlDRguBSukPl87n6o7PoWDY6em8QHGpr4cZRvE4UMay5w6ASpleyIzzwiqyPCBmbUs6vfSzx2p8qyqXq67ixPbBiumz-00pu9SLNp7ybF-ZN8WiHNfYUTLLTujFskoQcTMiif2OXI-tKJrAnvXsZZuw-2xpOEruTTGKFIbXYthrsa1bxtiwtW40wbJV-xuKAVhHG65cw0Rda_jyZ7uv7T4bv2zybagtYPWEfhHgXjClcjzEDbx0fBroiuo-uJw9-oYKjv7mZUtlLZYV1_5S0FZGmaVvbrnmalqPJ1GLmnap3O0_sqH7DcYQs3af9Xy3UYudfGY0uHVTdpSqFDBZHdG8csrHg70BaAwVethojXQ-IrN2VXYg_rOgzjWWwjdMCZfWz3bufK2DTYYRkXdmjPP2xaU8alOFgUbNWPO0HjooZW4yze9PZ44AMHe4i7M_Ub40aqIB5-Aedk-gk) -->

<p>Client에서 SDK동작의 완료 확인 대기작업을 삭제했다. 확인이 필요한 동작은 모두 이벤트로 구현했고, 이벤트는 선택적으로 연결하여 이후 작업을 처리할 수 있다.</p>

<p><br></p>

---
layout: post
title: 라이브 서비스 솔루션 연구개발
subtitle: 2019-12-16 ~ 2021-03-01 (1년 3개월)
categories: Co.GnFlex
tags: 
---


## 주 프로젝트
- **라이브 서비스 솔루션**  
| 프로젝트명 | 라이브 서비스 솔루션 R&D | 기간 | 2019-12-16 ~ 2021-03-01 (1년 3개월) |  
| :--- | :--- | :--- | :--- |  
| 개요 | 교육용 인터렉티브 컨텐츠 개발 | 팀원 | 4명 |  
| 주요 역할 및 담당 | 클라이언트 개발 전반. 기술조사. |||  
| 성과 | 서비스 개발 완료. |||  
| ^^ | 서비스 Loader와 Launcher, 1년차 서비스 Contents 10여편 제작. |||  

## 단기 프로젝트
- 분당 소재 **키즈카페 체험존 설치, 운영** (2020년 6월부터 약 3개월)  
- 프레젠테이션 용 **시연 패키지 제작**  
- **라이선스 기능**  
| 프로젝트명 | 라이선스 기능 개발 | 기간 | 2020-09-01 ~ 2020-09-20 (약2주) |  
| :--- | :--- | :--- | :--- |  
| 개요 | 구독or판매를 위해 사용제어 장치를 마련 | 팀원 | 2명 |  
| 주요 역할 및 담당 |클라이언트 개발. |||  
| 성과 | 개발완료. |||  
| ^^ | Sha2-256 암호화 기술을 사용, DLL로 코드를 숨김.<br>11 |||  
| ^^ | 영업팀에서 라이선스 발급에 사용할 홈툴 제작. |||  

<hr>

## 프로젝트 명세
- **투입**  
  - 인원 : 아트2, 프로그래머2  
  - 기간 : 1년 3개월  
  - 개발툴 : Unity, Visual Studio
- **산출**  
  - 플랫폼 : Windows OS, 인터렉티브 컨텐츠  
  - Loader_ 런쳐의 인스톨러  
  - Launcher_ 런쳐  
  - Content_ 1년차 서비스 컨텐츠 10여편 제작.  
  - 전국 유치원과 연결된 공급망에 유통계약 체결, 2021년부터 라이브 서비스 제공 중.  
- **연구개발 내용**  
  - 모션인식 적용 테스트_ Kinect v2, Azure  
  - 데이터마이닝    

<hr>

## Etc.  
초기에는 연구를 중심으로 기술적용 방법을 연구했다.<br>
이후 솔루션이 자리잡자 시연, 홍보를 위한 단기 패키징 작업이 주를 이뤘다.<br>
동시에 라이브 서비스 준비를 진행,<br>
서비스 계약이 성사된 후에는 추가 컨텐츠를 제작했다.<br>

<hr>

### 서비스 컨텐츠 링크
- 유통 자회사 [**PLAYSQ**](https://www.nextunicorn.kr/newsroom/10b95dd2afc9bc64)의 홍보 유튜브
  [![PLAYSQ Youtube Link](https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/YouTube_full-color_icon_%282017%29.svg/120px-YouTube_full-color_icon_%282017%29.svg.png)](https://www.youtube.com/channel/UCUz80hTii_HvnKrXiBESQqw)
- 공식블로그
  [![PLAYSQ 네이버블로그 Link](https://w.namu.la/s/7f46f2b6e9ed994a9b56221f87878fc295ab1155c6be3439de558677827c0768c5675dd3612a0261d618758a8cf0c3be9a78295481ec829e23c8d458f59a0ac7d4ba15b7e4b82ac32a076a2a7d58e1809ee6b14378dc7d790c6baf0118e5f58e)](https://blog.naver.com/playsq0104)
  
<hr>

### Solution Process

[![MainLoader Process](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20211022_main_loader_process.png)](https://mermaid.live/edit/#eyJjb2RlIjoic3RhdGVEaWFncmFtLXYyXG5kaXJlY3Rpb24gTFJcbnN0YXRlIE1haW5fTG9hZGVyX1Byb2Nlc3N7XG4gICAgc3RhdGUgQ2FsbF9MYXVuY2hlcl9WZXJzaW9uIHtcbiAgICAgICAgZGlyZWN0aW9uIExSXG4gICAgICAgIFsqXS0tPmNvbXBhcmVfd2l0aF9sb2NhbFxuICAgICAgICBjb21wYXJlX3dpdGhfbG9jYWwgLS0-IHJlYWR5X2Zvcl9sYXVuY2ggOiBlcXVhbHNcbiAgICAgICAgY29tcGFyZV93aXRoX2xvY2FsIC0tPiBkb3dubG9hZF9uZXdfbGF1bmNoZXIgOiBub3QgZXF1YWxzXG4gICAgICAgIGRvd25sb2FkX25ld19sYXVuY2hlciAtLT4gcmVhZHlfZm9yX2xhdW5jaFxuICAgICAgICByZWFkeV9mb3JfbGF1bmNoIC0tPiBbKl1cbiAgICB9XG5cbiAgICBbKl0tLT4gQ2FsbF9MYXVuY2hlcl9WZXJzaW9uXG4gICAgQ2FsbF9MYXVuY2hlcl9WZXJzaW9uIC0tPiBMYXVuY2hlcl9zdGFydFxuICAgIExhdW5jaGVyX3N0YXJ0IC0tPiBraWxsX01haW5fTG9hZGVyXG4gICAga2lsbF9NYWluX0xvYWRlciAtLT5bKl1cbn1cbiIsIm1lcm1haWQiOiJ7XG4gIFwidGhlbWVcIjogXCJkZWZhdWx0XCJcbn0iLCJ1cGRhdGVFZGl0b3IiOmZhbHNlLCJhdXRvU3luYyI6ZmFsc2UsInVwZGF0ZURpYWdyYW0iOmZhbHNlfQ)

[![Launcher Process](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20211022_launcher_process.png)](https://mermaid.live/edit/#eyJjb2RlIjoic3RhdGVEaWFncmFtLXYyXG5kaXJlY3Rpb24gTFJcbnN0YXRlIExhdW5jaGVyX1Byb2Nlc3N7XG4gICAgc3RhdGUgTG9naW57XG4gICAgICAgIGRpcmVjdGlvbiBMUlxuICAgICAgICBbKl0tLT5zZW5kX3JlcXVlc3RcbiAgICAgICAgc2VuZF9yZXF1ZXN0IC0tPiBlcnJvcl9tc2cgOm5vdCB2YWx1YWJsZS5cbiAgICAgICAgc2VuZF9yZXF1ZXN0IC0tPiBzdWNjZXNzXG4gICAgICAgIHN1Y2Nlc3MtLT5bKl0gOnJldHVybl9kYXRhc188YnI-ZnJvbV9zZXJ2ZXJcbiAgICB9XG4gICAgc3RhdGUgQ2hlY2tfQ29udGVudHNfVmVyc2lvbntcbiAgICAgICAgZGlyZWN0aW9uIExSXG4gICAgICAgIFsqXS0tPmNvbXBhcmVfZWFjaF88YnI-Y29udGVudF92ZXJzaW9uXG4gICAgICAgIGNvbXBhcmVfZWFjaF88YnI-Y29udGVudF92ZXJzaW9uIC0tPiBwYXRjaGVkIDogZXF1YWxzXG4gICAgICAgIGNvbXBhcmVfZWFjaF88YnI-Y29udGVudF92ZXJzaW9uIC0tPiBkb3dubG9hZF88YnI-bmV3X2NvbnRlbnRzIDogbm90IGVxdWFsc1xuICAgICAgICBkb3dubG9hZF88YnI-bmV3X2NvbnRlbnRzIC0tPiBwYXRjaGVkXG4gICAgICAgIHBhdGNoZWQtLT5bKl1cbiAgICB9XG4gICAgc3RhdGUgZm9yazw8Zm9yaz4-XG4gICAgc3RhdGUgam9pbiA8PGpvaW4-PlxuICAgIHN0YXRlIENob29zZV9Db250ZW50X1BhZ2V7XG4gICAgICAgIFsqXS0tPiBzZWxlY3RfY29udGVudFxuICAgICAgICBzZWxlY3RfY29udGVudC0tPnNlbGVjdF9tb2Rlc1xuICAgICAgICBzZWxlY3RfbW9kZXMtLT5bKl1cbiAgICB9XG5cbiAgICBbKl0tLT5Mb2dpblxuICAgIExvZ2luLS0-Q2hlY2tfQ29udGVudHNfVmVyc2lvblxuICAgIENoZWNrX0NvbnRlbnRzX1ZlcnNpb24tLT5mb3JrXG4gICAgZm9yay0tPk9yZ2FuaXphdGlvbjFcbiAgICBmb3JrLS0-T3JnYW5pemF0aW9uMlxuICAgIE9yZ2FuaXphdGlvbjEtLT5nZXRfYWNjb3VudFxuICAgIE9yZ2FuaXphdGlvbjItLT5jaG9vc2VfbnVtYmVyXzxicj5vZl9PcmcycGxheWVyXG5cbiAgICBzdGF0ZSBTZXRfQ3VycmVudF9QbGF5ZXJze1xuICAgICAgICBnZXRfYWNjb3VudC0tPmNob29zZV9udW1iZXJfPGJyPm9mX3BsYXllclxuICAgICAgICBjaG9vc2VfbnVtYmVyXzxicj5vZl9wbGF5ZXItLT5nZXRfYWNjb3VudCA6IGFkZCBtb3JlIHBsYXllcnNcbiAgICAgICAgY2hvb3NlX251bWJlcl88YnI-b2ZfT3JnMnBsYXllci0tPmNob29zZV9wbGF5ZXJcbiAgICAgICAgY2hvb3NlX251bWJlcl88YnI-b2ZfcGxheWVyLS0-am9pbiA6ZG9uZVxuICAgICAgICBjaG9vc2VfcGxheWVyLS0-am9pblxuICAgIH1cbiAgICBqb2luLS0-Q2hvb3NlX0NvbnRlbnRfUGFnZVxuXG4gICAgQ2hvb3NlX0NvbnRlbnRfUGFnZS0tPkNvbnRlbnRfc3RhcnRcbiAgICBDb250ZW50X3N0YXJ0LS0-U2V0X0N1cnJlbnRfUGxheWVycyA6bGlzdGVuPGJyPmlmIGNvbnRlbnQgZW5kcy4uXG59XG4iLCJtZXJtYWlkIjoie1xuICBcInRoZW1lXCI6IFwiZGVmYXVsdFwiXG59IiwidXBkYXRlRWRpdG9yIjpmYWxzZSwiYXV0b1N5bmMiOmZhbHNlLCJ1cGRhdGVEaWFncmFtIjpmYWxzZX0)

[![Content Process](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20211022_content_process.png)](https://mermaid.live/edit/#eyJjb2RlIjoic3RhdGVEaWFncmFtLXYyXG5kaXJlY3Rpb24gTFJcbnN0YXRlIENvbnRlbnRfUHJvY2Vzc3tcbiAgICBbKl0tLT4gZ2V0X3BsYXllcl9kYXRhc19mcm9tX2xhdW5jaGVyXG4gICAgZ2V0X3BsYXllcl9kYXRhc19mcm9tX2xhdW5jaGVyLS0-Y29udGVudF9wbGF5XG4gICAgY29udGVudF9wbGF5LS0-cmVjb3JkX2NhbGNfc2NvcmVcbiAgICByZWNvcmRfY2FsY19zY29yZS0tPnNlbmRfcmVzdWx0X3RvX3NlcnZlclxuICAgIHNlbmRfcmVzdWx0X3RvX3NlcnZlci0tPlsqXVxufSIsIm1lcm1haWQiOiJ7XG4gIFwidGhlbWVcIjogXCJkZWZhdWx0XCJcbn0iLCJ1cGRhdGVFZGl0b3IiOmZhbHNlLCJhdXRvU3luYyI6ZmFsc2UsInVwZGF0ZURpYWdyYW0iOmZhbHNlfQ)

---
layout: post
title: 인식률 저하 이슈 원인분석 및 개선
subtitle: 2022-06-01 ~ 2022-08-31 (2개월)
categories: 2022.Co.Marvrus
tags: 
---

## 주 프로젝트
- **이슈 대응**
<table>
  <tr>
    <td>프로젝트명</td>
    <td>인식률 저하 이슈 원인분석 및 개선</td>
    <td>기간</td>
    <td>2022-06-01 ~ 2022-08-31 (2개월)</td>
  </tr>
  <tr>
    <td>개요</td>
    <td>클라이언트에서 MEE SDK를 탑재 후 인식률 저하로 사용 불가 이슈가 발생하여 대응함</td>
    <td>팀원</td>
    <td>1명</td>
  </tr>
  <tr>
    <td>주요 역할 및 담당</td>
    <td colspan="3">MEE SDK 인식률 저하 원인분석 및 개선</td>
  </tr>
  <tr>
    <td>성과</td>
    <td colspan="3">원인 특정<br>
    개선 방안 검토 & 테스트<br>
    개선 방안 적용 & 배포 & 공유</td>
  </tr>
</table>

## 클라이언트에서 이슈 발생  
- **MEE SDK의 인식률이 낮음**  
  카메라에 사람이 잘 찍히도록 QA를 진행했으나, 테스트 디바이스에 따라 인식률이 낮거나 아얘 동작하지 않는 경우가 발생하여 원인 분석을 요청.  
<br>

## 원인 분석
<p>MEE Engine은 ML을 사용하는데, 학습시킨 데이터가 모두 정방향이었기 때문에 정방향의 데이터에 대해서만 정상적인 결과값이 산출됨을 확인했다.</p>
<p>기기와 방향이 고정되어있던 샘플(테스트)앱과 달리, 클라이언트에서는 유저 환경과 사용한 디바이스가 다양했다. 하여, 정방향이 아닌 이미지로 분석을 시도하는 경우가 존재했고 이 경우의 인식률이 현저히 낮았다.</p>

정방향 이미지 각도의 예시  
[![정방향 이미지 각도의 예시](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220601_img_rotation_example.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220601_img_rotation_example.png)  
<br>

## 개선 방안 검토
1. **디바이스 별로 각도를 지정하여 이미지를 회전시키는 코드를 구현**  
   - 모든 종류의 디바이스에서 테스트를 진행하기에는 현실적으로 어려움이 있음  
   - 앞으로 생산될 새로운 디바이스에도 매 번 대응해야하는 이슈가 있음  
   - 기각  
<br>

2. **EXIF 데이터를 사용하여 이미지의 방향 특정**  
   - 이미지 데이터의 방향정보를 가지고 있는 EXIF는 기본앱을 사용하여 사진이 저장되는 시점에 기록됨  
    따라서, 카메라(하드웨어)의 촬영 기능만을 사용하는 MEE Engine 솔루션에서는 EXIF가 생성되지 않아 사용 불가함  
   - 또한, 이미지의 방향만을 기록하기에 유저 환경에 대응할 수 없음  
    EXIF가 0이어도 사용자가 옆으로 누워 있다면, **사용자가 정방향이 아니므로** 인식률 저하 이슈가 발생할 여지가 있음  
   - 기각  
<br>

3. **인식이 잘 되는 방향을 찾는 로직 구현**
   - 디바이스의 카메라 하드웨어 설치 각도나 이미지 방향, 유저 환경에 영향을 받지 않을 방법이 요구됨  
   - 촬영된 이미지를 여러 각도로 MEE Engine에 분석시켜, 가장 인식률이 높은 각도를 찾는 방법  
   - 테스트  
<br>

## 개선 방안 테스트  
<p>촬영된 이미지를 0, 90, 180, 270의 4방향과 각각의 미러방향까지 총 8방향으로 분석을 진행한다.<br>
그 중 가장 인식률이 높은 방향으로 회전방향을 특정한다.</p>
<p>런타임에 구동되는 로직이기 때문에 시간과 자원에 제한이 있다.<br>
가장 성능이 낮은 디바이스를 기준으로 최대 10초 이내, 보급형 디바이스 기준으로 통상 5초 이내에 동작이 완료될 수 있도록 했다.</p>
<br>

이미지 회전 각도의 예시  
[![이미지 회전 각도의 예시](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220601_img_rotation_example2.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220601_img_rotation_example2.png)  
<br>

### 방향 결정 프로세스  

[![방향 결정 프로세스](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220601_rotation_deside_process.png)](https://raw.githubusercontent.com/SeungHyeon-Hong/SeungHyeon-Hong.github.io/main/assets/img/20220601_rotation_deside_process.png)  
<!-- (https://mermaid.live/edit#pako:eNqtVG9r00Ac_irHvdKZQjYYahgbQ_tOYehLIyEmtxloLuOSCmUUWo0wbEEHqwxpSqeMOhis26KMMd_4cZLLd_CSS8ylTtCxe3Ecz--5535_bwsajomgAl1P99BDS98gul17taDiDACP63WtjjcsjLQ14hjIdbdUDNh6Nvcc1GrLgI4HySCkE19LPvXp2I-nh8nHAxqEGh1tx-92o2lnhd_4F2YqGX_3qR_Q3pCOdoACWsjl90U8fZl5oOL_kwbcEJ1O2Y14f0gnXaBgh4vwnYf9Jy8Pu6Ssag9aRgMJeLpMiyDDsxwMHj2pWn4n7PURcyzpMt8-v42_9LWk_yHufa2S_0LiAkEYH5_TSYfHuvSCLN-SpfuyNH9Plhbuyj8vUuhONO3aFiEO4bHcnnngeiI8iUUh4vd-VVW0ZFSWwejsko47dHRQpYqWm8lL1g8FsV0ey1NRgrx0pSEHMuO8TMPt6PQH826lZIgod3d0lMcptOiVzMU0xUFI33Q1GpzTXkD9k-jsWzIYakKf7odMMRnsFd2qgKIv03U9DSHWG9MTJ2M29IqtUpJ2MalXDGClpdhsq7gNJWgjYuuWyX6mbMJU6L1ENlKhwo4mWtebDU-FnKo3PedpCxtQWdcbLpJgc9MsP7MZtG5ankNysP0LRGdS_Q) -->

<p><br></p>

<!-- [Android] MainApplication에 dagger, WorkManager 적용하기 -->
<!-- Android dagger Hilt WorkManager androidx Configuration-->

# WorkManager란?
---
`💡 Source : https://dongsik93.github.io/til/2020/05/15/til-jetpack-workmanager/`
- WorkManager API를 사용하면 **안정적으로 실행해야 하는 지연 가능한 비동기 작업**을 쉽게 예약가능
  - 안정적으로 실행 : 앱이 종료되거나 기기가 다시 시작되어도 실행되어야 한다
- 대부분의 백그라운드 처리는 지속적인 작업을 통해 가장 잘 처리되므로, WorkManager는 백그라운드 처리에 권장하는 기본 API이다
- [Android Jetpack](https://developer.android.com/jetpack?hl=ko) 아키텍처 구성요소 중 하나의 라이브러리이다
### 어떤 것을 백그라운드 작업으로 보는 것일까?
- 다음 중 하나에 해당하면 앱이 Foreground에 있는 것으로 간주된다
  - Activity가 시작 또는 일시중지 되었는지 여부에 관계없이 앱에 Activity가 표시된다
  - 앱에 Foreground Service가 있다
    - Foreground Service는 android의 어플리케이션 구성요소인 Service 중 한 가지 유형이며, 사용자의 눈에 보이는 작업을 수행하는 것이다
  - 다른 앱이 다음 항목에 바인드외어 있다면 foreground에 있는 것이다
    - IME (입력 방식 편집기)
    - 배경화면 서비스
    - 알림 리스너
    - 음성 또는 텍스트 서비스

위의 조건들 중 어느것도 해당되지 않는다면 앱이 백그라운드에 있는 것으로 간주된다

### 언제 WorkManager를 사용할까?
![](https://dongsik93.github.io/img/in-post/workmanager/workmanager_1.png)
앞서 말한 것과 같이, 
WorkManager는 사용자가 화면을 벗어나 이동하거나, 앱이 종료되거나, 기기가 다시 시작되도라도 안정적으로 실행되어야 하는 작업을 대상으로 설계되었다.
- 백엔드 서비스에 로그 또는 분석 전송
- 주기적으로 서버와 앱 데이터를 동기화

이런 예시가 그 작업에 해당한다.
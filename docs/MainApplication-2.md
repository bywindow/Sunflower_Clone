<!-- [Android] MainApplication에 dagger, WorkManager 적용하기 -->
<!-- Android dagger Hilt WorkManager androidx Configuration-->

# WorkManager란?
---
`💡 Source : https://dongsik93.github.io/til/2020/05/15/til-jetpack-workmanager/`
- WorkManager API를 사용하면 안정적으로 실행해야 하는 지연 가능한 비동기 작업을 쉽게 예약가능
  - 안정적으로 실행 : 앱이 종료되거나 기기가 다시 시작되어도 실행되어야 한다
- 
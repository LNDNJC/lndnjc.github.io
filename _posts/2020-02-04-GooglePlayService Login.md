# GooglePlayService Login

## KeyTool 시스템 환경 설정

- 윈도우키 + R를 누른 후, sysdm.cpl을 입력하여 제어판의 시스템 속성을 실행
- 고급 탭에서 환경 변수를 클릭
- 시스템 변수 항목들 중 Path를 선택하고 편집을 클릭
- 변수 값 끝에 ;C:\Program Files\Android\Android Studio\jre\bin를 입력하고 확인

[Windows에서 Android 개발 환경 준비하기(Android Studio 설치)](https://webnautes.tistory.com/1126)

SHA1 키 확인

    >keytool -list -printcert -jarfile TheCatAnchor.apk

    keytool -keystore holybear.keystore -list -v

1. Go to Google Developer Console
2. Click All Applications > Your Application
3. Go to Release Management > App Signing
4. Notice there is an " and an "

    *Upload Certificate"*

    *App Signing Certificate".*

5. **Copy the SHA1 from the APP SIGNING CERTIFICATE.** (Those bastards! After all that keystore rigmorale, they fail to mention this part in documentation!)
6. Click All Applications on the Top Left, then click Game Services > Game Details
7. Scroll all the way down and look for**API Console project**This game is linked to the API console project called 'YOUR APPLICATION NAME SHOULD BE HERE'
8. ***Click on your application name at this location.***
9. Now you're in the API's & services. Click on **Credentials**
10. Delete whatever you have under**OAuth 2.0 client IDs**
11. Now, click on Create Credentials > OAuth Client ID
12. **COPY THE SHA1 FROM THE HERE AND BE SURE YOUR PACKAGE NAME IS CORRECT.**

    ***APP SIGNING CERTIFICATE*** 

    [](https://forum.unity.com/threads/google-play-services-not-working.485322/)

    핸드폰 Setting > App Management → Delete Data

    게임 로그인 시 로그인된 팝업창이 나온다.

    그 이후엔 나오지 않음. 왜 그럴까?
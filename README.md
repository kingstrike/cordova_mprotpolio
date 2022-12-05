# 👨‍ 모바일 프트폴리오를 코르도바앱으로 구현해보기

[모바일 포트폴리오.apk 다운]() <br>

## ✔️ 코르도바 APP 만드는 방법
1. JDK (jdk-8u162-windows-x64.exe) 설치 <br><br>
2. ￦hybridapp 디렉토리 만들기 → cmd(nodejspromport)로 cd ￦를 입력한 후 md hybridapp을 입력한다.<br><br>
3. Apache-Ant 설치하기 → c:￦HybridApp￦ 폴더에 "apache-ant-1.9.16-bin.zip"을 다운 받고 압축을 해제한다.<br><br>
4. Gradle 설치하기 → c:￦HybridApp￦ 폴더에 "gradle-7.3.zip"을 다운 받고 압축을 해제한다.<br><br>
5. Android Studio 설치 및 환경 구축 → AVD는 Nexus 5나 Nexus 5X api 29로 진행한다. <br>
▶ SDK platforms : Android 12L (32) / Android 12 (31) / Android 11 (30) / Android (29) 설치 <br>
▶ SDK Tools : Android SDK Tools / Android SDK Platfor-tools / Android SDK Build-tools 설치 <br>
▶ Extra : Android Support Repository /	Android Auto Desktop head unit emulator /	Android auto API simulator /	Google Repository <br>
           google USB Driver / Google Play Services / Android SDK Command-line Tools / Intel x86 Emulator Accelerator(HAXM installer) 설치<br><br>
6. 환경변수 설정 (환경변수는 Window + X → 시스템 → 고급시스템 설정에서 작업 가능) <br>
▶ JAVA_HOME : c:\progrqm files\java\jdk1.8-- <br>
▶ ANDROID_SDK_ROOT : C:\Users\608\AppData\Local\Android\android-sdk<br>
▶ GRADLE_HOME : C:\gradle-7.3<br>
▶ Path : %JAVA_HOME%\bin; / %ANDROID_HOME%\tools / %ANDROID_HOME%\platform-tools / %ANDROID_HOME%\build-tools /<br> %ANDROID_HOME%\cmdline-tools\latest\bin 
	%ANDROID_HOME\emulator / %GRADLE_HOME%\bin / c:\HybridApp\apace-ant-1.9.16\bin <br><br>
7. Node.js 설치 → Node.js를 설치하고 Nodejspromport를 통해 "node -v", "npm-v", "npm update -g" 순으로 입력한다. <br><br>
8. Cordova 설치 → Nodejspromport를 통해 "npm install -g phonegap", "npm install -g cordova", "cordova -v", "npm update -g phonegap", "npm update -g cordova"를 입력한다. <br><br>
9. Android Cordova App 만들기<br>
→ mkdir \HybridProject / cd \HybridProject / cordova create test com.example.test testApp -d / cd test / dir / dir platform / <br>cordova platform add android / dir platform 순으로 입력한다.<br><br>
10.Android Studio 내에서 Bundle Script에서 build.gradle(:app) 파일을 아래와 같이 수정한다.<br>
→ android 밑에 namespace 위에 아래의 코드를 추가한다.<br>
packagingOptions {<br>
        exclude 'META-INF/DEPENDENCIES.txt'<br>
        exclude 'META-INF/LICENSE.txt'<br>
        exclude 'META-INF/NOTICE.txt'<br>
        exclude 'META-INF/NOTICE'<br>
        exclude 'META-INF/LICENSE'<br>
        exclude 'META-INF/DEPENDENCIES'<br>
        exclude 'META-INF/notice.txt'<br>
        exclude 'META-INF/license.txt'<br>
        exclude 'META-INF/dependencies.txt'<br>
        exclude 'META-INF/LGPL2.1'<br>
    }<br><br>
11. Android Studio 내에서 "App - Manifests - AndroidManifest.xml"로 경로를 찾아 진입 후 소스코드 내에 있는 application 안에 "android:largeHeap="true"를 추가한다.<br><br>
12.  C:\Users\[사용자명]\.android 내에 있는 debug.keystore 파일을 삭제한다. <br>
→ 삭제가 되지 않을 경우에는 Ctrl+Alt+Del => 작업관리자에서 해당 프로세스 작업 끝내기 후에 삭제 <br><br>
13. Android Studio에서 작업할 때 "Build - Clean Project"를 해주는 것이 좋다. <br><br>
14. 자신이 만든 프로젝트의 첫번째 파일 이름을 index.html로 변경하고 cdn 방식을 Download 방식으로 변경한다. <br><br> 
---------------------------------------------------------------------------------------<br>
	<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css"/><br>
	<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script><br>
	<script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script><br>

====><br>

	<link rel="stylesheet" href="./css/jquery.mobile-1.4.5.min.css"/><br>
	<script src="./js/jquery-1.11.1.min.js"></script><br>
	<script src="./js/jquery.mobile-1.4.5.min.js"></script><br>
---------------------------------------------------------------------------------------<br><br>
15. 그 후 head 위에 "<script src="cordova.js"></script>" 코드를 추가한다. <br><br>
16. 프로젝트 폴더에 있는 모든 파일을 test 폴더 아래에 있는 www 폴더로 복사한다. <br><br>
17. "삼성 USB 드라이버"를 검색하여 파일을 다운로드 받고 설치한다. <br><br>
18. 컴퓨터와 휴대폰을 연결한다. <br><br>
19. 그 후 AVD 실행 혹은 스마트폰(Android)를 통해 연결한다. <br>
→ cordova run android --list <br>
→ 에뮬레이터에 실행 : cordova emulate android <br>
→ 기기(스마트폰)에 실행 : cordova run android <br><br>


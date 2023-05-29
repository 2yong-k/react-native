# REACT NATIVE STARTER KIT

## React-Native-Cli (Expo X)
0. Chocolatey install
    - 터미널 관리자 권한으로 설치
    ```
    $ Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
    ```
    - 설치 확인
    ```
    $ choco
    ```
1. Node.js install
    - 사이트에서 설치 (https://nodejs.org/ko)
    - 혹은 터미널에서 설치
    ```
    $ choco install -y nodejs.install
    $ choco install -y nodejs-lts.install // Node JS LTS 설치하고 싶을 시
    ```
    - 설치 버전 확인
    ```
    $ node -v
    $ npm -v
    ```
2. React Native CLI install
    - 터미널에서 설치
    ```
    $ npm install -g react-native-cli
    ```
    - 설치 버전 확인
    ```
    $ react-native -v
    ```
3. For Android: JDK, Android Studio, Android SDK
    - JDK 설치
        - 사이트에서 설치(https://www.oracle.com/java/technologies/downloads/#java8)
        - 터미널에서 설치
        ```
        $ choco install -y jdk8
        ```
        - 환경변수 설정. 환경 변수에서 JAVA_HOME, path에 bin이 포함된 경로가 있는지 확인 필요
        ```
        $ set PATH=%PATH%;C:\"Program Files"\Java\jdk-19\bin;
        ```
        - 설치 버전 확인
        ```
        $ java -version
        ```
    - Android Studio 설치 & Android SDK 설치
        - 사이트에서 설치(https://developer.android.com/studio/index.html)
        - 경로에 한글이 들어가면 안될 수 있음 -> mklink로 링크를 만들거나, 관리자 모드로 들어가서 링크 변경 후 설치
        - Android Studio 들어가서 Customize > All Settings > Appearance & Behavior > System Settings > Android SDK 진입
        - SDK Platforms 탭 클릭 -> 오른쪽 아래 Show Package Details 체크 후 원하는 항목들 체크 확인. Android 버전 선택
        - SDK Tools 탭 클릭 -> 오른쪽 아래 Show Package Details 체크 후 원하는 항목들 체크 확인. Android SDK Build-Tools, Android SDK Platform-Tools 선택
        - 환경변수 설정. 환경 변수에서 ANDROID_HOME, path에 platform-tools와 build-tools가 포함된 경로가 있는지 확인 필요
        ```
        $ set PATH=%PATH%;C:\Users\DooyongKim\REACT_NATIVE\android-sdk\platform-tools
        $ set PATH=%PATH%;C:\Users\DooyongKim\REACT_NATIVE\android-sdk\build-tools\33.0.2
        ```
        - 설치 버전 확인
        ```
        $ adb --version
        ```
4. For iOS: Xcode
    - 일단 생략...
5. VScode extension install
    - React Native Tools 설치: 코드 디버깅과 빠른 코드 빌드를 위해
6. Create and execute projects
    - 새로운 프로젝트 만들기(버전이나 템플릿 이용 시 추가로 코드 작성)
    ```
    $ npx react-native init NEW_PROJECT (--version X.XX.X or --template react-native-template-typescript)
    ```
7. 물리적 기기 또는 가상 기기 준비 및 실행
    - 물리적 기기: 안드로이드 휴대폰이 있다면 휴대폰을 개발자 모드로 만들고 USD로 컴퓨터에 연결. USB 디버깅 허용
    - Android Studio를 이용해서 프로젝트 생성
        - 처음이라면 Create Virtual Device 클릭 후 원하는 가상 기기 생성
        - Android Studio new project 생성
        - 위치는 NEW_PROJECT\android 디렉토리
        - AVD Manager를 열어 사용 가능한 AVD 생성.
8. 리엑트 네이티브 앱 실행
    ```
    $ react-native run-android

    or

    $ npx react-native start // 한 터미널에서 메트로 실행
    $ npx react-native run-android // 다른 터미널에서 안드로이드 실행
    ```
※. 참고
    - https://compmath.korea.ac.kr/reactnative/Setup.html
    - https://reactnative.dev/docs/environment-setup?guide=native
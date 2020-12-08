# ionic-android-starter
## Requirements
### 프로그램 설치
> ```shell
> brew install gradle
> npm i -g cordova
> npm i -g native-run
> npm install -g @ionic/cli
> ```

### 프로그램 버전 확인
> ionic: `ionic -v`  
> Cordova: `cordova -v`

### android 가상 디바이스 추가
> android studio 설치 [설치 페이지 링크](https://developer.android.com/studio)   
> android studio 실행 후 상단 메뉴 Tools -> AVD Manager 를 통해서 안드로이드 가상 디바이스 추가

### 환경 변수 설정
> android 실행 관련 환경 변수 추가
> ```shell
> # bash 사용자
> $ vi ~/.bashrc
> 
> # zsh 사용자
> $ vi ~/.zshrc
> 
> # 문서 가장 아래에 내용 추가
> export ANDROID_SDK_ROOT=$HOME/Library/Android/sdk
> export PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin
> export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
> export PATH=$PATH:$ANDROID_SDK_ROOT/emulator
> ```

## 프로젝트 생성
### 웹 프로젝트 생성
> 프로젝트 담을 디렉터리로 이동 후 다음 명령어 실행: `ionic start [프로젝트 이름] [프로젝트 타입]`  
> UI 가 기본(empty)인 프로젝트 생성: `ionic start location-ionic-sample blank`

### 웹 프로젝트를 안드로이드 프로젝트로 변경
> android 프로젝트로 변경 [프로젝트를 새로 생성하지 않은 경우 넘어가기]
> 기존 ionic 웹 프로젝트를 android 프로젝트로 변경
> ```shell
> ionic cordova prepare android
> ```

## 프로젝트 시작
### npm
> `npm install` 을 통해서 npm module 가져오기

### 프로젝트 실행
> * 안드로이드 기기 목록 보기: `cordova run android --list`  
> * 안드로이드 실제 기기 목록만 보기: `cordova run android --list --device`  
> * 안드로이드 가상 디바이스 목록만 보기: `cordova run android --list --emulator`  
> 
> PC에 안드로이드 스마트폰을 직접 연결하지 않고 가상 디바이스를 사용하는 경우 `cordova run android --list --emulator` 명령어 실행 후 목록에 아무것도 없으면
> android studio 를 열어서 android 가상 디바이스를 먼저 실행  
> 터미널에서 해당 명령어를 통해서 프로젝트 실행: `ionic cordova run android -l`

### 참조사이트
> [ionic - Android Development](https://ionicframework.com/docs/developing/android)

## ionic 플러그인
### 플러그인 및 npm 설치
> ```shell
> ionic cordova plugin add cordova-plugin-nativegeocoder
> npm install @ionic-native/native-geocoder
> ```

### 플러그인 및 npm 삭제
> ```shell
> ionic cordova plugin rm cordova-plugin-nativegeocoder
> npm uninstall @ionic-native/native-geocoder
> ```

## 디버깅
### Android 프로젝트 console.log 보기
> Chrome 브라우저 열고 주소창에 `chrome://inspect/#devices` 이동
> inspect 버튼 클릭  

### 참조사이트
> [ionic Native API - Background Geolocation](https://ionicframework.com/docs/native/background-geolocation)

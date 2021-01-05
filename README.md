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
> UI 가 기본(empty)인 프로젝트 생성: `ionic start sample-project blank`

### 웹 프로젝트를 안드로이드 프로젝트로 변경
> android 프로젝트로 변경 [프로젝트를 새로 생성하지 않은 경우 넘어가기]
> 기존 ionic 웹 프로젝트를 android 프로젝트로 변경
> ```shell
> ionic cordova platform add android
> ionic cordova build android
> ```

## 프로젝트 시작하기
### 1. npm module 설치
> 터미널에서 현재 프로젝트로 디렉터리로 이동 후 아래 명령어를 통해서 npm module 설치
> ```shell
> npm i
> ```

### 2. platform 재설정
> 터미널에서 현재 프로젝트 디렉터리로 이동 후 아래 명령어를 차례로 입력하여 플랫폼 재설정
> macOS 에서 플랫폼이 정상적으로 설치 되었음에도 에러 메시지가 나오는 경우가 자주 발생함.   
> `ionic cordova build android` 를 통해서 에러가 없으면 정상 설치된 것으로 간주한다.
> ```shell
> ionic cordova platform rm android
> ionic cordova platform add android
> ionic cordova build android
> ```

### 3. 에뮬레이터에서 프로젝트 실행(실제 기기로 실행하는 경우 건너뛰기)
> * 에뮬레이터 기기 목록 보기: `avdmanager list avd`  
> * 에뮬레이터 시작하기: `emulator -avd [AVD 이름]`
> * 프로그램 실행이 가능한 에뮬레이터 목록 보기: `cordova run android --list --emulator`
> * 로컬 디버깅(liveload 옵션 적용): `ionic cordova run android -l --emulator`
> * 안드로이드 외부 테스트(liveload 옵션 미적용): `ionic cordova run android --emulator`

### 4. 실제 기기에서 프로젝트 실행(에뮬레이터에서 실행하는 경우 건너뛰기)
> * 안드로이드 기기 목록 보기: `cordova run android --list --device`
> * 로컬 디버깅(liveload 옵션 적용): `ionic cordova run android -l`
> * 안드로이드 외부 테스트(liveload 옵션 미적용): `ionic cordova run android`
> * 로컬 디버깅(liveload 옵션 적용): `ionic cordova run android -l --device`
> * 안드로이드 외부 테스트(liveload 옵션 미적용): `ionic cordova run android --device`

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

## 에러
### 프로젝트 빌드가 안될 경우 재설정해보기
> ```shell
> ionic cordova platform rm android
> ionic cordova platform add android
> ionic cordova build android
> ```

### Permission denied
> Error: EACCES, permission denied 에러 난 경우 권한 주기
> ```shell
> cd [해당 프로젝트]
> sudo chown -R `whoami` .
> ```

## 개발 시작하기
### Page 추가하기
> ```shell
> ionic g page [페이지 이름]
> ```

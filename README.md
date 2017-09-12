# AndroidManifest.xml
---------------------------------------------------

### AndroidManifest.xml 란?

  > 안드로이드 어플리케이션에 대한 각종 정보들을 기술한 어플리케이션 명세서이다.<br> 필수적인 정보를 안드로이드 플랫폼에 알려주기 때문에 모든 안드로이드 어플리케이션은 반드시 AndroidManifest.xml 파일을 루트 디렉토리에 가지고 있어야 한다.

  - 안드로이드 어플리케이션의 자바 패키지명 정의
  - 안드로이드 어플리케이션을 구성하는 4대 컴포넌트(Activity, Receiver, Provider, Service)를 기술
  - 안드로이드 어플리케이션이 제한된 API나 다른 어플리케이션의 컴포넌트에 접근하기 위한 권한 설정
  - 안드로이드 어플리케이션을 구동하기 위한 버전 명시
  - 안드로이드 어플리케이션이 사용하는 다른 추가적인 라이브러리 명시

### AndroidManifest 구조

  ```xml
  <manifest
    xmlns:android="http://schemas.android.com/apk/res/android"
    package=""
    android:versionCode=""
    android:versionName="">

    <uses-sdk
      android:minSdkVersion=""
      android:targetSdkVersion=""/>

    <uses-permission android:name=""/>
    <uses-library android:name=""/>

    <application
      android:allowBackup=""
      android:icon=""
      android:label=""
      android:theme="">

      <activity
        android:name=""
        android:label="">
        <intent-filter>
          <action android:name=""/>

          <category android:name=""/>
        </intent-filter>
      </activity>

      ...(4대 컴포넌트)
    </application>
  </manifest>
  ```

  1. manifest

      - package : 안드로이드 어플리케이션의 자바 패키지명 설정
      - android:versionCode="코드" : 안드로이드 어플리케이션의 버전 코드 설정
      - android:versionName="버전명" : 안드로이드 어플리케션의 버전 이름 설정

  2. uses-sdk

      - android:minSdkVersion="버전코드" : 안드로이드 최소 버전(20) 설정
      - android:targetSdkVersion="버전코드" : 안드로이드 기본 버전(23) 설정

  3. uses-permission

      - android:name="권한명" : 안드로이드 어플리케이션의 리소스 접근 및 기능 사용 권한 설정

  4. uses-library

      - 안드로이드 어플리케이션이 다른 추가적인 라이브러리를 사용할 때 해당 패키지를 설정

  5. application

      - android:allowBackup="true" : 어플리케이션이 백업에 참여하고 인프라를 복원할 여부 설정
      - android:icon="아이콘" : 안드로이드 어플리케이션 아이콘 설정
      - android:label="application명" : 안드로이드 어플리케이션 이름 설정

  6. activity

      - android:name="Activity클래스 명" : Activity명을 설정
      - android:label="Activity 명" : 화면에 표시할 제목을 설정

  7. intent-filter

      > Activity 가 처리할 수 있는 암시적 Intent 를 설정하여 언제 Activity가 시작될 지 설정

      - action : 어떤 작업을 처리할 지 설정
      - category : 요소를 정의하여 어떤 Component의 유형인지 설정

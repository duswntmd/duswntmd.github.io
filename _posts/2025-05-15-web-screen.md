---
layout: single
title:  "Web Screen"
categories: SpringBoot 
toc: true
toc_sticky: true # 주석하면 고정
toc_label: Web Screen # 오른쪽 목차 이름 변경가능
author_profile: true # true false로 왼쪽 삭제가능능
search: true # 검색기능에 나오게 할건지 여부       
---

# 로컬 웹 브라우저 화면 띄우기

## Web Screen 영상

{% include video id="AKP9lBumVAo" provider="youtube" %}

## 1. 인텔리제이 설치

[IntelliJ다운로드](https://www.jetbrains.com/ko-kr/idea/download/?section=windows)

[![인텔리제이설치옵션]({{site.url}}/images/2025-05-15-web-screen/인텔리제이설치옵션.png)]({{site.url}}/images/2025-05-15-web-screen/인텔리제이설치옵션.png)

필요한 옵션이 있으면 추가 체크

## 2. 자바jdk 서포트 로드맵

[자바jdk 서포트 로드맵](https://www.oracle.com/kr/java/technologies/java-se-support-roadmap.html)

[![자바jdk지원]({{site.url}}/images/2025-05-15-web-screen/자바jdk지원.png)]({{site.url}}/images/2025-05-15-web-screen/자바jdk지원.png)

버전 중 LTS 버전으로 받아주시면됩니다  
장기 업데이트를 약속한 버전입니다  
17이나 21버전을 다운받으시면 됩니다  

## 3. jdk-21 다운로드

[jdk-21 다운로드](https://www.oracle.com/java/technologies/downloads/#jdk21-windows)

os에 알맞게 다운로드 해주시면 됩니다
https://download.oracle.com/java/24/latest/jdk-24_windows-x64_bin.zip 저는 zip다운로드 하였습니다

시스템 환경 변수 편집

[![새시스템변수]({{site.url}}/images/2025-05-15-web-screen/새시스템변수.png)]({{site.url}}/images/2025-05-15-web-screen/새시스템변수.png)

[![자바환경변수편집]({{site.url}}/images/2025-05-15-web-screen/자바환경변수편집.png)]({{site.url}}/images/2025-05-15-web-screen/자바환경변수편집.png)

변수 이름 : JAVA_HOME    
변수 값 : jdk-21폴더 위치

PATH클릭 -> 편집 -> 새로 만들기 -> %JAVA_HOME%\bin

```
java --version
```

자바 버전 확인

## 4. 인텔리제이 프로젝트 생성

[![인텔리제이처음화면]({{site.url}}/images/2025-05-15-web-screen/인텔리제이처음화면.png)]({{site.url}}/images/2025-05-15-web-screen/인텔리제이처음화면.png)

New Project  
com.example.demo  
필요한 Dependencies 넣고 Create

maven 변경사항이 있을시
우클릭 -> maven -> sync project -> 갱신

```
package com.example.demo.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class TestController {

    @GetMapping("/")
    public String TestController() {
        return "Spring Boot is running!";
    }
}
```

## 5. 인텔리제이 RUN버튼 수동 잡기

실행버튼없으면  
edit configurations -> sprint boot

[![스프링부트실행변경]({{site.url}}/images/2025-05-15-web-screen/스프링부트실행변경.png)]({{site.url}}/images/2025-05-15-web-screen/스프링부트실행변경.png)

자바 실행 창이 안뜰 경우 찾아서 잡아줘야 합니다

## 6. 초기 성공화면

[![성공실행화면]({{site.url}}/images/2025-05-15-web-screen/성공실행화면.png)]({{site.url}}/images/2025-05-15-web-screen/성공실행화면.png)

실행을 성공하면 이렇게 나옵니다


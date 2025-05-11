---
layout: single
title:  "Anaconda PyCharm"
toc: true
toc_sticky: true # 주석하면 고정
toc_label: Anaconda PyCharm # 오른쪽 목차 이름 변경가능
author_profile: true # true false로 왼쪽 삭제가능능
search: true # 검색기능에 나오게 할건지 여부       
---

## Anaconda PyCharm 영상

{% include video id="DaoDRmNPQfA" provider="youtube" %}

## PyCharm 무료와 유료

파이참은 유료와 무료 버전이 있습니다.  
학생은 학생 인증 시 유료 버전을 1년간 사용할 수 있고 그 이후 갱신하여 계속사용할 수 있습니다.  
유료 버전으로 설치하신다면 30일 무료이고 그 다음 결제를 하셔야합니다.  
1년 연간 청구를 하면 US $99.00인 138483원 입니다.  
비싼데 연간 구독제를 하면 좋은점은 Fallback Version이라는 특정 버전에 대해서 평생 무료사용권을 부여받습니다.  
연구소장이 가능합니다.

## PyCharm 다운로드

[PyCharm다운로드](https://www.jetbrains.com/pycharm/download/?section=windows)

[![파이참설치옵션]({{site.url}}/images/2025-05-11-anaconda-pycharm/파이참설치옵션.png)]({{site.url}}/images/2025-05-11-anaconda-pycharm/파이참설치옵션.png)

[![파이참초기화면]({{site.url}}/images/2025-05-11-anaconda-pycharm/파이참초기화면.png)]({{site.url}}/images/2025-05-11-anaconda-pycharm/파이참초기화면.png)

New Project 클릭

jupyter notebook 생성

아래 세팅 코드를 넣어서 실행 시 오류가 날겁니다.
코드를 넣어주시고 아래 PyCharm과 Anaconda 연동 항목을 실행해주시면 됩니다.

## Jupyter notebook 세팅

jupyter notebook 들어가기 테스트

```
print("hi")
```

```
import sys
 
cdPyVer = 0x600
cdSysVer = sys.version[:5]
print("%s%s" %("my python version is: ", cdSysVer))
```

```
pip install "numpy<2"
```

```
import tensorflow as tf
print("TensorFlow 버전:", tf.__version__)
print("GPU 감지됨:", tf.config.list_physical_devices('GPU'))
```

## PyCharm과 Anaconda 연동

Ctrl + Alt + S 파이참 환경변수 들어오기

Project -> Interpreter  
Add interpreter -> Add Local Interpreter  
Select existing  
Type -> Conda  
Environment -> 가상환경으로 변경  

PyCharm과 Anaconda 연동완료




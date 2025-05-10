---
layout: single
title:  "Anaconda GPU"
toc: true
toc_sticky: true # 주석하면 고정
toc_label: Anaconda GPU # 오른쪽 목차 이름 변경가능
author_profile: true # true false로 왼쪽 삭제가능능
search: true # 검색기능에 나오게 할건지 여부       
---

## Anaconda GPU 영상

<!-- {% include video id="" provider="youtube" %} -->

## Anaconda 다운로드

[Anaconda다운로드](https://www.anaconda.com/download)

[![아나콘다홈페이지]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다홈페이지.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다홈페이지.png)

[![아나콘다다운로드창]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다다운로드창.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다다운로드창.png)

이메일 입력후 OS버전에 맞게 다운로드

[![아나콘다PATH]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다PATH.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다PATH.png)

PATH 체크박스 선택 나머진 기본으로 설치하면 됩니다.  

## 텐서플로우 버전 관리

[텐서플로우 테스트 빌드 구성](https://www.tensorflow.org/install/source_windows?hl=ko#tested_build_configurations)

| 버전       | 파이썬 버전                | 	컴파일러              | 빌드 도구       | cuDNN                | 쿠다               |  
|------------|------------------------|--------------------|------------|------------------------|--------------------|
| tensorflow_gpu-2.10.0        | 3.7-3.10       | MSVC 2019    | 바젤 5.1.1        | 8.1       | 11.2    |

텐서프로우 GPU를 사용하기 위해서 버전 맞춰야합니다.  
3.10이상 파이썬 버전은 지원을 안합니다.

## Anaconda 가상환경 설치하기

[![아나콘다프롬프트]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다프롬프트.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/아나콘다프롬프트.png)

Anaconda Prompt들어가기 <-- cmd창 아닙니다.

```
conda create -n <가상환경 이름> python=3.10
```

가상환경 생성 및 3.10버전 파이썬 설치

```
conda activate <가상환경 이름>
```

가상환경 변경

```
python -m pip install --upgrade pip
```

pip 업그레이드 (선택)

```
pip install jupyter notebook
```

jupyter notebook 설치

```
pip install tensorflow==2.10
```

tensorflow 설치

```
pip install tensorflow-gpu==2.10.0
```

tensorflow-gpu 설치

[![GPU코드세팅]({{site.url}}/images/2025-05-10-anaconda-gpu/GPU코드세팅.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/GPU코드세팅.png)

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

## cuDNN다운로드

[cuDNN다운로드](https://developer.nvidia.com/rdp/cudnn-archive)

[![cuDNN다운로드]({{site.url}}/images/2025-05-10-anaconda-gpu/cuDNN다운로드.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/cuDNN다운로드.png)

cuDNN 8.1 다운로드

## CUDA다운로드

[CUDA다운로드](https://developer.nvidia.com/cuda-11.2.0-download-archive)

[![CUDA11.2다운로드]({{site.url}}/images/2025-05-10-anaconda-gpu/CUDA11.2다운로드.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/CUDA11.2다운로드.png)

윈도우 10 버전 받아도 원도우 11 문제없습니다.

CUDA 11.2 다운로드

## cuDNN -> CUDA11.2 폴더 변경

| cuDNN 압축 폴더 | 복사 대상 위치                                                |
| ----------- | --------------------------------------------------------------- |
| `bin\*`     | `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\bin\` |
| `include\*` | `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\include\`     |
| `lib\*`     | `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\lib\`         |

해당폴더 덮어쓰기

## 시스템 환경 변수 편집

```
C:\Users\사용자이름\anaconda3
```

```
C:\Users\사용자이름\anaconda3\Scripts
```

```
C:\Users\사용자이름\anaconda3\Library
```

```
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\bin  
```

```
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\libnvvp  
```
시스템 환경 변수 편집 확인하기

[![가상환경진입후주피터노트북]({{site.url}}/images/2025-05-10-anaconda-gpu/가상환경진입후주피터노트북.png)]({{site.url}}/images/2025-05-10-anaconda-gpu/가상환경진입후주피터노트북.png)

전부 완료되었으면 GPU확인코드 실행하면 끝

---
title: "WSL에 설치된 아나콘다 윈도우에서 사용하기 + jupyter notebook 사용하기 (with Visual Studio Code)"
categories: WSL-환경설정
tags:
  - WSL
  - Window10
  - Ubuntu
  - 윈도우
  - VScode
  - Visual Studio Code
  - python
  - interpreter
  - SSH
  - anaconda
  - virtual enviroment
  - jupyter
  - jupyter notebook
  - ipython

last_modified_at: 2019-05-08T13:00:00+09:00
toc: true 
toc_label: "Table of Contents"
toc_icon: "cog" 
toc_sticky: true 
author_profile: true
comments: true

gallery1: 
  - url: /assets/images/WSL_anaconda/001.PNG
    image_path: /assets/images/WSL_anaconda/001.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery2: 
  - url: /assets/images/WSL_anaconda/002.PNG
    image_path: /assets/images/WSL_anaconda/002.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery3: 
  - url: /assets/images/WSL_anaconda/003.PNG
    image_path: /assets/images/WSL_anaconda/003.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery4: 
  - url: /assets/images/WSL_anaconda/004-2.PNG
    image_path: /assets/images/WSL_anaconda/004-2.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"
    
gallery5: 
  - url: /assets/images/WSL_anaconda/004-1.PNG
    image_path: /assets/images/WSL_anaconda/004-1.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"
--- 

## 0. Preliminary
이후의 내용은 윈도우에 WSL, Ubuntu 18.04와 윈도우 사이에 VScode insider로 연결된 환경에서 진행됩니다. 만약 설치하지 않으셨다면 아래 링크를 보고 와 주세요!

[Window에 WSL설치하기](https://gyeonghunkim.github.io/blog/%ED%99%98%EA%B2%BD%EA%B5%AC%EC%B6%95/install-WSL/)


[WSL Python Interpreter 윈도우에서 VSCode로 이용하기](https://gyeonghunkim.github.io/wsl-%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95/install-VSCode-on-WSL/)

## 1. WSL에 anaconda 설치하기
우선 WSL에 anaconda를 설치해야합니다. 이를 위해서 [링크](https://repo.continuum.io/archive/)에서 최신 버전의 아나콘다 버전을 다운받아줍니다. **Anaconda3-[최근 날짜]-Linux-x86_64.sh**를 다운 받으면 될 것 입니다. 

{% include gallery id="gallery1" %}

그 뒤에 VSCode insider를 실행합니다. **ctrl + `** 를 눌러 터미널을 실행한 뒤에, .sh파일이 다운받아진 경로로 **cd** 명령어를 이용하여 이동합니다. 예를 들어서 저 같은 경우는 window의 **Downloads** 폴더에 저장되어있었고, 아래의 명령어를 입력해서 이동했습니다. 

> cd /mnt/c/Users/aass98998/Downloads/

그 뒤에 아래의 명령어로 anaconda를 WSL에 설치해줍니다. 

> bash [Anaconda로 시작하는 다운받은 파일 이름].sh

이때 한 가지 팁은 터미널에서 입력할 때, 어느정도 친 뒤에 **tab** 키를 누르면 자동으로 뒤의 것들을 입력해줍니다.   
위의 명령어를 입력하면 약관이 나오는데 계속 엔터 쳐 주다가 yes를 입력해줍니다. 설치 경로도 별 이유가 없다면, default로 해주면 됩니다. 

## 2. PATH에 추가하기
일반적으로 자동으로 경로에 추가되지 않기 때문에 아래와 같은 방법으로 anaconda bin 폴더를 경로에 추가해 주어야 합니다. 이를 위해서 WSL의 ~/.bashrc가장 밑에 아래의 명령어를 추가해 주어야 합니다. 

> export PATH=/home/ghkim/anaconda3/bin:$PATH

이때, 주의할 점은 위의 추가한 경로에 /home 뒤에 ghkim을 본인의 **WSL 계정 명** 으로 설정해 주어야 한다는 것 입니다. 

## 2. VSCode insider에서 인터프리터 설정해주기
이 부분은 이전에 VSCode insider와 WSL python interpreter를 연결할 때 python2를 3으로 바꾼 과정과 정확히 동일합니다. **ctrl + shift + p** 를 누른 뒤, **select interpreter**를 검색하고, 아래 그림과 같이 anaconda interpreter를 선택해주면 됩니다. 만약 anaconda interpreter가 보이지 않는다면, VSCode insider와 WSL을 각각 종료했다가 다시 실행하면 해결 될 것 입니다. 

{% include gallery id="gallery2" %}

## 3. 설치 확인하기
앞서 WSL의 기본 python interpreter에는 numpy나 pandas와 같은 모듈이 설치가 되어있지 않지만, Anaconda base 환경에는 설치가 되어 있을 것 입니다. 따라서 [이전](https://gyeonghunkim.github.io/wsl-%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95/install-VSCode-on-WSL/#4-python-test%ED%95%98%EA%B8%B0)의 hello.py를 아래와 같이 수정했습니다. 

```python
import numpy as np
import pandas as pd

x = np.arange(3)
print(x)
y = pd.Series(x)
print(y)
```

이를 anaconda interpreter로 실행했을 때 아래와 같이 실행 결과가 나오면 성공입니다!

```
[0 1 2]
0    0
1    1
2    2
dtype: int64
```
## 4. Jupyter notebook 사용하기
anaconda를 설치하면서 jupyter notebook도 설치가 되었을 것 입니다. 한가지 아쉬운 점은, 윈도우에서 jupyter notebook을 사용할 때 처럼 바로 웹 창이 뜨는 것이 아니라 터미널에서 링크를 제공해주면 그 링크를 이용하여 웹으로 접속해야합니다. 

VSCode insider 터미널 또는 WSL 터미널을 이용해서 아래의 명령어를 입력합니다. 

> jupyter notebook

그러면 아래와 같이 여러 글이 정신없이 나올 것 입니다. 

```
[I 18:38:04.795 NotebookApp] JupyterLab extension loaded from /home/ghkim/anaconda3/lib/python3.7/site-packages/jupyterlab
[I 18:38:04.796 NotebookApp] JupyterLab application directory is /home/ghkim/anaconda3/share/jupyter/lab
[I 18:38:04.799 NotebookApp] Serving notebooks from local directory: /home/ghkim
[I 18:38:04.800 NotebookApp] The Jupyter Notebook is running at:
[I 18:38:04.802 NotebookApp] http://localhost:8888/?token=d5adf4220ead35e4b849cbe13167e26420bc162ccdcfc56b
[I 18:38:04.803 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[W 18:38:04.896 NotebookApp] No web browser found: could not locate runnable browser.
[C 18:38:04.897 NotebookApp]

    To access the notebook, open this file in a browser:
        file:///home/ghkim/.local/share/jupyter/runtime/nbserver-475-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/?token=d5adf4220ead35e4b849cbe13167e26420bc162ccdcfc56b
```

여기서 가장 아랫줄의 링크를 복사해 윈도우 상의 Chrome에 붙여넣습니다. 그러면 아래와 같이 jupyter notebook이 실행 될 것 입니다. 

{% include gallery id="gallery3" %}

만약 특정 anaconda 환경에서 jupyter notebook을 실행하고 싶다면, WSL 터미널이나 VSCode insider 터미널에서 **conda activate [환경이름]** 으로 환경을 활성화시키고 **jupyter notebook** 을 실행하면 됩니다. 예를 들어서 qutip이라는 모듈이 설치된 quantum_info라는 환경에 대해서 base에서 jupyter notebook을 실행해서 qutip 모듈을 불러오면 아래와 같이 없는 모듈이라고 나옵니다. 

{% include gallery id="gallery4" %}

그러나 quantum_info 환경에서 jupyter notebook을 실행하고 import해보면 불러와 지는 것을 볼 수 있습니다. 

{% include gallery id="gallery5" %}


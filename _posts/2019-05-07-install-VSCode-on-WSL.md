---
title: "WSL 파이썬 인터프리터 윈도우에서 사용하기 (with Visual Studio Code)"
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

last_modified_at: 2019-05-07T13:00:00+09:00
toc: true 
toc_label: "Table of Contents"
toc_icon: "cog" 
toc_sticky: true 
author_profile: true
comments: true

gallery1: 
  - url: /assets/images/WSL_python/001.PNG
    image_path: /assets/images/WSL_python/001.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery2: 
  - url: /assets/images/WSL_python/002.PNG
    image_path: /assets/images/WSL_python/002.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery3: 
  - url: /assets/images/WSL_python/003.PNG
    image_path: /assets/images/WSL_python/003.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery4: 
  - url: /assets/images/WSL_python/004.PNG
    image_path: /assets/images/WSL_python/004.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery5: 
  - url: /assets/images/WSL_python/005.PNG
    image_path: /assets/images/WSL_python/005.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery6: 
  - url: /assets/images/WSL_python/006.PNG
    image_path: /assets/images/WSL_python/006.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery7: 
  - url: /assets/images/WSL_python/007.PNG
    image_path: /assets/images/WSL_python/007.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

gallery8: 
  - url: /assets/images/WSL_python/008.PNG
    image_path: /assets/images/WSL_python/008.PNG
    alt: "placeholder image "
    title: "Image 1 title caption"

--- 

## 0. Preliminary
이후의 내용은 윈도우에 WSL을 이용하여 Ubuntu 18.04가 설치된 환경에서 진행됩니다. 만약 설치하지 않으셨다면 아래 링크를 보고 와 주세요!

[Window에 WSL설치하기](https://gyeonghunkim.github.io/blog/%ED%99%98%EA%B2%BD%EA%B5%AC%EC%B6%95/install-WSL/)

## 1. Visual Studio Code insider 설치하기
WSL에서 visual studio code를 이용하여 python을 이용하기 위해서는 일반적으로 설치할 수 있는 VScode가 아닌 VScode insider를 이용해야 합니다. VScode insider는 더 최근 버전의 (검증이 충분히 되지 않은) 최신의 VS code라고 생각하시면 됩니다. 설치를 위해서는 이[링크](https://code.visualstudio.com/insiders/)에 접속하여 Download for Windows를 클릭한 뒤, 지시에 따라서 설치를 완료하면 됩니다. 설치가 완료되면 기존의 파란 VS code가 아닌 초록색 VS code가 실행될 것 입니다. 

## 2. Remote development extension pack 설치하기
초록색 VS code(VS code insider)를 실행한 뒤의 일은 Remote development extension pack을 설치하는 것 입니다. 이를 위해서 창 왼쪽의 다섯개의 큰 아이콘 중에 마지막 아이콘을 클릭합니다. 이 화면을 통해서 일반적으로 extension pack을 설치할 수 있습니다. 우리는 Remote Development을 검색해서 아래 그림과 같은 extension pack을 설치해야합니다.

{% include gallery id="gallery1" %}

그 후에 **ctrl + `** 를 눌러서 VScode의 터미널을 실행할 수 있습니다. 터미널에서 아래의 명령어를 입력합니다. 

> git config --global core.autocrlf false  

마지막으로 설치된 WSL Ubuntu shell을 실행한 뒤에 아래의 명령어를 입력합니다. 

> code-insiders .

그러면 아래와 같이 잠깐의 시간이 지난 후, 설치가 완료됩니다. 

{% include gallery id="gallery2" %}

완료된 뒤, VS code insider를 종료했다가 실행하면 좌측 하단이 아래 그림과 같이 되어 있다면, 성공입니다!

{% include gallery id="gallery3" %}

## 3. Python extension pack 설치하기
앞서 Remote development extension pack을 설치한 것과 마찬가지로 python extension pack을 설치해야 합니다. Extension pack 아이콘을 누른 뒤, python을 검색하고, 초록 박스 속 **install on WSL**을 눌러서 설치하면 됩니다!

{% include gallery id="gallery4" %}

## 4. Python test하기
아래 그림과 같이 왼쪽 아이콘들 중, 첫 아이콘을 클릭하고, 그림 상의 마우스 위치의 아이콘을 클릭해 새 파일의 이름을 **hello.py**로 지정해줍니다.

{% include gallery id="gallery5" %}

그 뒤에 그 파일을 클릭하고 그림과 같이 아래의 코드를 입력해줍니다. 

> print("Hello, World!")

그 후 **F5**를 누르면 아래 그림과 같이 Debug configuration을 선택할 수 있게 해줍니다. *.py로 확장명을 지정해 두었기 때문에 python을 기본적으로 맨 위에 두고, 우리는 엔터만 쳐 주면 됩니다. 

{% include gallery id="gallery6" %}

그러면 아래와 같이 출력이 되는 것을 확인할 수 있습니다. 


{% include gallery id="gallery7" %}


그러나 현재의 Python의 버전은 python2일 것이고, 이를 python3으로 바꾸어 주어야 합니다. 이를 위해서 **ctrl + shift + p**의 단축키를 누르고 아래와 같이 입력합니다.

> select interpreter

엔터를 누르면 아래 그림과 같이 사용 가능한 interpreter의 목록이 나오고 여기서 선택하면 됩니다. 

{% include gallery id="gallery8" %}


이 환경에서는 기본적으로 설치 된 python2 또는 python3만 사용할 수 있습니다. Anaconda enviroment와 jupyter notebook환경을 사용하는 방법은 아래의 링크를 참조해주세요!

[WSL에 설치된 아나콘다 윈도우에서 사용하기 + jupyter notebook 사용하기](https://gyeonghunkim.github.io/wsl-%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95/anacoda-python-WSL-VSCode/)
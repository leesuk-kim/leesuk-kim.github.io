---
layout: post
title: WSL, winbash, winbuntu 차이점
description: windows 10부터 지원하는 linux 환경의 차이를 살펴본다.
category: news
tags: [win10, winbash, winbuntu, WSL]
comments: true
---

## Windows Subsystem for linux

이 논의를 시작하려면 먼저 WSL(Windows Subsystem for linux, 리눅스용 윈도우 하위 시스템)를 살펴봐야 합니다.
2016년 3월 30일, 윈도우는 WSL라는 서비스를 발표했습니다. 
이 서비스는 윈도우에서 작동하는 리눅스 커널입니다.
우분투 기반이고, 마이크로소프트가 윈도우에 맞게 수정한 커널입니다.
WSL을 그냥 쓰기는 힘드니, WSL을 설치하면 기본적으로 bash가 포함되어 있습니다.
실제로 bash를 실행해서 `uname -a` 명령어를 입력하면 다음과 같이 출력합니다.
```
luvix@windows-bash:/mnt/c/Users/luvix$ uname -a
Linux windows-bash 4.4.0-17134-Microsoft #471-Microsoft Fri Dec 07 20:04:00 PST 2018 x86_64 x86_64 x86_64 GNU/Linux
```
리눅스 커널에 bash만 있으므로 기본적인 어플리케이션만 작동합니다.
하지만 이것저것 패키지를 설치하면 거의 진짜 Ubuntu 처럼 사용할 수 있습니다.

![wsl](/postres/181223/window-features-wsl.jpg)

## Bash on Windows

Bash on Windows, 소위 winbash 라 부르는 이 어플리케이션은 WSL을 실행하는 기본 어플리케이션입니다.
linux를 사용하는 분 중에 shell 없이 작동시키는 분은 거의 없을겁니다.
그리고 shell 중에 가장 유명한 shell 은 bash죠.
bash를 이용해 윈도우에서도 bash 명령을 실행할 수 있을 뿐만 아니라 ubuntu 어플리케이션도 실행할 수 있습니다.
GUI 어플리케이션도 실행할 수 있을 것 같은데, 적어도 WSL에 드라이버를 설치하고 하드웨어를 잡지 않는 이상 쉽지는 않나 생각합니다.
컴퓨터가 많이 아플까봐 해보진 않았습니다.
윈도우 스토어에 [X410](https://www.microsoft.com/store/productId/9NLP712ZMN9Q) 이란 어플리케이션으로 X windows를 실행할 수 있습니다.

![winbash](/postres/181223/winbash.jpg)

## Ubuntu on Windows

WSL을 활성화했다면, 윈도우 스토어에서 Ubuntu 나 OpneSUSE 등을 설치할 수 있습니다.
그러므로 Bash on Ubuntu on Windows가 있다면 Bash on OpenSUSE on Windows 도 있습니다.
winbash와 다른점이 있다면 추가로 설치해야 하고, 거의 모든 기능을 사용할 수 있습니다.
가상머신으로 돌리는 Ubuntu와 다르게 작동하지 않는 패키지(예: Docker) 도 있어서 Winbuntu 라고도 부릅니다.

![Windows Store search: linux](/postres/181223/winstore-linux.jpg)

## 정리

WSL은 윈도우 기능, winbash는 WSL에 포함된 어플리케이션입니다.
Bash on Ubuntu on Windows나 Bash OpenSUSE on Windows는 윈도우 스토어에서 추가할 수 있는 어플리케이션입니다.

## References

- [위키피디아: 리눅스용 윈도우 하위 시스템](https://ko.wikipedia.org/wiki/%EB%A6%AC%EB%88%85%EC%8A%A4%EC%9A%A9_%EC%9C%88%EB%8F%84%EC%9A%B0_%ED%95%98%EC%9C%84_%EC%8B%9C%EC%8A%A4%ED%85%9C)
---
layout: post
title: Windows 10 L2TP VPN 로그인 실패 대응
description: Windows에서 L2TP 프로토콜로 VPN 서버에 로그인할 수 없을 때 레지스트리를 수정하여 로그인한다.
category: computer operation
tags: [win10, VPN, L2TP]
comments: true
---

L2TP VPN server로 접속하기 위해 레지스트리를 수정합니다.

원래 윈도우에서는 VPN을 지원합니다.
하지만 PPTP는 잘 지원하지만, L2TP는 매우 제한적으로 지원합니다.
외부망에 있는 L2TP VPN server로는 접속을 차단합니다.
접속하려면 레지스트리를 수정해야 합니다.

![레지스트리 편집기 실행](/postres/181223/win+r+regedit.jpg)

그냥 윈도우의 '시작'을 실행해서 regedit 이라고 입력해도 똑같이 나옵니다.
실행시 관리자 권한을 요구하므로 긴장하지 말고 확인을 누릅니다.

![키를 등록할 폴더로 이동](/postres/181223/regedit-policyagent.jpg)

레지스트리 편집기를 실행하면 다음 경로로 이동합니다.

```
컴퓨터\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\PolicyAgent
```

![DWARD32 키 추가](/postres/181223/regedit-new-dword32.jpg)

이제 키를 추가합니다.
키 종류는 _DWARD(32비트)값_ 입니다.

![](/postres/181223/edit-item-name.jpg)

키를 추가하면 바로 아래에 _새 값 #1_ 이라고 생성됩니다.
이 상태에서 키 이름 **AssumeUDPEncapsulationContextOnSendRule** 을 입력합니다.

![](/postres/181223/submit-new-key.jpg)

엔터를 누르거나 빈 화면을 클릭하면 저장됩니다.
입력한 키를 우클릭해서 보조메뉴를 연 후 _수정_ 을 클릭합니다.

![](/postres/181223/edit-key-value.jpg)

여기에서 데이터를 변경합니다. 데이터는 **2** 입니다.

![](/postres/181223/finish.jpg)

이제 재부팅하면 로그인할 수 있습니다.
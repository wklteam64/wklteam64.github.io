---
# category: page
layout: post
title: Instalacja i uruchomienie QLC+ na RaspBerry Pi 4 z systemem Raspberry Pi OS
author: WKL TEAM64
# sidebar_link: true
---

Komputery jednopłytkowe **(SBC – Single Board Computers)** mogą być z powodzeniem stosowane do sterowania oświetleniem pobierając o wiele mniej energii niż standardowe komputery i zapewniają wystarczającą moc obliczeniową do obsługi aplikacji DMX512. Mogą być schowane w szafach teleinformatycznych lub rozdzielniach elektrycznych jak używane na wszelkich imprezach na żywo z udziałem publiczneości.
Takim przykładem jest **RPI 4 model B Rev 1.1** zawierający 32 bitowy procesor i 4GB RAM.
Na nim można zainstalować QLC+ z repozytorium. Dzięki wbudowanej karcie WI-FI możemy podłączyć się pod ruter z Internetem a kartę Ethernet podłączyć do bramki Artnet np: PROMYK 3.XX.

``` mermaid
flowchart LR
subgraph RPI
A[RPI4]
L(LAN)
W(WIFI)
end

subgraph RUTER_INTERNET
R[ruter]
LR(LAN)
WR(WIFI)
end

subgraph Bramka_ARTNET
BR[ruter]
LB(LAN)
end

A-->L
L-->LB
LB-->BR

R-->WR
WR<-->W


```
***Rysunek nr 1: Podłączenie RPI do bramki Artnet i rutera***

Dane komputera RPI:

```shell
  lulek@lulek:~ $ cat /proc/cpuinfo 
processor	: 0
BogoMIPS	: 108.00
Features	: fp asimd evtstrm crc32 cpuid
CPU implementer	: 0x41
CPU architecture: 8
CPU variant	: 0x0
CPU part	: 0xd08
CPU revision	: 3

processor	: 1
BogoMIPS	: 108.00
Features	: fp asimd evtstrm crc32 cpuid
CPU implementer	: 0x41
CPU architecture: 8
CPU variant	: 0x0
CPU part	: 0xd08
CPU revision	: 3

processor	: 2
BogoMIPS	: 108.00
Features	: fp asimd evtstrm crc32 cpuid
CPU implementer	: 0x41
CPU architecture: 8
CPU variant	: 0x0
CPU part	: 0xd08
CPU revision	: 3

processor	: 3
BogoMIPS	: 108.00
Features	: fp asimd evtstrm crc32 cpuid
CPU implementer	: 0x41
CPU architecture: 8
CPU variant	: 0x0
CPU part	: 0xd08
CPU revision	: 3

Revision	: c03111
Serial		: 10000000a43957f6
Model		: Raspberry Pi 4 Model B Rev 1.1

```

wersja OS:

```shell
lulek@lulek:~ $ uname -a
Linux lulek 6.12.47+rpt-rpi-v8 #1 SMP PREEMPT Debian 1:6.12.47-1+rpt1~bookworm (2025-09-16) aarch64 GNU/Linux
```

Aby zainstalować QLC PLus na komputerze RPI należy w oknie konsoli sprawdzić czy program jest w repozytorium a potem go zainstalować.

```shell
lulek@lulek:~ $ sudo apt search qlcplus
Sorting... Done
Full Text Search... Done
qlcplus/stable,now 4.12.6-1 armhf 
  Control DMX or analog lighting systems

qlcplus-data/stable,now 4.12.6-1 all 
  Control DMX or analog lighting systems (data files)

  lulek@lulek:~ $ sudo apt install qlcplus

```

Dla 



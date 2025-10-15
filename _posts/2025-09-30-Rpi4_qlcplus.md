---
# category: page
layout: post
title: Instalacja i uruchomienie QLC+ na RaspBerry Pi 4 z systemem Raspberry Pi OS
author: WKL TEAM64
# sidebar_link: true
---

Komputery jednopłytkowe **(SBC – Single Board Computers)** mogą być z powodzeniem stosowane do sterowania oświetleniem pobierając o wiele mniej energii niż standardowe komputery i zapewniają wystarczającą moc obliczeniową do obsługi aplikacji DMX512. Mogą być schowane w szafach teleinformatycznych lub rozdzielniach elektrycznych. 
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
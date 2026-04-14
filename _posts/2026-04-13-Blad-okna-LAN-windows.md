---
layout: post
title: Błędne działanie okna "Edytowanie Ustawień protokołu IP" w systemie Windows
author: WKL TEAM64
---

## Wprowadzenie

Konfiguracja bramki ARTNET PROMYK 3.60 jest bardzo prosta i jest formalnością czego dowodem są instrukcje i filmy instruktażowe dostępne na tej stronie statycznej dokumentacji. Czasem jednak zdarza się że użytkownik ma problem z konfiguracją i nie jest w stanie znaleźć przyczyny błędnego działania mimo że postępuje zgodnie z instrukcjami.

![okno protokolu](https://wklteam64.github.io/img/editErr.webp)

Takim przykładem jest błąd w oknie **"Edytowanie Ustawień protokołu IP"**. Przyczyną tego błędu jest błąd Windowsa i należy przejść innego okna do konfiguracji protokołu IP.

## Rozwiązanie problemu 

Aby rozwiązać ten problem należy przejść do **"Centrum sieci i udostępniania"** i kliknąć w **"Zmień ustawienia karty sieciowej"**. Następnie należy kliknąć prawym przyciskiem myszy na kartę sieciową i wybrać **"Właściwości"**. W oknie właściwości należy znaleźć **"Protokół internetowy w wersji 4 (TCP/IPv4)"** i kliknąć na niego dwukrotnie. W ten sposób otworzy się okno konfiguracji protokołu IP, które powinno działać poprawnie.

![okno protokolu](https://wklteam64.github.io/img/konfWlascIpv4a192168130.webp)


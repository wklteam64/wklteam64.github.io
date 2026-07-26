---
layout: post
title: Korzystanie z AI zamiast instrukcji przy konfiguracji PROMYK 3.60 może zaprowadzić na manowce
author: WKL TEAM64
---

## Wprowadzenie

Ostatnio coraz częściej nowi użytkownicy bramek artnet zaczynają konfigurację urządzenia od zapytania AI a nie instrukcji dostępnej na stronie firmowej. Taka droga prowadzi na manowce bo AI podaje niekiedy błędne odpowiedzi. Oto sprawdzenie kilku agentów AI i pułapek dla początkujących.

### Przykład Gemini

```shell

jak skonfigurować bramke artnet promyk 3.60 z QLC+ ?

Konfiguracja bramki ArtNet **Promyk 3.60** (od WKL TEAM64) w programie **QLC+** sprowadza się do dwóch głównych etapów: prawidłowego ustawienia sieci w komputerze oraz wydelegowania sygnału w samym QLC+.

---

### Krok 1: Przygotowanie sieci na komputerze

Bramka Promyk 3.60 działa jako węzeł sieciowy (Art-Net Node), więc komputer i bramka muszą znajdować się w tej samej podsieci.

1. **Fabryczny adres IP bramki:** `192.168.1.30` (maska `255.255.255.0`).
2. **Ustawienie karty Ethernet w systemie Windows / macOS:**
* Otwórz ustawienia karty sieciowej przewodowej (LAN) połączonej z bramką.
* Przypisz stały (statyczny) adres IP, np. `192.168.1.50` z maską `255.255.255.0`.


3. *(Opcjonalnie)* Otwórz przeglądarkę internetową i wpisz `192.168.1.30`. W panelu WWW możesz sprawdzić, które uniwersum ArtNet przypisane jest do wyjścia **DX0** oraz **DX1** (np. DX0 = Universe 0, DX1 = Universe 1).

---

### Krok 2: Konfiguracja QLC+

1. **Otwórz zakładkę Wejścia/Wyjścia:** QLC+.
Uruchom program QLC+ i na dole ekranu kliknij zakładkę **Wejścia/Wyjścia** (Inputs/Outputs).


2. **Wybierz Uniwersum DMX:** Zakładka Wyjścia.
Na liście po lewej stronie zaznacz **Uniwersum 1** (obsługujące pierwsze wyjście DMX, np. port DX0).


3. **Włącz wtyczkę ArtNet:** Lista interfejsów.
W tabeli po prawej stronie znajdź pozycję **ArtNet**. Zaznacz ptaszek w kolumnie **Wyjście** (Output) przy interfejsie sieciowym odpowiadającym Twojej karcie LAN (z adresem z podsieci `192.168.1.x`).


4. **Skonfiguruj adresowanie ArtNet:** Ikonka zębatki / klucza.
Zaznacz wtyczkę **ArtNet** i kliknij ikonę **Konfiguracja wtyczki** (zębatka na dole panelu):

* **Mode / Mode transmisji:** Wybierz **Broadcast** (wysyłanie do całej sieci) lub **Unicast** wpisując adres IP bramki: `192.168.1.30`.
* **ArtNet Universe:** Upewnij się, że numer uniwersum zgadza się z ustawieniem portu DX0 w Promyku (domyślnie Universe 0 lub 1).


5. **Podłącz drugą linię DMX (opcjonalnie):** Uniwersum 2.
Jeśli korzystasz z drugiego portu **DX1**:

1. Wybierz **Uniwersum 2** po lewej stronie w QLC+.
2. Przypisz do niego wyjście **ArtNet**.
3. W konfiguracji wtyczki ustaw kolejny numer uniwersum ArtNet przypisany do linii DX1.


---

> **Szybka weryfikacja połączenia:**
> Po prawidłowym nawiązaniu transmisji ArtNet z programu QLC+, zielona dioda **STATUS** na bramce Promyk 3.60 zacznie pulsować z wyższą częstotliwością (powyżej 5 Hz), a diody portów DMX (DX0/DX1) zaczną sygnalizować aktywność wysyłania pakietów.

```

I na końcu jest jeden błąd dioda status nie pokazuje pakietów Artnet i częstotliwość jej migania od tego nie zależy, szybkie miganie pokazuje że interfejs LAN do którego jest podłączony PROMYK jest podniesiony.  



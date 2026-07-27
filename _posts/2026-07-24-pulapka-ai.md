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
Jeżeli chodzi od podłączenie w scenariuszu podłączenia bramki artnet do karty sieciowej komputera bezpośrednio po wyjęciu z pudełka to można uznać za poprawne.


### Przykład COPILOT 

```shell
Poniżej masz **konkretną, praktyczną instrukcję krok po kroku**, jak poprawnie skonfigurować **bramkę ArtNet PROMYK 3.60** z **QLC+**. Informacje są oparte na dokumentacji PROMYK 3.60 oraz oficjalnym opisie pluginu ArtNet w QLC+   [wklteam64.pl](https://www.wklteam64.pl/wp-content/uploads/2024/12/manual-promyk3_60.pdf)  [docs.qlcplus.org](https://docs.qlcplus.org/v4/plugins/art-net).

---

## Najważniejsze założenia konfiguracji
**PROMYK 3.60** fabrycznie pracuje w sieci **192.168.1.x/24**.  
**QLC+** wysyła ArtNet jako **UDP na port 6454**, domyślnie **broadcast 192.168.1.255**.  
**QLC+ Universe 1 = ArtNet Universe 0** (ważne!)   [docs.qlcplus.org](https://docs.qlcplus.org/v4/plugins/art-net).

---

## Kompletny przewodnik konfiguracji





**Sources:**   [wklteam64.pl](https://www.wklteam64.pl/wp-content/uploads/2024/12/manual-promyk3_60.pdf)  [docs.qlcplus.org](https://docs.qlcplus.org/v4/plugins/art-net)  [wklteam64.github.io](https://wklteam64.github.io/2026/03/20/Chamsys_przy_wielu_LAN.html)

---

## Podsumowanie
Po wykonaniu powyższych kroków **PROMYK 3.60** powinien poprawnie odbierać dane ArtNet z **QLC+** i wysyłać je jako DMX512.  
Najczęstsze błędy to: zła podsieć, zły Universe, broadcast zamiast unicast, konflikt adresów IP.

---

Jeśli chcesz, mogę przygotować **wersję dla dwóch bramek PROMYK**, **konfigurację przez router Wi‑Fi**, albo **diagnozę krok po kroku**, gdy coś nie działa.  
Co chcesz zrobić dalej?

```

Tu też nie można się przyczepić, ale zmiana pytania na ogólne już może dać inną odpowiedź:

> jak podłączyć bramkę artnet w qlc+ ?

```shell

Podłączenie bramki Art-Net (konwertera Art-Net na DMX) w programie **QLC+ (QLight Controller Plus)** jest stosunkowo proste, ale wymaga prawidłowej konfiguracji sieciowej zarówno na komputerze, jak i na samym urządzeniu.

Oto krótki przewodnik krok po kroku, który pozwoli Ci to szybko i bezboleśnie uruchomić.

---

## Krok 1: Konfiguracja sieciowa (Kluczowy krok!)

Art-Net działa w sieci LAN, co oznacza, że Twój komputer i bramka Art-Net muszą znajdować się w tej samej podsieci.

1. **Sprawdź IP bramki:** Większość bramek Art-Net ma domyślny adres IP zaczynający się od `2.x.x.x` lub `10.x.x.x` (np. `2.0.0.10`) z maską podsieci `255.0.0.0`.
2. **Skonfiguruj kartę sieciową w komputerze:**
* Wejdź w ustawienia karty sieciowej (Ethernet lub Wi-Fi, w zależności od tego, jak podłączasz bramkę).
* Ustaw **statyczny adres IP** (np. jeśli bramka ma `2.0.0.10`, Ty ustaw dla komputera `2.0.0.1`).
* Maskę podsieci ustaw na `255.0.0.0`.



> 💡 **Wskazówka:** Jeśli Twoja bramka pozwala na pracę w standardowej sieci domowej (np. `192.168.1.x` z maską `255.255.255.0`), możesz ją tak skonfigurować – ważne, aby komputer i bramka "widziały się" nawzajem (możesz to sprawdzić, wpisując w terminalu/wierszu poleceń `ping [adres_IP_bramki]`).

---

## Krok 2: Konfiguracja wejść/wyjść w QLC+

Po przygotowaniu sieci czas na konfigurację w samym programie QLC+.

1. Otwórz QLC+ i przejdź do zakładki **Wejścia/Wyjścia** (Input/Output) na dole ekranu.
2. W panelu po lewej stronie zobaczysz listę Twoich przestrzeni adresowych (**Universes** / Wszechświaty). Wybierz ten, który chcesz wysłać do bramki (najczęściej **Universe 1**).
3. W prawym panelu zobaczysz listę dostępnych interfejsów i protokołów. Znajdź pozycję o nazwie **ArtNet**.
4. Rozwiń listę interfejsów ArtNet. Zobaczysz tam dostępne adresy IP Twojego komputera.
5. Zaznacz pole w kolumnie **Wyjście** (Output) przy odpowiednim adresie IP (tym, który jest w tej samej sieci co bramka).

---

## Krok 3: Przypisanie bramki i Universe (Właściwości wtyczki)

Gdy zaznaczysz wyjście ArtNet, musisz upewnić się, że sygnał trafia w odpowiednie miejsce.

1. Kliknij na wiersz z wybranym interfejsem ArtNet, a następnie kliknij ikonę **koła zębatego** (Właściwości / Configure IP plugin) na górze panelu po prawej stronie.
2. Otworzy się okno konfiguracji wtyczki Art-Net:
* **Output IP Address (Adres IP odbiorcy):** Możesz wybrać konkretny adres IP swojej bramki (tryb *Unicast* – zalecany, stabilniejszy) lub adres rozgłoszeniowy (tryb *Broadcast*, np. `2.255.255.255` – wysyła sygnał do wszystkich urządzeń w sieci).
* **ArtNet Universe:** Upewnij się, że Universe w QLC+ odpowiada Universe ustawionemu na fizycznej bramce (często domyślnie jest to `0` lub `1`). *Uwaga: W standardzie Art-Net universes liczy się zazwyczaj od 0, natomiast w QLC+ od 1. Zazwyczaj Universe 1 w QLC+ odpowiada Universe 0 w bramce.*
* **Transmission Mode:** Wybierz standardowy tryb pracy (zazwyczaj *Standard* lub *LTP* w zależności od potrzeb).


3. Kliknij **OK**.

---

## Krok 4: Test połączenia

Aby upewnić się, że wszystko działa:

1. Przejdź do zakładki **Wirtualna Konsola** (Virtual Console) lub **Urządzenia** (Fixtures).
2. Dodaj proste urządzenie (np. zwykły dimmer lub reflektor RGB) przypisane do Universe 1.
3. Spróbuj zmienić wartość suwaka (DMX ch). Jeśli dioda sygnalizacyjna na Twojej bramce Art-Net (zazwyczaj opisana jako *DMX*, *Data* lub *Link*) zacznie mrugać, oznacza to, że bramka prawidłowo odbiera sygnał z QLC+.

Masz już wszystko spięte w jedną sieć? Jeśli napotkasz problem z brakiem reakcji bramki, daj znać – najczęściej to kwestia drobnego błędu w adresacji IP lub numeracji Universe!

```

Co przeważnie w tym momencie robi początkujący? Ustawia adres karty sieciowej komputera na 2.0.0.1 z maską 255.0.0.0 i próbuje się połączyć z PROMYKIEM 3.60, którego adres fabryczny jest 192.168.1.30 z maską 255.255.255.0 co kończy się niepowodzeniem. W instrucji tej bramki artnet na stronie 7 w tabel nr 1 podano tryby pracy które można zmienić za pomocą przycisku z tyłu. 
Wejście w tryb 3 powoduje że PROMYK 3.60 :

* uzyskuje adres **2.168.1.30** i maskę **255.0.0.0**
* na złączu DX0 jest Universe nr 0 a DX1 Universe nr 1
* adres strony konfiguracji (wpisywany do przeglądarki www) jest teraz taki sam adres bramki artnet **2.168.1.30** (a nie 192.168.1.30 bo w tym momencie urządzenie sieciowe takiego nie ma).
* Ta konfiguracja jest opisana jako nietrwała i po wyłączeniu zasilania nie będzie zapamiętana. Aby **PROMYK 3.60** startował z tymi ustawieniami należy wejść w przeglądarkę www, wpisać adres 2.168.1.30 maska 8-bit i tą konfigurację zapisać .
* Przycisk z tyłu urządzenia tej bramki służy oprócz resetu urządzenia do ustawień fabrycznych na stałe także do szybkiego przejścia do adresacji natywnej artnetu 2.x.x.x/8. Zakres tej sieci jest od 2.0.0.1 do 2.255.255.255. 

### Przypadek istnienia kilku kart sieciowych na jednym komputerze

Przy zadawaniu pytania o konfigurację użytkownik nie podaje faktu że posiada na komputarze oprócz karty LAN także karty WI-FI. Jeśli karta sieciowa LAN i WI-FI posiadają ten sam adres sieci np:

> 192.168.1.1 ma LAN i 192.168.1.1 na WIfi to nie będzie prawidłowej komunikacji , pytanie do AI GEMINI : "jeżeli na karcie LAN mam adres 192.168.1.1 a na karcie wifi podłączonej do rutera mam sieć 192.168.1.0/24 to jak ustawić promyk "

```shell
W wierszu poleceń (CMD) masz do wyboru kilka poleceń, w zależności od tego, jak szczegółowych informacji potrzebujesz:

---

### 1. Szybka lista (podstawowe informacje i adresy IP)

Najpopularniejsze polecenie, które wyświetli nazwy kart, ich adresy IP, maski i bramy domyślne:

```cmd
ipconfig

```

---

### 2. Pełny profil kart (adresy MAC, serwery DNS, DHCP)

Jeśli chcesz zobaczyć fizyczne adresy kart (MAC), status DHCP czy serwery DNS:

```cmd
ipconfig /all

```

---

### 3. Zwięzła lista ze stanem połączenia

Jeśli zależy Ci na czystym zestawieniu, które karty są fizycznie podłączone, a które wyłączone:

```cmd
netsh interface show interface

```

---

### 4. Wyświetlenie informacji systemowych przez WMIC

Aby sprawdzić dokładny model, nazwę sprzętową karty oraz jej identyfikator:

```cmd
wmic nic get name, netconnectionstatus, speed

```

*(W kolumnie `NetConnectionStatus` wartość **2** oznacza kartę połączoną, a **7** rozłączoną).*

---

> **Wskazówka do konfiguracji Art-Net:**
> Używając `ipconfig /all`, upewnij się, że pod pozycją odpowiadającą Twojemu gniazdu Ethernet (LAN) widzisz ustawiony stały adres IP (np. `10.0.0.1`), a opcja **DHCP aktywne** wskazuje wartość **Nie**.

```
Komendy wpisywane w **CMD (wiersz poleceń)** mają to zaletę że nie zmieniły się od windows 95 i o wiele szybciej uzyskuje się informację zamiast tracić czas na przeskakiwanie między oknami i co wersja windows to innymi.

![Ipconfig](https://wklteam64.github.io/img/Wipcon.webp)
przykład użycia komendy **ipconfig**


![ping 2.168.1.30](https://wklteam64.github.io/img/ping200.webp)
Na przykład, jeśli bramka ma adres IP 2.168.1.30, to można użyć komendy **ping 2.168.1.30** w terminalu.




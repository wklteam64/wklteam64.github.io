---
layout: post
title: Konfiguracja bramki Artnet PROMYK 3.xx z oprogramowaniem ONYX OBSIDIAN
author: WKL TEAM64
---

 **Konfiguracja bramki Artnet PROMYK 3.xx z oprogramowaniem ONYX OBSIDIAN**
Bramka Artnet PROMYK 3.xx jest urządzeniem sieciowym, które umożliwia przesyłanie sygnałów DMX przez protokół Artnet w sieciach Ethernet. Poniżej przedstawiamy kroki konfiguracji tej bramki z oprogramowaniem ONYX OBSIDIAN.

**Plan konfiguracji:**

1. bramka artnet PROMYK 3.xx ma mieć ustawiony adres IP w podsieci 2.x.x.x z maską 255.0.0.0, więc będzie ona miała adres 2.168.1.30 i maskę podsieci 255.0.0.0
2. karta sieciowa komputera/konsoli z oprogramowaniem ONYX OBSIDIAN ma mieć ustawiony adres IP w tej samej podsieci, np.2.0.0.1 z maską podsieci 255.0.0.0


**Krok 1: Podłączenie bramki PROMYK 3.xx do sieci**

- Podłącz bramkę do zasilania.
  
> w przypadku bramek PROMYK 3.00 i 3.50 wymuszenie pracy z adresami IP w podsieci 2.x.x.x wymaga przełączenia dwóch dźwigni znajdujących się z przodu obudowy bramki w pozycję ON (dół). Urządzenia PROMYK 3.60 mają tę funkcję poprzez przytrzymanie przycisku z tyłu obudowy zgodnie z instrukcją obsługi. Te dokumenty są dostępne na stronie producenta: https://wklteam64.github.io/manual.html .

- Ustaw adres IP karty sieciowej komputera/konsoli z oprogramowaniem ONYX OBSIDIAN na adres 2.0.0.1 z maską podsieci 255.0.0.0
  
- Otwórz wiersz poleceń (cmd) i sprawdź połączenie z bramką PROMYK 3.xx za pomocą polecenia ping:
  
``` shell
  ping 2.168.1.30

```
A do wyświetlenia wszystkich ustawień sieciowych użyj polecenia:
  
``` shell
  ipconfig
```
![ipconfig](https://wklteam64.github.io/img/Wipcon.webp)
**Rysunek nr 1: Rezultat polecenia ipconfig, w tym przypadku oprócz bramki PROMYK 3.xx na złączu *Ethernet 2* które ma adres 2.0.0.1/8, jest podłączony ruter z wifi, który przydzielił po DHCP adres 192.168.250.110/24**

Jeżeli złącze *ETHERNET 2* nie ma adresu IPv4 ustawionego wyświetli się komunikat **Media disconnected** jak na rysunku nr 1.

Wtedy należy wejść w ustawienia karty sieciowej i ustawić adres IP ręcznie.
![ipconfig okno](https://wklteam64.github.io/img/WekranKonfEth.webp)
**Rysunek nr 2: Aby dostać się do tego okna ustawień należy odszukać ustawienia karty sieciowej w ustawieniach komputera dotyczących sieci komputerowych przewodowych i bezprzewodowych**


![ipconfig okno ](https://wklteam64.github.io/img/WethKonf.webp)
**Rysunek nr 3:Aby dostać się do tego okna ustawień należy odszukać ustawienia karty sieciowej i kliknąć w niej prawym przyciskiem myszy, a następnie wybrać opcję "Właściwości", w starszych systemach Windows używa się tego okna**

> **UWAGA:** W kartach sieciowych LAN nie ma włączonego protokołu DHCP, więc adres IP musi być ustawiony ręcznie.

Jeżeli polecenie ping zakończy się sukcesem, oznacza to, że bramka PROMYK 3.xx jest poprawnie podłączona do sieci i gotowa do konfiguracji.

> **UWAGA:** Strona konfiguracji bramki PROMYK 3.xx jest dostępna pod adresem obecnym a nie fabrycznym, czyli jeżeli bramka ma adres IP 2.168.1.30 to strona konfiguracyjna będzie dostępna pod adresem http://2.168.1.30 a nie pod adresem http://192.168.1.30. Stronę konfiguracyjną możemy otworzyć tylko do wglądu, gdy nic nie zmieniamy w ustawieniach bramki. W przypadku zmiany **PROMYKA 3.60** w trybie 3, który jest nietrwałym trybem pracy, po restarcie bramka wróci do ustawień fabrycznych, należy te zmiany zapisać aby były trwałe.

![web-config](https://wklteam64.github.io/img/Wwebpage.webp)
**Rysunek nr 4: Strona konfiguracyjna bramki PROMYK 3.50**


**Krok 2: Konfiguracja oprogramowania ONYX OBSIDIAN**


- Otwórz oprogramowanie ONYX OBSIDIAN.
- Przejdź do MENU > ETHERDMX
  
  ![onyx-settings](https://wklteam64.github.io/img/WonGlogalOut.webp)
**Rysunek nr 5: W tym oknie należy włączyć protokół Artnet, opcjonalnie można włączyć protokół *bROADcast* dla celów diagnostyki za pomocą programu *Wireshark* lub https://www.lightjams.com/artnetominator/**

- W sekcji **DEVICES** powinno pojawić się urządzenie PROMYK 3.xx z adresem IP
  
  ![onyx-devices](https://wklteam64.github.io/img/WonyxKonfDev.webp)
  **Rysunek nr 6: W tym oknie należy wybrać urządzenie PROMYK 3.xx i przypisać mu odpowiednie UNIVERSE, w wersji PC możemy bez licencji uruchomić tylko jeden universe, a numeracja w programie zaczyna się o numeru 1, który jest w protokole ARTNET numerem 0**


  > W aplikacji ONYX OBSIDIAN numeracja UNIVERSE zaczyna się od 1, natomiast w protokole Artnet numeracja zaczyna się od 0. Należy pamiętać o tej różnicy podczas przypisywania UNIVERSE do bramki PROMYK 3.xx.

**Należy pamiętać, że w wersji bez licencji oprogramowania ONYX OBSIDIAN można używać tylko jednego UNIVERSE. Jeśli potrzebujesz więcej UNIVERSE, konieczne będzie zakupienie odpowiedniej licencji lub podłączenie do konsoli tej firmy.**

![onyx-M2g0](https://wklteam64.github.io/img/W_M2goEthDmx.webp)
**Rysunek nr 7: Złącza konsoli Martin, bramkę ARTNET PROMYK 3.xx podłącza się do portu *EtherDMX***

>W przypadku podłączenia bramki PROMYK 3.xx do konsoli Martin, ONYX itp w większej liczbie należy podłączyć je do przełącznika sieciowego (switch) i ustawić odpowiednie adresy IP w tej samej podsieci 2.x.x.x/8. 

Po wykonaniu powyższych kroków bramka Artnet PROMYK 3.xx powinna być poprawnie skonfigurowana i gotowa do pracy z oprogramowaniem ONYX OBSIDIAN. Możesz teraz przesyłać sygnały DMX przez sieć Ethernet za pomocą protokołu Artnet, gdy zostaną dodane odpowiednie urządzenia **(FIXTURES)** i efekty świetlne w oprogramowaniu ONYX OBSIDIAN za pomocą **patch** i przypisania ich do odpowiednich UNIVERSE.

Wtedy miga dioda LED na bramce PROMYK 3.xx na złączu DX0 (przy jednym universe) lub DX0 i DX1 (przy dwóch universe) sygnalizując odbiór danych DMX.

[Film instruktażowy dotyczący konfiguracji bramki Artnet PROMYK 3.xx z oprogramowaniem ONYX OBSIDIAN-Youtube](https://youtu.be/WJkzyEks0rM)

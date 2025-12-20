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


**Krok 2: Konfiguracja oprogramowania ONYX OBSIDIAN**

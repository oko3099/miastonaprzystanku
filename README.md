# Miasto Na Przystanku

Prosta strona wizytówkowa (bez backendu) z linkami do social mediów i sekcją plików do pobrania.

## Struktura plików

- `index.html` — strona główna, minimalistyczny styl (motyw linii przystankowej, akcent pomarańczowy)
- `pliki.html` — osobna podstrona z plikami do pobrania (wersja nowoczesna)
- `graty.html` — wersja na graty: lekka, czysta strona w stylu stron sprzed ery CSS3,
  oparta na tabelach, zoptymalizowana pod starsze komputery i przeglądarki
- `graty-pliki.html` — osobna podstrona z plikami do pobrania w wersji na graty
  (wygląda jak klasyczny listing katalogu)
- `files/` — pliki do pobrania (wspólny katalog dla obu wersji)
- `robots.txt`, `sitemap.xml` — pliki pomagające Google zaindeksować stronę
- `background.jpg` — **dodaj własne zdjęcie tła (poziome)** dla `index.html`
- `logo.png` — **dodaj własny obrazek logo** w miejsce napisu "Miasto Na Przystanku"
  na stronie głównej (`index.html`)
- `banner.png` — **dodaj własny baner** (poziomy, ok. 900×260 px) w miejsce napisu
  "Miasto Na Przystanku" na stronach `graty.html` i `graty-pliki.html`

## Obrazki do wstawienia

| Plik | Gdzie jest używany | Zalecany rozmiar |
|---|---|---|
| `background.jpg` | tło banera na `index.html` | min. 1920 px szer., poziome |
| `logo.png` | nagłówek `index.html` (zamiast tekstu) | ok. 500–800 px szer., tło przezroczyste zalecane |
| `banner.png` | nagłówek `graty.html` i `graty-pliki.html` | ok. 900×260 px |

Sam tekst „Miasto Na Przystanku” został zachowany w kodzie jako niewidoczny nagłówek
(`h1`) na `index.html` oraz jako atrybut `alt` obrazka na `graty.html` — dzięki temu
wyszukiwarki i czytniki ekranu nadal „widzą” nazwę strony, nawet gdy widoczny jest
tylko Twój obrazek.

## Kolory

Akcent w wersji nowoczesnej to teraz pomarańcz (`--stop-orange: #c8551f`) —
zmieniaj go w bloku `:root` na górze `index.html` i `pliki.html`.

## SEO / widoczność w Google

1. Podmień wszystkie wystąpienia `https://TWOJA-DOMENA/` na docelowy adres strony
   (w `index.html`, `pliki.html`, `graty.html`, `graty-pliki.html`, `robots.txt`
   i `sitemap.xml`) — to adres, pod którym strona będzie działać po publikacji
   na GitHub Pages, np. `https://oko3099.github.io/miasto-na-przystanku`.
2. Po publikacji dodaj stronę w [Google Search Console](https://search.google.com/search-console)
   i zgłoś adres `sitemap.xml` — to znacznie przyspiesza zaindeksowanie.
3. Strony mają już uzupełnione tytuły, opisy (`meta description`) oraz tagi
   Open Graph (podgląd przy udostępnianiu na Facebooku/Discordzie itp.).

## Jak dodać/zmienić linki społecznościowe

- `index.html` — sekcja `<div class="route">`, każdy link to blok `.stop`
- `graty.html` — lista `<ul class="linklist">` oraz pasek nawigacji `.nav`

Podmień same adresy `href="..."`.

## Jak dodać pliki do pobrania

1. Wrzuć plik do katalogu `files/`.
2. Skopiuj jeden blok pliku:
   - w `pliki.html` — `<div class="file">...</div>`
   - w `graty-pliki.html` — wiersz `<tr>...</tr>` w tabeli `.listing`
   i podmień nazwę pliku oraz `href="files/NAZWA"`.

## Publikacja na GitHub Pages

```bash
git init
git add .
git commit -m "Miasto Na Przystanku - strona"
git branch -M main
git remote add origin https://github.com/oko3099/NAZWA-REPO.git
git push -u origin main
```

Potem w ustawieniach repo: **Settings → Pages → Source: `main` / `/root`** i zapisz.
Strona pojawi się pod adresem `https://oko3099.github.io/NAZWA-REPO/`.

Domyślnie otwiera się `index.html`. Link do plików jest na stronie głównej
("Pliki do pobrania"), a link do wersji na graty — w stopce ("wersja na graty").

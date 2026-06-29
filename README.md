# 🌤️ Meteostanice Palkovice

Jednoduchá mobilní webová aplikace pro zobrazení meteorologických dat ze stanice **Palkovice** ([amet.cz](http://www.amet.cz/aktualPalkovice.html)).

Optimalizováno pro **Android 4.4.2 / Chrome 31** — funguje bez jakýchkoli moderních závislostí.

---

## 📱 Screenshoty / ukázka

Aplikace zobrazuje:
- 🌡️ Teplota vzduchu a půdy
- 💧 Vlhkost vzduchu a rosný bod
- 🔵 Atmosferický tlak
- 💨 Rychlost a směr větru, nárazy
- 🌧️ Srážky (minutové + denní)
- ☀️ Sluneční záření a UV index

---

## 🚀 Použití

### Varianta A – GitHub Pages (doporučeno)

1. Forkni tento repozitář
2. Jdi do **Settings → Pages**
3. Nastav source: `main` / `/ (root)`
4. Otevři na telefonu: `https://TVOJE_JMENO.github.io/REPO_NAZEV/`

### Varianta B – Lokálně

Stáhni `index.html` a otevři přímo v prohlížeči. **Nevyžaduje server.**

---

## 🔧 Technické detaily

| Vlastnost | Hodnota |
|-----------|---------|
| Cílová platforma | Android 4.4.2, Chrome 31.0.1650.59 |
| Závislosti | **žádné** (čisté HTML/CSS/JS) |
| Zdroj dat | http://www.amet.cz/aktualPalkovice.html |
| Obnova dat | automaticky každých 5 minut |
| CORS proxy | allorigins.win → corsproxy.io → thingproxy (fallback) |

### Kompatibilita

- ✅ Android 4.4.2 / Chrome 31
- ✅ Moderní prohlížeče (Chrome, Firefox, Safari)
- ✅ Bez ES6+, bez Fetch API, bez CSS Grid
- ✅ Používá `XMLHttpRequest`, `-webkit-` prefixy, `flexbox` s prefixy

### Datový zdroj

Data jsou načítána z veřejné HTML stránky `amet.cz` přes CORS proxy,
protože stránka amet.cz neobsahuje CORS hlavičky. Aplikace zkouší tři
různé proxy v pořadí a při selhání zobrazí chybovou hlášku.

---

## 📂 Struktura souborů

```
.
└── index.html    # Celá aplikace v jednom souboru
```

---

## ⚙️ Přizpůsobení

Chceš zobrazovat jinou stanici amet.cz? V souboru `index.html` změň URL v proměnné `PROXY_URLS`:

```javascript
var PROXY_URLS = [
  'https://api.allorigins.win/get?url=' + encodeURIComponent('http://www.amet.cz/aktualXXXXXX.html'),
  ...
];
```

Interval obnovy (výchozí 5 minut) změníš v:
```javascript
var REFRESH_MS = 5 * 60 * 1000;
```

---

## 📄 Licence

MIT — volně použij a uprav.

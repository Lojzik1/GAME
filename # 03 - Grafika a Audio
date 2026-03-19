# 03 - Grafika a Audio

## 1. Grafika

### Vizuální styl a Zásady designu
Pro hru byl zvolen styl **Pixel Art**. Tento styl je ideální pro precizní platformovky (typu Jump King), protože jasně ukazuje hranice objektů (hitboxy). Zásadním požadavkem je dokonalá čitelnost okrajů platformy a polohy hráče, aby hráč přesně věděl, kam může dopadnout.

### Použité nástroje
* **Tvorba grafiky:** Piskel (online pixel-art editor)
* **Formát:** PNG s průhledným pozadím
* **Engine:** Godot 4

### Postup tvorby grafických podkladů

**1. Hráč:**
Postava byla navržena v editoru Piskel. Rozhodl jsem se pro modrou barvu těla pro silný kontrast a jednoduchý, geometrický tvar, který zajišťuje dobrou viditelnost i při malém rozlišení. Postava je zaoblený obdélník s dvěma bílými obdélníky jako oči (viz screenshot z designové fáze v editoru). Sprite byl následně vyexportován jako PNG.

*(Design postavy v editoru Piskel)*
`![Screenshot designu hráče v editoru Piskel](docs/piskel_ukazka.png)`

*Finální sprite list:*
`![Vyexportovaný sprite list hráče (PNG)](assets/sprites/hlavni_postava.png)`

**2. Prostředí (Tileset):**
Pro tvorbu herního světa byl navržen jednoduchý tileset. Vytvořil jsem základní, jednobarevný dlaždicový blok pro podlahu a stěny, který je barevně odlišný od hráče.

*(Ukázka dlaždice prostředí)*
`![Ukázka tileset dlaždice (PNG)](docs/ground_ukazka.png)`

**3. Import do Godotu a nastavení:**
Obrázky byly importovány do Godotu. Aby byl zachován "retro" feeling a ostré pixely, byl v nastavení importu (v Project Settings -> Rendering -> Textures) změněn **Texture Filter** z výchozího na **"Nearest"**. Tím se zabránilo nežádoucímu rozmazání grafiky.

**4. Cíl levelu (Brána):**
Pro označení konce úrovně jsem vytvořil sprite červené brány o velikosti 32x64 pixelů. Má výraznou barvu, aby na ni hráč okamžitě zaměřil pozornost, a je dvakrát vyšší než hráčská postava, aby do ní hráč proporčně "zapadl".

*(Ukázka brány)*
`![Screenshot Brány](docs/gate_ukazka)`

*(Ukázka nastavení Nearest filtru)*
`![Screenshot nastavení filtru Nearest v Godotu](docs/godot_import_nearest.png)`

### Ukázka implementace ve scéně
Vytvořil jsem základní zkušební scénu v Godotu, která demonstruje viditelnost hráče na platformách.

*(Maketa herní scény v Godotu)*
`![Screenshot scény v Godotu s hráčem a platformou](docs/godot_scene.png)`

---

## 2. Audio

### Zvukový styl a Zdroje
Ke zvolené pixel-artové grafice se nejlépe hodí zvukové efekty a hudba, které doplňují atmosféru hardcore plošinovky. Design zvuku je navíc tematicky propojen s hlavní postavou (sliz/blob), takže místo tvrdých 8-bitových zvuků byly zvoleny více organické a "mokré" zvuky.
* **Zdroje audia:** Veškeré zvukové efekty (SFX) i hudba v pozadí byly staženy z volně dostupné databáze [Freesound.org](https://freesound.org/).
* **Formáty:** Všechny stažené soubory jsou ve formátu WAV.

### Seznam zvuků
Jelikož byla ze hry odstraněna klasická chůze a postava se pohybuje primárně pouze pomocí přesných skoků, jsou zvuky zaměřeny čistě na tuto mechaniku a herní smyčku:
* **Skok:** Typický "slizký" zvuk (squish/čvachtnutí) při odrazu.
* **Dopad:** Mokrý zvuk (splat) při kontaktu slizké postavy s tvrdou platformou.
* **Game Over (Pád):** Zvuk spadnutého slizu/slimu z výšky.
* **Hudba:** Krátká (8sekundová) smyčka hrající na pozadí, která šetří velikost hry a dodává retro atmosféru.

### Implementace v Godotu
Zvukové soubory jsou v enginu zpracovány pomocí uzlů:
* **AudioStreamPlayer:** Využívá se pro plošné zvuky (hudební smyčka). U hudby byl v nastavení importu v Godotu zapnut **Loop Mode (Forward)**, aby těch 8 sekund plynule navazovalo a hrálo do nekonečna.
* **AudioStreamPlayer2D:** Využívá se pro poziční zvuky (skok, dopad), kde je zdroj zvuku napojený přímo na uzlu hráče.

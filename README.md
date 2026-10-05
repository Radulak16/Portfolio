# Radek Šmíd — osobní portfolio

České portfolio v čistém HTML, CSS a JavaScriptu, bez frameworku a build kroku. Pět sekcí: `#home`, `#work`, `#skills`, `#about`, `#contact`. Obsah a navigace jsou dostupné bez JavaScriptu. JavaScript přidává historii, animace, mobilní menu a kopírování e-mailu.

## Spuštění

Otevřete `index.html` v prohlížeči. Pro lokální server lze ve složce spustit `python3 -m http.server 8000` a otevřít `http://localhost:8000`. Kopírování do schránky vyžaduje podporovaný bezpečný kontext (HTTPS nebo localhost).

## Nasazení na GitHub Pages

1. Rozbalte soubory a nahrajte obsah složky `portfolio` do kořene repozitáře `Radulak16/Portfolio`. Před nahrazením existujících souborů je porovnejte.
2. V nastavení repozitáře otevřete Pages a zvolte nasazení z větve, odpovídající větev a složku `/ (root)`.
3. Po dokončení nasazení ověřte adresu zobrazenou GitHubem. Předpokládaná adresa je `https://radulak16.github.io/Portfolio/`; v této dodávce není potvrzeno její skutečné nasazení.
4. Pokud se adresa liší, aktualizujte canonical, OG URL a image, JSON-LD, robots.txt, sitemap.xml a absolutní cestu `/Portfolio/` ve 404.html.

Vlastní doména nebyla uvedena, proto soubor `CNAME` není přiložen. Při jejím přidání aktualizujte všechny adresy a cestu stránky 404. Formulář nebyl vyžádán, kontakt proto funguje přes e-mail.

## Soubory

- `index.html`: celý web s interním CSS a JS.
- `404.html`: stránka pro nenalezené adresy.
- `robots.txt`, `sitemap.xml`: indexace plánované adresy.
- `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png`: ikony RŠ.
- `og-image.html`: šablona 1200 × 630 px pro budoucí snímek obrazovky.
- `og-image.png`: hotový typografický obrázek pro sdílení, vytvořený samostatně se stejnými barvami a textem.
- `KONTROLA.md`: ověřené body a limity ověření.

## Obsah a struktura

Úvod představuje Radka jako studenta se zájmem o investování a AI. Sekce Projekty obsahuje jediný potvrzený záměr TR-AI, bez vymyšleného dema, kódu, technologií či výsledků. Dovednosti uvádějí ChatGPT a Astra, TradingView, externí AI Ondřeje Koběrského a další učení. O mně obsahuje čtyři krátké odstavce, fakta a vzdělání bez nepodložených dat. Kontakt nabízí e-mail a jediný poskytnutý GitHub odkaz.

Není doložena četnost používání nástrojů, proto je úroveň „Používám / Učím se“, nikoli „Denně používám“. Nebyly uvedeny jazyky ani přesný stav dostupnosti, tyto údaje nejsou doplněné. Certifikáty a účasti na akcích nejsou uvedeny. Odkaz vede do konkrétního repozitáře, nikoli na všechny repozitáře nebo profil. JSON-LD proto netvrdí `sameAs` pro tento odkaz. Bez fotografie se používá dekorativní orbit s iniciálami.

## Vizuální systém a efekty

Aktuální podoba vychází z přiloženého souboru `Vložený markdown.md` (uživatelem označeného jako vzhled-webu-pro-ai.md) a z následného požadavku na tmavě modrou a bílou.

- Pozadí `#061224`, nadpisy a hlavní akcent `#ffffff`.
- Běžný text `#c5d1e2`, popisky `#bfccde`, fokus a stav `#acd1ff`.
- Modré skleněné panely, pilulková navigace, menu pod 920 px, pohyb šipek, světelný pruh projektu, jemný hover karet a časová osa.
- Všechny původní popisné odstavce byly zachovány.

Kontrast byl vypočten nejen vůči základnímu pozadí, ale i vůči konzervativní světlé mezi všech tmavých ploch a překryvů `#36577f`. Nejnižší poměr je 4,57:1. Výsledky a limity jsou v KONTROLA.md.

Inter Tight (400, 600) a JetBrains Mono (400) se načítají z Google Fonts s `display=swap` a lokálními fallbacky. Nepoužité řezy ani písmo pro chybějící citáty se nenačítají.

Knihovny mají pevné verze:

- GSAP 3.12.5: `https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js`.
- ogl 1.0.11: `https://cdn.jsdelivr.net/npm/ogl@1.0.11/+esm`.

Efekty se načítají až po vykreslení obsahu. FoldText je vlastní implementace parametrů z přílohy: písmena po slovech, zachování vnořených značek, horní závěs, stín přehybu a kopie pro čtečku obrazovky. Vlnové pozadí je vlastní shader podle popisu LineWaves v příloze (32 vnitřních a 36 vnějších linií, rotace −45°, rychlost 0,2, jas 0,17), nikoli převzatý zdrojový kód React Bits. Běžící pásy, magnetické prvky, naklápění, vlastní kurzor a další volitelné efekty nejsou zapnuté.

Jediné WebGL pozadí se vůbec nenačítá při `pointer: coarse` nebo `prefers-reduced-motion: reduce`. Smyčka se zastaví při skryté kartě, otevřeném menu, tisku a ztrátě WebGL kontextu. Statický modrý podklad je dostupný vždy. Při omezeném pohybu se nenačítá GSAP a vypínají se i CSS animace. Čas v levém dolním rohu používá výhradně `Europe/Prague`.

Bez analytiky a vlastních cookies. Externí fonty, GSAP a ogl způsobují síťové požadavky na Google a jsDelivr. Výpadek CDN neblokuje text a navigaci. Při tisku jsou všechny sekce pod sebou, černě na bílém podkladu, bez skla a efektů.

## Co lze doplnit později

Vlastní fotografie, reálný náhled TR-AI, technologie implementace, veřejný kód či demo, jazyky, dostupnost, další ověřené profily a případná doména. Formspree identifikátor bude potřeba pouze při požadavku na kontaktní formulář. Tyto údaje nejsou nutné pro fungování současné verze.

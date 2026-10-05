# Kontrola modrobílé verze

## Provedené kontroly

| Oblast | Výsledek |
| --- | --- |
| Barvy | Splněno: tmavě modrá #061224, bílé nadpisy a akcenty, šedomodrý běžný text. Fialové a mátové hodnoty v HTML ani grafických šablonách nezůstaly. |
| Texty | Splněno: všech 16 původních popisných odstavců se přesně shoduje s předchozí verzí. Bez nových biografických tvrzení. |
| HTML a odkazy | Splněno: jediný H1, unikátní ID, všech pět sekcí, všechny interní kotvy mají existující cíl, každý odkaz má href. |
| JavaScript | Kontrola syntaxe přes node --check prošla. Vlastní JS má přibližně 4,9 kB po kompresi; externí knihovny se načítají později. |
| Kontrast | Výpočet lineární sRGB luminance prošel pro všechny textové tokeny, tlačítka i konzervativní mez překryvů. Podrobnosti níže. |
| Související soubory | Upraveny 404.html, favicon.svg, PNG ikony, og-image.html a og-image.png. Sitemap zůstává platné XML. |

## Kontrast

Horní mez světlosti tmavých ploch byla zvolena jako #36577f, světlejší než vypočtené kombinace shaderu, clony, bílého šumu, hover panelu, světelného pruhu, stavové pilulky a gradientů menu. Shader omezuje každý kanál na nejvýše 0,32, nad ním je 52% tmavě modrá clona. Kontrasty níže jsou konzervativní poměry pro plně zobrazený text; na běžném podkladu jsou vyšší.

| Text | Barva | Minimální vypočtený poměr |
| --- | --- | --- |
| Nadpisy a hlavní akcenty | #ffffff | 7,43:1 |
| Běžný text | #c5d1e2 | 4,81:1 |
| Popisky | #bfccde | 4,57:1 |
| Stav a potvrzení | #acd1ff | 4,71:1 |
| Tmavý text bílého tlačítka | #061224 na #ffffff | 18,75:1 |

Během odhalovacích animací se záměrně mění opacity. Při omezení pohybu jsou texty ihned plně viditelné.

## Implementováno, vyžaduje ověření v prohlížeči

- Úvod se jménem, rolí, podnadpisem a dvojicí tlačítek; ověřit umístění bez rolování na cílových rozměrech.
- Historie pushState/popstate a přechody Zpět/Vpřed mezi sekcemi.
- Menu s kruhovým odhalením, postupným zobrazením položek, aria-expanded, zámkem fokusu, Escape a návratem fokusu.
- Přístupnost klávesnicí, skip link, focus-visible a plochy ovládacích prvků minimálně 44 px.
- Rozkládání nadpisů po celých slovech, přístupná textová kopie, jemné odhalování bloků.
- Jeden canvas s modrými vlnami a statický fallback. Zastavení smyčky na pozadí a při otevřeném menu.
- Vypnutí všech animací při prefers-reduced-motion; žádné WebGL ani průběžné efekty na coarse pointer.
- Kopírování e-mailu, dvousekundové potvrzení a srozumitelná chyba.
- Čas je výslovně Europe/Prague.
- Náhled tisku: všechny sekce, bílé pozadí, černý text, bez animací.

Prohlížečové QA, reálné načtení CDN, WebGL na konkrétním zařízení a Lighthouse nebyly v tomto prostředí spuštěny. Není proto potvrzeno skóre Performance ≥90, Accessibility/Best Practices/SEO 100 ani načtení do 1,5 s.

## Před publikováním

Web nebyl zveřejněn ani zapsán do GitHub repozitáře. Po nahrání ověřit URL GitHub Pages uvedenou v canonical, Open Graph, JSON-LD, robots.txt a sitemap.xml. Vlastní doména nebyla uvedena, proto chybí CNAME. Fotografie, náhled TR-AI, nové profily a formulář lze doplnit později; nejsou nahrazené smyšlenými údaji.

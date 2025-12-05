# Backlog Grooming Co-Pilot – maandumisleht

See ZIP sisaldab minimaalset, kuid praktilist maandumislehte teenusele **Backlog Grooming Co-Pilot** – ChatGPT/LLM-põhine abiline, mis aitab Product Owneritel ja tiimidel oma backlog'i korrastada, duplikaate leida ning piletitele value vs effort skoori anda.

![](https://github.com/arvutionu2015m/backlog-grooming-co-pilot/blob/main/Backlog.png)

## Failistruktuur

- `index.html` – põhileht (Vapor Bootstrap 5 stiilis), SEO-sõbralik ja mobiilisõbralik.
- `style.css` – kohandatud stiilid (glassmorphism, hero, pricing, prompti plokk).
- `main.js` – loogika 25 kasutusjuhtu / prompti jaoks, rippmenüü täitmine ja kopeerimisnupp.
- `README.md` – see fail.

Kõik koos moodustavad iseseisva staatilise lehe, mida saab serveerida mistahes odavast hostingust (Netlify, Vercel, GitHub Pages, klassikaline Apache/Nginx jne).

## Põhiidee (resümee)

**Backlog Grooming Co-Pilot** on LLM-i peale ehitatud tööriist, mille eesmärk on:
- lugeda läbi Jira / Trello / muu backlog;
- tuvastada duplikaadid ja ebamäärased piletid;
- pakkuda automaatset **value vs effort** skoori;
- valmistada ette backlog nii, et grooming'u koosolekul kuluks vähem aega vaidlustele ja rohkem aega otsustamiseks.

Lehel on eraldi plokid:

1. **Hero + rippmenüü 25 promtiga**  
   – PO või tiimiliige saab valida konkreetse olukorra (nt “duplikaatpiletite tuvastamine”, “OKRidega joondamine”, “quick win'ide sõelumine”)  
   – süsteem näitab selle kasutusjuhtumi jaoks optimeeritud prompti, mida saab ühe klikiga kopeerida LLM-i.

2. **Kuidas töötab**  
   – 3-sammuline selgitus: sisend → analüüs → väljund, selgelt ärifookusega.  
   – rõhk on sellel, et Co-Pilot ei tee otsuseid PO eest, vaid vähendab müra ja eeltöö mahtu.

3. **25 kasutusjuhtu**  
   – tekstiline selgitus, mis tüüpi backlog-probleeme need promtid katavad (duplikaadid, tech debt, riskid, OKRid, discovery vs delivery, jne).

4. **Tiimipaketid (Starter / Growth / Enterprise)**  
   – raamistik, kuidas teenus tooteks pakendada:
     - Starter: üks backlog + üks tiim, MVP integratsioon.
     - Growth: mitu tiimi, rollipõhised vaated, täpsem skooring.
     - Enterprise: oma LLM endpoint, SSO, turvanõuded.

5. **CTA ja kontakt**  
   – tugev üleskutse võtta üks konkreetne backlog'i lõik (nt 200–500 piletit) ja teha pilootanalüüs;  
   – kontaktinfo: `Arvutionu.ee`, `info@arvutionu.ee`, telefon `+372 5335 9094`.

## Kuidas lehte kasutada / kohandada

1. Ava projekt
   - Ava `index.html` oma koodiredaktoris (VS Code jne).
   - Stiilid tulevad `style.css` failist ja Bootswatch Vapor Bootstrap 5 CDNist.
   - Lõpuosas laaditakse `main.js`.

2. Kohanda brändingut
   - Muuda `<title>` ja meta kirjeldust, kui soovid muuta nime või positsioneeringut.
   - Uuenda hero-teksti ja CTA-sid vastavalt oma brändi toonile (nt “AI Product Ops Studio” jne).
   - Vajadusel lisa logo või pildid (praegu on leht puhas, ilma piltideta).

3. Kohanda promte
   - Ava `main.js` ja otsi muutujat `useCases`.
   - Iga objekt:
     - `label` – mida kuvatakse rippmenüüs.
     - `problem` – lühike äriline valupunkt selle kasutusjuhtumi kohta.
     - `prompt` – tegelik LLM prompt, mida kasutaja saab kopeerida.
   - Muuda või tõlgi promte, lisa oma muutujad (`{TOOTE_KIRJELDUS}`, `{OKR_LOEND}` jne) vastavalt organisatsioonile.

4. Kontrolli, et JavaScript oleks puhas
   - Fail `main.js` on kirjutatud nii, et VS Code ei peaks näitama süntaksivigu (valid JS, ei ole HTML-i sees segast koodi).
   - Kui näed vigu, kontrolli, kas:
     - pole lisatud juhuslikke tähemärke,
     - fail salvestatud UTF-8 formaadis.

5. Deployment
   - Pane kogu kaust serverisse või kasuta:
     - Netlify (drag-and-drop ZIP),
     - Vercel (Git repo),
     - GitHub Pages (static site hosting).
   - Kuna leht on wholly client-side, backend'i vaja ei ole.

## Edasised arendusideed

- Lisa tegelik kontaktivorm (backend või kolmanda osapoole form service).
- Seo leht reaalsete screeshot'idega Jira/Trello integratsioonidest ja ROI graafikutest.
- Lisa sektsioon “Kuidas me mõõdame võitu” (säästetud töötunnid, grooming'u ettevalmistuse aeg, backlog'i mahu vähenemine).
- Ehita järgmine samm: admin-UI, kust PO saab promte redigeerida ja jagada tiimiga.

Kui lehte kohandad või laiendad, hoia struktuur lihtne ja SEO-sõbralik: üks selge fookus, tugev pealkiri, nähtav CTA ja konkreetsed kasutusjuhtumid.

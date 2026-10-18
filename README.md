# Analytická geometrie

Tento repozitář obsahuje vznikající středoškolský učební text z analytické geometrie. Autorem je Ondřej Škubala.

Cílem projektu není vytvořit stručný přehled vzorců, ale souvislý učební text, ve kterém jsou jednotlivé pojmy postupně motivovány, vysvětleny, odvozeny a následně použity v příkladech. Text má být použitelný jak při výuce, tak pro samostatné studium žáka.

Tento soubor zároveň slouží jako pracovní manuál projektu. Pravidla uvedená níže jsou závazná i při generování nebo úpravách textu pomocí AI. Při pokračování práce na projektu je potřeba nejprve respektovat zde popsaný styl, značení, strukturu a aktuální stav dokumentu.

---

## 1. Základní princip psaní

Text má působit jako jedna souvislá učebnice, nikoli jako sbírka nezávislých poznámek nebo encyklopedických hesel.

Nová látka by měla pokud možno vznikat v přirozeném pořadí

**geometrická myšlenka → vysvětlení → odvození → výsledný vztah nebo definice → příklady → případné důsledky a rozšíření.**

Vzorec by se neměl objevit bez vysvětlení, odkud pochází a co geometricky znamená. Naopak není nutné uměle odvozovat vztahy, u kterých by takové odvození bylo didakticky horší než přímé vysvětlení.

Výklad má být psán především souvislými odstavci. Nadměrné členění textu na krátké podkapitoly, seznamy a jednotlivé body není žádoucí. Nové nadpisy mají vznikat pouze tehdy, pokud skutečně oddělují nový matematický problém nebo větší myšlenkový celek.

Není cílem na každém místě připomínat, že určitá vlastnost je „stejná jako v rovině, pouze přibyde souřadnice \(z\)“. U prostorové analytické geometrie je vhodnější zdůrazňovat právě ty jevy, které jsou pro prostor nové nebo geometricky podstatné.

---

## 2. Závazná pravidla formátování textu

Následující pravidla vycházejí z původního `README.md` a jsou pro projekt důležitá. Nemají být při dalších úpravách odstraněna ani ignorována.

- poznámky musí být psané jako souvislý text, bez použití nového řádku (ENTER)
- zadání příkladu musí být psané jako souvislý text, bez použití nového řádku, mimo parametrické rovnice a další víceřádkové matematické texty
- nesepisovat shrnutí

Poslední pravidlo znamená, že na konci kapitol a podkapitol nevznikají části typu `Shrnutí`, které pouze opakují již vysvětlené definice, vzorce a postupy.

To se netýká souhrnných nebo aplikačních příkladů. Ty jsou žádoucí, pokud propojují několik dříve vysvětlených myšlenek v jedné úloze.

---

## 3. Styl výkladu

Text je určen především středoškolskému studentovi. Má být matematicky správný, ale nemá zbytečně používat vysokoškolskou terminologii tam, kde pro pochopení látky není potřeba.

Preferuje se jednoduché a přesné vysvětlení před formálně složitější formulací.

Je vhodné:

- nejprve pracovat s konkrétní geometrickou představou a až následně ji zobecnit;
- u nových vztahů vysvětlit význam jednotlivých členů;
- upozornit na speciální nebo problematické případy přímo tam, kde přirozeně vznikají;
- ukazovat více způsobů řešení, pokud každý z nich přináší jiný užitečný pohled;
- využívat již zavedené pojmy a vztahy namísto jejich opakovaného zavádění;
- propojovat algebraický výpočet s geometrickým významem.

Není vhodné:

- přidávat shrnutí;
- psát dlouhé seznamy vlastností bez souvislého výkladu;
- opakovat stejnou definici na více místech;
- zavádět nový termín bez potřeby;
- měnit již zavedenou notaci pouze proto, že jiný zápis je také matematicky správný;
- zbytečně přepisovat starší text, pokud stačí lokální oprava;
- měnit styl celé kapitoly při doplnění jedné nové části.

---

## 4. Prostředí používaná v textu

Projekt používá zejména prostředí

```latex
\begin{definition}
    ...
\end{definition}
```

pro definice,

```latex
\begin{example}
    ...
\end{example}
```

pro řešené příklady a

```latex
\begin{remark}
    ...
\end{remark}
```

pro poznámky.

Při psaní nového obsahu je vhodné navazovat na způsob používání těchto prostředí v již hotových částech dokumentu.

Samotné zadání příkladu má být uvnitř prostředí `example` zapsáno jako souvislý text na jednom řádku zdrojového kódu. Výjimkou jsou například parametrické rovnice nebo jiné matematické zápisy, které přirozeně vyžadují více řádků.

Stejné pravidlo platí pro obsah prostředí `remark`: poznámka má být ve zdrojovém souboru zapsána souvisle, bez ručního rozdělování textu pomocí ENTERu.

---

## 5. Matematická notace

### Body

Body v rovině zapisujeme například

```latex
A[2;-3]
```

a v prostoru

```latex
A[2;-3;4].
```

Používáme tedy hranaté závorky a jednotlivé souřadnice oddělujeme středníkem.

### Vektory

Vektory zapisujeme pomocí `\vec{}`:

```latex
\vec{u}
```

Souřadnice vektoru zapisujeme například

```latex
\vec{u}=(2;-1;3).
```

Souřadnice vektorů jsou stejně jako souřadnice bodů oddělovány středníkem.

### Parametrické vyjádření přímky v prostoru

Preferovaný zápis je

```latex
\[
\begin{aligned}
    p: x&=x_A+t u_x,\\
       y&=y_A+t u_y,\\
       z&=z_A+t u_z; \qquad t\in\mathbb{R}.
\end{aligned}
\]
```

Písmeno přímky se uvádí pouze u první rovnice.

Analogicky se zapisuje parametrická přímka v rovině.

### Parametrické vyjádření roviny

Rovina je určena bodem a dvěma navzájem nerovnoběžnými směrovými vektory. Vektorový zápis má tvar

```latex
\[
    X=A+t\vec{u}+s\vec{v},
    \qquad t,s\in\mathbb{R}.
\]
```

### Obecná rovnice roviny

Používáme tvar

```latex
\[
    \alpha: ax+by+cz+d=0,
\]
```

kde

```latex
\[
    \vec{n}=(a;b;c)
\]
```

je normálový vektor roviny.

---

## 6. Obrázky a TikZ

Geometrické obrázky jsou součástí výkladu a nemají být pouze dekorací. Obrázek má pomáhat vysvětlit konkrétní geometrickou myšlenku.

### Obrázky v prostoru

Pro nové prostorové obrázky se nepoužívá `tdplot`. Obrázky se vytvářejí přímo v běžném prostředí

```latex
\begin{tikzpicture}
    ...
\end{tikzpicture}
```

pomocí souřadnic `(x,y,z)`.

Standardní orientace souřadnicové soustavy je:

- osa \(x\) směřuje doprava;
- osa \(y\) směřuje nahoru;
- osa \(z\) směřuje směrem k pozorovateli podle projekce používané v dokumentu.

Kladné části os se kreslí plnou čarou zakončenou šipkou. Záporné části os se kreslí čárkovaně a rovněž se šipkou.

Například:

```latex
\draw[->] (0,0,0) -- (4,0,0) node[right] {$x$};
\draw[->] (0,0,0) -- (0,4,0) node[above] {$y$};
\draw[->] (0,0,0) -- (0,0,4) node[below left] {$z$};

\draw[->, dashed] (0,0,0) -- (-2,0,0);
\draw[->, dashed] (0,0,0) -- (0,-2,0);
\draw[->, dashed] (0,0,0) -- (0,0,-2);
```

Pro vektory je v `preamble.tex` definován styl

```latex
\tikzset{
    vector/.style = {-{Stealth[length=2.5mm]}, very thick}
}
```

a při kreslení vektoru se proto používá například

```latex
\draw[vector] (A) -- (B);
```

Nové obrázky by měly vizuálně navazovat na existující obrázky dokumentu.

---

## 7. Labely a odkazy

Objekty, ke kterým se bude později odkazovat, mají mít `\label`.

Používané prefixy jsou například:

```text
sec:
subsec:
subsubsec:
def:
eq:
exa:
fig:
rem:
```

Před vytvořením nového labelu je potřeba ověřit, zda již stejný label v projektu neexistuje.

Jeden matematický objekt nebo příklad nesmí být zbytečně duplikován na několika místech dokumentu pouze s totožným obsahem.

Při přesunu nebo odstranění části textu je nutné zkontrolovat také reference pomocí `\ref`, `\eqref` apod.

V současných souborech se historicky vyskytují různé způsoby pojmenovávání labelů. Jejich globální sjednocení není důvodem k přepisování již fungujícího textu. U nových labelů je však vhodné používat srozumitelné a jednoznačné názvy.

---

## 8. Struktura projektu

Hlavní dokument je

```text
main.tex
```

Jeho základní struktura je:

```text
main.tex
├── preamble.tex
├── předmluva.tex
├── úvod.tex
├── kartézskáSoustavaPrvků.tex
├── body.tex
├── vektory.tex
├── AnalytickáGeometrieVRovině.tex
└── AnalytickáGeometrieVProstoru.tex
```

### Analytická geometrie v rovině

Soubor

```text
AnalytickáGeometrieVRovině.tex
```

postupně načítá:

```text
parametrickaPrimka.tex
obecnaPrimka.tex
smernicovaPrimka.tex
prevodyTvaruPrimek.tex
polohoveVztahyPrimek.tex
vzdalenostBoduOdPrimky.tex
odchylkaPrimek.tex
```

Soubor

```text
polohoveVztahyPrimek.tex
```

dále využívá:

```text
parametrickaPrimkaVzajemnaPoloha.tex
obecnaPrimkaVzajemnaPoloha.tex
smernicovaPrimkaVzajemnaPoloha.tex
vzajemnaPolohaRuzneTvary.tex
```

### Analytická geometrie v prostoru

Soubor

```text
AnalytickáGeometrieVProstoru.tex
```

postupně načítá:

```text
primkyVProstoru.tex
parametrickaPrimkaProstor.tex
parametrickaPrimkaProstorVzajemnaPoloha.tex
odchylkaPrimekProstor.tex
vzdalenostBoduOdPrimkyProstor.tex
vzdalenostPrimkyOdPrimkyProstor.tex
obecnaPrimkaProstor.tex
rovinyVProstoru.tex
```

Soubor

```text
rovinyVProstoru.tex
```

nyní načítá:

```text
parametrickaRovina.tex
obecnaRovina.tex
```

Další části věnované rovinám budou do této struktury postupně doplněny.

---

## 9. Aktuální stav učebnice

### Základní části

Zpracováno je:

- úvod do analytické geometrie;
- kartézská soustava souřadnic;
- body v rovině a prostoru;
- vzdálenost dvou bodů;
- střed úsečky;
- vektory v rovině a prostoru;
- operace s vektory;
- lineární kombinace;
- skalární součin;
- vektorový součin;
- smíšený součin.

### Analytická geometrie v rovině

Zpracováno je zejména:

- parametrické vyjádření přímky;
- obecná rovnice přímky;
- směrnicový tvar přímky;
- převody mezi jednotlivými tvary rovnic přímky;
- vzájemná poloha dvou přímek;
- vzdálenost bodu od přímky;
- vzdálenost rovnoběžných přímek;
- body stejně vzdálené od dvou přímek;
- odchylka dvou přímek;
- související aplikační úlohy.

Analytická geometrie kuželoseček zatím není součástí této části.

### Analytická geometrie v prostoru

Zpracováno je:

- přímka v prostoru;
- parametrické vyjádření přímky;
- vzájemná poloha dvou přímek;
- různoběžné, rovnoběžné, totožné a mimoběžné přímky;
- odchylka dvou přímek;
- vzdálenost bodu od přímky;
- vzdálenost dvou rovnoběžných přímek;
- vzdálenost mimoběžných přímek;
- přímka jako průnik dvou rovin – zatím pouze úvodní část;
- rovina v prostoru;
- parametrické vyjádření roviny;
- obecná rovnice roviny;
- normálový vektor roviny;
- převody mezi parametrickým a obecným vyjádřením roviny;
- různé způsoby určení roviny.

---

## 10. Aktuální pokračování práce

Po dokončení parametrického a obecného vyjádření roviny následuje rozpracování vzájemných vztahů přímek a rovin.

Nejbližší plánované části jsou v tomto pořadí:

### P1 – dokončení analytické geometrie v prostoru

1. vzájemná poloha přímky a roviny;
2. vzájemná poloha dvou rovin;
3. návrat k přímce jako průniku dvou rovin;
4. odchylka přímky a roviny;
5. odchylka dvou rovin;
6. vzdálenost bodu od roviny;
7. vzdálenost přímky od roviny;
8. vzdálenost dvou rovin;
9. případně kolmé průměty bodů, přímek a dalších objektů.

### P2 – další analytická geometrie v rovině

Podle výsledného rozsahu učebnice bude vhodné doplnit zejména:

- kružnici;
- vzájemnou polohu přímky a kružnice;
- tečnu ke kružnici;
- elipsu;
- parabolu;
- hyperbolu.

Rozsah kuželoseček bude ještě potřeba rozhodnout.

### P3 – sjednocení starších částí

Po dokončení hlavního matematického obsahu bude vhodné projít starší části dokumentu, zejména `body.tex` a `vektory.tex`, a sjednotit jejich sazbu, notaci a styl s novějšími kapitolami.

Nemá jít o bezdůvodný kompletní přepis, ale o cílenou revizi.

### P4 – technický úklid projektu

Později bude vhodné prověřit:

- zda je ještě potřeba balíček `tikz-3dplot`;
- zda je ještě potřeba balíček `pgfplots`;
- strukturu souborů v kořenovém adresáři;
- vhodnost názvů některých souborů;
- používání diakritiky v názvech souborů;
- zda má být `main.pdf` dlouhodobě verzován v Gitu;
- případné automatické sestavení dokumentu pomocí GitHub Actions;
- licenční podmínky projektu.

---

## 11. Důležité vztahy již zavedené v prostoru

Pro dvě přímky se směrovými vektory \(\vec{u}\) a \(\vec{v}\) je odchylka určena vztahem

\[
    \cos\varphi
    =
    \frac{|\vec{u}\cdot\vec{v}|}
    {|\vec{u}||\vec{v}|},
    \qquad
    \varphi\in\langle0^\circ;90^\circ\rangle.
\]

Vzdálenost bodu \(P\) od přímky určené bodem \(A\) a směrovým vektorem \(\vec{u}\) je

\[
    d(P,p)
    =
    \frac{|\overrightarrow{AP}\times\vec{u}|}
    {|\vec{u}|}.
\]

Pro dvě rovnoběžné přímky je

\[
    d(p,q)
    =
    \frac{|\overrightarrow{AB}\times\vec{u}|}
    {|\vec{u}|}.
\]

Pro dvě mimoběžné přímky je

\[
    d(p,q)
    =
    \frac{|\overrightarrow{AB}\cdot(\vec{u}\times\vec{v})|}
    {|\vec{u}\times\vec{v}|}.
\]

Tyto vztahy již byly v dokumentu zavedeny a při dalším výkladu je možné je používat bez jejich opětovného odvozování, pokud nové téma nevyžaduje připomenutí jejich geometrického významu.

---

## 12. Pravidla pro úpravy pomocí AI

Při práci s tímto repozitářem má AI nejprve přečíst tento `README.md` a relevantní zdrojové soubory.

Před navržením nové části je nutné zjistit:

1. kam má nová část ve struktuře dokumentu patřit;
2. co již bylo v předchozích kapitolách definováno;
3. jaká notace se v dané části používá;
4. zda již podobný příklad, definice nebo obrázek v projektu neexistuje.

AI nemá při lokální úpravě svévolně měnit styl okolního textu.

Pokud uživatel žádá opravu konkrétní části, preferuje se co nejmenší zásah, který opraví matematický, jazykový nebo sazečský problém.

Pokud uživatel žádá novou kapitolu nebo větší část výkladu, má nový text co nejvíce navazovat na styl nejnovějších částí projektu.

Není žádoucí automaticky:

- vytvářet závěrečná shrnutí;
- přejmenovávat existující labely;
- měnit zavedené značení;
- nahrazovat souvislý výklad seznamem bodů;
- přidávat nové balíčky do `preamble.tex`, pokud nejsou skutečně potřeba;
- používat jiný způsob kreslení prostorových obrázků než ten používaný v projektu;
- duplikovat již existující definice;
- přesouvat látku mezi soubory bez jasného didaktického důvodu.

Pokud se objeví rozpor mezi obecnými zvyklostmi LaTeXu a pravidly tohoto projektu, mají přednost pravidla projektu uvedená v tomto README.

---

## 13. Kompilace

Dokument se sestavuje z `main.tex`.

Doporučený příkaz je:

```bash
latexmk -pdf -interaction=nonstopmode -file-line-error main.tex
```

Vyčištění pomocných souborů:

```bash
latexmk -c
```

Kontrola závažných problémů v logu:

```bash
grep -nEi "undefined|multiply defined|error|fatal" main.log
```

Kontrola warningů:

```bash
grep -nE "LaTeX Warning|Package .* Warning" main.log
```

Kontrola přetékajících řádků:

```bash
grep -n "Overfull" main.log
```

Pomocné LaTeXové soubory jsou uvedeny v `.gitignore` a nemají být commitovány.

---

## 14. Git workflow

Před větším blokem práce je vhodné mít čistý pracovní strom.

Kontrola stavu:

```bash
git status
```

Po dokončení logického celku:

```bash
git add .
git commit -m "Popis provedene zmeny"
git push
```

Jeden commit by měl pokud možno představovat jeden smysluplný blok práce.

Při konfliktu v generovaných LaTeXových souborech jako `.aux`, `.log`, `.toc`, `.fls`, `.fdb_latexmk` nebo `.synctex.gz` se tyto soubory nemají verzovat. Patří do `.gitignore`.

---

## 15. Stav kontroly projektu

Před zahájením dalšího rozšiřování byla provedena kontrola současného obsahu projektu.

Bylo opraveno zejména:

- duplicitní uvedení stejného příkladu se středovou souměrností přímky;
- duplicitní zavedení normálového vektoru roviny;
- odstranění závěrečného shrnutí obecné rovnice roviny;
- chybný obrázek vzdálenosti bodů v `body.tex`;
- některé LaTeXové warningy a přetékající sazba;
- kontrola duplicitních labelů a neexistujících referencí.

Po této kontrole dokument neobsahoval nevyřešené reference ani duplicitně definované labely.

Další obsah má navazovat na tento stav.

---

## 16. Aktuální místo práce

Aktuálně je dokončena obecná rovnice roviny.

Další část:
**vzájemná poloha přímky a roviny v prostoru**

Po ní následuje:
**vzájemná poloha dvou rovin**.


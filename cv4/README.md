Ve chvíli, kdy začneme pracovat na seriózních projektech s větším množstvím kódu, objeví se starosti, které s programováním až tolik nesouvisí. Budeme chtít:

* zajistit, aby se nám projekt nerozpadl pod rukama tím, jak přibývá stále více a více kódu,
* zálohovat náš kód, aby se nestalo, že nám klekne počítač a příjdeme třeba o rok práce,
* spravovat různé verze projektu, abychom mohli zákazníkovi předat funkčí produkt a zároveň jej dále vylepšovat,
* organizovat spolupráci více lidí na jednom projektu tak, aby si navzájem nelezli do zelí.

Se všemi těmito výzvami nám pomůže takzvaný verzovací systém. Takových systémů je k dispozici vícero, ale zdaleka nejpopulárnější je systém jménem Git.

## Systém Git
Verzovací systém Git je jeden z nejpopulárnější systémů pro správu verzí, protože je velmi dobře promyšlený. Díky tomu se dá použít jak na malé projekty, tak na rozsáhlý software, na kterém pracují desítky lidí zároveň.

Git je velmi flexibilní a dá se použít mnoha různými způsoby. Existuje vícero různých metodik, jak s Gitem pracovat, které se liší podle typu a velikosti projektu. Základní princip je však víceméně pořád stejný.

### Repozitář
Základním pojmem Gitu je takzvaný repozitář, ve kterém se nachází všechny soubory, které tvoří váš projekt. Většinou bývá na nějakém serveru, na který mají přistup všichni vývojáři projektu a mohou do něj přispívat svým kódem. Takový server může běžet například v rámci nějaké firmy a mají do něj přístup pouze vývojáři z této firmy. Pokud na projektu pracujete sami, můžete si pro něj vytvořit repozitář na některé hostovací službě, jako GitHub, GitLab, Bitbucket a další.

## Základní pojmy
Představte si, že jste právě dokončili určitou ucelenou věc na vašem projektu. Například jste opravili nějakou chybu nebo přidali nějakou funkčnost. V tuto chvíli si chcete udělat jakýsi snímek toho, v jakém stavu se projekt právě teď nachází, abyste se případně do tohoto stavu mohli kdykoliv vrátit. Je to podobné, jako když hrajete počítačovou hru a chcete si ji v nějakém místě uložit, abyste se pak na toto místo mohli vrátit, kdyby vaši postavu později ve hře potkal neblahý osud.

Náš snímek si tedy pamatuje stav celého projektu v určitém čase. V teorii verzování kódu se takovému snímku říká revize. Git však místo termínu revize používá slovo commit, které nemá žádný český překlad.

Ke každému commitu se navíc přidává zpráva o tom, co se v něm dokončilo za práci. Po čase si pak můžeme prohlédnout historii commitů v projektu a přehledně vidět, co se přesně dělo.

![gitukazka1](https://github.com/anetryg/pocitacova_grafika_2024/blob/main/cv4/images/commits.svg)


Všimněte si, že každý commit obsahuje zprávu a takzvaný digitální otisk. Tento otisk jednoznačně identifikuje každý commit, abychom se kdykoliv mohli k libovolnému commitu vrátit.

## Důležité příkazy
* clone : Vytvoří lokální kopii vzdáleného repozitáře.

* add : Přidá změny do oblasti připravených změn.

* status : Zobrazí všechny rozpracované změny proti poslednímu commitu.

* restore --staged : Vyprázdní oblast připravených změn (experimentální!)

* reset : Nebezpečnější alternativa příkazu restore.

* commit : Vytvoří novou revizi.

* push : Nahraje všechny nově vytvořené commity do vzdáleného repozitáře.

* log : Zobrazí historii commitů. Pokud se úplně dole na konci historie zobrazí dvojtečka :, znamená to, že historie je delší a můžete v ní listovat. Výpis logu ukončíte (a vrátíte se do terminálu) stisknutím klávesy q.

## Časté příkazy
Zahrnout do stage všechny změny z aktuálního adresáře

* $ git add .

Zobrazit lokální stav (ukáže například, co je a není na stage)

* $ git status

Vytvořit commit ze stage

* $ git commit -m "Zpráva"

Nahrát nové commity na server (GitHub, GitLab, Bitbucket, …)

* $ git push

## Větve
Větve jsou oddělené cesty v rámci repozitáře, které umožňují vývojářům pracovat na různých částech projektu nezávisle. Hlavní větev (nejčastěji main nebo master) obsahuje stabilní verze kódu, zatímco větve odvozené od ní mohou obsahovat experimentální nebo vývojové změny. Při dokončení práce na větvi se obvykle sloučí zpět do hlavní větve pomocí operace známé jako "merge" nebo "pull request". Větve umožňují izolovat změny, snadno spolupracovat s ostatními vývojáři a zajistit stabilitu a bezpečnost kódu.

![gitukazka2](https://github.com/anetryg/pocitacova_grafika_2024/blob/main/cv4/images/git-branches-merge.png)

## Pull request 
Pull request (často označovaný jako "PR") je žádost o sloučení změn provedených ve větvi do hlavní větve. Při vytváření pull requestu mohou ostatní členové týmu prohlížet změny, poskytovat zpětnou vazbu a provádět kódové revize. Tento proces pomáhá zajistit kvalitu kódu a minimalizovat chyby. Konflikty vznikají, když se dvě větve snaží provést změny ve stejném souboru nebo na stejných řádcích kódu. Je důležité tyto konflikty rozřešit manuálně a poté provést sloučení změn. Většina verzovacích systémů poskytuje nástroje pro řešení konfliktů.

## GitHub
Git je nástroj (program), který můžete používat u sebe a nepotřebujete žádného externího posktovatele služeb. Nicméně největší síla Gitu je v tom, že můžete kód snadno sdílet s dalšími vývojáři nebo doslova s kýmkoli na světě. Aby bylo sdílení s dalšími lidmi snadné, je vhodné kopii vašeho repozitáře vystavit někde na internetu, aby byl k dispozici kdykoli – bez ohledu na to, zda zrovna máte zapnutý počítač a jste připojeni k internetu. Postupem času vzniklo mnoho poskytovatelů služeb, kteří vám umožní takto zveřejnit Git repozitář – a často k tomu přidávají další služby. Největším takovým poskytovatelem je GitHub (před několika lety ho koupil Microsoft). GitHub vám umožňuje zdarma hostovat soukromé i veřejné repozitáře.

Občas se plete, co je Git a co GitHub - je dobré si pamatovat, že to není jedno a totéž – GitHub je jeden z poskytovatelů služeb postavených nad Gitem.

### Soubor README.md
Pokud máte v repozitáři v kořenové složce soubor README.md, GitHub bude jeho obsah zobrazovat na úvodní stránce repozitáře na webu. Hodí se tedy do tohoto souboru popsat, co v repozitáři je, k čemu to slouží, jak se daný program či web používá.

![gitukazka2](https://github.com/anetryg/pocitacova_grafika_2024/blob/main/cv4/images/readme.png)

## GitHub Pages
Pokud máte v repozitáři nahrané soubory pro webové stránky (index.html, styly, skripty, obrázky…), GitHub z nich umí udělat veřejný web s vlastní adresou vhodnou pro běžného uživatele internetu, návštěvníka webu. Službu na GitHubu aktivujete z detailu repozitáře v záložce Settings v části GitHub Pages. Ve vybírátku Source stačí vybrat hlavní větev (měla by to být větev main, občas se ještě podaří vytvořit repozitář, který má jako hlavní větev master) a uložit. Po uložení se zobrazí modrý pruh s adresou, kde web běží.

Je šikovné přidat odkaz s touto webovou adresou přímo do GitHub repozitáře. Na úvodní stránce repozitáře je vpravo panel About. Stačí kliknout na ozubené kolečko vpravo od něj a v konfiguračním panelu zaškrtnout volbu Use your GitHub Pages website. V panelu About se pak objeví klikatelný odkaz na běžící web. Mimochodem, ve stejném konfiguračním panelu můžete změnit i popis projektu Description.

## Conventional Commits
Conventional Commits jsou konvence pro strukturované označování commitů v repozitářích verzovacího systému Git. Tato konvence přináší jasně definované standardy pro psaní commit zpráv, což usnadňuje čtení a pochopení historie změn projektu. Zde jsou klíčové body a principy spojené s Conventional Commits:

1. Jednotný formát:
* Commit message má jednotný formát, který se skládá ze tří hlavních částí: typ, oblast a popis.
* Typ označuje druh změny (například "feat" pro novou funkci, "fix" pro opravu chyby, "docs" pro změny v dokumentaci).
* Oblast určuje oblast kódu, která byla změněna (například "login", "database", "UI").
* Popis poskytuje stručný popis provedených změn.

2. Jednoduché rozlišení:
* Konvence umožňuje snadné rozlišení mezi různými typy změn na základě jejich označení.
* Tím, že se v commit message jasně identifikují typy změn, je snazší filtrovat a vyhledávat commity.

3. Automatizace generování changelogů:
* Díky strukturovanému formátu Conventional Commits je možné automatizovat generování changelogů.

4. Podpora pro automatizované práce:
* Conventional Commits jsou často používány v kombinaci s dalšími nástroji a službami, jako jsou CI a CD.
* Automatizované procesy mohou na základě typu commitů spouštět specifické akce, jako je spouštění testů, nasazení do produkce nebo aktualizace dokumentace.


### Klíčová slova:

```
feat: Nová funkce
fix: Oprava chyby
docs: Změny v dokumentaci
style: Změny v kódu, které neovlivňují běh aplikace (např. formátování, pravopis)
refactor: Refaktorování kódu bez změny chování
perf: Zlepšení výkonu
test: Přidání nebo úprava testů
build: Změny týkající se systému sestavení nebo externích závislostí
ci: Změny v konfiguraci nebo skriptech pro integraci nebo nasazení (CI/CD)
chore: Ostatní změny, které nejsou zahrnuty výše
revert: Vrácení předchozí změny
```

Tyto klíčová slova jsou používána jako prefix v commit zprávě, aby jasně identifikovala typ změny provedené v rámci commitu.

![gitukazka1](https://github.com/anetryg/pocitacova_grafika_2024/blob/main/cv4/images/gitexplain.png)


# React
React je open-source javascriptová knihovna pro tvorbu uživatelského rozhraní (anglicky UI jako User Interface). Vyvinula ji společnost Meta. Podobných reaktivních frameworků existuje vícero. Mezi nejznámější vedle Reactu patří Angular a Vue, ale svoji popularitu si získávají i další, například Svelte nebo Solid. V současné době je však React stále s přehledem nejpopulárnější a také nejžádanější na trhu práce.

Manuální obsluha formulářů v JavaScriptu, jejich validace nebo třeba obnovování různých částí stránky novými daty, nejsou úplně triviální úlohy. Právě s tímto vším nám React pomůže a ve výsledku budeme mít aplikaci vytvořenou rychleji a kvalitněji. Důležité je také rozdělení aplikace do komunikujících komponent, čímž se zjednoduší.

Základní stavební kameny React aplikací tvoří tzv. komponenty (components). To jsou různé znovupoužitelné HTML elementy se zapouzdřenou funkcionalitou, jejichž skládáním vzniká komplexní UI aplikace. Komponentou může být např. přihlašovací formulář nebo hvězdičkové hodnocení produktu. Rozdělením aplikace na menší celky je aplikace přehlednější a vývoj jednodušší.

React komponenty pak mají své:
 * vstupní vlastnosti (props) a
 * svůj vnitřní stav (state).


## React komponenty
React dokáže automaticky reagovat na změnu stavů a překreslovat aplikaci jen kdy a kde je to potřeba. Způsob práce v React je tzv. deklarativní. To znamená, že definujeme stavy a prvky rozhraní a neřešíme např. jak se má překreslovat při změně. Právě to je jedním z důvodů, proč je tato knihovna tak populární.

Komponenty lze v React vytvářet buď jako funkce nebo jako třídy (class). Pro tvorbu UI má funkcionální způsob hned několik výhod a proto převládá nad objektovým.

## Založení nového projektu
V praxi byl dlouho standardem pro zakládání nových projektů v Reactu create-react-app, ale dnes už to přestává platit. Již existují modernější a vhodnější nástroje. Často má každá firma či vývojář vytvořené vlastní workflow, jak nový projekt založit a co je jeho součástí. Protože create-react-app se snažil být výchozím a univerzálním startovním bodem pro obrovské množství různých projektů, obsahuje velké množství balíčků, které zabírají hodně místa a založení nového projektu může i dlouho trvat.

## JSX
JSX (JavaScript XML) je způsob, jakým se v Reactu vytváří obsah stránky. Pomocí JSX můžeme s HTML obsahem pracovat jako s jakoukoliv jinou hodnotou a můžeme ho například vložit do proměnné, předat jako hodnotu do funkce nebo je z funkcí vracet, ukládat je do polí, a podobě. JSX nebalíme do úvozovek, nejedná se o textový řetězec.

Přestože JSX vypadá jako HTML, nejedná se o čisté HTML, ale jsou zde drobné rozdíly. Např. atribut class musíme v JSX nahradit atributem className.

``` javascript
const obsah = <h1 className="title">Titulek stránky</h1>;
```

## Základ aplikace v Reactu
Abychom mohli JSX obsah vložit na stránku, musíme v kódu založit React aplikaci. To se dělá pomocí metody createRoot objektu ReactDOM, který naimportujeme z balíčku react-dom/client. Do funkce createRoot předáme DOM element, do kterého se bude naše aplikace v Reactu vykreslovat. To obvykle bývá prázdný div element s id nastaveným na root.

Funkce vrátí objekt, na kterém zavoláme metodu render a předáme do ní JSX obsah naší aplikace, který se má vykreslit na stránku.

Minimální podoba React aplikace pak může vypadat například takto.

``` javascript
import React from 'react'
import ReactDOM from 'react-dom/client'

const appRoot = ReactDOM.createRoot(document.geElementById('root'));
appRoot.render(<h1 className="title">Moje stránka</h1>);
```

## Fragment
Metoda render jako parametr akceptuje pouze jeden JSX element. Pokud bychom chtěli na stránce vykreslit např. nadpis a odstavec, nebude náš příklad fungovat.

``` javascript
appRoot.render(
  <h1 className="title">Moje stránka</h1>
  <p>Textový obsah stránky</p>
);
```

Můžeme samozřejmě vše zabalit do divu nebo jiného prvku, ale pak máme v aplikaci prvky, které tam nutně nepotřebujeme a mohou nám třeba i zoůsobit problémy se stylováním.

React nabízí speciální element, kterému říká fragment. Vypadá jako prázdná HTML značka, do které můžeme zabalit další elementy, ale která se ve výsledné stránce neobjeví.

``` javascript
appRoot.render(
  <>
    <h1 className="title">Moje stránka</h1>
    <p>Textový obsah stránky</p>
  </>
);
```

## Komponenty a props
Každá aplikace v Reactu se skládá z komponent. Komponenty jsou dílky stavebnice, ze kterých naši aplikace postupně skládáme.

Komponenta v Reactu je funkce, která na svém výstupu vrací JSX. Toto JSX se na stránce vykreslí v místě, kde naši komponentu použijeme.

``` javascript
const App = () => {
  return (
    <>
      <h1 className="title">Moje stránka</h1>
      <p>Textový obsah stránky</p>
    </>
  );
};
```

Název funkce, která tvoří komponentu, musí začínat velkým písmenem. Takto vytvořenou komponentu pak můžeme používat jako běžnou HTML značku.

``` javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import './index.css'

const App = () => {
  return (
    <>
      <h1 className="title">Moje stránka</h1>
      <p>Textový obsah stránky</p>
    </>
  );
};

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);
```

Komponenty jsou mnohem užitečnější, když do nich můžeme předat data, se kterými komponenta může pracovat. V terminologii Reactu se říká, že do komponenty předáváme props (zkráceno z properties).

V místě, kde komponentu používáme, přidáme props jako atributy HTML značky. Do komponenty se props dostanou jako jeden objekt, kde každá prop je jedna vlastnost tohoto objektu. Pro jednodušší používání props uvnitř komponenty můžeme objekt destrukturovat do proměnných.

``` javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import './index.css'

const ShoppingItem = (props) => {
  const { name, amount } = props;

  return (
    <div className="item">
      <span className="item__name">{name}</span>
      <span className="item__amount">{amount}</span>
    </div>
  );
};

const App = () => {
  return (
    <>
      <header>
        <h1>Nákupní seznam</h1>
      </header>
      <main className="shopping-list">
        <ShoppingItem name="Mléko" amount="1 l" />
        <ShoppingItem name="Máslo" amount="250 g" />
        <ShoppingItem name="Rohlíky" amount="8 ks" />
      </main>
    </>
  );
};

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
);

```

## Události
Události tvoří základ pro jakoukoliv interaktivitu v aplikaci. Pomocí událostí reagujeme na uživatelský vstup a případně i další události, které mohou v prohlížeči nastat.

``` javascript
const App = () => {
  const handleClick = () => {
    alert('ahoj');
  };

  return (
    <button className="greet" onClick={handleClick}>
      Pozdrav
    </button>
  );
};
```

Reagujeme-li na událost, kde potřebujeme o události další informace, můžeme v našem posluchači události přijmout tzv. event object. Například při reakci na změnu textového políčka se můžeme v posluchači zeptat na jeho aktuální hodnotu.

``` javascript
const App = () => {
  const handleChange = (event) => {
    console.log(event.target.value);
  };

  return <input type="text" onChange={handleChange} />;
};
```

## Stav
Stav (state) je základem každé interaktivní komponenty. Stav si můžeme představit jako vlastnosti předmětu v reálném světě, které se mohou během životnosti věci měnit. Například u auta se průběžně mění stav nádrže, rychlost, počet najetých kilometrů, apod. Pokud naše komponenta představuje například položku v úkolníčku, může mít stav splněno/nesplněno.

Pro vytvoření stavu v Reactu používáme funkci useState. Jako parametr do ní předáme vychozí hodnotu stavu. Funkce vrátí pole, které obsahuje dva prvky - první je samotný stav, druhá je funkce, pomocí které můžeme stav měnit.

``` javascript
import React, { useState } from 'react';

const Auto = () => {
  const [tankLevel, setTankLevel] = useState('full');

  return <div className="auto">Tank level: {tankLevel}</div>;
};
```

Když chceme hodnotu stavu změnit, použijeme funkci, kterou jsme dostali z useState pro tento účel.

``` javascript
setTankLevel('empty');
```

## Efekty
Tzv. efekty používáme ve chvíli, kdy potřebujeme zareagovat na určité situace, které nastávají během vykreslování komponenty. Například chceme určitý kód spustit ve chvíli, když se komponenta poprvé objeví na stránce.

Efekty jsou velmi podobné událostem. Když uvnitř komponenty něco nastane, chceme spustit funkci, která na to zareaguje. K vytvoření efektu používáme funkci useEfect.

``` javascript
const App = () => {
  useEffect(() => {
    console.log('aplikace se spustila');
  }, []);

  return (
    <>
      <h1>Aplikace</h1>
      <p>Textový obsah naší super appky.</p>
    </>
  );
};
```

Funkce useEffect má dva parametry. Prvním je funkce, která se má zavolat a druhý parametr říká, za jakých okolností se má naše funkce volat.

* Když druhý parametr chybí, funkce se spustí při každém překreslení komponenty.
* Prázdné pole [] znamená, že se efekt spustí pouze ve chvíli, kdy se komponenta poprvé objeví na stránce.
* Připadně do pole můžeme napsat název stavové proměnné a efekt se spustí pokaždé, když dojde ke změně tohoto stavu.
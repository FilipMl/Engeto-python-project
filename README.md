# Engeto-python-project

Jedná se o druhý projekt v rámci kurzu datové analýzy. Projekt je vytvořen v prostředí Google Colab, který je online alternativou k jupyter notebook. V projektu jsem využil knihovny Pandas, Sql-alchemy, scipy a matplotlib.pylab. Veškerý výstupy prjektu se nachází v souboru **ENGETO_python_projekt_v3.ipynb**.


## ***Zadání:***

V Edinburghu, stejně jako v dalších městech, funguje systém "bike sharing" - ve městě jsou stanice s koly, člověk si může nějaké půjčit a potom ho vrátit v nějaké další stanici. Problém je, že v některých stanicích se kola pravidelně hromadí a jinde naopak chybí. Cílem projektu je systém zefektivnit.

##**Provést standardní deskriptivní statistiku dat**

## **Zjistit následující informace:**

###  1. identifikujte aktivní a neaktivní stanice


***Celkový počet stanic: 200***

Pří posuzování aktivity a neaktivity stanic jsem si zvolil metriku při které je neaktivní stanice ta, která má ve sledovaném období průměrně méně než 5 výpujček/vrácení v průběhu jednoho týdne. Ná základě této metriky je stav aktivních a neaktiních stanic následovný:

***Neaktivních stanic: 57***

***Aktivních stanic: 143***


###  2. identifikujte nejfrekventovanější stanice


Nejfrekventovanější stanice pro výpujčku je stanice id:265 Meadows East s 17390 záznamy.

Nejfrekventovanější cílová stanice je id:1728 Portobello - Kings Road s 16656 záznamy.


###  3. identifikujte stanice, na kterých se kola hromadí a stanice, kde potenciálně chybí


***Nejvíce se hromadí ve stanici s id: 1728***

***Nejvíce scházejí ve stanici s id: 248***

Jako problémové stanice hodnotím ty u kterých je průměrný týdenní rozdíl více než pět kol.

Dle tohoto pravidla existuje ***16 stanic*** u kterých v průměru za týden přibude více než 5 kol. U čťyř stanic se rozdíl dokonce v průměru přibývá více než 20 kol.

Dle tohoto pravidla existuje ***20 stanic*** u kterých v průměru za týden ubyde více než 5 kol. U čťyř stanic se rozdíl dokonce v průměru ubývá více než 20 kol.

Průměrný týdenní přebytek kol u stanic, kde přebytky pravidělně vznikají jsou tři kola. Průměrný tydenní nedostatek kol u stanic, kde nedostatky pravidělně vznikají jsou čtyři kola.

###  4. spočítejte vzdálenosti mezi jednotlivými stanicemi

viz. dokument

###  5. jak dlouho trvá jedna výpůjčka? Najděte odlehlé hodnoty, zobrazte histogram

***Jedna výpujčka trvá v průměru 32 minut.***

Z hodinového logaritmického histogramu je zrějmý pokles v počtu zápujček trvající déle než 1 hodinu. To indikuje snahu uživatelů vrátit kolo pokud možno do 1 hodiny od zápujčky.

Vyobrazení dat na histogramu indikuje, že se v datech nachází několoik odlehlých hodnot. Aby histogram zobrazoval data neodlehlá, tak jsem je vyfiltroval na data splňující podmínku z-score > 4.

Z histogramu dále vyplívá, že při z-score > 4 patří mezi odlehlé hodnoty zápujčky trvající déle než 7h, kterých se v datové sadě nachází 317. Pří výčtu těchto odlehlých hodnot vidímě, že se v datové sadě nachází i výpujčky trvající několik dní

## **Analýzovat poptávku:**

###  1. zobrazte vývoj poptávky po půjčování kol v čase

Z grafu je zřejmé, že poptávka po kolech výrazně roste v letních měsících květen, červen, červenec a srpen. Rok 2021 však tvoří výjímku, kdy tento skokový růst nebyl tyto měsíce zaznamenán.

Z grafu je zřejmé, že poptávka po kolech je nejvyšší v odpoledních hodinách od 12:00 do 17:00.

###  2. identifikujte příčiny výkyvů poptávky

viz. 1. bod

###  3. zjistěte vliv počasí na poptávku po kolech (údaje o počasí v Edinburghu jsou v tabulce edinburgh_weather)

Při rostoucí teplotě roste poptávka. Při rostoucí rychlosti větru poptávka klesá. Déšť nemá výrazný vliv na výpujčku kol.

###  4. půjčují si lidé kola více o víkendu než během pracovního týdne?

Na základě výstupu je zřejmé, že lidé častěji poptávají kola o víkendu (v průměru 472 výpujček) než v týdnu (průměrně 412 výpujček).

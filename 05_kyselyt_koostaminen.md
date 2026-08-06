# Kyselyt - koostaminen funktiolla
>- AGGREGAATTI: SUM, COUNT, AVG, MAX,...
>- SKALAARI: ROUND(),...

Jatkamme tiedon käsittelyyn ja sen esittämiseen tässä osassa.
Kyselyillä saamme haettua tietoa, mutta kun haluamme yhdistää numeerista tietoa (kuten tuotehintojen yhdistäminen 

Jos aiemmin pystyimme etsimään asiakkaat, joiden toimipaikka sijaitsi tietyssä kaupungissa, pystymme nyt sen lisäksi etsimään myös 

> Esimerkki 01: kahden ehdon yhdistäminen AND -operaattorilla
> 

## Aggregaatti eli koostefunktiot
Nämä funktiot yhdistävät tietoa useasta rivistä ja palauttavat vain yhden tiedon. Tämä tieto voi olla joko yhdistetty (kuten SUM) tai yksi rivi (kuten MIN).

| FUNKTIO | MERKITYS | ESIMERKKI | 
|---|---|---|
|COUNT()| Laskee kaikki rivit | COUNT(*) |
|SUM()| Laskee kaikkien rivien yhden sarakkeen arvot summaksi | SUM(hinta)|
|AVG()| Laskee kaikkien rivien yhden sarakkeen arvojen keskiarvon| AVG(hinta)|
|MIN()| Vertailee kaikkien rivien yhden sarakkeen arvoista pienimmän | MIN(hinta)|
|MAX()| Vertailee kaikkien rivien yhden sarakkeen arvoista suurimman | MAX(hinta)|

> Esimerkki 02: kahden vaihtoehtoisen ehdon tutkiminen OR -operaattorilla
> 

## Skalaari eli mittafunktiot
Nämä funktiot käsittelevät yhtä tietoa.

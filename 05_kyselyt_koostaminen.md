# Kyselyt - koostaminen funktiolla
>- AGGREGAATTI-funktiot: SUM, COUNT, AVG, MAX,...
>- SKALAARI-funktiot: ROUND(),...

Jatkamme syvemmälle tiedon käsittelyyn ja sen esittämiseen tässä osassa.
Kyselyillä saamme haettua tietoa, mutta kun haluamme yhdistää numeerista tietoa (kuten valittujen tuotteiden hintojen kokoaminen kokonaishinnaksi) tarvitaan funktioita. SQL-kielessä on valmiina funktioita, jotka voidaan jakaa kahteen ryhmään: **aggregaatti eli koostefunktiot**, jotka käsittelevät useita rivejä tietoa ja koostavat niistä yhden arvon ja **skalaari- eli mittafunktioiksi**, jotka käsittelevät vain yhden arvon ja palauttavat sen käsiteltynä.

Jos aiemmin pystyimme etsimään asiakkaat, joiden toimipaikka sijaitsi tietyssä kaupungissa, pystymme nyt sen lisäksi etsimään myös 

> Esimerkki 01: kokonaishinnan laskeminen
> Asiakas on valinnut kolme tuotetta
> 

> Esimerkki 02: haluamme tietää mikä on kallein tuote
> 

## Aggregaatti- eli koostefunktiot
Nämä funktiot yhdistävät tietoa useasta solusta ja palauttavat vain yhden arvon. Tämä arvo voi olla joko yhdistetty (kuten SUM-funktio) tai yksi rivi (kuten MIN-funktio).

| FUNKTIO | MERKITYS | ESIMERKKI | 
|---|---|---|
|COUNT()| Laskee kaikki rivit | COUNT(*) |
|SUM()| Laskee kaikkien rivien yhden sarakkeen arvot summaksi | SUM(hinta)|
|AVG()| Laskee kaikkien rivien yhden sarakkeen arvojen keskiarvon| AVG(hinta)|
|MIN()| Vertailee kaikkien rivien yhden sarakkeen arvoista pienimmän | MIN(hinta)|
|MAX()| Vertailee kaikkien rivien yhden sarakkeen arvoista suurimman | MAX(hinta)|

> Esimerkki 02: kahden vaihtoehtoisen ehdon tutkiminen OR -operaattorilla
> 

### Aggregaattifunktiot tarvitsevat tuekseen GROUP BY -käskyn.


## Skalaari eli mittafunktiot
Nämä funktiot käsittelevät vain yhtä solua kerrallaan. Näitä ovat esim. lukuja käsittelevät funktiot (kuten pyöristys, ROUND()) ja merkkijonoja käsittelevät funktiot (kuten pituus, LEN()). Lisäksi löytyy hyödyllisiä funktiota kuten päivämäärän ja kellonajan palauttava funktio NOW().

| FUNKTIO | MERKITYS | ESIMERKKI | 
|---|---|---|
| ROUND() | Pyöristää luvun haluttuun määrään desimaaleja |  |
| NOW() | Palauttaa tämän päivän ja kellonajan |  |
| MOD() | Palauttaa  |  |
| LEN() |  |  |


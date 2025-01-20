# Kyselyt - perusteet

SQL-kielessä käytetyt käskyt ovat kaikki kyselyitä (engl. query), sillä jokainen kysely palauttaa tuloksen käyttäjälle. [^1]

Tämä koskee erityisesti SELECT-kyselyä.
Yleisin käyttötarkoitus sille on tietojen hakeminen nykyisestä tietokannasta. Tietoa haetaan SELECT-lauseella, jota täydennetään muilla käskyillä ja rajoitteilla. 
Tärkeää on saada haettua *KAIKKI* haluttu tieto ilman *MITÄÄN VÄÄRÄÄ* tietoa. 

> ***Esimerkiksi:*** kuvitellaan, että meillä on tietokannan taulu, johon on tallennettu asiakastietoja.
> Kuten asiakasnumero, asiakkaan nimi, asiakkaan osoite, asiakkaan puhelinnumero, asiakkaan toimipaikka sekä asiakkaan tilausten kokonaismäärä.

> Kyseinen relaatiotaulu voisi näyttää esimerkiksi tältä.

 |asiakkaan nimi|asiakkaan osoite|asiakkaan puhelinnumero|asiakkaan toimipaikka|tilausten kokonaismäärä|
 |---|---|---|---|---|
 |Reijon keittiö ay|Konetie 2|044 123123|Espoo|6|
 |Allun asvaltti oy|katutie 1|044 223344|Kirkkonummi|5|
 |Maken majoitus oy|lepotie 5|040 987654|Helsinki|8|
 |Kuljetus Kaisa ab|rengastie 12|050 456789|Vantaa|3|
 |Veikan vihannekset oy|puutarhatie 4|041 112233|Espoo|10|
 |Pekan paikkaus oy|kaivostie 8|040 776655|Helsinki|7|
 |Rakennus-Rane oy|rakennustie 10|045 334455|Helsinki|4|
 

|  KÄSKY | MERKITYS |
|---|---|
| SELECT | Valitsee käyttäjälle näytettävät sarakkeet. |
| FROM | Valitsee mistä taulusta tieto haetaan. |
| WHERE | Valitsee millä ehdoilla tietoa haetaan taulusta. Ehtoja voi olla useita. |

> [!TIP]
> Kun aloitat SQL-haun suunnittelun,  1) tutustu ensin tietokannan tauluihin ja selvitä mistä taulusta hakemasi tieto löytyy,  2) suunnittele ja kirjoita alustava SLQ-haku ja 3) aja haku ja tarkista saamasi tulos. Korjaa hakua, mikäli tarpeen.

### Esimerkki 01: kaikkien tietojen haku taulusta.
> 
```sql
SELECT *  
FROM 
```


### Esimerkki 02: 

# Vertailuoperaattorit

WHERE-ehdon yhteydessä käytetään vertailuoperaattoreita, joiden avulla hakua rajoittava ehto ilmaistaan.

> SQL-kielessä käytetyt operaattorit eroavat, jonkin verran yleisesti ohjelmointikielissä käytetyistä operaattoreista. Käyttö vaatii siis tarkkuutta!

| OPERAATTORI | MERKITYS | SELITYS |
|---|---|---|
| = | yhtäsuuri kuin | molempien puolien arvojen tulee olla identtiset. Esim. 1 = 1 |
| > | suurempi kuin | vasemman puolen tulee olla suurempi kuin oikean puolen. Esim. 2 > 1 |
| < | pienempi kuin | vasemman puolen tulee olla pienempi kuin oikean puolen. Esim. 1 < 2 |
| >= | suurempi tai yhtäsuuri kuin | vasemman puolen tulee olla suurempi kuin oikean puolen. Tai ne voivat olla identtiset. Esim. 1 >= 1 |
| <= | pienempi tai yhtäpieni kuin | vasemman puolen tulee olla pienempi kuin oikean puolen. Tai ne voivat olla identtiset. Esim. 1 <= 1 |
| <> | erisuuri kuin | molempien puolien tulee olla erilaiset. Esim. 1 <> 5 |

> HUOM. Vertailuoperaattoreilla voidaan verrata mitä tahansa kenttien sisältämiä tietoja. Ei ainostaan numeerista tietoa, vaan myös merkkijonoja.
> Merkkijonojen vertailuun on käytössä myös toinen SQL-käsky (LIKE), johon tutustumme seuraavassa luvussa.

# Lähteet ja vinkit
[^1]: Tietoa
https://www.w3schools.com/sql/sql_select.asp 

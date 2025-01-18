# Kyselyt - perusteet

SQL-kielessä käytetyt käskyt ovat kaikki kyselyitä (engl. query), sillä jokainen kysely palauttaa tuloksen käyttäjälle. Tämä koskee erityisesti seuraavaa kyselyä.
Yleisin käyttötarkoitus on tietojen hakeminen nykyisestä tietokannasta. Tietoa haetaan SELECT-lauseella, jota täydennetään muilla käskyillä ja rajoitteilla. 
Tärkeää on saada haettua *KAIKKI* haluttu tieto ilman *MITÄÄN VÄÄRÄÄ* tietoa. 

> ***Esimerkiksi:*** kuvitellaan, että meillä on tietokannan taulu, johon on tallennettu asiakastietoja.
> Kuten asiakasnumero, asiakkaan nimi, asiakkaan osoite, asiakkaan puhelinnumero ja asiakkaan kotimaa.
>
> 

|  KÄSKY | MERKITYS |
|---|---|
| SELECT | Valitsee käyttäjälle näytettävät sarakkeet. |
| FROM | Valitsee mistä taulusta tieto haetaan. |
| WHERE | Valitsee millä ehdoilla tietoa haetaan taulusta. Ehtoja voi olla useita. |

### Esimerkki 01: 

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

> HUOM. Vertailuoperaattoreilla voidaan verrata mitä tahansa kenttien sisältämiä tietoja. Ei ainostaan numeroita, vaan myös merkkijonoja.
> Merkkijonojen vertailuun on käytössä myös toinen SQL-käsky (LIKE).




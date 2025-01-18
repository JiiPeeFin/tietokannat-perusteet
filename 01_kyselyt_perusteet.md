# Kyselyt - perusteet

SQL-kielessä käytetyt käskyt ovat kaikki kyselyitä (engl. query), sillä jokainen kysely palauttaa tuloksen käyttäjälle. Tämä koskee erityisesti seuraavaa kyselyä.
Yleisin käyttötarkoitus on tietojen hakeminen nykyisestä tietokannasta. Tietoa haetaan SELECT-lauseella, jota täydennetään muilla käskyillä ja rajoitteilla. 
Tärkeää on saada haettua *KAIKKI* haluttu tieto ilman *MITÄÄN VÄÄRÄÄ* tietoa. 

> ***Esimerkiksi:*** kuvitellaan, että meillä on tietokannan taulu, johon on tallennettu asiakastietoja.
> Kuten asiakasnumero, asiakkaan nimi, asiakkaan osoite, asiakkaan puhelinnumero ja asiakkaan kotimaa.
>
> 

|  Käsky | Merkitys |
|---|---|
| SELECT | Valitsee käyttäjälle näytettävät sarakkeet. |
| FROM | Valitsee mistä taulusta tieto haetaan. |
| WHERE | Valitsee millä ehdoilla tietoa haetaan taulusta. Ehtoja voi olla useita. |

## Esimerkki 01: 

# Tietokannat - perusteet
1. Sisältö ja oppimistavoitteet
2. Tietokantojan teoriaa
3. Kyselyt - perusteet
   >- SELECT, FROM, WHERE
5. Kyselyt - ehdot
   >- AND, OR, LIKE
6. Kyselyt - koostaminen ja funktiot
   >- SUM(), COUNT(), AVG(), MAX(),... 
7. Kyselyt - järjestäminen ja rajoittaminen
   >- ORDER BY, DISTINCT, LIMIT,...
8. Kyselyt - taulujen yhdistäminen
   >- INNER JOIN, LEFT/RIGHT JOIN, OUTER JOIN,...
9. Kyselyt - tiedon lisäys, muokkaus ja poisto
   >- INSERT INTO, UPDATE, DELETE
10. Kyselyt - rakenteen luonti, muokkaus ja poisto
    >- CREATE DATABASE/TABLE, ALTER TABLE, DROP DATABASE/TABLE
12. Tietokannan suunnittelu
13. Tehtäviä
14. Lisämateriaalia

## Sisältö ja oppimistavoitteet

>Tämä kurssi on lyhyt ja kapea perehdytys tietokantojen käyttöön. Kurssissa keskitytään lähinnä relaatiotietokantoihin ja SQL -kyselykielen käyttämiseen.
>Lisäksi käymme läpi lyhyesti tietokannan suunnittelua, joka on oma monimutkainen kokonaisuutensa.
>Kurssin tarkoitus on antaa opiskelijalle eväät ymmärtää ja käyttää perustason SQL-kyselyitä sekä ymmärtää tietokannan rakennetta ja suunnitteluprosessia.

Tämän kurssin jälkeen opiskelija...
- ymmärtää tietokantojen perusteet ja peruskäsitteistön
- osaa tehdä erilaisia kyselyitä tietokannasta
- osaa lisätä, muokata ja poistaa tietoa tietokannasta
- osaa luoda, muokata ja poistaa tietokannan rakenteen osia
- ymmärtää tietokannan suunnittelun vaiheet ja käsitteet
- osaa etsiä tietoa käsittellyistä aiheista ja ratkaista ongelmia

Käytetyt teknologiat ja menetelmät
- relaatiotietokannat
- SQL-kieli
- XAMPP -sovellus (MariaDB, phpMyAdmin,...)

## Tietokantojen teoriaa

Tietokannat ovat digitaalisia tietovarastoja, joiden tiedot liittyvät jotenkin toisiinsa ( eli muodostavat kokonaisuuden). 
Tietokannat ovat sovellusten ja verkkopalveluiden pitkäaikainen muisti.

> Esimerkki tietokannasta on esim. yhdistyksen jäsenrekisteri, verkkokaupan tuotelista ja videopelin pistelista.

Yleisin tietokantatyyppi on **relaatiotietokanta**. 
Relaatiotietokanta on toteutettu siten, että tieto jaetaan useaan **tauluun**, joissa tiedolla on yhtenäinen suhde (relaatio) toisiinsa. Yleensä tietokannassa on useampia tauluja ja näillä tauluilla on yhteys toisiinsa niin kutsutun **avaimen** avulla. 

> Relaatio (engl. relation, relationship) tarkoittaa suhdetta.

>Esimerkki relaatiotaulusta
>
>TaulunNimi
>|Sarake yksi|Sarake kaksi|Sarake kolme|Sarake neljä|
>|---|---|---|---|
>|Yksi|rivi|on|yhtenäistä tietoa|

Relaatiotietokannan tärkeimpiä piirteitä ovat:
- **Taulut:** tietojen tallentaminen **tauluihin**, joissa rivit edustavat yhtä tietuetta ja sarake tietueiden ominaisuutta.
- **Relaatiot:** taulun tiedot ovat **suhteessa** toisiinsa ja lisäksi taulut ovat suhteessa toisiinsa avainten avulla.
- **SQL-kieli:** kieltä käytetään tiedon ja tietorakenteiden käsittelyyn.
- **Normalisointi:** tiedot lohkotaan niin pieniin tauluihin, että tietoa ei tarvitse toistaa. Normalisoinnin tavoite on toiston, eli **redundanssin** vähentäminen.

> Muita mahdollisia tietokantatyyppejä ovat mm. dokumentti-, graafi- ja avain-pari-tietokannat.

### SQL-kieli

**Structured Query Language (SQL)** on relaatiotietokannoissa käytetty tietokannan **hallintaan** tarkoitettu ohjelmointikieli. SQL-kieltä käytetään tällä kurssilla tietokannan tietojen hakemiseen, lisäämiseen, päivittämiseen ja poistamiseen. Lisäksi kielellä luodaan, muokataan ja tuhotaan tietokannan tietorakenteita.

>Huom. Kaikkia SQL käskyjä kutsutaan nimellä kysely (engl. query). 

### Tietokantojen käsitteet

Tärkeimpiä tietokantojen käsitteitä ovat mm. seuraavat:
|Käsite | Englanniksi | Selitys
|---|---|---|
|tietokannan hallintajärjestelmä | database management system, DBMS | Sovellus, jonka avulla tietokantoja ja niiden ominaisuuksia hallitaan. |
|tietokanta | database, DB | Tietokanta on järjestetty kokonaisuus rakenteellista tietoa, jota DBMS hallitsee. |
|suhde, relaatio  | relation | 1) Taulu tietokannassa, jonka tiedot ovat suhteessa toisiinsa 2) Taulujen välinen suhde, jota ilmaistaan avaimilla. |
|tietorakenne, skeema  | data structure, schema | Rakenne siitä miten tieto on järjestetty tauluissa ja eri taulujen välillä. |
|kysely, haku, käsky  | query | Käsky/komento, joka hakee tietoa tietokannasta. Voivat myös muuttaa tietokantaa ja sen rakennetta. |
|taulu   | table | Yksittäinen taulu sisältää tietoa tietystä suhteesta. |
|rivi, tietue | row, tuple | Rivin tiedot liittyvät suoraan toisiinsa. Esim. tietyn asiakkaan nimi, osoite ja tilaus. |
|sarake  | column | Sarakkeet liittyvät tietorakenteeseen ja kuvaavat millaista tietoa kyseisessä kohdassa on. Esim. asiakkaan nimi, joko on merkkijono. |
|solu | cell | Yksi ja tietty kohta tietokantataulussa. Esim. tietyn asiakkaan nimi. |
|avain | key | Lisätieto, joka avulla tietokannan taulut liitettään toisiinsa. Ja tietoon luodaan rajoitteita. |
|tietotyyppi | data type | Tieto siitä millaista tietoa sarakkeeseen ja sen soluihin on tallennettu. Esim. merkkijonot tai kokonaisluvut. |

Lisäksi on paljon käsitteitä, jotka liittyvät tietokannan hallintaan, kehittyneempiin hakuihin ja käyttöön. Näitä ei käydä tässä kurssissa.

## Kyselyt - perusteet

## Kyselyt - ehdot

## Kyselyt - koostaminen ja funktiot

## Kyselyt - järjestäminen ja rajoittaminen

## Kyselyt - taulujen yhdistäminen

## Kyselyt - tiedon lisäys, muokkaus ja poisto

## Kyselyt - rakenteen luonti, muokkaus ja poisto

Tietokannan rakennetta vuodaan muokata seuraavilla tavoilla:
- taulun luominen ja poistaminen
- taulun rakenteen muokkaaminen


## Tehtäviä

Tehtävät löytyvät kansiosta ["tehtävät"](tehtävät/).
Tehtävät on jaettu useaan eri tiedostoon kurssin rakenteen mukaan.

KUVA

## Lisämateriaalia

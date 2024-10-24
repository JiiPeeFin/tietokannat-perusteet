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

Tietokannat ovat digitaalisia tietovarastoja, joiden tiedot liittyvät jollain tavalla toisiinsa. 
Tietokannat ovat sovellusten ja verkkopalveluiden pitkäaikainen muisti.

> Esimerkki tietokannasta on esim. yhdistyksen jäsenrekisteri, verkkokaupan tuotelista ja videopelin pistelista.

Yleisin tietokantatyyppi on **relaatiotietokanta**. 
Relaatiotietokanta on toteutettu siten, että tieto jaetaan useaan **tauluun**, joissa tiedolla on yhtenäinen suhde (relaatio) toisiinsa. Yleensä tietokannassa on useampia tauluja ja näillä tauluilla on yhteys toisiinsa niin kutsutun **avaimen** avulla. 

> Relaatio (engl. relation, relationship) tarkoittaa suhdetta.

>Esimerkki relaatiotaulusta
>
>TaulunNimi
>|Sarake yksi|Sarake kaksi|Sarake kolme|
>|---|---|---|
>

Relaatiotietokannan tärkeimpiä piirteitä ovat:
- **Taulut:** tietojen tallentaminen **tauluihin**, joissa rivit edustavat yhtä tietuetta ja sarake tietueiden ominaisuutta.
- **Relaatiot:** jokaisen taulun tiedot ovat **suhteessa** toisiinsa ja lisäksi taulut ovat suhteessa toisiinsa avainten avulla.
- **SQL-kieli:** kieltä käytetään tiedon ja tietorakenteiden käsittelyyn.
- **Normalisointi:** tiedot lohkotaan niin pieniin tauluihin, että tietoa ei tarvitse toistaa. Normalisoinnin tavoite on toiston, eli **redundanssin** vähentäminen.

> Muita mahdollisia tietokantatyyppejä ovat mm. dokumentti-, graafi- ja avain-pari-tietokannat.

### SQL-kieli

**Structured Query Language (SQL)** on relaatiotietokannoissa käytetty tietokannan **hallintaan** tarkoitettu ohjelmointikieli. SQL-kieltä käytetään tällä kurssilla tietokannan tietojen hakemiseen, lisäämiseen, päivittämiseen ja poistamiseen. Lisäksi kielellä luodaan, muokataan ja tuhotaan tietokannan tietorakenteita.

>Huom. Kaikkia SQL käskyjä kutsutaan nimellä kysely (engl. query). 

### Tietokantojen käsitteet

Tärkeimpiä tietokantojen käsitteitä ovat seuraavat:
|Käsite | Englanniksi |
|---|---|
|tietokannan hallitajärjestelmä | database management system, DBMS |
|tietokanta | database, DB |
|suhde, relaatio  | relation | 
|tietorakenne, skeema  | data structure, schema | 
|kysely, haku, käsky  | query | 
|taulu   | table | 
|rivi, tietua | row, tuple | 
|sarake  | column | 
|solu | cell | 
|avain | key | 
|tietotyyppi | data type | 

## Kyselyt - perusteet

## Kyselyt - ehdot

## Kyselyt - koostaminen ja funktiot

## Kyselyt - järjestäminen ja rajoitaminen

## Kyselyt - taulujen yhdistäminen

## Kyselyt - tiedon lisäys, muokkaus ja poisto

## Kyselyt - rakenteen luonti, muokkaus ja poisto

## Tietokannan suunnittelu

### Tietokannan normalisointi

Tietokannan normalisointi on menetelmä, jossa tietokanta käydään.

## Tehtäviä

Tehtävät löytyvät kansiosta ["tehtävät"](tehtävät/).
Tehtävät on jaettu useaan eri tiedostoon kurssin rakenteen mukaan.

KUVA

## Lisämateriaalia

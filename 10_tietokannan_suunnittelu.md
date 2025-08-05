# Tietokannan suunnittelu

Tietokannan suunnittelu ja toteutus on oma taiteenlajinsa. Tietokanta suunnitellaan aina tiettyä tarkoitusta varten. 



Tietokanta voi koostua vain yhdestä suuresta taulusta, mutta tämä ratkaisu johtaa yleensä hankaluuksiin myöhemmin. Yleensä relaatiotietokanta koostuu useista tauluista sekä niiden välitauluista, joilla kerätään yhteen taulujen välistä tietoa.

> [!NOTE]
> Tämän koulutuksen aikana teidän tarvitsee suunnitella ja toteuttaa ainakin yksi tietokanta alusta loppuun. Tässä luvussa käsittelememme suunnitteluun liittyviä aiheita, käsitteitä ja menetelmiä. Muistakaa myös hakea tietoa muista lähteistä.

Tietokannan suunnittelun perusperiaatteita ovat mm.
* 

Tietokannan tulee siis olla
* Tietokanta sisältää ennalta määrittelemättömän määrän yhteenkuuluvaa tietoa.
* Tietokanta on suunniteltu ja toteuttu ennalta määriteltyä tarkoitusta varten.
* Tietokannalla on käyttäjiä, joiden tarvitsee hakea, lisätä, muokata ja poistaa tietoja tietokannasta. CRUD-operaatiot.


## Nimeämiskäytännöt
> Selkeä ja johdonmukainen nimeämiskäytäntö (engl. naming convention) tekee tietokannasta helpommin käytettävän ja ylläpidettävän.

Nimeämisen peruskäytännöt on tärkeä sopia projektin alussa, jotta nimet ovat johdonmukaisia. Nimet tulee mietti mm. tauluilla, taulujen sarakkeille, avaimille ja monille muille rakenteille. Nimiä käyttävät kehittäjien ja ohjelmoijien lisäksi myös monet muut sovelluksen käyttäjät. Ja nimet vaikuttavat koko sovelluksen ja sen tietokannan eliniän ajan.[^1]


Nimeämisen hyvät peruskäytännöt ovat
* käytä pieniä kirjaimia. Esim. asiakas
* käytä alaviivaa, jos erotat sanoja. Esim. asiakas_puhelinnumero. Tai käytä lainausmerkkejä ottaaksesi välilyönnin huomioon. Esim. "asiakas puhelinnumero".
* käytä sanoja yksikkömuodossa. Älä monikossa. Esim. asiakas. Ei asiakkaat.


## Entiteettien suhteet

Entiteeteillä tulee olla suhde johonkin muuhun entiteettiin, jotta ne voidaan ryhmitellä samaan tietokantaa.

Mahdolliset suhteet (esimerkkinä ihmissuhteet) ovat:
- Yhden suhde yhteen (1 - 1): esimerkiksi avioliitto, sillä yhdellä henkilöllä voi olla VAIN yksi puoliso.
- Yhden suhde moneen (1-N, 1-*): esimerkiksi ensijainen huoltaja, sillä yhdellä lapsella voi olla vain yksi ensisijainen huoltaja (yhteyshenkilö). Mutta yhdellä huoltajalla voi olla monta lasta.
- Monen suhde moneen (*-*, N-M): esimerkiksi ystävyys, sillä yhdellä henkilöllä voi olla MONTA henkilöä ystävänä. Ja yhdellä ystävällä voi olla monta henkilöä ystävänä.

Mahdolliset suhteet (esimerkkinä yritys) ovat:
- Yhden suhde yhteen (1 - 1): esimerkiksi toimitusjohtaja, sillä yhdellä yrityksellä on vain yksi toimitusjohtaja. Ja yksi toimitusjohtaja työskentelee vain yhdessä yrityksessä.
- Yhden suhde moneen (1-N, 1-*): esimerkiksi esihenkilöt, sillä yhdellä esihenkilöllä on monta alaista. Mutta yhdellä alaisella on vain yksi esihenkilö. 
- Monen suhde moneen (*-*, N-M): esimerkiksi tuotteet, sillä yhdellä yrityksellä on monta tuotetta. Ja yhden samanlaiset tuotteen voi tuottaa monta yritystä. 

>[!TIP]
>Suhteiden selvittäminen on yllättävän hankalaa. Ota huomioon, että tietokanta on AINA yksinkertaistettu malli monimutkaisesta todellisuudesta. Tietokannan suunnittelijan tulee tehdä valintoja ja päätöksiä siitä miten tietoa tallennetaan ja miten tiedot liittyvät toisiinsa. Kaikkea ei voi saada. 
> 


## Tietokannan normalisointi 

Tietokannan normalisointi on menetelmä, jossa tietokanta käydään vaihevaiheelta läpi. Normalisointi tehdään yleensä silloin kun halutaan parantaa nykyisen tietokannan toimintakykyä ja rakennetta. Normalisointi voidaan tehdä myös silloin kun oma

Normalisoinnissa on 5-6 vaihetta, joista yleensä toteutetaan kolme ensimmäistä. Normalisoinnin tavoite on toteuttaa tietokanta, jossa on mahdollisimman vähän toistoa (redundanssia) sekä tyhjiä kenttiä (null). Tällä pyritään yhteinäiseen ja helposti hallittavaan tietokantaan. 
Käytännössä tietokannan normalisointi tarkoittaa sitä, että harvoja isoja tauluja jaetaan useammiksi pienemmiksi tauluiksi.

> Tässä kurssissa käymme normalisoinnin hyvin pintapuolisesti läpi. Aiheeseen kannattaa tutustua itsenäisesti.

Usein työelämässä käytetään listoja asioiden tallentamiseen, mutta tiedon hakeminen listasta on hankalaa ja tehotonta. Myös tiedon yhdistely uusilla tavoilla on hyvin hankalaa listoilla. Normalisointi voidaan nähdä prosessina, jossa listasta tehdään aito tietokanta.

|Normaalimuoto|Normaalimuodon ehdot|Tavoite|
|---|---|---|
|Ensimmäinen normaalimuoto, 1NF| Solun tieto on atomista, jokaisella rivillä yksilöllinen avain|Tieto on helposti käsiteltävää, eri rivit pysyvät selkeinä|
|Toinen tormaalimuoto, 2NF|Kaikilla ei-avain kentillä on TÄYSI riippuvuus rivin avaimesta|Taulu jaetaan, jos taulussa on avaimesta riippumatonta tietoa|
|Kolmas normaalimuoto, 3NF|||
|Boyce-Codd normaalimuoto, BCNF|||
|Neljäs normaalimuoto, 4NF|||
|Viides normaalimuoto, 5NF|||

## Lähteet ja vinkit
[^1]: nimeäminen, https://www.sqlshack.com/learn-sql-naming-conventions/

# Tietokannan suunnittelu

Tietokannan suunnittelu ja toteutus on oma taiteenlajinsa. Tietokanta suunnitellaan aina tiettyä tarkoitusta varten. 



Tietokanta voi koostua vain yhdestä suuresta taulusta, mutta tämä ratkaisu johtaa yleensä hankaluuksiin myöhemmin. Yleensä relaatiotietokanta koostuu useista tauluista sekä niiden välitauluista, joilla kerätään yhteen taulujen välistä tietoa. Tietokantojen luomiseen on useita malleja ja viitekehityksiä, joissa yritetään tehostaa jotain tietokannan ominaisuutta. Yleensä tämä tehostaminen heikentää muita ominaisuuksia. Tässä kurssissa keskitymme siihen miten suunnitellaan ja toteutetaan yleisimmän käytettyjä relaatiotietokantoja. Emme ota huomioon suurinta osaa tietokantojen suunnittelussa käytettäviin näkökulmiin, vaan pohdimme pääasiassa tiedon rakennetta ja tiedon toiston vähentämistä.

> [!NOTE]
> Tämän koulutuksen aikana teidän tarvitsee suunnitella ja toteuttaa ainakin yksi tietokanta alusta loppuun. Tässä luvussa käsittelemme suunnitteluun liittyviä aiheita, käsitteitä ja menetelmiä. Muistakaa hakea tietoa myös muista lähteistä.

Tietokannan suunnittelun perusperiaatteita ovat mm.
* 

Tietokannan tulee siis...
* sisältää ennalta määrittelemättömän määrän yhteenkuuluvaa tietoa.
* olla suunniteltu ja toteuttu ennalta määriteltyä tarkoitusta varten.
* hallita käyttäjiä, joiden tarvitsee hakea, lisätä, muokata ja poistaa tietoja tietokannasta.


### Nimeämiskäytännöt
> Selkeä ja johdonmukainen nimeämiskäytäntö (engl. naming convention) tekee tietokannasta helpommin käytettävän ja ylläpidettävän.

Nimeämisen peruskäytännöt on tärkeä sopia projektin alussa, jotta nimet ovat johdonmukaisia. Nimet tulee mietti mm. tauluilla, taulujen sarakkeille, avaimille ja monille muille rakenteille. Nimiä käyttävät kehittäjien ja ohjelmoijien lisäksi myös monet muut sovelluksen käyttäjät. Ja nimet vaikuttavat koko sovelluksen ja sen tietokannan eliniän ajan.[^1]


Nimeämisen hyvät peruskäytännöt ovat
* käytä pieniä kirjaimia. Esim. asiakas
* käytä alaviivaa, jos erotat sanoja. Esim. asiakas_puhelinnumero. Tai käytä lainausmerkkejä ottaaksesi välilyönnin huomioon. Esim. "asiakas puhelinnumero".
* käytä sanoja yksikkömuodossa. Älä monikossa. Esim. asiakas. Ei asiakkaat.


### Entiteettien suhteet

Entiteeteillä tulee olla suhde johonkin muuhun entiteettiin, jotta ne voidaan ryhmitellä samaan tietokantaa.

Mahdolliset suhteet (esimerkkinä ihmissuhteet) ovat:
- Yhden suhde yhteen (1 - 1): esimerkiksi avioliitto, sillä yhdellä henkilöllä voi olla VAIN yksi puoliso.
- Yhden suhde moneen (1-N, 1-*): esimerkiksi ensijainen huoltaja, sillä yhdellä lapsella voi olla vain yksi ensisijainen huoltaja (yhteyshenkilö). Mutta yhdellä huoltajalla voi olla monta lasta.
- Monen suhde moneen (*-*, N-M): esimerkiksi ystävyys, sillä yhdellä henkilöllä voi olla MONTA henkilöä ystävänä. Ja yhdellä ystävällä voi olla monta henkilöä ystävänä.

Mahdolliset suhteet (esimerkkinä yritys) ovat:
- Yhden suhde yhteen (1 - 1): esimerkiksi toimitusjohtaja, sillä yhdellä yrityksellä on vain yksi toimitusjohtaja. Ja yksi toimitusjohtaja työskentelee vain yhdessä yrityksessä.
- Yhden suhde moneen (1-N, 1-*): esimerkiksi esihenkilöt, sillä yhdellä esihenkilöllä on monta alaista. Mutta yhdellä alaisella on vain yksi esihenkilö. 
- Monen suhde moneen (*-*, N-M): esimerkiksi tuotteet, sillä yhdellä yrityksellä on monta tuotetta. Ja yhden samanlaiset tuotteen voi tuottaa monta yritystä. 

>[!IMPORTANT]
>***Suhteiden selvittäminen on yllättävän hankalaa.*** Ota huomioon, että tietokanta on ***AINA*** yksinkertaistettu malli monimutkaisesta todellisuudesta. Tietokannan suunnittelijan tulee tehdä valintoja ja päätöksiä siitä miten tietoa tallennetaan ja miten tiedot liittyvät toisiinsa. Kaikkea ei voi saada. 
> 

## Tietokannan suunnittelun vaiheet

Tietokannan suunnittelu sisältää yksinkertaisimmillaan kolme vaihetta. Käsiteanalyysin, jossa asiakkaan vaatimukset muutetaan ensin tarinaksi, josta löydetään käsitteet, niiden ominaisuudet ja lopulta niiden väliset suhteet ja rajoitteet. Tässä vaiheessa yhteys todelliseen maailmaan alkaa katketa, ja ajattelun pitää siirtyä käsittelemään sitä miten tietoa voidaan tallentaa. Käsiteanalyysin lopputuote on käsitekaavio, joka piirretään usein ER-mallina. ER-malli kuuluu UML-kaavioiden ryhmään, ja siitä löytyy useita erilaisia piirto-ohjeita. ER-malli auttaa suunnittelijaa ja asiakasta korjaamaan käsitteiden, niiden suhteiden ja ominaisuuksien luonnissa tapahtuneita virheitä. Lopuksi ER-malli puretaan relaatiomalliksi, joka toteutetaan listana ja/tai taulukkona, jossa näkyy lopullisten tietokannan taulujen nimet, sarakkeet ja sarakkaiden tietotyypit. Lisäksi on tärkeää määritellä yhteydet pää- ja vierasavainten avulla. Tämä relaatiomalli puretaan SQL-komennoiksi, joiden avulla toteutetaan tietokanta.

Tietokannan suunnittelun pääosat
1. Käsiteanalyysi                (engl. concept analysis)
2. Konseptuaalinen suunnittelu   (engl. conceptual design)
3. Looginen suunnittelu          (engl. logical design)

> [!TIP]
> Jokainen vaihe voidaan joutua tekemään useaan kertaan. Sekä palaamaan takaisin alkuun.

### Tietokannan suunnittelun vaiheet
1. Käsiteanalyysi
   - Käyttäjätarina (laaja)
   - Käsitteiden tunnistaminen
   - Käsitteiden yhteydet
   - Käsitteiden rajoitteet
   - Lisää ominaisuudet käsitteidelle
2. Käsitekaavion piirtäminen
3. ER-kaavion piirtäminen
4. ER-kaavion muuttaminen relaatiomalliksi
5. SQL kyselyiden 

### Tietokannan normalisointi 

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

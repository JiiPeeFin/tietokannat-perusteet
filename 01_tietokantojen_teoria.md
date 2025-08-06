# Tietokantojen teoria

### Mikä on tietovarasto (engl. data repository)?
- Mikä tahansa kokoelma tietoa (dataa).
- Ei välttämättä suunniteltu, ei välttämättä tarkoitusta.
- Ei välttämättä rakennetta.
- ***UUSI MÄÄRITELMÄ:*** tietovarasto (engl. data warehouse) voi tarkoittaa tietokantojen erikoistapausta, jossa keskitytään tiedon hakemiseen, puhdistamiseen ja analysointiin (esim. ETL-prosessi).

>***Esimerkkitapaus 01***: iso kasa kirjoja työpöydällä on tietovarasto. Ei järjestystä, ei suunnitelmaa, rakenne vain yksiköissä (kirjoissa).

>***Esimerkkitapaus 02:*** iso hyllyllinen kirjoja kirjastossa on tietokanta. Kirjat on järjestetty aiheittain, teoksen nimen mukaan ja tyypin mukaan. Suunnitelma, jotta kirjoja on helppo löytää ja lisätä. 

>***Esimerkkejä erilaisista tavoista toteuttaa tietokanta***
> - paperinen lista
> - tekstitiedosto (esim. word)
> - taulukkotiedosto (esim. excel)
> - automatisoitu taulukkotiedosto (esim. excel)
> - tietokantasovellus (esim. XAMPP, jossa MySQL phpMyAdmin käyttöliittymällä)

### Mikä on tietokanta (engl. database)?
- Kokoelma yhteen liittyvää tietoa (dataa).
- Yhtenäinen kokoelma tietoa, jolla on jokin merkitys.
- Suunniteltu, rakennettu ja täytetty tiedolla jotain tiettyä tarkoitusta varten.
- Tietovarasto, jota käytetään sovelluksen tilan pysyvään tallentamiseen.
- Ei tarvitse olla digitaalinen/sähköinen, mutta yleensä on.

### Mitä tietokannalta halutaan ensisijaisesti?
- Turvallinen tiedon säilytys
- Hallittu tietojen muuttaminen
- Monipuolinen tietojen haku
- Tehdä yhteenvetoja ja laskutoimituksia
- Tiedon jakaminen

- Turvallinen ja pysyvä paikka tiedolle.
- Tehostaa: poistaa tiedon toisto (redundanssi).
- Eristää: eristää ohjelma (toiminnat) ja tiedot.
- Tietojen käsittely: Tehokas ja nopea tietojen hakeminen ja lisääminen.
- Monet käyttäjät: Monet käyttäjät voivat käsitellä tietoja samaan aikaan.
- Käyttäjähallinta: eri oikeustasoja eri tietoihin. Mahdollisuus rajoittaa tietojen näkyvyyttä ja muokkausta.
- Rakenne: tietojen tallentamisessa ja käsittelyssä on rajoitteita, jotka suojaavat tietoa ja sen rakennetta.

## Tietokannan ominaisuuksia:
- Tiedon pysyvyyteen ja turvallisuuteen liittyvät toiminnot (ACID)
  - Atomicity - kaikki muutokset suoritetaan tai mitään ei suoriteta. Ei keskeneräisiä tiloja.
  - Consistency (eheys) - tietokannan tila pysyy ehjänä muutoksista huolimatta
  - Isolation (eristyneisyys) - toimenpiteet eivät vaikuta toisiinsa. Toimenpiteiden väliset tilat eivät näy toisille toiminnoille.
  - Durability (pysyvyys) - toimenpiteen jälkeen muutokset eivät katoa järjestelmästä
- Tiedon käsittelyyn liittyvät toiminnot (CRUD)
  - Create - tiedon lisääminen, tiedon rakenteiden ja metatietojen lisääminen
  - Read/retriev - tiedon hakeminen ja esittäminen
  - Update - tiedon, tiedon rakenteiden ja metatietojen muuttaminen
  - Destroy/drop - tiedon, tiedon rakenteiden ja metatietojen poistaminen 

 

### Mikä on relaatiotietokanta (engl. relational database)?
- Data järjestetään äärellisiksi listoiksi.
- Listat on ryhmitelty relaation mukaan tauluiksi.
- Jokainen rivi on oma tietueensa.
- Jokainen sarake on oma ominaisuutensa.
- Taulut voidaan yhdistää toisiinsa avaimilla.

### Tietokannan suunnittelun vaiheet

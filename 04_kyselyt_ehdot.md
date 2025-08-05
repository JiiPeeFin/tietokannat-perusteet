# Kyselyt - ehdot
>- AND, OR, NOT

Edellisessä luvussa tutustuimme kyselyiden perusteisiin.
Jatkamme nyt samasta aiheesta. Kun vertailuoperaattoreiden lisäksi otetaan käyttöön loogiset operaattorit AND ja OR, niin pystymme rakentamaan yhdellä kertaa monimutkaisemman kyselyn.
Käytännössä voimme asettaa yhden tai useampia ehtoja kyselylle (AND). Sekä tehdä vaihtoehtoisia ehtoja (OR).

Jos aiemmin pystyimme etsimään asiakkaat, joiden toimipaikka sijaitsi tietyssä kaupungissa, pystymme nyt sen lisäksi etsimään myös 

> Esimerkki 01: kahden ehdon yhdistäminen AND -operaattorilla
> 

OR -operaattorilla voimme luoda kaksi (tai useampia) valinnaisia ehtoja, joista voin yhden tarvitsee toteutua.

> Esimerkki 02: kahden vaihtoehtoisen ehdon tutkiminen OR -operaattorilla
> 


## Merkkijonojen vertailu
>- LIKE

Vaikka merkkijonoja voi vertailla edellisessä luvussa tutuilla vertailuoperaattoreilla (=, <, >, =<, =>, <>) on niiden käytössä parempi käyttää LIKE-operaattoria. 
Koska merkkijonot eroavat monella tavalla numeroista ja luvuista, tarvitsemme lisää ***jokerimerkkejä*** (engl. wildcards). 
Näillä voimme etsiä, tunnistaa ja vertailla merkkijonoja eri tavoilla.

| JOKERIMERKKI | MERKITYS | ESIMERKKI |
|---|---|---|
| % | esittää ei yhtään, yhtä tai monta kirjainmerkkiä | *%nen* mikä tahansa sana, joka päättyy kirjaimiin *nen*.  |
| _ | esittää yhtä kirjainmerkkiä |  |

> Muitakin jokerimerkkejä on, mutta tässä kurssissa nämä riittävät.
> Ohjelmoinnissa vastaava työkalu on *säännölliset lausekkeet* (engl. regular expression, regexp)


## Lähteet ja vinkit
[^1]:

### Loogisten operaattoreiden esittäminen taulukolla
Loogisia operaattoreita, kuten AND ja OR, esitetään usein taulukon avulla. Tämä esitystapa on tutumpi elektroniikassa sekä boolen algebrassa. Olen lisännyt tämän tähän mukaan, sillä esitystapa tulee usein vastaan jatko-opinnoissa ja ainakin omalla kohdallanni esitystapa on selkeyttänyt operaattoreiden toimintaa.

|A|B|A AND B|
|---|---|---|
|totta|totta|totta|
|totta|epätotta|epätotta|
|epätotta|totta|epätotta|
|epätotta|epätosi|totta|

> [!NOTE]
> Molempien verrattavien arvojen tulee olla ***IDENTTISET***.
> Mikäli toinen on eri, lopputulos on epätotta.
> AND operaattori on vaativampi operaattori kuin OR. 

|A|B|A OR B|
|---|---|---|
|totta|totta|totta|
|totta|epätotta|totta|
|epätotta|totta|totta|
|epätotta|epätosi|epätotta|

> [!NOTE]
> Riittää, että ***toinen*** arvo on totta.
> Vain tilanteessa, jossa molemmat verrattavat arvot ovat epätotta, on myös tulos epätosi.
> OR operaattori siis hyväksyy helpommin arvoja. 

# Kyselyt - ehdot
>- AND, OR

Edellisessä

## Merkkijonojen vertailu
>- LIKE

Vaikka merkkijonoja voi vertailla edellisessä luvussa tutuilla vertailuoperaattoreilla (=, <, >, =<, =>, <>) on niiden käytössä parempi käyttää LIKE-operaattoria. 
Koska merkkijonot eroavat monella tavalla numeroista ja luvuista, tarvitsemme lisää ***jokerimerkkejä*** (engl. wildcards). 
Näillä voimme etsiä ja tunnistaa merkkijonoja eri tavoilla.

| JOKERIMERKKI | MERKITYS | ESIMERKKI |
|---|---|---|
| % | esittää ei yhtään, yhtä tai monta kirjainmerkkiä | *%nen* mikä tahansa sana, joka päättyy kirjaimiin *nen*.  |
| _ | esittää yhtä kirjainmerkkiä |  |

> Muitakin jokerimerkkejä on, mutta tässä kurssissa nämä riittävät.
> Ohjelmoinnissa vastaava työkalu on *säännölliset lausekkeet* (engl. regular expression, regexp)

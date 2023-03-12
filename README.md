# LinuxPalvelimet-h14-Uusi-komento
    Kirjoittanut: Jesse Reunamo
    Kurssi:       Linux-palvelimet
    Linkki:       https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/


Aloitus klo 19:30
## a)
Luodaan uusi komento kaikille käyttäjille käyttäen bash- kieltä. Luodaan uusi komento käyttämällä micro- tekstieditoria. Komento tervehtii käytössä olevaa käyttäjää.

    micro komento

![image](https://user-images.githubusercontent.com/112503770/224565514-150d5dbc-11a0-4303-bfc2-bc567d4a1ff2.png)

Kokeillaan ajaa luotu komento, komennolla:

    bash komento

![image](https://user-images.githubusercontent.com/112503770/224565537-ed33cdae-f9e8-4e67-9391-84fec3c51979.png)

Lisätään x: siis ajo-oikeus komennolla chmod.

    chmod ugo+x komento

![image](https://user-images.githubusercontent.com/112503770/224565578-f72ba82c-8d8e-4d5c-8f9f-486a3f3edbcc.png)

Testataan komennon suorittamista.

    komento
    ./komento

![image](https://user-images.githubusercontent.com/112503770/224565646-7c55d3ea-7b4b-4626-beaa-2707432e7062.png)

Huomataan, että pelkkä komento ei vielä toimi, mutta `./komento toimii`. Komento pitää vielä siirtää hakemistoon, josta se voidaan ajaa koko järjestelmän sisäisesti. Testataan kopioinnin jälkeen `komento` .

    sudo cp ./komento /usr/local/bin/
    komento

![image](https://user-images.githubusercontent.com/112503770/224565985-25ef82d4-234c-405d-90ed-337d8c1e0673.png)

Huomataan, että `komento` toimii. Testataan kuitenkin vielä toisellä käyttäjällä. 

![image](https://user-images.githubusercontent.com/112503770/224567733-5576c4f5-9bfb-40f2-a086-f690132e90a8.png)

Nähdään, että komento toimii. 
klo 21.20
## b)
Luodaan uusi komento kaikille käyttäjille käyttäen python- kieltä.

## c)
Luodaan uusi komento kaikille käyttäjille, joka vaikuttaa useaempaan tiedostoon.

## Lähteet:
    https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/
    https://linuxputkis.wordpress.com/?query-8-page=2

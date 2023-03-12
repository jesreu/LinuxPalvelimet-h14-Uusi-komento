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
Luodaan uusi komento kaikille käyttäjille käyttäen python- kieltä. Tehdään samankaltainen komento kuin edellä.

    micro terve
    
![image](https://user-images.githubusercontent.com/112503770/224568564-729e7edc-d99f-4500-a313-bb45854ec9e4.png)

Komento kysyy käyttäjältä Kuka olet?, johon käyttäjä voi vastata miten haluaa. Käyttäjän syötetyn tiedon perusteella komento tulostaa tervehdysviestin.

    pyhton3 terve
    Kuka olet? Jesse
    Hei! Jesse

![image](https://user-images.githubusercontent.com/112503770/224568595-3c0f4dfe-8c1d-4158-8621-a3adf87b1e93.png)

Lisätään komennolle ajo oikeudet.

    chmod ugo+x terve
    
![image](https://user-images.githubusercontent.com/112503770/224569089-cb440cbc-ac4a-4112-94a3-805ca5fbee48.png)

Testataan komennon ajamista.

![image](https://user-images.githubusercontent.com/112503770/224569278-b9c2b050-5b47-4697-9474-f5314dfb43b6.png)

Huomataan, että valitus koskee shebang- riviä, joten siinä on todennäköisesti virhe. Pienellä googlettamisella saadaan selville, että oikea syntaksi olisi `#!/usr/bin/env python3`, joten käydään muokkaamassa tiedostoa. `micro terve`

![image](https://user-images.githubusercontent.com/112503770/224569412-aa4b8e3f-6d20-4d63-ba99-08651e52a1a2.png)

Yritetään ajaa komento uudelleen `./terve`
    
    Kuka olet? Jesse
    Hei! Jesse
    
![image](https://user-images.githubusercontent.com/112503770/224569609-253e156e-53ac-4c53-9bf2-b920535bbb3d.png)

Hyvin toimii. Kopioidaan komento vielä oikeaan hakemistoon. Testataan myös komennon ajamista.

    sudo cp ./komento /usr/local/bin/
    terve

![image](https://user-images.githubusercontent.com/112503770/224569676-205880be-fb6d-423a-9887-34e3a2fcdad8.png)

Toimii taas! Viimeisenä testinä kokeillaan eri käyttäjällä.

![image](https://user-images.githubusercontent.com/112503770/224569736-e22c218a-916e-4b57-b93e-d3efab95c60b.png)

## c)
Luodaan uusi komento kaikille käyttäjille, joka vaikuttaa useaempaan tiedostoon.


Käytetty aika: 1h + ?
## Lähteet:
    https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/
    https://linuxputkis.wordpress.com/?query-8-page=2
    https://stackoverflow.com/questions/2429511/why-do-people-write-usr-bin-env-python-on-the-first-line-of-a-python-script

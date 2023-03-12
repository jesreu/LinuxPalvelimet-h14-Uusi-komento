# LinuxPalvelimet-h14-Uusi-komento
    Kirjoittanut: Jesse Reunamo
    Kurssi:       Linux-palvelimet
    Linkki:       https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/


Aloitus klo 19:30
## a)
Luodaan uusi komento kaikille käyttäjille käyttäen bash- kieltä. Komento tervehtii käytössä olevaa käyttäjää.

    micro komento

![image](https://user-images.githubusercontent.com/112503770/224565514-150d5dbc-11a0-4303-bfc2-bc567d4a1ff2.png)

Kokeillaan ajaa luotu komento:

    bash komento

![image](https://user-images.githubusercontent.com/112503770/224565537-ed33cdae-f9e8-4e67-9391-84fec3c51979.png)

Lisätään x: siis ajo(execute) oikeus komennolla chmod.

    chmod ugo+x komento

![image](https://user-images.githubusercontent.com/112503770/224565578-f72ba82c-8d8e-4d5c-8f9f-486a3f3edbcc.png)

Testataan komennon suorittamista.

    komento
    ./komento

![image](https://user-images.githubusercontent.com/112503770/224565646-7c55d3ea-7b4b-4626-beaa-2707432e7062.png)

Huomataan, että pelkkä komento ei vielä toimi, mutta `./komento` toimii. Komento pitää vielä siirtää hakemistoon, josta se voidaan ajaa koko järjestelmän sisäisesti. Testataan kopioinnin jälkeen `komento` .

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

    python3 terve
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

    micro monikomente
    #!/usr/bin/bash
    
    for file in *
    do
        if [ -f $file ];
            then grep -H "kissa" $file
        fi
    done

![image](https://user-images.githubusercontent.com/112503770/224576313-fd5946f3-b634-488f-bab8-5279ff0d27ed.png)

Komento tulostaa kaikki rivit nykyisen hakemiston tiedostoista, jossa on sana kissa. Komentoon lisätty if lause, että komento pätee vain tiedostoihin. Testataan komentoa.

    bash monikomente

![image](https://user-images.githubusercontent.com/112503770/224576544-cb181c58-8146-4103-b854-ae7f4c8d635b.png)

Huomataan, että komento tulostaa osan itsestään, koska komento on tallennettuna siihen hakemistoon. Annetaan komennolle ajo-oikeudet ja testataan sitä.

    chmod ugo+x monikomente
    ./monikomente
    
![image](https://user-images.githubusercontent.com/112503770/224576629-e850fb4e-bc79-46fb-bb67-1faaf22d17bf.png)

Toimii hyvin, nyt tehdään komento järjestelmän kattavaksi.

    sudo cp ./monikomente /usr/local/bin/
    monikomente

![image](https://user-images.githubusercontent.com/112503770/224576720-997ddb04-81e5-40d5-97cc-1ec52d41f920.png)

Testaan vielä toisella käyttäjällä. Tein testin samassa hakemistossa kuin aiemmat, jotta nähdään, että komento osaa löytää oikeat tiedot.

![image](https://user-images.githubusercontent.com/112503770/224576745-def374f4-6a34-4e25-a22b-d53c1ad76401.png)

Toimii hyvin.

Käytetty aika: 3h
## Lähteet:
    https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/
    https://linuxputkis.wordpress.com/?query-8-page=2
    https://stackoverflow.com/questions/2429511/why-do-people-write-usr-bin-env-python-on-the-first-line-of-a-python-script

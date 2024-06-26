# Kolmas harjoitus, Toimiva versio
## x) lue ja tiivistä
### What is Git? ([Chacon and Straub 2014](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F))

- Git näkee datansa sarjana kuvakaappauksia miniatyyri-tiedostojärjestelmästä.
- Suurin osa Gitin toiminnoista tapahtuu paikallisesti ilman verkkoyhteyttä.
- Git varmistaa tietojen eheyden tarkistussummien avulla.
- Gitin perusprosessi koostuu kolmesta tilasta: modified, staged ja committed
   
### 'git add . && git commit; git pull && git push' 
- Git add . - komento päivittää indeksin työpuun nykyisellä sisällöllä ([Git 2024](https://git-scm.com/docs/git-add)).
- Git commit -komento tallentaa tehdyt muutokset, niiden tekijät, ajankohdan ja commit viestin ([Git 2024](https://git-scm.com/docs/git-commit)).
- Git pull -komento hakee muutokset etävarastosta nykyiseen paikalliseen versioon ([Git 2024](https://git-scm.com/docs/git-pull)).
- Git push -komento päivittää tehdyt muutokset ([Git 2024](https://git-scm.com/docs/git-push)).
 

### Varaston loki
- Varaston [terokarvinen/suolax/](https://github.com/terokarvinen/suolax/) lokissa näkyy 8 muutosta
- Kaikki muutokset ovat tehnyt Tero Karvinen 10.4

## a) Online
Loin uuden varaston GitHubiin. Lisäsin varastoon README.md ja GNU General Public License 3 -tiedostot.
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/4b871267-46a4-438d-a01b-238a9123a4dd)

> Kuva 1. Uuden varaston luomisnäkymä.

## b) Dolly
Kloonaa juuri tehty varasto itsellesi, tee muutoksia ja puske palvelimelle, jotta ne näkyvät webbipalvelimessa. Varaston kloonauksen tarvittava url on kopioitavana varaston webbipalvelimelta.

1. Kopioi varaston ssh-url
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/43a924f6-5c52-43bd-8691-2a93e9d47934)

> Kuva 2. 
2. Kloonasin varaston. Terminaalissa kloonaus suoritetaan alla olevalla komennolla, jonka perään laitetaan varaston yksilöllinen ssh-url.

        $ git clone <ssh-url>
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/66f6162d-8d89-4cb9-8ac3-310f16c65c68)

> Kuva 3. Varaston kloonaus onnistui
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/3517196f-0268-41e1-adf7-ae1a40394401)

> Kuva 4. Varastossa ei vielä ole muita tiedostoja kuin README.md ja lisenssi.
3. Loin varastoon uuden tekstitiedoston. Lisäsin siihen markdownin.

        $ micro Mee-töihin.md
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/d1eca7cc-f2c1-4758-b5f0-262be6f75b57)

> Kuva 5. Microlla tehty tekstitiedosto, johon lisäsin sisältöä
Jotta muutokset tulevat näkyviin webbipalvelimeen, on käytettävä komentoa, joka kertoo gitille tallennettavista muutoksista.

4. Selitin tehdyt muutokset engalnniksi käskymuodossa.

        $ git add . && git commit; git pull && git push
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/6781f1e6-e663-40b0-948c-505d8a322525)

> Kuva 6. Lisäsin tekstin "Add new file" ja tallensin tiedoston.
Nyt muutokset ovat valmiit ja ne pitäisivät olla näkyvissä webbipalvelimessa.

5. Tarkistin, että uusi luotu tiedosto ja siihen tehdyt muutokset näkyvät webbipalvelimessa.
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/b08998bc-b1b7-46f6-87c0-2ec22185e2bc)
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/3ed0eb9a-d8ba-4bd4-b6c3-72765828c6da)

> Kuvat 7 & 8. Muutokset onnistuivat.

## Doh!
Tein turhan muutokset gittiin ja en tallentanut niitä. Tuhosin muutokset  ‘git reset --hard’ -komennolla.
1. Loin uuden tiedoston.
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/8f7ffa99-802c-460c-b066-9bc6a7ba45ec)

> Kuva 9. Uusi luotu tiedosto.
2. Ideksoin uuden tiedoston ja tarkistin nykyisen työskentelytilan vaiheen.

        $ git add opiskele.md
        $ git status
    
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/4562a082-819b-43dd-bc58-3e7b58f40d33)

> Kuva 10. Tiedosto lisätty.
3. Tuhosin muutokset ja tarkistin, että muutokset oli tuhoutuneet.

        $ git reset --hard
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/362715f6-a868-4e41-b380-b3a4a4ee4bc4)

> Kuva 11. Turhat muutokset ovat tuhottu.

Edellä tehdyt turhat muutokset saatiin helpolla tavalla tuhottua, mutta tuhottuja muutoksia ei saa enään peruutettua.

## Tukki
Tarkastelin varastoni lokia. Lokeista voin nähdä tehnyt muutokset, niiden ajankohdat, tekijät ja commmit -viestin.

### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/14c9f3cd-cada-4482-ba14-0c1811ee284f)

> Kuva 12. Lokissa näkyy kaksi muutosta.

Lokin mukaan varastoon on tehty vain kaksi muutosta, varaston luominen ja tiedoston lisääminen. Tiedosto, jonka loin ja tuhosin ei näy lokissa ollenkaan. 
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/21929631-903d-4eb8-9f61-969920db11b8)

> Kuva 13. Tiedostoon tehnyt muutokset näkyvät myös webbipalvelimessa.

Olen aikaisemmin lisännyt nimeni ja sähköpostin gittiin käyttämällä alla olevia komentoja. Ne näkyvät lokissa.

        $ git config --global user.email "<sähköposti>"
        $ git config --global user.name "<nimi>"

## Suolattu rakki
Ajoin Salt-tiloja varatossani.
1. Loin hakemiston srv/salt/hello, johon tein init.sls -nimisen tiedoston

       $ micro init.sls
2. Tallensin init.sls -tiedostoon:
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/3f62691d-6b5f-4eeb-9b3d-dd9ff0a99500)

> Kuva 14. Salt tilan tallennus init.sls -kansioon.

3. Suoritin alla olevan komennon.

       $  sudo salt-call --local --file-root srv/salt/ state.apply hello

### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/84e95547-ded8-4b50-bff2-7800e32a642d)
> Kuva 15. Virheilmoitus komennon jälkeen.
Yritin noin tunnin ajan selvitellä ongelmaa kokeilemalla ja tarkistamalla eri asioita, mutta en päässyt tästä eteenpäin.


## Vapaaehtoinen
Aikaisemmat tehtävät olin tehnyt Mac koneella, nyt kokeilinkin Gittiä Debianilla. Minulla oli jo Debian virtuaalikone käytettävissä, johon asensin gitin. 
1. Asensin gitin

       $ sudo apt-get -y install git
2. Loin ssh-avaimet. Git luo avaimet ja kertoo hakemiston mihin laittoi kopioitavan julkisen avaimen.

       $ ssh key-gen
3. Kopioi julkinen avain ja liitä se githubiin 'New SSH key' -kohtaan.
4. Kopioi Githubista kurssin reposition ssh url

       $ git clone <ssh-url>

Kaikki gitin toiminnot ovat samat Mac ja Debian koneilla.

5. Tein uuden tiedoston

       $ micro Opiskele.md
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/e2ac8732-0beb-4fe3-b4d0-bead0c17327d)

> Kuva 16. Lisäsin tiedostoon siältöä.

6. Ajoin komennon `git add . && git commit && git pull && git push`. Muutokset päivittyivät webbipalvelimeen.
### ![image](https://github.com/Lambizzzz/infra-as-code/assets/148875838/b53d864b-dd47-4ccb-bfd7-b76a9aeefba4)

> Kuva 17. Muutokset näkyvät webbipalvelimessa.

   
## Lähteet
https://git-scm.com/docs/git-add

https://git-scm.com/docs/git-commit

https://git-scm.com/docs/git-pull

https://git-scm.com/docs/git-push

https://terokarvinen.com/2024/configuration-management-2024-spring/





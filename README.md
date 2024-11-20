# Nollatoleranssi-hankkeen liitesivusto

Tämä repo sisältää Nollatoleranssi-hankkeen liitesivuston lähdekoodin. Liitesivusto on saatavilla osoitteessa: <https://osaal.github.io/nollatoleranssi_liitesivusto>.

## Asennus

Liitesivusto on rakennettu käyttäen Quarto-järjestelmää. Jotta voit tarkastaa ja rakentaa liitesivuston itse, tarvitset vähintään seuraavat työkalut:

-   R-ohjelmointikieli, versio 4.3.2 ("Eye Holes")
-   Quarto-järjestelmä, versio 1.3.450
-   renv-pakettijärjestelmä, versio 1.0.2

Asenna ensin yllämainitut työkalut. Uudempia versioita ei olla kokeiltu, mutta kirjoitushetkellä ongelmia ei pitäisi olla.

Lataa sitten Git-repositorio valitsemallasi tavalla.

Ennen renderöintiä, aktivoi Renv kansiossa R-komennolla `renv::restore()`. Tämä varmistaa, että sinulla on kaikki tarvittavat R-paketit asennettuna. Renv asentaa paketit paikallisesti kansioon, eli järjestelmäpaketteja ei tarvitse muuttaa tai päivittää.

Ensimmäisen renderöinnin yhteydessä kannattaa poistaa kansio `/_freeze` kokonaan, jotta Quarto varmasti renderöi jokaisen luvun. HUOM: Renderi voi kestää useita tunteja!

Renderöi koko sivusto komentokehotteessa komennolla `quarto render`.

## Repositorion rakenne

-   /: Yläkansiosta löytyy muun muassa:
    -   Kaikki `qmd`-tiedostot -- näitä muokkaamalla voit tehdä muutoksia sivuston sisältöön

    -   `_quarto.yml`: Verkkosivun rakenteen ja formatoinnin määrittelyt

    -   `custom.scss`: Eräiden visuaalisten elementtien määrittelyt (mm. sivuston väriteema)

    -   `nollatoleranssi_liitesivusto.Rproj`: RStudio-ohjelman projektitiedosto (tarpeellinen vain, jos käytät RStudiota tiedostojen muokkaamiseen)

    -   `references.bib`: Kaikki verkkosivulla käytetyt viitteet BibTeX-muodossa

    -   `renv.lock`: Renv-järjestelmän pakettien lukkotiedosto
-   /data: Avoimesti saatavat datatiedostot, enimmäkseen kirjallisuuskatsauksen osioita varten
-   /docs: Renderöity verkkosivu löytyy täältä (deployattava, jos verkkosivu julkaistaan)

## Käyttö

Luvut 1-11 ovat täysin toistettavissa, eli niiden lähdekoodit voidaan ajaa paikallisesti ilman mitään lisäasetuksia.

Luvut 12-20 eivät ole toistettavissa, sillä niiden vaatimat aineistotiedostot eivät ole tietosuojasyistä saatavilla. Luvut ovat olemassa dokumentaatiosyistä.

Luvut 21-35 ovat toistettavissa, jos käyttäjällä on hallussaan Nollatoleranssi-hankkeen anonymisoitu data-aineisto (tulossa Tietoarkistoon tutkijoiden käyttöön).

HUOM: Data-aineisto tulee olla sijoitettuna sijaintiin `output/valmisdata.csv`.

Jokainen luku on rakennettu itsenäisesti suoritettavaksi, eli lukujen välillä ei siirry mitään tietoja, muuttujia tmv.

Oletusasetuksena Quartolle on määritelty `eval: false`, eli koodiosiot eivät renderöidy automaattisesti. Uusiin renderöitäviin tiedostoihin pitää lisätä YAML-headeri merkinnällä `eval: true` (tai vaihtoehtoisesti yksittäisiin koodiblokkeihin), jotta ne renderöityvät. Repositoriossa esiintyvissä tiedostoissa tämä on valmiiksi lisätty, mutta eräät koodiblokit ovat merkitty `eval: false`, sillä ne aiheuttavat virheitä.

Oletuksena Quarto tallentaa kopion renderitiedostoista kansioon `/_freeze`. Tällöin Quarto renderöi luvun uudelleen vain, jos kansion renderitiedostojen hash-luvut ovat muuttuneet (eli lähdekoodia on muokattu). Asetuksen voi muuttaa yksittäisille sivuille tai koodiblokeille halutessaan.

Renderitulokset sijoittuvat aina kansioon `/docs`. Jos renderöity verkkosivu halutaan deployata, kaikki tarvittavat tiedostot löytyvät tästä kansiosta.

## Kontribuutiot

Tähän GitHub-repositorioon ei oteta vastaan muutoksia ollenkaan. Repositorio on olemassa dokumentoinnin ja myöhemmän toistettavuuden vuoksi.

Hankkeen lopussa repositorio merkitään arkivoiduksi, jolloin muutoksia ei enää voida tehdä.

## Lisenssi

Lähdekoodia voi vapaasti käyttää [MIT](https://choosealicense.com/licenses/mit/)-lisenssillä. Jollei erikseen mainita, kuviot ja visuaaliset elementit ovat käytettävissä [Creative Commons 4.0 Nimeä](https://creativecommons.org/licenses/by/4.0/deed.fi) -lisenssillä.

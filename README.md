# RegioData API Documentation

## 1. Read data

A call to https://us-central1-mcs-pim.cloudfunctions.net/products?apiKey=YOUR_API_KEY returns all available products.

Contact hannes.kleist@fooxes.de to get your api key.

## 2. Write data

#### 2.1. Create token with registered user

```
curl -X "POST" "https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key=AIzaSyAwutv86wQC4-c9kT5FvGhiwJddUXmvQZc" \
     -H 'Content-Type: application/json; charset=utf-8' \
     -d $'{
  "email": "john@doe.com",
  "returnSecureToken": true,
  "password": "super-hard-password"
}'
```

#### 2.2 Grab the `idToken`

#### 2.3. POST to /updateProduct

Call https://us-central1-mcs-pim.cloudfunctions.net/updateProduct

Set the field "sys_id" to update a product. 

Leave it empty to create a new product.

Returns a status and the id of the product.

```
{
    "status": "success",
    "id": "YbF5oYMFfCC7d7aCMrvD"
}
```

Example: 

Replace "THE_ID_TOKEN" with your id token.

```
curl -X "POST" "https://us-central1-mcs-pim.cloudfunctions.net/updateProduct" \
     -H 'Content-Type: application/json' \
     -H 'Authorization: THE_ID_TOKEN' \
     -d $'{
  "wein_verschlussart_id": "echter_korken",
  "log_gewicht_vke_brutto": 1596,
  "pbm_produktname_mittel": "Champagne Pommery a Reims-France 12:19",
  "pbm_saisonartikel_TRUE": false,
  "log_dim_vpe1_hoehe": 33,
  "markinf_produktbeschreibung_kurz": "CHAMPAGNE POMMERY ROYAL BRUT, CHAMPAGNE AC, GESCHENKETUI",
  "wgsa_mindestalter_kaeufer_konsument": 18,
  "pbm_bezeichnung_des_lebensmittels": "Champagner",
  "preis_emcs_verbrauchssteuergruppe_id": "z1",
  "log_gewicht_vp_vpe1": 98,
  "nwae_mehrfach_ungesaettigte_fettsaeuren_flag_id": "<",
  "pbm_warengruppe_id": "sekt_schaumwein",
  "log_dim_vpe1_breite": 9,
  "log_gewicht_vpe1_brutto": 1694,
  "allg_dinkel": "nein_ohne_analyse",
  "allg_macadamianuesse": "nein_ohne_analyse",
  "allg_eier": "nein_ohne_analyse",
  "allg_cashewnuesse": "nein_ohne_analyse",
  "nwae_einfach_ungesaettigte_fettsaeuren_flag_id": "<",
  "allg_walnuesse": "nein_ohne_analyse",
  "ihf_abtropfgewicht_inhalt": 200,
  "log_palettenart_id": "keine_palette",
  "wein_geographische_angabe_id": "champagne",
  "urhk_ursprungsland_intrastat_id": "fr",
  "allg_senf": "nein_ohne_analyse",
  "allg_pecannuesse": "nein_ohne_analyse",
  "log_gewicht_vp_vke": 850,
  "media_images": [
    "https://storage.googleapis.com/meck-schweizer.appspot.com/3/7cf9a108-e464-4f50-ab52-686b3c74a971.jpg"
  ],
  "pbm_rechtlicher_status_id": "lebensmittel",
  "allg_sesam": "nein_ohne_analyse",
  "allg_erdnuss": "nein_ohne_analyse",
  "ihf_packungsinhalt_art_id": "karton",
  "allg_glutenhaltiges_getreide": "nein_ohne_analyse",
  "ihf_wiegeartikel_gh": false,
  "pack_verpackungsmaterial_vpe1_de": "pappe_papier_kartonagen_pkk",
  "zut_zutatenlegende": [
    "aus_regionaler_Erzeugung"
  ],
  "wein_land_id": "FR",
  "wein_saeuregehalt_orientierungswert": 3.3,
  "preis_emcs_produktbuchungsgruppe_id": "W300",
  "urhk_verarbeitungsland_id": "FR",
  "kaese_fettgehalt_im_milchanteil_flag_id": ">",
  "idnr_artikelnr_inverkehrbringer": "152956",
  "ihf_abweichende_verkaufseinheit": false,
  "nwae_gesaettigte_fettsaeuren_flag_id": "<",
  "last_contributor": "JpkZcFtY2jWOjWF2x6JvTUqGNxm2",
  "wgsa_alkohol": 12.5,
  "idnr_gtin": "3352370002830",
  "log_dim_vke_hoehe": 32,
  "creator": "Y2ihIGGUNIRlYHLYzSo4XJgrk5l1",
  "ihf_packungsinhalt_mehrere_stuecke": false,
  "allg_paranuesse": "nein_ohne_analyse",
  "nwae_mehrwertige_alkohole_flag_id": "<",
  "ihf_nettofuellmenge_oder_mengenangabe": 750,
  "allg_lactose": "nein_ohne_analyse",
  "nwae_fett_flag_id": "<",
  "contributors": [
    "JpkZcFtY2jWOjWF2x6JvTUqGNxm2"
  ],
  "wein_geschmack_kurz": "komplex & reif",
  "nwae_eiweiss_flag_id": "<",
  "ihf_gewicht_wiegeartikel": 200,
  "milch_fettgehalt_im_milchanteil_flag_id": ">",
  "wein_rebsorten": "33% Chardonnay, 33% Pinot Meunier, 34% Pinot Noir",
  "wein_traditionelle_qualitaetsbezeichnungen": [
    "schaumwein"
  ],
  "allg_milch": "nein_ohne_analyse",
  "allg_haselnuesse": "nein_ohne_analyse",
  "pbm_warengruppe_pfad": "/Getraenke (auch gekuehlte)/Wein, Schaumwein/",
  "pbm_markenname": "Vranken-Pommery",
  "allg_lupine": "nein_ohne_analyse",
  "allg_sellerie": "nein_ohne_analyse",
  "allg_hafer": "nein_ohne_analyse",
  "allg_fisch": "nein_ohne_analyse",
  "allg_sulfit": "ja_laut_rezeptur_enthalten",
  "nwae_kohlenhydrate_flag_id": "<",
  "log_dim_vke_tiefe": 9,
  "wein_geschmack_schaumwein_id": "brut ",
  "allg_pistazien": "nein_ohne_analyse",
  "allg_mandeln": "nein_ohne_analyse",
  "nwae_staerke_flag_id": "<",
  "pack_pfandpflicht_artikel_de_id": "kein_pfand",
  "wein_restzucker_orientierungswert_id": "12",
  "log_vpe1_art_id": "kartons",
  "preis_grundpreiseinheit_endverbraucher_id": "liter",
  "nwae_salz_flag_id": "<",
  "fleisch_reifezeit_duration_id": "Tag(e)",
  "allg_gerste": "nein_ohne_analyse",
  "ihf_wiegeartikel_eh": false,
  "kerzen_brenndauer_unit_id": "Stunden",
  "urhk_gu_gga_gts": [
    "ggA"
  ],
  "allg_krebstiere": "nein_ohne_analyse",
  "urhk_region": "Champagne",
  "nwae_ballaststoffe_flag_id": "<",
  "pack_verpackungsmaterial_artikel_de": "glas",
  "milch_fettgehalt_absolut_flag_id": ">",
  "nwae_mehrwertige_alkohole": 50,
  "allg_soja": "nein_ohne_analyse",
  "preis_mwst_id": "null",
  "allg_khorasan_weizen": "nein_ohne_analyse",
  "wein_produzent_oder_hersteller_regalschild": "Vranken-Pommery ",
  "log_dim_vpe1_tiefe": 9,
  "allg_roggen": "nein_ohne_analyse",
  "allg_weichtiere": "nein_ohne_analyse",
  "zut_zutatenverzeichnis": "33% Chardonnay\\n33% Pinot Meunier\\n34% Pinot Noir",
  "ihf_abtropfgewicht_einheit_id": "g",
  "vitmin_mgo_wert": 200,
  "preis_empfohlener_verkaufspreis_deutschland": 36.9,
  "ihf_nettofuellmenge_oder_mengenangabe_einheit_id": "Milliliter (ml)",
  "ihf_gewicht_spanne_von_einheit_id": "kg",
  "urhk_verpackungsland_id": "FR",
  "log_rlz_hersteller_gh_duration_id": "Tage",
  "urhk_hersteller_id": "JpkZcFtY2jWOjWF2x6JvTUqGNxm2",
  "sys_created": {
    "seconds": 253402300799,
    "nanoseconds": 0
  },
  "sys_gesamtstatus": "oeffentlich",
  "ihf_verpackungsart_artikel_id": "flasche_glas",
  "markinf_produktbeschreibung_mittel": "Der Pommery Brut Royal ueberzeugt auf der ganzen Linie: das Mousseux ist unuebertrefflich feinperlend und ein betoerender Strauss an intensiven Aromen eroeffnet sich dem Geniesser. Auch am Gaumen praesentiert er sich leicht und frisch mit klaren Fruchtaromen. Ein begeisternder Champagner, der belebt und beste Laune macht! Kommt in schoener Geschenkverpackung.",
  "idnr_gtin_alternativ": "694199006365",
  "pbm_produktname_kurz": "Pommery Brut Royal",
  "nwae_zucker_flag_id": "<",
  "pbm_etiketten_sprachen": [
    "FR"
  ],
  "pbm_etiketten_in_anderen_sprachen": true,
  "pbm_artikel_art_id": "standardartikel",
  "allg_sonstiges_glutenhaltiges_getreide": "nein_ohne_analyse",
  "pack_registrierungsnr_verpackungsregister": "shsjajfkLNF",
  "log_gewicht_vke_netto": 750,
  "ihf_gewicht_wiegeartikel_flag_id": "Circa",
  "sys_last_modified": {
    "seconds": 253402300799,
    "nanoseconds": 0
  },
  "pbm_produktname_lang": "Champagne Pommery a Reims-France, Brut Royal",
  "allg_schalenfruechte": "nein_ohne_analyse",
  "pbm_endverbraucher": true,
  "milch_fett_i_tr_flag_id": ">",
  "allg_weizen": "nein_ohne_analyse",
  "urhk_ursprungsland": [
    "FR"
  ],
  "kaese_fettgehalt_absolut_id": ">",
  "log_vpe1_gtin": "3352379006365",
  "creator_display_name": "Theresa Silberstein",
  "kaese_reifezeit_duration_id": "Tag(e)",
  "log_dim_vke_breite": 9,
  "log_vpe1_menge": 1,
  "ihf_gewicht_spanne_bis": 200
}'
```

## 3. Data model details

Get the latest data model at https://app.regiodata.org/data-models/product.json

### 3.1 Properties

- `id`: String, Identifier, i.e. "allg_fisch"
- `title`: String, The title of the property, i.e. "Fisch"
- `type`: String, The type, written as the HTML form element, i.e. "input[type="radio"]",
- `required`: Boelean, is the field required or optional, i.e. true
- `fields`: String, a reference to an enum, only relevant when type == select, i.e."[allergies]"
- `description_short`: String, A short description, "Angabe gleich, kleiner oder kleiner gleich"
- `description_long`: String, A longer description, i.e. "FISCH und daraus gewonnene Erzeugnisse (außer Fischgelatine, die als Trägerstoff...- section: String, One of 9 sections, "3. Inhaltsstoffe & Produkthinweise"
- `sub_section`: String, One of 23 sub sections, "3.2 Allergene & Unverträglichkeiten"

### 3.2 Property Types

- `input[type="date"]`, a date field as a string in the format YYYY-MM-DD, i.e. "2024-07-25"
- `input[type=\"datetime-local\" readonly=true]`, a structured date time object with seconds and nanoseconds since 1970-01-01, i.e. {"seconds": 1652310819,"nanoseconds": 0}
- `input[type="number"], step="0.01"]`, a floating number, i.e. 0.134
- `input[type="number"]`, a integer number, i.e. 123
- `input[type="radio"]`, a boolean, i.e. true
- `select[multiple=true]`, an array of Strings, i.e. ["aus_regionaler_Erzeugung", "aus_kontrolliert_oekologischer_erzeugung"]
- `input[type="file"]`, an array of URLs, ["https://storage.googleapis.com/mcs-pim.appspot.com/ZHg24eriKfJWxpWEk8YG/media_images/foto.png"]
- `textarea`, a long string, i.e. "Lorem ipsum"
- `shortString`, a short string with less than 255 characters, i.e. "Lorem ipsum"
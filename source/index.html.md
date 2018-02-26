---
title: Verkehrsrundschau API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:


includes:
  - errors

search: true
---

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "http://rest-api.verkehrsrundschau.de"
  -H "X-Auth-Token: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

This API expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Auth-Token: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# News

## Get All News from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/news/ids/1519257600"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2135028",
    "2135002",
    "2134982",
    "2134976",
    "2134973",
    "2134937",
    "2134926",
    "2134150",
    "2134636"
]
```

This endpoint retrieves all news with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/news/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a Specific News


```shell
curl "http://rest-api.verkehrsrundschau.de/news/detail/2135002"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2135002",
    "title": "Logimat: M3 mit neuen App-Funktionen",
    "online_date": "2018-02-26 13:05:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2018-02-26 11:17:48",
    "teaser": "Dr. Malek stellt in Stuttgart die Transportmanagementsoftware M3 Logisticware im komplett überarbeiteten Design sowie die um neue Funktionen und Module erweiterte M3 App vor.",
    "text": "<p>Dresden. Dr. Malek Software (Halle 8, Stand A06) zeigt auf der Logimat sein Transportmanagementsystem M3 Logisticware im komplett &uuml;berarbeiteten Design. So wurde die Software f&uuml;r Windows 10 optimiert und erm&ouml;glicht jetzt zudem die Nutzung mehrerer Monitore mit unterschiedlichen Formaten und Aufl&ouml;sungen. Dar&uuml;ber hinaus verf&uuml;gt M3 neuerdings &uuml;ber spezialisierte Erfassungsmasken f&uuml;r verschiedene Gesch&auml;ftsbereiche wie St&uuml;ckgut oder Ladungsverkehr und neue Features f&uuml;r schnelleres Arbeiten und Recherchieren. &ldquo;Bei der Weiterentwicklung der Oberfl&auml;chen haben wir darauf geachtet, dass sich die Anwender unserer rund 400 Kunden sofort damit zurechtfinden&rdquo;, betont Gesch&auml;ftsf&uuml;hrer Ralf Malek.</p>\r\n<p><b>KEP-L&ouml;sung in der App</b></p>\r\n<p>Ebenfalls weiterentwickelt wurde die M3 App f&uuml;r das mobile Auftragsmanagement. Neben den App-Versionen f&uuml;r St&uuml;ckgut und Ladungsverkehr gibt es mit der KEP-Variante inzwischen auch eine L&ouml;sung f&uuml;r Paket und Kurierdienste mit kleinteiligen Sendungen. Die App verf&uuml;gt jetzt au&szlig;erdem &uuml;ber weitere Funktionalit&auml;ten f&uuml;r die Hallen-Umschlagscannung. In Verbindung mit der ebenfalls neuen Scannerserie TC2X von Zebra will das Dresdner Familienunternehmen die Neuerungen live am Messestand demonstrieren. (mh)</p>",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5709/Malek1920.jpg",
    "image_copyright": "Dr. Malek Software",
    "image_caption": "<p>Die M3 App verf&uuml;gt jetzt &uuml;ber weitere Funktionalit&auml;ten f&uuml;r die Hallen-Umschlagscannung</p>",
    "navigation": "NFZ + Fuhrpark",
    "tags": "Markt Lkw-Landverkehr & Stückgut,Markt KEP-Markt,IT Speditions-Software,IT Telematik Kommunikation Lkw Fahrer,Event Logimat Messe,Dr. Malek Software",
    "attachments": [],
    "published": 1
}
```

This endpoint retrieves a specific news.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/news/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the news to retrieve

# Magazine

## Get All Magazine Issues from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/magazine_issue/ids/1514764800"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2133000",
    "2064141",
    "2062176",
    "2059972",
    "2057120",
    "2052296"
]
```

This endpoint retrieves all Magazine Issues with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/magazine_issue/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a Specific Magazine Issue


```shell
curl "http://rest-api.verkehrsrundschau.de/magazine_issue/detail/2133000"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2133000",
    "title": "Ausgabe 08/2018",
    "online_date": "2018-02-22 15:00:00",
    "change_date": "2018-02-21 10:23:06",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/4903/thumbnails/90003_2018_73_08_I_001_Titelseite_EA_Roadshow_250028_print.pdf.15633211.png",
    "issue": "08",
    "year": "2018",
    "text": "",
    "url_epaper_lesen": "http://digital.verkehrsrundschau.de/verkehrsrundschau082018/"
}
```

This endpoint retrieves a specific Magazine Issue.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/magazine_issue/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Issue to retrieve

## Get All Magazine Articles from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/magazine_article/ids/1517443200"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2133082",
    "2133079",
    "2133076",
    "2133066",
    "2133064",
    "2133062",
    "2133057",
    "2133051",
    "2133049",
    "2133047",
    "2133045",
    "2133043",
    "2133040",
    "2133036",
    "2133034",
    "2133032",
    "2133008"
]
```

This endpoint retrieves all Magazine Articles with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/magazine_article/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a Specific Magazine Article


```shell
curl "http://rest-api.verkehrsrundschau.de/magazine_article/detail/2133082"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2133082",
    "issue_id": "2133000",
    "title": "Alles was Nutzfahrzeuge betrifft, kommt ins Portfolio",
    "online_date": "2018-02-22 15:00:00",
    "change_date": "2018-02-21 12:40:37",
    "kicker": "Krone ET-Zentrallager",
    "teaser": "Interview mit Ralf Faust, Geschäftsführer Kundendienst, Service und Telematik der Krone Gruppe, über die Funktion des neuen Zentrallagers sowie die künftigen Expansionspläne.",
    "page_number": "45",
    "text": "<p><strong>Wieso war die Neuordnung des Ersatzteilgesch&auml;ftes geboten?</strong></p>\r\n<p>Der Umsatz unseres ET-Gesch&auml;ftes ist in den letzten sechs Jahren von 12 auf 40 Millionen Euro gestiegen. Das war auf Dauer mit unseren alten Strukturen nicht mehr zu bew&auml;ltigen. Zudem versenden wir rund 50 Prozent der Ersatzteile europaweit im Nachtsprung. Das erfordert eine moderne Logistik. Wir sehen zudem, dass unsere Kunden eine hohe Affinit&auml;t zur Online-Bestellung haben und bereits eine Million Euro Umsatz pro Monat im Online-Shop machen. Und die Kunden bestellen selbst Teile, die 13,6 Meter lang und 50 Kilo schwer sind. Um das realisieren zu k&ouml;nnen, mussten wir neu denken. Das Ergebnis ist unser neues Zentrallager in Herzlake.</p>\r\n<p><strong>Bei der ET-Versorgung geht es meist um die Schnelligkeit. Wie schnell ist Krone mit dem neuen Lager?</strong></p>\r\n<p>Ich erl&auml;utere das mal an einem Beispiel: Wir haben einen gro&szlig;en Flottenbetreiber in der Kundschaft, der bis zu 10.000 Trailer von Krone im Einsatz hat und selbst repariert. Nach unseren Analysen betr&auml;gt die durchschnittliche Zustellzeit 2,9 Tage. Das mag f&uuml;r sich betrachtet mehr sein als die propagierte 24-Stunden-Lieferung. Aber wir sprechen da vom Durchschnitt aller Teile. Und das unabh&auml;ngig von der Varianz und Destination in Europa.</p>\r\n<p><strong>Das neue Zentrallager ist aber nicht Krones einziges ET-Lager?</strong></p>\r\n<p>Nein, wir verf&uuml;gen &uuml;ber sechs Hubs in Europa f&uuml;r die lokale Belieferung. Aktuell planen wir die Vernetzung - inklusive des ET-Lagers in der T&uuml;rkei. Dann weiter sind geplant England - trotz Brexit - und Spanien.</p>\r\n<p><strong>Geschwindigkeit ist eines - bringt aber wohl nur etwas, wenn der Kunde auch das richtige Teil bekommt?</strong></p>\r\n<p>V&ouml;llig richtig. Aber da haben wir zur IAA 2016 unser OR-Code-System eingef&uuml;hrt. &Uuml;ber das Scannen des QR-Codes mit dem Smartphone lassen sich jedes Fahrzeug und die darin verbauten Bauteile ganz exakt identifizieren. Die Nutzer k&ouml;nnen &uuml;ber ihre Login-Daten alle wichtigen Infos abrufen. Aktuell haben wir bereits etwa 250.000 Trailer hinterlegt. Einiges m&uuml;ssen wir noch nachhalten und ein paar &auml;ltere Modelle manuell einpflegen. Aber ich gehe davon aus, dass wir zeitnah alle etwa 350.000 Anh&auml;nger und Auflieger, die sich auf Europas Stra&szlig;en befinden, im System haben werden.</p>\r\n<p><strong>Was sind denn die g&auml;ngigsten Ersatzteile?</strong></p>\r\n<p>Wir verkaufen pro Monat 400 (!) Profiliner-T&uuml;ren. F&uuml;r Gro&szlig;kunden bevorraten wir sogar Komponenten in passenden Farben. Genau genommen k&ouml;nnte man aus den ET-Paketen, die wir f&uuml;r einige gro&szlig;e Flottenbetreiber bevorraten, zwei komplette Trailer bauen. Das mag sich &uuml;bertrieben anh&ouml;ren - ist es aber nicht.</p>\r\n<p><strong>Geben Sie uns doch noch ein paar Eckdaten zum neuen Zentrallager.</strong></p>\r\n<p>Wir haben aktuell 10.000 Artikel im Lager, die Kunden k&ouml;nnen &uuml;ber unseren Online-Shop rund 50.000 Artikel bestellen. Am Lager haben wir aktuell alleine 600 T&uuml;ren und wir arbeiten pro Monat rund 5000 Auftr&auml;ge ab. Dabei haben wir mit 1,5 Prozent einen sehr kleinen Anteil an Retouren. Und auf dem Gel&auml;nde h&auml;tten wir Platz, um unsere 105 Meter lange Halle noch mal zu spiegeln und weitere 8000 Quadratmeter Lagerfl&auml;che zu realisieren.</p>\r\n<p><strong>Klingt nach gro&szlig;en Pl&auml;nen:</strong></p>\r\n<p>Die haben wir auch! Wir wollen uns abseits der Ersatzteile f&uuml;r unsere Lafetten, Trailer und Wechselbr&uuml;cken zu einem gro&szlig;en Ersatzteilh&auml;ndler entwickeln. Alles was Bezug zum Nutzfahrzeug hat, etwa Bremsbel&auml;ge, Reifen, Sto&szlig;d&auml;mpfer, wollen wir &uuml;ber kurz oder lang ins Portfolio nehmen. Nur ein Beispiel: Krone verkauft alleine 5000 Reifen unserer Eigenmarke pro Jahr. &Uuml;ber alle Teile gehen aktuell 70 Prozent unserer Lieferungen ins Ausland. Gestern hatten wir die erste Lieferung nach S&uuml;dkorea. Auch Chile war schon dabei. Da ist also noch Luft nach oben.</p>",
    "category": "Test + Technik",
    "image": "https://media1.autohaus.de/sixcms/media.php/4903/thumbnails/90003_2018_73_08_I_044-046_Krone_ET-Zentrum_249369_print.15633412.pdf.15633415.jpg",
    "tags": "VR Interview,Krone Trailer 1112",
    "published": 1
}
```

This endpoint retrieves a specific Magazine Article.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/magazine_article/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Article to retrieve

## Get All Magazine Articles by Magazine Issue

```shell
curl "http://rest-api.verkehrsrundschau.de/magazine_article/by_issue/2133000"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    {
        "id": "2133082",
        "issue_id": "2133000",
        "title": "Alles was Nutzfahrzeuge betrifft, kommt ins Portfolio",
        "online_date": "2018-02-22 15:00:00",
        "change_date": "2018-02-21 12:40:37",
        "kicker": "Krone ET-Zentrallager",
        "teaser": "Interview mit Ralf Faust, Geschäftsführer Kundendienst, Service und Telematik der Krone Gruppe, über die Funktion des neuen Zentrallagers sowie die künftigen Expansionspläne.",
        "page_number": "45",
        "text": "<p><strong>Wieso war die Neuordnung des Ersatzteilgesch&auml;ftes geboten?</strong></p>\r\n<p>Der Umsatz unseres ET-Gesch&auml;ftes ist in den letzten sechs Jahren von 12 auf 40 Millionen Euro gestiegen. Das war auf Dauer mit unseren alten Strukturen nicht mehr zu bew&auml;ltigen. Zudem versenden wir rund 50 Prozent der Ersatzteile europaweit im Nachtsprung. Das erfordert eine moderne Logistik. Wir sehen zudem, dass unsere Kunden eine hohe Affinit&auml;t zur Online-Bestellung haben und bereits eine Million Euro Umsatz pro Monat im Online-Shop machen. Und die Kunden bestellen selbst Teile, die 13,6 Meter lang und 50 Kilo schwer sind. Um das realisieren zu k&ouml;nnen, mussten wir neu denken. Das Ergebnis ist unser neues Zentrallager in Herzlake.</p>\r\n<p><strong>Bei der ET-Versorgung geht es meist um die Schnelligkeit. Wie schnell ist Krone mit dem neuen Lager?</strong></p>\r\n<p>Ich erl&auml;utere das mal an einem Beispiel: Wir haben einen gro&szlig;en Flottenbetreiber in der Kundschaft, der bis zu 10.000 Trailer von Krone im Einsatz hat und selbst repariert. Nach unseren Analysen betr&auml;gt die durchschnittliche Zustellzeit 2,9 Tage. Das mag f&uuml;r sich betrachtet mehr sein als die propagierte 24-Stunden-Lieferung. Aber wir sprechen da vom Durchschnitt aller Teile. Und das unabh&auml;ngig von der Varianz und Destination in Europa.</p>\r\n<p><strong>Das neue Zentrallager ist aber nicht Krones einziges ET-Lager?</strong></p>\r\n<p>Nein, wir verf&uuml;gen &uuml;ber sechs Hubs in Europa f&uuml;r die lokale Belieferung. Aktuell planen wir die Vernetzung - inklusive des ET-Lagers in der T&uuml;rkei. Dann weiter sind geplant England - trotz Brexit - und Spanien.</p>\r\n<p><strong>Geschwindigkeit ist eines - bringt aber wohl nur etwas, wenn der Kunde auch das richtige Teil bekommt?</strong></p>\r\n<p>V&ouml;llig richtig. Aber da haben wir zur IAA 2016 unser OR-Code-System eingef&uuml;hrt. &Uuml;ber das Scannen des QR-Codes mit dem Smartphone lassen sich jedes Fahrzeug und die darin verbauten Bauteile ganz exakt identifizieren. Die Nutzer k&ouml;nnen &uuml;ber ihre Login-Daten alle wichtigen Infos abrufen. Aktuell haben wir bereits etwa 250.000 Trailer hinterlegt. Einiges m&uuml;ssen wir noch nachhalten und ein paar &auml;ltere Modelle manuell einpflegen. Aber ich gehe davon aus, dass wir zeitnah alle etwa 350.000 Anh&auml;nger und Auflieger, die sich auf Europas Stra&szlig;en befinden, im System haben werden.</p>\r\n<p><strong>Was sind denn die g&auml;ngigsten Ersatzteile?</strong></p>\r\n<p>Wir verkaufen pro Monat 400 (!) Profiliner-T&uuml;ren. F&uuml;r Gro&szlig;kunden bevorraten wir sogar Komponenten in passenden Farben. Genau genommen k&ouml;nnte man aus den ET-Paketen, die wir f&uuml;r einige gro&szlig;e Flottenbetreiber bevorraten, zwei komplette Trailer bauen. Das mag sich &uuml;bertrieben anh&ouml;ren - ist es aber nicht.</p>\r\n<p><strong>Geben Sie uns doch noch ein paar Eckdaten zum neuen Zentrallager.</strong></p>\r\n<p>Wir haben aktuell 10.000 Artikel im Lager, die Kunden k&ouml;nnen &uuml;ber unseren Online-Shop rund 50.000 Artikel bestellen. Am Lager haben wir aktuell alleine 600 T&uuml;ren und wir arbeiten pro Monat rund 5000 Auftr&auml;ge ab. Dabei haben wir mit 1,5 Prozent einen sehr kleinen Anteil an Retouren. Und auf dem Gel&auml;nde h&auml;tten wir Platz, um unsere 105 Meter lange Halle noch mal zu spiegeln und weitere 8000 Quadratmeter Lagerfl&auml;che zu realisieren.</p>\r\n<p><strong>Klingt nach gro&szlig;en Pl&auml;nen:</strong></p>\r\n<p>Die haben wir auch! Wir wollen uns abseits der Ersatzteile f&uuml;r unsere Lafetten, Trailer und Wechselbr&uuml;cken zu einem gro&szlig;en Ersatzteilh&auml;ndler entwickeln. Alles was Bezug zum Nutzfahrzeug hat, etwa Bremsbel&auml;ge, Reifen, Sto&szlig;d&auml;mpfer, wollen wir &uuml;ber kurz oder lang ins Portfolio nehmen. Nur ein Beispiel: Krone verkauft alleine 5000 Reifen unserer Eigenmarke pro Jahr. &Uuml;ber alle Teile gehen aktuell 70 Prozent unserer Lieferungen ins Ausland. Gestern hatten wir die erste Lieferung nach S&uuml;dkorea. Auch Chile war schon dabei. Da ist also noch Luft nach oben.</p>",
        "category": "Test + Technik",
        "image": "https://media1.autohaus.de/sixcms/media.php/4903/thumbnails/90003_2018_73_08_I_044-046_Krone_ET-Zentrum_249369_print.15633412.pdf.15633415.jpg",
        "tags": "VR Interview,Krone Trailer 1112",
        "published": 1
    },
    {
        "id": "2133079",
        "issue_id": "2133000",
        "title": "Effizientes Ersatzteilwesen",
        "online_date": "2018-02-22 15:00:00",
        "change_date": "2018-02-21 12:40:10",
        "kicker": "Krone ET-Zentrallager",
        "teaser": "Mit einem Invest von 8,5 Millionen Euro ordnet Trailerhersteller Krone das Ersatzteilwesen neu. Herzstück ist künftig das ET-Zentrum \r\nin Herzlake.",
        "page_number": "44",
        "text": "<p>Nach den Zugfahrzeugherstellern, die sich neu erfunden haben und immer mehr Services neben ihrem Kernprodukt anbieten, setzen auch die Trailerproduzenten vermehrt auf das Gesch&auml;ft rund um die Hardware. J&uuml;ngster Coup in der Branche: das neue Ersatzteilzentrum der Krone Gruppe in Herzlake, verkehrsg&uuml;nstig an der Europastra&szlig;e 233 gelegen - eine der Hauptverkehrsadern der Region.</p>\r\n<p>Das Investitionsvolumen des modernen Ersatzteil-Distributionszentrums beziffert die Krone-Nutzfahrzeug-Gruppe auf 8,5 Millionen Euro. \"Wir setzen mit der Inbetriebnahme des neuen Ersatzteil-Zentrums konsequent unsere definierte Service-Offensive um, festigen unseren Wettbewerbsvorsprung im Ersatzteilgesch&auml;ft und bauen die Teileverf&uuml;gbarkeit f&uuml;r unsere europaweit t&auml;tigen Kunden noch weiter aus\", so Bernard Krone, gesch&auml;ftsf&uuml;hrender Gesellschafter der Krone-Gruppe. \"Der Ausbau dieser wichtigen Dienstleistung ist ein zentraler Baustein unserer Zukunftsstrategie.\"</p>\r\n<p>Das neue Lager befindet sich auf einem Areal von 38.000 Quadratmetern - einer Fl&auml;che von rund f&uuml;nfeinhalb Fu&szlig;ballfeldern. Die &uuml;berdachte Lagerfl&auml;che von 8400 Quadratmetern verteilt sich auf zw&ouml;lf Ebenen mit 17.500 Stellpl&auml;tzen f&uuml;r Europaletten sowie 16.000 Beh&auml;lter f&uuml;r Kleinteile. Sollte das Gesch&auml;ft wie erwartet weiter prosperieren, ist ausreichend Fl&auml;che vorhanden, sodass Krone das bereits vorhandene Lager noch ein zweites Mal gespiegelt aufbauen kann.</p>\r\n<p>Aktuell kommissionieren 40 Mitarbeiter monatlich mehr als 23.000 Positionen. Wenn n&ouml;tig, erfolgt der Versand im Nachtsprung oder im definierten Zeitfenster. Zudem bedient das Ersatzteilzentrum wichtige Au&szlig;enstellen in Istanbul, Budapest, Lyon, Skandinavien und im Baltikum. Das Portfolio des Versandzentrums in Herzlake umfasst Ersatzteile f&uuml;r Anh&auml;nger, Aufbauten, Containerfahrgestelle, Pritschen- und Koffersattelauflieger, Fahrzeuge f&uuml;r Kurier-Express-Dienste sowie f&uuml;r die hauseigenen Krone Trailer Achsen. Das neue Zentrallager ist ein Schritt der Krone Gruppe f&uuml;r weiteres Wachstum. Der Umsatz liegt aktuell bei 1,9 Milliarden Euro. In den Megatrends \"Zunahme der Weltbev&ouml;lkerung\" sowie \"Globale Vernetzung\" und der damit steigenden Nachfrage nach Nahrungs- und Transportmitteln sieht Krone wesentliche Punkte, dass sich der Absatz von Nutzfahrzeugen auch weiterhin positiv entwickeln wird.</p>\r\n<p>Mehr zum Thema finden Sie im Dossier \u0084Krone\u0093 www.verkehrsrundschau.de/dossiers</p>",
        "category": "Test + Technik",
        "image": "https://media1.autohaus.de/sixcms/media.php/4903/thumbnails/90003_2018_73_08_I_044-046_Krone_ET-Zentrum_249369_print.pdf.15633408.jpg",
        "tags": "Trend-Idee Lager Umschlag,Trend-Idee Logistik,Krone Trailer 1112",
        "published": 1
    },
    {
        "id": "2133076",
        "issue_id": "2133000",
        "title": "V8-Giganten im Eisduell",
        "online_date": "2018-02-22 15:00:00",
        "change_date": "2018-02-21 12:39:25",
        "kicker": "Scanias V8 im Vergleich",
        "teaser": "Im norwegischen Winter treten die beiden stärksten V8 von Scania zum Vergleich an. Obwohl einer schneller ist, gibt es zwei Sieger.",
        "page_number": "40",
        "text": "<p>Es ist angerichtet zum gro&szlig;en V8-Duell: Auf einem Flugplatz im norwegischen Wintersportgebiet Trysil stehen die Kontrahenten noch friedlich nebeneinander. Der rubinrote S 650 in SCR-only-Technologie fordert als zweitst&auml;rkste und modernste Scania-Maschine den saphirblauen S 730 heraus, die aktuelle Top-Motorisierung der Schweden (siehe Kasten oben rechts).</p>\r\n<p>An dem grauen Januartag zeigt das Thermometer knapp unter null Grad Celsius, f&uuml;r norwegische Verh&auml;ltnisse fast sommerliche Temperaturen. Dennoch sorgen Schnee- und Eisreste f&uuml;r eine teils schl&uuml;pfrige Fahrbahn. Die Strecke f&uuml;hrt durch eine Schneefurche vom Flugplatz auf die Riksvei 25 Richtung schwedische Grenze. Vorbei an tief verschneiten W&auml;ldern geht es mit Gef&auml;llen zwischen vier und sechs Prozent bergab &uuml;ber den Fluss Klar&auml;lven.</p>\r\n<p><strong>Last verschieben f&uuml;r mehr Grip</strong></p>\r\n<p>Im Kreisverkehr nach der Br&uuml;cke wird gewendet und wir fahren den gleichen Weg zur&uuml;ck. Die Gef&auml;lle wandeln sich jetzt zu Steigungen, und die beiden Duellanten m&uuml;ssen zeigen, was in ihrem V8 steckt.</p>\r\n<p>Damit das Ganze f&uuml;r die beiden 16-Liter-Aggregate nicht zu leicht wird, sind wir mit den in Norwegen zul&auml;ssigen 50 Tonnen Gesamtgewicht unterwegs.</p>\r\n<p>Dass die Boliden dabei nicht die Traktion verlieren, soll Load-Transfer (Achslastverschiebung) verhindern. &Uuml;ber die Luftfederung kann das System die letzte Achse unserer dreiachsigen Sattelzugmaschinen entlasten und so mehr Druck auf die vordere Antriebsachse bringen. Eine Funktion, die sich im Duellverlauf als n&uuml;tzlich erweist, in Deutschland aber nur eingeschr&auml;nkt erlaubt ist.</p>\r\n<p><strong>Das Getriebe setzt aufs Drehmoment</strong></p>\r\n<p>Der Favorit mit seinen 730 PS muss vorlegen. Mit dem Dreh am Z&uuml;ndschl&uuml;ssel erwacht der V8 im Blue Safir zum Leben. Sein Leerlaufgrummeln bricht mit der nordischen Stille und f&uuml;llt dezent die Kabine. Entspannt geht es bergab Richtung Kreisverkehr. Entspannt? Angesichts der glitschigen Stra&szlig;enverh&auml;ltnisse nicht wirklich. Der mich begleitende Werksfahrer mahnt zur Zur&uuml;ckhaltung im Umgang mit dem Retarder. Bei zu viel Bremsmoment an den Antriebsachsen faltet sich der Zug zusammen wie ein Zollstock.</p>\r\n<p>Unten angekommen geht es durch den Kreisel, zur&uuml;ck &uuml;ber die Br&uuml;cke, noch einmal links abbiegen - jetzt gilt's. Durchatmen, Fu&szlig; aufs Gas und los. Der V8-Sound wird kerniger, ein Pfeifen k&uuml;ndigt von der Arbeit des Turboladers, das L&auml;mpchen der Antischlupfregelung leuchtet auf und signalisiert, was der Chauffeur l&auml;ngst merkt: Die Zugmaschine schlingert an den Hinterachsen. Fu&szlig; vom Gas, Lenkrad ruhig halten und mit dem Finger auf dem Knopf f&uuml;r Load-Transfer mehr Druck auf die vordere Antriebsachse schicken.</p>\r\n<p>Jetzt zieht der S 730 souver&auml;n den Berg hoch. Bis auf 72 Kilometer pro Stunde im 11. Gang bei 1200 Umdrehungen bringt er es. In der Steigung wechselt Opticruise erst bei 1400 Touren den Gang und damit genau am Ende des Drehzahlbereichs, an dem das Drehmomentmaximum von 3500 Newtonmetern anliegt.</p>\r\n<p>Der Schlussanstieg setzt der Maschine dann aber doch noch zu und im zehnten Gang geht es mit 60 km/h bei 1300 Umdrehungen &uuml;ber die gedachte Ziellinie - ein Schild am Stra&szlig;enrand.</p>\r\n<p><strong>Der Herausforderer h&auml;lt kurz den Elften</strong></p>\r\n<p>Danach startet Red Rubin, der Herausforderer, in dem bereits die neue Motorengeneration verbaut ist, seinen Angriff. Die Bergabpassage bleibt wenig &uuml;berraschend wieder ohne Erkenntnisgewinn, welcher V8 die bessere Maschine ist.</p>\r\n<p>Mit der Erfahrung aus Runde eins ist Load-Transfer bereits justiert und der Gasfu&szlig; geht nach dem Abzweig zu Beginn der Steigung sanfter zu Werke. Mit rund 13 von 18 m&ouml;glichen Tonnen presst sich die vordere der beiden Hinterachsen jetzt auf den glatten Fahrbahnbelag. Dennoch flackert das ASR-L&auml;mpchen kurz auf. Danach zieht der 650-PS-Scania sauber die Steigung hoch. Auch er vertraut auf sein Drehmoment und schafft es kurzzeitig in den elften Gang, wenn auch mit ein paar km/h weniger auf der Uhr. Am Ende k&auml;mpft er sich mit 50 km/h bei 1100 Touren im zehnten Gang &uuml;ber die Ziellinie - zweiter Sieger.</p>\r\n<p><strong>&Uuml;berraschungssieger im Akustikduell</strong></p>\r\n<p>Verlierer w&auml;re zu hart. Zum einen musste ich aus Sicherheitsgr&uuml;nden angesichts der zunehmenden Gl&auml;tte in zwei lang gezogenen Rechtskurven bei Gegenverkehr kurz vom Gas. Ein paar Kilometer mehr Geschwindigkeit w&auml;ren also noch drin gewesen, die 60 h&auml;tte der S 650 aber sicher nicht erreicht.</p>\r\n<p>Zum anderen gewinnt er die Sound-Wertung - den neuen Abgassammelrohren sei Dank. Der S 650 klingt lauter, kerniger und damit mehr nach V8 als der vergleichsweise leise S 730, ohne dabei st&ouml;rend laut zu dr&ouml;hnen.</p>\r\n<p>Dass beim S 650 der Bereich des Drehmomentmaximums um 50 Touren nach unten verschoben ist, ist an der Steigung nicht zu merken. Die fehlenden 200 Newtonmeter und die um 80 PS geringere Motorleistung schon. Etwas. Im Alltag f&auml;llt beides nicht wirklich ins Gewicht. Hier punktet der S 650 mit dem moderneren SCR-only-Triebwerk, vermeintlich geringeren Verbrauchswerten und dem besseren V8-Sound.</p>\r\n<p>Alle Tests und Fahrberichte f&uuml;r Abonnenten www.verkehrsrundschau-plus.de</p>\r\n<div class=\"ha-kasten1\">\r\n<div class=\"title\">\r\n<h4>Die neue V8-Generation</h4>\r\n<h4>Das hat sich ge&auml;ndert</h4>\r\n</div>\r\n<div class=\"content\">\r\n<p>Vergangenen Sommer hat Scania die neue Generation V8-Motoren in den Leistungsstufen 520, 580, 650 und 730 PS vorgestellt. Wobei bei der Top-Motorisierung nicht alle Neuerungen &uuml;bernommen wurden. F&uuml;r sie wirbt Scania mit einem daher Minderverbrauch von 5,5 Prozent, w&auml;hrend dieser bei den anderen Einstellungen zwischen 7 und 10 Prozent liegen soll. Der Hauptgrund f&uuml;r die niedrigeren Verbr&auml;uche ist die im Gegensatz zur 730-PS-Version fehlende Abgasr&uuml;ckf&uuml;hrung. Zudem arbeiten die Motoren jetzt mit einem Twin-Scroll-Turbolader mit fester Turbinengeometrie (FGT). Das soll robuster und leichter sein als der Vorg&auml;nger mit variabler Geometrie. Weitere Ver&auml;nderungen betreffen das Ansaug- und Einspritzverfahren sowie die beweglichen Motorenteile, die weniger Reibung erzeugen. Luftkompressor und Dieselpumpe arbeiten jetzt bedarfsgesteuert w&auml;hrend ein Thermostat die &Ouml;lpumpe regelt. sv</p>\r\n</div>\r\n</div>\r\n<div class=\"ha-kasten2\">\r\n<div class=\"title\">\r\n<h4>Fazit</h4>\r\n<h4>Luxusprobleme</h4>\r\n</div>\r\n<div class=\"content\">\r\n<p>\"Zwei Seelen wohnen, ach! in meiner Brust\", hei&szlig;t es in Goethes Faust. Meine Fahrer- Seele sagt: Nimm den mit 730 PS - das Leistungsplus gegen&uuml;ber dem Motor mit 650 PS bringt einfach noch mehr Fahrspa&szlig;. Die Unternehmer-Seele sagt: Nimm den mit 650 PS - es ist das modernere Aggregat und die fehlende Leistung ist in der Praxis meist irrelevant. H&auml;tte ich eine dritte, spa&szlig;frei-ehrliche Seele, w&uuml;rde die sagen: Im 40-Tonnen-Fernverkehr ist das ein Luxusproblem, denn f&uuml;r den braucht niemand 650 oder 730 PS.serge.voigt@springernature.comSerge Voigt, Redakteur f&uuml;r Test und Technik</p>\r\n</div>\r\n</div>",
        "category": "Test + Technik",
        "image": "https://media1.autohaus.de/sixcms/media.php/4903/thumbnails/90003_2018_73_08_I_040-043_Scania_gegen_Scania_250049_print.pdf.15633401.jpg",
        "tags": "Markt Lkw-Landverkehr & Stückgut,Lkw 7,5 t und mehr,VW Scania NFZ und Services 1111",
        "published": 1
    }
]
```

This endpoint retrieves all Magazine Articles belonging to a given Magazine Issue sorted by change date

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/magazine_article/by_issue/<ISSUE_ID>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
issue_id | 0 | Id of a Magazine Issue

# Video

## Get All Video Topics from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/video-topic/ids/1501545600"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2062018",
    "2053647",
    "2048136",
    "2048134",
    "2052406",
    "2048124"
]
```

This endpoint retrieves all Video Topics with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/video-topic/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a Specific Video Topic


```shell
curl "http://rest-api.verkehrsrundschau.de/video-topic/detail/2062018"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2062018",
    "title": "Datenschutz - Die neuen Herausforderungen",
    "type": "Videoschulungen zum Webinar",
    "online_date": "2018-02-06 16:52:00",
    "change_date": "2018-02-07 09:50:26",
    "offline_date": "9999-12-31 00:00:00",
    "teaser": "In unserer Videoreihe \"Datenschutz - Die neuen Herausforderungen\" werden Ihnen anhand von sechs anschaulichen Videos die wichtigsten Änderungen der Datenschutzgrundverordnung näher gebracht. Gültig ab 25.5.2018, können Sie hier erfahren, wie Sie sich vorbereiten können, was sich geändert hat und was Sie auch bisher schon beachten mussten. Neuerungen im Datenschutzrecht, Auswirkungen auf die Verarbeitung von Daten und das Direktmarketing sowie Pflichten für Unternehmer werden erklärt und wichtige Fragen zum Thema von unserem Fachexperten beantwortet. ",
    "text": "<p>In unserer Videoreihe \"Datenschutz - Die neuen Herausforderungen\" werden Ihnen anhand von 6 anschaulichen Videos die wichtigsten &Auml;nderungen der Datenschutzgrundverordnung n&auml;her gebracht. G&uuml;ltig ab 25.5.2018, k&ouml;nnen Sie hier erfahren, wie Sie sich vorbereiten k&ouml;nnen, was sich ge&auml;ndert hat und was Sie auch bisher schon beachten mussten. Neuerungen im Datenschutzrecht, Auswirkungen auf die Verarbeitung von Daten und das Direktmarketing sowie Pflichten f&uuml;r Unternehmer werden erkl&auml;rt und wichtige Fragen zum Thema von unserem Fachexperten beantwortet.&nbsp;</p>",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5709/Datenschutz_Trueffelpix_stockadobe1920.jpg",
    "image_copyright": "Trueffelpix/stock.adobe.com",
    "video": [
        {
            "id": "2062027",
            "title": "Datenschutz - Teil 1 - Einführung",
            "online_date": "2018-02-06 00:00:00",
            "change_date": "2018-02-07 09:49:13",
            "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. In Teil 1 gibt es eine generelle Einführung in das Thema und die weiteren Videos dazu.",
            "video_topic_id": "2062018",
            "video_html": "<iframe src=\"https://player.vimeo.com/video/254501871?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil1-Einf&uuml;hrung\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
            "length": "02:20",
            "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681665875_960.jpg",
            "tags": "Recht Transport und Spedition",
            "sorting_index": 10,
            "published": 1
        },
        {
            "id": "2062029",
            "title": "Datenschutz - Teil 2 - Neues Datenschutzrecht",
            "online_date": "2018-02-06 00:00:00",
            "change_date": "2018-02-07 10:23:09",
            "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. In Teil 2 wird die neue Verordnung vorgestellt und geklärt, was sich jetzt für Sie verändert und was bleibt wie bisher.",
            "video_topic_id": "2062018",
            "video_html": "<iframe src=\"https://player.vimeo.com/video/254502786?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil2-Neues Datenschutzrecht\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
            "length": "10:48",
            "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681845638_960.jpg",
            "tags": "Recht Transport und Spedition",
            "sorting_index": 20,
            "published": 1
        },
        {
            "id": "2062030",
            "title": "Datenschutz - Teil 3 - Datenverarbeitung",
            "online_date": "2018-02-06 00:00:00",
            "change_date": "2018-02-07 10:23:25",
            "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. In Teil 3 erfahren Sie, wann Daten verarbeitet werden dürfen und worauf Sie dabei achten müssen.",
            "video_topic_id": "2062018",
            "video_html": "<iframe src=\"https://player.vimeo.com/video/254500824?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil3-Datenverarbeitung\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
            "length": "14:17",
            "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681665498_960.jpg",
            "tags": "Recht Transport und Spedition",
            "sorting_index": 30,
            "published": 1
        },
        {
            "id": "2062031",
            "title": "Datenschutz - Teil 4 - Direktmarketing",
            "online_date": "2018-02-06 00:00:00",
            "change_date": "2018-02-07 09:49:29",
            "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. Teil 4 befasst sich mit dem Thema Direktmarketing - was ist erlaubt, was nicht.",
            "video_topic_id": "2062018",
            "video_html": "<iframe src=\"https://player.vimeo.com/video/254501630?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil4-Direktmarketing\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
            "length": "05:25",
            "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681665760_960.jpg",
            "tags": "Recht Transport und Spedition",
            "sorting_index": 40,
            "published": 1
        },
        {
            "id": "2062032",
            "title": "Datenschutz - Teil 5 - Neue Pflichten für Unternehmen",
            "online_date": "2018-02-06 00:00:00",
            "change_date": "2018-02-07 10:23:32",
            "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. In Teil 5 stellt unser Fachexperte die neuen Pflichten für Unternehmen vor, die mit der Verordnung einhergehen.",
            "video_topic_id": "2062018",
            "video_html": "<iframe src=\"https://player.vimeo.com/video/254503182?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil5-Pflichten\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
            "length": "15:35",
            "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681845567_960.jpg",
            "tags": "Recht Transport und Spedition",
            "sorting_index": 50,
            "published": 1
        },
        {
            "id": "2062034",
            "title": "Datenschutz - Teil 6 - Fragen und Antworten",
            "online_date": "2018-02-06 00:00:00",
            "change_date": "2018-02-07 10:22:51",
            "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. Im 6. und letzten Teil werden Fragen und Antworten zum Thema und den vorhergehenden Videos gegeben.",
            "video_topic_id": "2062018",
            "video_html": "<iframe src=\"https://player.vimeo.com/video/254501964?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil6-Fragen\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
            "length": "16:03",
            "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681846040_960.jpg",
            "tags": "Recht Transport und Spedition",
            "sorting_index": 60,
            "published": 1
        }
    ],
    "documents": [],
    "published": 1
}
```

This endpoint retrieves a specific Video Topic.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/video-topic/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Video Topic to retrieve

## Get All Videos from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/video/ids/1501545600"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2062032",
    "2062030",
    "2062029",
    "2062034",
    "2062031",
    "2062027",
    "2058281",
    "2053684",
    "2053682",
    "2053680",
    "2053679",
    "2053671",
    "2053670",
]
```

This endpoint retrieves all Videos with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/video/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a Specific Video


```shell
curl "http://rest-api.verkehrsrundschau.de/video/detail/2062032"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2062032",
    "title": "Datenschutz - Teil 5 - Neue Pflichten für Unternehmen",
    "online_date": "2018-02-06 00:00:00",
    "change_date": "2018-02-07 10:23:32",
    "teaser": "Die Videoreihe \"Datenschutz - Die neuen Herausforderungen\" besteht aus sechs Teilen und befasst sich mit Ihren veränderten Pflichten und Aufgaben als Unternehmer laut Datenschutzgrundverordnung. In Teil 5 stellt unser Fachexperte die neuen Pflichten für Unternehmen vor, die mit der Verordnung einhergehen.",
    "video_topic_id": "2062018",
    "video_html": "<iframe src=\"https://player.vimeo.com/video/254503182?title=0&byline=0&portrait=0&color=e22713\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"DSGVO-Teil5-Pflichten\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
    "length": "15:35",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/893/681845567_960.jpg",
    "tags": "Recht Transport und Spedition",
    "sorting_index": 50,
    "published": 1
}
```

This endpoint retrieves a specific Video.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/video/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Video to retrieve



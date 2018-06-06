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

# Insolvency Database

## Get All Insolvency Companies from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/insolvency-company/ids/1501545600"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2162479",
    "2162469",
    "2162468",
    "2162467",
    "2162466",
    "2162465",
    "2162458",
    "2162456"
]
```

This endpoint retrieves all Companies with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/insolvency-company/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Insolvency Company


```shell
curl "http://rest-api.verkehrsrundschau.de/insolvency-company/detail/2162466"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2162466",
    "title": "Adler Transport UG",
    "online_date": "2018-05-08 00:00:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2018-05-08 09:46:31",
    "datum": "2018-05-02",
    "court": "Amtsgericht Montabaur",
    "zip": "56244 ",
    "location": "Leuterod",
    "status": "Verfahren eröffnet",
    "statusId": "1019476",
    "published": 1
}
```

This endpoint retrieves a specific Insolvency Company.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/insolvency-company/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Company to retrieve

## Get All Stati from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/insolvency-status/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "1019477",
    "1019478",
    "1019476",
    "1019475"
]
```

This endpoint retrieves all Stati with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/insolvency-status/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a Specific Status


```shell
curl "http://rest-api.verkehrsrundschau.de/insolvency-status/detail/1019477"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1019477",
    "title": "Mangels Masse abgelehnt/eingestellt",
    "online_date": "2011-04-12 14:46:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2011-07-25 15:41:00",
    "published": 1
}
```

This endpoint retrieves a specific Company.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/insolvency-status/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Status to retrieve

# Test Database

## Get All Test DB Entries from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-entry/ids/1501545600"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2162884",
    "2158819",
    "2156107",
    "2156104",
    "2151383",
    "2147099",
    "2141685"
]
```

This endpoint retrieves all Test DB Entries with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-entry/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Test DB Entry


```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-entry/detail/2162884"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2162884",
    "title": "Scania G 450 XT 8x4: King of Construction?",
    "online_date": "2018-05-10 15:00:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2018-05-11 13:01:58",
    "issue": "19",
    "teaser": "Mit dem G 450 XT 8x4 tritt der erste Kipper aus Scanias neuer Baufahrzeugreihe zum Test an. Ein neues System soll den Verbrauch senken.",
    "issue_date": "2018-05-11",
    "test_db_category": [
        {
            "id": "1019435",
            "title": "Fahrzeugtest",
            "online_date": "2010-08-03 16:19:00",
            "offline_date": "9999-12-31 00:00:00",
            "change_date": "2011-04-12 14:03:57",
            "published": 1
        }
    ],
    "test_db_vehicle_category": [
        {
            "id": "958466",
            "title": "LKW",
            "online_date": "2010-08-03 16:19:00",
            "offline_date": "9999-12-31 00:00:00",
            "change_date": "2010-08-03 16:19:35",
            "published": 1
        }
    ],
    "test_db_manufacturer": [
        {
            "id": "958482",
            "title": "Scania",
            "online_date": "2010-08-03 16:19:00",
            "offline_date": "9999-12-31 00:00:00",
            "change_date": "2010-08-03 16:19:36",
            "published": 1
        }
    ],
    "model_1": "G 450 XT 8x4",
    "pdf_upload": "https://media1.verkehrsrundschau.de/sixcms/media.php/4395/90003_2018_73_19_I_040-043_Scania_G_450_XT_268424_print.pdf",
    "published": 1
}
```

This endpoint retrieves a specific Test DB Entry.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-entry/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve

## Get All Test DB Forklifts from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-forklift/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "1790220",
    "1653013",
    "1652651",
    "1366377",
    "1360966",
    "1357965",
    "1284950",
    "1187198",
    "1176976",
    "1176925",
    "1121719"
]
```

This endpoint retrieves all Forklifts with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-forklift/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Test DB Forklift


```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-forklift/detail/1790220"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1790220",
    "title": "Toyota Traigo 48-16 Li-Ion: Der Schnelllader unter den Staplern",
    "online_date": "2016-05-03 11:19:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2016-09-15 11:52:00",
    "teaser": "Wie gut sind Bedienung, Fahrleistung und Energieverbrauch des 1,6 Tonnen Elektro-Frontstapler von Toyota in der Praxis? Und, welchen Vorteil bringt die Lithium-Ionen-Batterie? Antworten liefert der Test des Toyota Traigo 48-16 Li-Ion. Mit dem kompletten Test als PDF-Download.",
    "text": "<p>Im Staplertest der VerkehrsRundschau hat der Traigo 48-16 Li-Ion von Toyota mit der Note &bdquo;gut&ldquo; (1,9) abgeschnitten. Technischer Leckerbissen des Fahrzeugs war seine f&uuml;r Frontstapler noch untypische Lithium-Ionen-Batterie, welche die Ladezeiten deutlich verk&uuml;rzt und so im Mehrschichtbetrieb den Batteriewechsel &uuml;berfl&uuml;ssig machen kann. Der Dreirad-Elektrofrontstapler hebt Lasten von bis zu 1,6 Tonnen.<!--?xml:namespace prefix = \"o\" ns = \"urn:schemas-microsoft-com:office:office\" /--></p>\r\n<p>Pluspunkte sammelte der in Italien gefertigte Japaner bei den drei Testfahrern unter anderem mit seiner wartungsfreien Batterie, die nicht gewechselt werden muss, mit dem serienm&auml;&szlig;igen System f&uuml;r mehr Fahrstabilit&auml;t sowie dem einfachen Zugang zu allen wichtigen Komponenten.</p>\r\n<p>Weniger &uuml;berzeugt haben dagegen die Platzierung des Schalters f&uuml;r den Fahrtrichtungswechsel, die fehlenden Ablagem&ouml;glichkeiten f&uuml;r Fahrerutensilien und die etwas ungleichen Spaltma&szlig;e in der Seitenverkleidung.</p>\r\n<p>Der Stapler musste den VerkehrsRundschau-Testparcours im Leistungsmodus absolvieren. Mit 33 Minuten und 44 Sekunden erzielte der Traigo zwar nur eine ordentliche Zeit beim Be- und Entladung eines Sattelaufliegers mit 32 Europaletten. Daf&uuml;r verursacht die moderne Batterietechnik rekordverd&auml;chtig geringe Energiekosten in H&ouml;he von 22 Cent.</p>\r\n<p><a href=\"http://www.verkehrsrundschau.de/fm/3576/VR_Test_Toyota_Traigo48I.pdf\" target=\"_Blank\" title=\"VR-Staplertest: Toyota Traigo 48-16 Li-Ion\">Klicken Sie hier, um den gesamten Test als PDF-Datei herunterzuladen.</a>&nbsp; (sv)</p>",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/4494/VR_Test_Toyota_Traigo48.jpg",
    "image_copyright": "VerkehrsRundschau/Serge Voigt",
    "image_caption": "<p>Die Batterie des Staplers ist schneller aufgeladen als ein Smartphone</p>",
    "attachments": [
        {
            "file": "https://media1.verkehrsrundschau.de/fm/3576/VR_Test_Toyota_Traigo48I.pdf",
            "title": "VR_Test_Toyota_Traigo48"
        }
    ],
    "issue_date": "2015-05-01",
    "test_db_category": [
        {
            "id": "1019435",
            "title": "Fahrzeugtest",
            "online_date": "2010-08-03 16:19:00",
            "offline_date": "9999-12-31 00:00:00",
            "change_date": "2011-04-12 14:03:57",
            "published": 1
        }
    ],
    "test_db_vehicle_category": [
        {
            "id": "1817226",
            "title": "Gabelstapler",
            "online_date": "2016-08-01 12:55:00",
            "offline_date": "9999-12-31 00:00:00",
            "change_date": "2016-08-01 12:55:40",
            "published": 1
        }
    ],
    "test_db_manufacturer": [
        {
            "id": "1142326",
            "title": "Toyota",
            "online_date": "2012-07-27 13:45:00",
            "offline_date": "9999-12-31 00:00:00",
            "change_date": "2012-07-27 13:45:19",
            "published": 1
        }
    ],
    "published": 1
}
```

This endpoint retrieves a specific Test DB Forklift.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-forklift/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Test DB Forklift to retrieve

## Get All Test DB Manufacturer from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-manufacturer/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2046383",
    "2019079",
    "2019078",
    "2019077",
    "2019076",
    "2019075",
    "2013540"
]
```

This endpoint retrieves all Test DB Manufacturer with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-manufacturer/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Test DB Manufacturer


```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-manufacturer/detail/2046383"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2046383",
    "title": "Xetto",
    "online_date": "2017-12-14 09:59:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2017-12-14 10:00:27",
    "published": 1
}
```

This endpoint retrieves a specific Test DB Manufacturer.

## Get All Test DB Vehicle Categories from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "1817226",
    "1026105",
    "1001427",
    "958507",
    "958466"
]
```

This endpoint retrieves all Test DB Vehicle Categories with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Test DB Vehicle Category


```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/detail/1817226"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1817226",
    "title": "Gabelstapler",
    "online_date": "2016-08-01 12:55:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2016-08-01 12:55:40",
    "published": 1
}
```

This endpoint retrieves a specific Test DB Vehicle Category.

## Get All Test DB Vehicle Categories from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "1817226",
    "1026105",
    "1001427",
    "958507",
    "958466"
]
```

This endpoint retrieves all Test DB Vehicle Categories with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Test DB Vehicle Category


```shell
curl "http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/detail/1817226"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1817226",
    "title": "Gabelstapler",
    "online_date": "2016-08-01 12:55:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2016-08-01 12:55:40",
    "published": 1
}
```

This endpoint retrieves a specific Test DB Vehicle Category.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/test-db-vehicle-category/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Test DB Vehicle Category to retrieve

# Courses
## Get All courses from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/course/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2164840",
    "2164820"
]
```

This endpoint retrieves all Courses with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Course


```shell
curl "http://rest-api.verkehrsrundschau.de/course/detail/2164840"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164840",
    "online_date": "2018-05-16 00:00:00",
    "change_date": "2018-05-16 15:57:51",
    "title": "Test2",
    "author": [
        {
            "id": "2164816",
            "online_date": "2018-05-16 15:40:00",
            "change_date": "2018-05-16 15:40:10",
            "title": "Hans Meiser",
            "published": 1
        }
    ],
    "is_credit_package_required": 1,
    "has_certificate": 1,
    "certificate_template": "VerkehrsRundschau plus",
    "credit_cost": "7",
    "is_unlock_modules_one_after_one": 1,
    "retries_final_test": "3",
    "goals": "Weiter als 2 Meter springen.\r\nKugelstoßen Weltrekord.\r\n",
    "target_audience": "Weitspringer, Kugelstoßer",
    "teaser": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
    "image_url": "https://media1.verkehrsrundschau.de/sixcms/media.php/2732/traumphase_by_markuszeller-dc1821o.png.jpg",
    "published": 1
}
```

This endpoint retrieves a specific Course.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Course to retrieve

## Get All Course Authors from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/course-author/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2164817",
    "2164816"
]
```

This endpoint retrieves all Course Authors with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-author/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Course Author


```shell
curl "http://rest-api.verkehrsrundschau.de/course-author/detail/2164817"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164817",
    "online_date": "2018-05-16 15:40:00",
    "change_date": "2018-05-16 15:40:31",
    "title": "Olleg Bollek",
    "published": 1
}
```

This endpoint retrieves a specific Course Author.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-author/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Course Author to retrieve


## Get All Course Languages from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/course-language/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2164813",
    "2164812"
]
```

This endpoint retrieves all Course Languages with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-language/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Course Language


```shell
curl "http://rest-api.verkehrsrundschau.de/course-language/detail/2164817"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164813",
    "online_date": "2018-05-16 15:30:00",
    "change_date": "2018-05-16 15:30:02",
    "title": "Deutsch",
    "published": 1
}
```

This endpoint retrieves a specific Course Language.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-language/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Course Language to retrieve


## Get All Course Modules from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/course-module/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2164838",
    "2164833"
]
```

This endpoint retrieves all Course Modules with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-module/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Course Module


```shell
curl "http://rest-api.verkehrsrundschau.de/course-module/detail/2164838"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164838",
    "online_date": "2018-05-16 15:56:00",
    "change_date": "2018-05-16 15:57:44",
    "title": "Hui Boo",
    "text": "Ich bin ein Test",
    "type": "Video",
    "is_final_test": 1,
    "translations": [
        {
            "id": "2164836",
            "online_date": "2018-05-16 15:57:00",
            "change_date": "2018-05-16 15:57:40",
            "title": "Testing the honk",
            "video": {
                "id": "2164834",
                "title": "Honk",
                "online_date": "2018-05-16 00:00:00",
                "change_date": "2018-05-16 15:50:09",
                "video_html": "<iframe src=\"https://player.vimeo.com/video/268216832?title=0&byline=0&portrait=0&color=e22713&app_id=122963\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"Why Are You Honking?\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
                "length": "05:26",
                "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5827/700619362_960.jpg",
                "published": 1
            },
            "wbt_upload": "",
            "language": {
                "id": "2164812",
                "online_date": "2018-05-16 15:29:00",
                "change_date": "2018-05-16 15:29:55",
                "title": "Englisch",
                "published": 1
            },
            "published": 1
        },
        {
            "id": "2164837",
            "online_date": "2018-05-16 15:57:00",
            "change_date": "2018-05-16 15:57:44",
            "title": "I like the Erdbeerchen",
            "video": {
                "id": "2164830",
                "title": "Erdbeerchen",
                "online_date": "2018-05-16 00:00:00",
                "change_date": "2018-05-16 15:48:53",
                "video_html": "<iframe src=\"https://player.vimeo.com/video/191887252?title=0&byline=0&portrait=0&color=e22713&app_id=122963\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"Szagos H&ouml;rigekk&oacute;k - Eper (Strawberry)\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
                "length": "02:05",
                "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5827/700544898_960.jpg",
                "published": 1
            },
            "wbt_upload": "",
            "language": {
                "id": "2164812",
                "online_date": "2018-05-16 15:29:00",
                "change_date": "2018-05-16 15:29:55",
                "title": "Englisch",
                "published": 1
            },
            "alt_title": "Strawberries",
            "alt_text": "They are damn tasty.",
            "published": 1
        }
    ],
    "sorting_index": 0,
    "published": 1
}
```

This endpoint retrieves a specific Course Module.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-module/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Course Module to retrieve

==================
## Get All Course Translations from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/course-translation/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2164837",
    "2164836",
    "2164832"
]
```

This endpoint retrieves all Course Translations with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-translation/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Course Translation


```shell
curl "http://rest-api.verkehrsrundschau.de/course-translation/detail/2164817"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164837",
    "online_date": "2018-05-16 15:57:00",
    "change_date": "2018-05-16 15:57:44",
    "title": "I like the Erdbeerchen",
    "video": {
        "id": "2164830",
        "title": "Erdbeerchen",
        "online_date": "2018-05-16 00:00:00",
        "change_date": "2018-05-16 15:48:53",
        "video_html": "<iframe src=\"https://player.vimeo.com/video/191887252?title=0&byline=0&portrait=0&color=e22713&app_id=122963\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"Szagos H&ouml;rigekk&oacute;k - Eper (Strawberry)\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
        "length": "02:05",
        "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5827/700544898_960.jpg",
        "published": 1
    },
    "wbt_upload": "",
    "language": {
        "id": "2164812",
        "online_date": "2018-05-16 15:29:00",
        "change_date": "2018-05-16 15:29:55",
        "title": "Englisch",
        "published": 1
    },
    "alt_title": "Strawberries",
    "alt_text": "They are damn tasty.",
    "published": 1
}
```

This endpoint retrieves a specific Course Translation.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-translation/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Course Translation to retrieve

## Get All Course Videos from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/course-video/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2164834",
    "2164830"
]
```

This endpoint retrieves all Course Videos with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-video/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Course Video


```shell
curl "http://rest-api.verkehrsrundschau.de/course-video/detail/2164834"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164834",
    "title": "Honk",
    "online_date": "2018-05-16 00:00:00",
    "change_date": "2018-05-16 15:50:09",
    "video_html": "<iframe src=\"https://player.vimeo.com/video/268216832?title=0&byline=0&portrait=0&color=e22713&app_id=122963\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"Why Are You Honking?\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
    "length": "05:26",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5827/700619362_960.jpg",
    "published": 1
}
```

This endpoint retrieves a specific Course Video.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/course-video/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Course Video to retrieve

==================
# Key Figure
## Get All Key Figure Overviews from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/keyfigure-overview/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2167846"
]
```

This endpoint retrieves all Key Figure Overviews with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/keyfigure-overview/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Key Figure Overview


```shell
curl "http://rest-api.verkehrsrundschau.de/keyfigure-overview/detail/2167846"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
{
    "id": "2167846",
    "online_date": "2018-05-28 00:00:00",
    "change_date": "2018-06-06 16:51:32",
    "title": "Steuerungsdokument",
    "headline": "Kennzahlen zum Straßengüterverkehr: Frachtraten, Aufkommensentwicklung und vieles mehr ",
    "text": "<p>Neu: Die Plattform der VerkehrsRundschau zu den Kennzahlen im Transportgewerbe. Hier finden Sie die aktuellen Daten aus dem VerkehrsRundschau-Index. Aber es geht hier nicht nur um Transportpreise, unterteilt nach verschiedenen Kriterien, sondern um viel mehr: Sie erhalten hier Prognosen zur Aufkommens- und Preisentwicklung und viele weitere Informationen, die f&uuml;r Logistikdienstleister und Verlader eine unverzichtbare St&uuml;tze im Unternehmensalltag sind.</p>\r\n<p>Mehr Informationen zum VerkehrsRundschau Index finden Sie <a href=\"http://www.verkehrsrundschau.de/transportpreise\" target=\"http://www.verkehrsrundschau.de/transportpreise\">hier</a>. Wie oft und auf welche Art der Index erhoben wird, wie Sie mitmachen k&ouml;nnen und welche Pr&auml;mien Sie erwarten.</p>",
    "charts": [
        {
            "id": "2146309",
            "online_date": "2018-03-27 14:29:00",
            "change_date": "2018-06-06 16:54:16",
            "title": "Veränderung des Aufkommens im Vergleich zum Vorjahr (Anteil der Unternehmen in Prozent)",
            "type": "Column",
            "js_code": "(function()\n{\nvar chart_container_name = \"chart_2146309\";\n                   \n                  var data = google.visualization.arrayToDataTable([\n['','gestiegen','konstant','gesunken'],\n['Verlader',59.60,23.40,17],\n['Logistikdienstleister',58.80,33.30,7.90],\n]);\nvar formatter1 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter1.format(data, 1);\nvar formatter2 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter2.format(data, 2);\nvar formatter3 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter3.format(data, 3);\n var options = {\n                        colors: ['#e22713', '#022d5c', '#555f6a', '#a6a6a6', '#e6e6e6', '#f6f6f6']\n\n                    ,vAxis: {\ntitle: 'Prozent'\n}\n    \n};\n                    var chart = new google.charts.Bar(document.getElementById(chart_container_name));            \n                    chart.draw(data, google.charts.Bar.convertOptions(options));\n                  \n                \n})();\n",
            "html_code": "<div id=\"chart_2146309\" class=\"chart chart-column\"></div>",
            "headline": "Entwicklung des Aufkommens Quartal 2/2017 bis Quartal 1/2018 im Vergleich zum entsprechenden Vorjahreszeitraum",
            "teaser": "<p>Das ist ein Teaser</p>",
            "text": "<p>F&uuml;r die Logistikdienstleister waren die letzten zw&ouml;lf Monaten gute Monate: Das Aufkommen ist bei den meisten im Vergleich zu dem entsprechenden Vorjahreszeitraum (Q2/2016 bis Q1/2017) gestiegen. Nur 7,9 Prozent der befragten Dienstleister gaben an, dass das Volumen gesunken ist. &Auml;hnlich, aber nicht ganz so positiv sieht es bei den Verladern aus. Dort berichten immerhin 17 Prozent von einem sinkenden Aufkommen in den letzten zw&ouml;lf Monaten.</p>",
            "sorting_index": 10,
            "published": 1
        },
        {
            "id": "2146290",
            "online_date": "2018-03-27 14:11:00",
            "change_date": "2018-04-10 11:27:41",
            "title": "Veränderung des Aufkommens im Vergleich zum Vorquartal (Anteil der Unternehmen in Prozent)",
            "type": "Column",
            "js_code": "(function()\n{\nvar chart_container_name = \"chart_2146290\";\n                   \n                  var data = google.visualization.arrayToDataTable([\n['','gestiegen','konstant','gesunken'],\n['Verlader ',33.30,52.10,14.60],\n['Logistikdienstleister',28.10,45.30,26.60],\n]);\nvar formatter1 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter1.format(data, 1);\nvar formatter2 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter2.format(data, 2);\nvar formatter3 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter3.format(data, 3);\n var options = {\n                        colors: ['#e22713', '#022d5c', '#555f6a', '#a6a6a6', '#e6e6e6', '#f6f6f6']\n\n                    ,vAxis: {\ntitle: 'Prozent'\n}\n    \n};\n                    var chart = new google.charts.Bar(document.getElementById(chart_container_name));            \n                    chart.draw(data, google.charts.Bar.convertOptions(options));\n                  \n                \n})();\n",
            "html_code": "<div id=\"chart_2146290\" class=\"chart chart-column\"></div>",
            "headline": "Entwicklung des Aufkommens im ersten Quartal 2018 im Vergleich zum Vorquartal",
            "text": "<p>Bei den Logistikdienstleistern ist das erste Quartal 2018 eher ruhig verlaufen. Der Anteil derjenigen, bei denen im Vergleich zum Vorquartel die Mengen gestiegen sind, ist etwa so gro&szlig; wie der Anteil derjenigen, bei denen die Mengen gesunken sind. Bei den Verladern sieht es hingegen etwas anders aus. Bei ihnen verzeichnete immerhin ein Drittel ein Wachstum auch im ersten Quartal 2018.</p>",
            "sorting_index": 20,
            "published": 1
        },
        {
            "id": "2142808",
            "online_date": "2018-03-16 16:34:00",
            "change_date": "2018-04-13 11:24:42",
            "title": "Aktuelle Preise von EPAL Europaletten",
            "type": "External",
            "html_code": "<style type=\"text/css\">\n\n\t\t.widget-swoplo {\n\t\t\twidth:100%;\n\t\t\tpadding:0;\n\t\t\tmargin:0;\n\t\t\tfont-family:\"Helvetica Neue\", Helvetica, Arial, sans-serif;\n\t\t}\n\n\t\t.widget-swoplo h6 {\n\t\t\tfont-size:16px;\n\t\t\tfont-weight:bold;\n\t\t\tcolor:#444444;\n\t\t\tmargin:0 0 20px 0;\n\t\t}\n\n\t\t.widget-swoplo .pricing {\n\t\t\twidth:100%;\n\t\t\tmargin:0;\n\t\t\tpadding:0;\n\t\t\tborder:none;\n\t\t\tborder-collapse:collapse;\n\t\t\ttext-align:left;\n\t\t}\n\n\t\t.widget-swoplo .pricing thead tr th {\n\t\t\tvertical-align:middle;\n\t\t\tbackground-color:#ebebeb;\n\t\t\tborder-bottom:1px solid #ffffff;\n\t\t\tmargin:0;\n\t\t\tpadding:20px 0 10px;\n\t\t\ttext-align:left;\n\t\t\tfont-size:14px;\n\t\t\tfont-weight:bold;\n\t\t\tcolor:#444444;\n\t\t}\n\n\t\t.widget-swoplo .pricing thead tr th span {\n\t\t\tdisplay:inline-block;\n\t\t\twidth:14px;\n\t\t\theight:14px;\n\t\t\tmargin:0 0 0 10px;\n\t\t\tbackground-color:#022d5c;\n\t\t\t-webkit-border-radius:50%;\n\t\t\t-moz-border-radius:50%;\n\t\t\tborder-radius:50%;\n\t\t\tfont-family:Courier New, Courier, Lucida Sans Typewriter, Lucida Typewriter, monospace;\n\t\t\tcolor:#ffffff;\n\t\t\tfont-weight:bold;\n\t\t\tfont-size:13px;\n\t\t\ttext-align:center;\n\t\t}\n\n\t\t.widget-swoplo .pricing tbody:before {\n\t\t\tcontent:\"\";\n\t\t\tdisplay:block;\n\t\t\tline-height:1px;\n\t\t\tcolor:transparent;\n\t\t}\n\n\t\t.widget-swoplo .pricing tbody tr td {\n\t\t\tborder:1px solid #ebebeb;\n\t\t\tmargin:0;\n\t\t\tpadding:20px 10px;\n\t\t\ttext-align:left;\n\t\t\tfont-size:14px;\n\t\t\tcolor:#444444;\n\t\t\twidth:20%;\n\t\t}\n\n\t\t.widget-swoplo .pricing tbody tr td.title {\n\t\t\tfont-weight:bold;\n\t\t\tline-height:20px;\n\t\t}\n\n\t\t.widget-swoplo .pricing tbody tr td.title .small {\n\t\t\tdisplay:block;\n\t\t\tfont-weight:normal;\n\t\t}\n\n\t\t.widget-swoplo .pricing tbody tr td a {\n\t\t\tcolor:#022d5c;\n\t\t\ttext-decoration:underline;\n\t\t}\n\n\t\t.widget-swoplo .pricing tbody tr td a:hover {\n\t\t\tcolor:#022d5c;\n\t\t\ttext-decoration:none;\n\t\t}\n\n\t\t.widget-swoplo .pricing tfoot tr td {\n\t\t\tfont-size:12px;\n\t\t\tcolor:#444444;\n\t\t\tpadding:15px 0 0;\n\t\t\tfont-weight:normal;\n\t\t}\n\n\t\t.widget-swoplo .pricing tfoot tr td .homelink {\n\t\t\tdisplay:block;\n\t\t\tfont-size:12px;\n\t\t\tcolor:#022d5c;\n\t\t\tfont-weight:bold;\n\t\t\ttext-decoration:none;\n\t\t}\n\n\t\t.widget-swoplo .pricing tfoot tr td .homelink:hover {\n\t\t\ttext-decoration:underline;\n\t\t}\n\n\t\t.widget-swoplo .pricing tfoot tr td.logo {\n\t\t\ttext-align:right;\n\t\t\tpadding:10px 20px 0;\n\t\t}\n\t\t\n\t\t@media only screen and (max-width:480px) {\n\n\t\t\t.widget-swoplo .pricing thead tr th {\n\t\t\t\tpadding:5px;\n\t\t\t\ttext-align:center;\n\t\t\t\tfont-size:12px;\n\t\t\t}\n\n\t\t\t.widget-swoplo .pricing tbody tr td {\n\t\t\t\tpadding:5px;\n\t\t\t\ttext-align:center;\n\t\t\t}\n\n\t\t\t.widget-swoplo .pricing tbody tr td.price span {\n\t\t\t\tdisplay:block;\n\t\t\t}\n\n\t\t\t.widget-swoplo .pricing tbody tr td.title {\n\t\t\t\tposition:relative;\n\t\t\t\tfont-weight:bold;\n\t\t\t\tline-height:auto;\n\t\t\t\tpadding:5px;\n\t\t\t\twidth:10%;\n\t\t\t\theight:170px;\n\t\t\t}\n\t\t\t\n\t\t\t.widget-swoplo .pricing tbody tr td.title div {\n\t\t\t\tposition:absolute;\n\t\t\t\tleft:-67px;\n\t\t\t\ttop:71px;\n\t\t\t\tdisplay:block;\n\t\t\t\twidth:170px;\n\t\t\t\tline-height:16px;\n\t\t\t\ttransform: rotate(270deg);\n\t\t\t\t-webkit-transform: rotate(270deg);\n\t\t\t\t-moz-transform: rotate(270deg);\n\t\t\t\t-o-transform: rotate(270deg);\n\t\t\t\t-ms-transform: rotate(270deg);\n\t\t\t}\n\t\t\n\t\t}\n\n\t</style><div class=\"widget-swoplo\"><table class=\"pricing\"><thead><tr><th>&nbsp;</th><th>Neu</th><th>Klasse A</th><th>Klasse B</th><th>Klasse C</th></tr></thead><tbody><tr><td class=\"title\"><div>Aktuelle Angebote</div></td><td class=\"price\"><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><span><nobr>7,90 &euro;</nobr></span> - \n\t\t\t\t\t\t\t<span><nobr>7,90 &euro;</nobr></span></a></td><td class=\"price\"><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><span><nobr>6,00 &euro;</nobr></span> - \n\t\t\t\t\t\t\t<span><nobr>7,40 &euro;</nobr></span></a></td><td class=\"price\"><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><span><nobr>4,50 &euro;</nobr></span> - \n\t\t\t\t\t\t\t<span><nobr>6,60 &euro;</nobr></span></a></td><td class=\"price\"><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><span><nobr>2,20 &euro;</nobr></span> - \n\t\t\t\t\t\t\t<span><nobr>6,10 &euro;</nobr></span></a></td></tr><tr><td class=\"title\"><div>Ist Transaktionspreis <span class=\"small\">(ab Station)</span></div></td><td><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><nobr>7,90 &euro;</nobr></a></td><td><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><nobr>6,73 &euro;</nobr></a></td><td><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><nobr>5,21 &euro;</nobr></a></td><td><a href=\"https://www.swoplo.com/de/sources?partner=verkehrsrundschau&amp;campaign=pricewidget\" target=\"_blank\"><nobr>4,60 &euro;</nobr></a></td></tr></tbody></table></div>",
            "headline": "Preise von EPAL Europaletten",
            "text": "<p>In dieser Tabelle finden Sie Preise von EPAL Europaletten, sortiert nach Neuware sowie den Klassen A, B und C. Unser Kooperationspartner swoplo AG, eine branchen&uuml;bergreifende Palettenb&ouml;rse, liefert die Informationen t&auml;glich anhand der aktuellen Preise im Portal.</p>",
            "sorting_index": 80,
            "published": 1
        }
    ],
    "google_js_pre": "<script type=\"text/javascript\" src=\"https://www.gstatic.com/charts/loader.js\"></script>\n    <script>\n        (function()\n        {\n            google.charts.load('current', {'packages':['table', 'line', 'bar', 'corechart'], 'language': 'de'});\n            var drawCharts = function()\n            {",
    "google_js_suffix": "};\n            google.charts.setOnLoadCallback(drawCharts);\n            window.addEventListener(\"resize\", drawCharts);\n        })();\n    </script>",
    "tags": "Pegel, Christian (SPD)",
    "published": 1
}
```

This endpoint retrieves a specific Key Figure Overview.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/keyfigure-overview/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Key Figure Overview to retrieve

==================
## Get All Key Figure Charts from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/keyfigure-chart/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2142808",
    "2146290",
    "2146309",
    "2146084",
    "2142662",
    "2142659",
    "2146167",
    "2142658",
    "2145943",
    "2146261",
    "2145903",
    "2142646",
    "2146203",
    "2142661"
]
```

This endpoint retrieves all Key Figure Charts with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/keyfigure-chart/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Key Figure Chart


```shell
curl "http://rest-api.verkehrsrundschau.de/keyfigure-chart/detail/2145903"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2145903",
    "online_date": "2018-03-26 16:51:00",
    "change_date": "2018-04-09 13:24:10",
    "title": "VerkehrsRundschau-Index",
    "type": "Line",
    "js_code": "(function()\n{\nvar chart_container_name = \"chart_2145903\";\n \n   \n                var data = google.visualization.arrayToDataTable([\n['Quartal/Jahr','VR-Index in Punkten'],\n['Q1/2015',120.32],\n['Q2/2015',120.35],\n['Q3/2015',121.08],\n['Q4/2015',122.11],\n['Q1/2016',121.56],\n['Q2/2016',121.63],\n['Q3/2016',120.96],\n['Q4/2016',121.24],\n['Q1/2017',122.14],\n['Q2/2017',122.08],\n['Q1/2018',123.23],\n]);\nvar formatter1 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter1.format(data, 1);\n  \n          var options = {\n          colors: ['#e22713', '#022d5c', '#555f6a', '#a6a6a6', '#e6e6e6', '#f6f6f6'],\n\n          legend: { position: 'bottom' },hAxis: {\ntitle: 'Quartal/Jahr',\ngridlines: {\ncolor: '#cccccc'\n},\nbaselineColor: '#cccccc',\nbaseline: -1\n},\nvAxis: {\ntitle: 'VR-Index in Punkten'\n,format:'###.###'\n}\n};\n                    \n                    var chart = new google.charts.Line(document.getElementById(chart_container_name));\n                    chart.draw(data, google.charts.Line.convertOptions(options));              \n                \n})();\n",
    "html_code": "<div id=\"chart_2145903\" class=\"chart chart-line\"></div>",
    "headline": "Preisindex für den Straßengüterverkehr in Deutschland",
    "text": "<p>Der VerkehrsRundschau-Index ist im ersten Quartal 2018 um 0,93 Prozent gegen&uuml;ber dem zweiten Quartal 2017 auf 123,23 Punkte gestiegen. Verteilt auf die drei Quartale ergibt sich ein Preisanstieg um 0,31 Prozent pro Quartal. Die im ersten Quartal 2018 erreichten 123,23 Punkte sind der h&ouml;chste Stand seit Bestehen des Index im Jahr 2007. Beim VR-Index werden jedes Quartal die Transportpreise im Stra&szlig;eng&uuml;terverkehr in Deutschland ermittelt. Es gibt den Index seit 2007. Er ist damit der &auml;lteste Index am Markt. Zugleich gibt es keinen Index im Stra&szlig;eng&uuml;terverkehr, der so schnell die Transportpreise zum abgelaufenen Quartal ver&ouml;ffentlicht.</p>",
    "sorting_index": 70,
    "published": 1
}
```

This endpoint retrieves a specific Key Figure Chart.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/keyfigure-chart/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the  Key Figure Chart to retrieve

==================

# Deleted Objects

## Get All Deleted Objects from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/deleted/1501545600"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    {
        "id": 2147386,
        "content_class": "VrVideoTopic",
        "deleted_date": "2018-03-30T13:54:03+0200"
    },
    {
        "id": 2147385,
        "content_class": "VrVideo",
        "deleted_date": "2018-03-30T13:52:29+0200"
    },
    {
        "id": 2147384,
        "content_class": "VrMagazineIssue",
        "deleted_date": "2018-03-30T13:50:01+0200"
    },
    {
        "id": 2147383,
        "content_class": "VrMagazineArticle",
        "deleted_date": "2018-03-30T13:49:42+0200"
    },
    {
        "id": 2147381,
        "content_class": "VrNews",
        "deleted_date": "2018-03-30T13:44:44+0200"
    }
]
```

This endpoint retrieves all Deleted Objects with deleted dates greater than given timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/deleted/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with





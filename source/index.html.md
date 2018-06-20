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
curl "http://rest-api.verkehrsrundschau.de/course/detail/2164820"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164820",
    "online_date": "2018-05-16 00:00:00",
    "change_date": "2018-06-08 09:13:52",
    "title": "Test1",
    "category": "Meine Kategorie",
    "author": [
        {
            "id": "2164817",
            "online_date": "2018-05-16 15:40:00",
            "change_date": "2018-05-16 15:40:31",
            "title": "Olleg Bollek",
            "published": 1
        }
    ],
    "is_credit_package_required": 1,
    "has_certificate": 1,
    "certificate_template": "VerkehrsRundschau plus",
    "credit_cost": "1",
    "is_unlock_modules_one_after_one": 1,
    "retries_final_test": "3",
    "goals": "Kugelstoßen Weltrekord.\r\nWeiter als 2 Meter springen.",
    "target_audience": "Kugelstoßer, Weitspringer",
    "teaser": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5709/Xurzon_GettyImages_iStock-803348678.jpg",
    "image_copyright": "Xurzon/Getty Images/iStock",
    "image_caption": "dasd asdasdasdasda dasdasdasdasd",
    "video": [],
    "modules": [
        {
            "id": "2164833",
            "online_date": "2018-05-16 15:44:00",
            "change_date": "2018-06-08 09:13:52",
            "title": "Modul 1",
            "text": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
            "type": "WBT",
            "is_final_test": 1,
            "translations": [
                {
                    "id": "2164832",
                    "online_date": "2018-05-16 15:46:00",
                    "change_date": "2018-06-08 09:13:52",
                    "title": "Sprache 1",
                    "wbt_upload": "https://media1.verkehrsrundschau.de/sixcms/media.php/5828/original.txt",
                    "language": {
                        "id": "2164813",
                        "online_date": "2018-05-16 15:30:00",
                        "change_date": "2018-05-16 15:30:02",
                        "title": "Deutsch",
                        "published": 1
                    },
                    "alt_title": "Titel für die Extrawurst",
                    "alt_text": "Jajajaja.",
                    "published": 1
                }
            ],
            "sorting_index": 0,
            "published": 1
        }
    ],
    "tools": [
        {
            "id": "2162262",
            "online_date": "2018-05-07 00:00:00",
            "change_date": "2018-05-07 14:38:59",
            "title": "Zuwächse der Mautsätze Stand 7.5.2018",
            "type": "Studien&Dokumente",
            "upload": "https://media1.verkehrsrundschau.de/sixcms/media.php/4513/Zuwachs%20Mautsaetze.pdf",
            "teaser": "Die voraussichtlichen Zuwächse der Mautsätze im Vergleich. Grundlage für die Angaben bilden der Entwurf des 5. Gesetzes zur Änderung des Bundesfernstraßenmautgesetzes vom 27. April 2018 und das Wegekostengutachten 2018-2022.",
            "tags": "Markt Lkw-Landverkehr & Stückgut,Verkehr Maut Deutschland Lkw Pkw",
            "published": 1
        },
        {
            "id": "1878398",
            "online_date": "2018-04-06 00:00:00",
            "change_date": "2018-04-06 11:36:45",
            "title": "Entsenderegeln in Europa",
            "type": "Studien&Dokumente",
            "upload": "https://media1.verkehrsrundschau.de/sixcms/media.php/4513/Entsenderegeln-in-Europa.pdf",
            "teaser": "Die Regeln für die Entsendung ausländischer Mitarbeiter wurden in vielen Nachbarländern verschärft. Gebietsfremde Arbeitgeber müssen ihre Arbeitnehmer anmelden. Die aktuellen Vorschriften finden Sie hier auf einen Blick. \r\n\r\nStand: März 2018",
            "image": "/sixcms/media.php/4494/Europafahne%20Picture%20Alliance%20CHROMORANGE%20620.jpg",
            "tags": "E-Benelux,E-Frankreich,E-Nordeuropa,E-Österreich,E-Polen,E-Schweiz,E-Tschechien-Slowakei,Geld Mindestlohn,Recht Transport und Spedition,Beruf Arbeitsrecht & Personalwesen,Geld Löhne und Gehälter",
            "published": 1
        },
        {
            "id": "2131974",
            "online_date": "2018-02-19 00:00:00",
            "change_date": "2018-02-19 10:14:51",
            "title": "Luftverkehrskonzept des Bundesministeriums für Verkehr und digitale Infrastruktur",
            "type": "Studien&Dokumente",
            "upload": "https://media1.verkehrsrundschau.de/sixcms/media.php/4513/luftverkehrskonzept.pdf",
            "teaser": "Das Dokument enthält das Luftverkehrskonzept des BMVI mit Maßnahmen zur Stärkung und Sicherung des Luftverkehrsstandorts Deutschland ",
            "tags": "Markt Luftfracht,Verkehr Infrastruktur allgemein,Verkehrspolitik Deutschland",
            "published": 1
        }
    ],
    "tags": "D-Nordrhein-Westfalen",
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
    "teaser": "Mein Teaser",
    "text": "Mein Text",
    "video_html": "<iframe src=\"https://player.vimeo.com/video/268216832?title=0&byline=0&portrait=0&color=e22713&app_id=122963\" width=\"1055\" height=\"593\" frameborder=\"0\" title=\"Why Are You Honking?\" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>",
    "length": "05:26",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5827/700619362_960.jpg",
    "tags": "Mein Tag",
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
    "change_date": "2018-06-07 09:27:28",
    "title": "VerkehrsRundschau-Index",
    "type": "Line",
    "js_code": "(function()\n{\nvar chart_container_name = \"chart_2145903\";\n \n   \n                var data = google.visualization.arrayToDataTable([\n['Quartal/Jahr','VR-Index in Punkten'],\n['Q1/2015',120.32],\n['Q2/2015',120.35],\n['Q3/2015',121.08],\n['Q4/2015',122.11],\n['Q1/2016',121.56],\n['Q2/2016',121.63],\n['Q3/2016',120.96],\n['Q4/2016',121.24],\n['Q1/2017',122.14],\n['Q2/2017',122.08],\n['Q1/2018',123.23],\n]);\nvar formatter1 = new google.visualization.NumberFormat({pattern:'###.##'});\nformatter1.format(data, 1);\n  \n          var options = {\n          colors: ['#e22713', '#022d5c', '#555f6a', '#a6a6a6', '#e6e6e6', '#f6f6f6'],\n\n          legend: { position: 'bottom' },hAxis: {\ntitle: 'Quartal/Jahr',\ngridlines: {\ncolor: '#cccccc'\n},\nbaselineColor: '#cccccc',\nbaseline: -1\n},\nvAxis: {\ntitle: 'VR-Index in Punkten'\n,format:'###.###'\n}\n};\n                    \n                    var chart = new google.charts.Line(document.getElementById(chart_container_name));\n                    chart.draw(data, google.charts.Line.convertOptions(options));              \n                \n})();\n",
    "html_code": "<div id=\"chart_2145903\" class=\"chart chart-line\"></div>",
    "headline": "Preisindex für den Straßengüterverkehr in Deutschland",
    "teaser": "<p>ajbgkdf</p>",
    "text": "<p>Der VerkehrsRundschau-Index ist im ersten Quartal 2018 um 0,93 Prozent gegen&uuml;ber dem zweiten Quartal 2017 auf 123,23 Punkte gestiegen. Verteilt auf die drei Quartale ergibt sich ein Preisanstieg um 0,31 Prozent pro Quartal. Die im ersten Quartal 2018 erreichten 123,23 Punkte sind der h&ouml;chste Stand seit Bestehen des Index im Jahr 2007. Beim VR-Index werden jedes Quartal die Transportpreise im Stra&szlig;eng&uuml;terverkehr in Deutschland ermittelt. Es gibt den Index seit 2007. Er ist damit der &auml;lteste Index am Markt. Zugleich gibt es keinen Index im Stra&szlig;eng&uuml;terverkehr, der so schnell die Transportpreise zum abgelaufenen Quartal ver&ouml;ffentlicht.</p>",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/209/VR-Index.PNG",
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

# Market Overview

## Get All Market Overviews from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "1035643",
    "1015825",
    "1831688",
    "1051978",
    "1062793",
    "1049861",
    "1049000",
    "1019238"
]
```

This endpoint retrieves all Market Overviews with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get specific Market Overview


```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview/detail/1015825"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1015825",
    "online_date": "2017-11-27 00:00:00",
    "change_date": "2017-11-28 12:52:06",
    "title": "Marktübersicht: Miete 2017/2018",
    "type": "Standard",
    "teaser": "In der interaktiven Marktübersicht können Sie die Gesamtangebote von über dreißig lokalen und nationalen NFZ-Vermietern direkt miteinander vergleichen. Über eine Filterfunktion lässt sich gezielt nach Vermietern suchen, die den gewünschten Service und die benötigten Fahrzeuge bieten.",
    "text": "<p><b>Viel Auswahl, mehr Service</b></p>\r\n<p><b>Mietkunden profitieren von&nbsp;gr&ouml;&szlig;eren Flotten und mehr&nbsp;Service, m&uuml;ssen sich aber&nbsp;teilweise auf steigende Raten&nbsp;einstellen. Diese Trends&nbsp;zeigt die gro&szlig;e Markt&uuml;bersicht&nbsp;</b><b>Nutzfahrzeugmiete.</b><br /><br />Deutschlands Nutzfahrzeugvermieter&nbsp;haben offenbar gut zu tun. Das&nbsp;ist einer der zentralen Trends, die&nbsp;eine gro&szlig;e Umfrage der VerkehrsRundschau&nbsp;unter Deutschlands f&uuml;hrenden Vermietern&nbsp;von Lkw und Trailern ergab. So&nbsp;berichtet der Gro&szlig;teil der Unternehmen,&nbsp;die im Rahmen der j&auml;hrlichen Markt&uuml;bersicht&nbsp;Nutzfahrzeugmiete Angaben zur&nbsp;j&uuml;ngsten Gesch&auml;ftsentwicklung machten,&nbsp;von einer stabilen oder gar gestiegenen&nbsp;Auslastung. Und die gute Laune auf&nbsp;Vermieterseite d&uuml;rfte anhalten: Die&nbsp;Gesch&auml;ftsentwicklung f&uuml;r das Transportgewerbe&nbsp;sch&auml;tzt der Gro&szlig;teil f&uuml;r die kommenden&nbsp;Monate positiv oder zumindest&nbsp;stabil ein.<br /><br />Aber nun zu der f&uuml;r den potenziellen&nbsp;Mietkunden wohl spannendsten Frage,&nbsp;denn &uuml;ber drei Viertel der f&uuml;r die Markt&uuml;bersicht&nbsp;befragten Vermieter machten&nbsp;Angaben zur Preisentwicklung. Davon&nbsp;verzeichnete deutlich &uuml;ber die H&auml;lfte in&nbsp;den vergangenen zw&ouml;lf Monaten stabile&nbsp;Mietraten. Aber: Dies k&ouml;nnte sich bei so&nbsp;manchem Anbieter im Laufe der kommenden&nbsp;zw&ouml;lf Monate &auml;ndern. So plant&nbsp;rund ein Drittel der Unternehmen Mieterh&ouml;hungen,&nbsp;mit fallenden Raten brauchen&nbsp;Mieter den Umfrageergebnissen&nbsp;zufolge erst gar nicht rechnen. Investiert&nbsp;wurde in diesem Jahr auf jeden Fall in die&nbsp;Flotten. Rund 40 Prozent der Vermieter&nbsp;melden eine gleich gro&szlig;e Flotte als noch&nbsp;vor zw&ouml;lf Monaten, &uuml;ber ein Drittel hat&nbsp;seinen Fuhrpark sogar ausgebaut. Die Wenigsten&nbsp;haben im Vergleich zum Herbst&nbsp;2016 eine verkleinerte Flotte vorzuweisen.&nbsp;<br /><br /><b>Mehr Spezialfahrzeuge<br /></b>Bei den Erweiterungen des Angebots eine&nbsp;gr&ouml;&szlig;ere Rolle spielen bei nicht wenigen&nbsp;Vermietern offenbar Spezialfahrzeuge.&nbsp;Pema beispielsweise hat in diesem Jahr das&nbsp;Angebot an Erntefahrzeugen ausgebaut,&nbsp;indem der Fahrzeugbestand an gro&szlig;volumigen&nbsp;Kippmulden deutlich erh&ouml;ht&nbsp;wurde. Lieferant der dreiachsigen&nbsp;Sattelanh&auml;nger mit Aluminium-Kastenmulde&nbsp;ist Schmitz Cargobull. Der badenw&uuml;rttembergische&nbsp;Vermieter Mezger meldet&nbsp;als Neuzug&auml;nge in der Flotte unter&nbsp;anderem Kippsattel mit unterschiedlichen&nbsp;Ausstattungen wie Thermomulden und&nbsp;Mulden mit hydraulischer Heckklappe&nbsp;sowie Sattelzugmaschinen f&uuml;r das Baugewerbe&nbsp;wie Mercedes Arocs HAD und&nbsp;Volvo X-Track. Erst seit einigen Jahren auf&nbsp;dem deutschen Markt pr&auml;sent ist Fraikin.&nbsp;&bdquo;Als herstellerunabh&auml;ngige&nbsp;Tochter der&nbsp;franz&ouml;sischen Fraikin-Gruppe setzen wir&nbsp;gegenw&auml;rtig unsere strategischen Wachstumsziele&nbsp;in den verschiedenen Marktsegmenten&nbsp;erfolgreich um. Und zwar sowohl&nbsp;qualitativ als auch quantitativ&ldquo;, betont&nbsp;Vertriebsleiter Marcus Burmeister. Unternehmensangaben&nbsp;zufolge ist die Gr&ouml;&szlig;e des&nbsp;Fraikin-Fuhrparks hierzulande in den vergangenen&nbsp;zw&ouml;lf Monaten um 40 Prozent&nbsp;gewachsen. Eine Besonderheit ergibt sich&nbsp;bei der ungew&ouml;hnlich langen H&ouml;chstmietdauer:&nbsp;Da Fraikin Deutschland sich neben&nbsp;Standardeinheiten stark auf Abfall-, Entsorgungs-&nbsp;und Kommunalfahrzeuge fokussiert,&nbsp;k&ouml;nnen Fahrzeuge f&uuml;r einen Zeitraum&nbsp;von einem bis zu 120 Monate&nbsp; vemietet&nbsp;werden. Auch der auf MAN-Fahrzeuge&nbsp;spezialisierte Vermieter BFS hat den Bereich&nbsp;der Spezialfahrzeuge ausgebaut und&nbsp;bietet neuerdings auch Saugbagger an. Zu&nbsp;den weiteren Neuzug&auml;ngen in der BFSFlotte&nbsp;in diesem Jahr z&auml;hlt au&szlig;erdem der&nbsp;Transporter MAN TGE.<br /><br /><b>Gro&szlig;e Auswahl bei kleinen Fahrzeugen<br /></b>Apropos Transporter: Ihre Flotten aufger&uuml;stet&nbsp;haben auch die Vermieter vornehmlich&nbsp;kleinerer Nutzfahrzeuge. Buchbinder&nbsp;etwa hat zuletzt neben dem neuen&nbsp; MAN-Transporter&nbsp;unter anderem diverse&nbsp;3,5-Tonner von Ford sowie Iveco Daily-Koffer (7,2 Tonnen) angeschafft.&nbsp;<br />Europcar bietet gewerblichen Kunden an&nbsp;seinen Nutzfahrzeug-Stationen seit diesem&nbsp;Jahr eine Sonderflotte an. Diese umfasst&nbsp;beispielsweise 12- und 14-Tonner,&nbsp;K&uuml;hlfahrzeuge, Frischdienstk&uuml;hler, Dreiseitenkipper&nbsp;und Fahrzeuge mit Doppelkabine&nbsp;und Anh&auml;ngerkupplung. Sixt Rent&nbsp;a Truck derweil hat K&uuml;hlfahrzeuge aus&nbsp;dem Hause Mercedes-Benz ins Sortiment&nbsp;genommen. Bei Hertz&nbsp; sind unter anderem&nbsp;Mercedes-Sprinter und Citroen Jumper,&nbsp;jeweils mit Koffer und Ladebordwand,&nbsp;hinzugekommen. Mietinteressenten finden&nbsp;aber nicht nur viele neue Fahrzeugmodelle&nbsp;in den Flotten der Vermieter,&nbsp;sondern k&ouml;nnen teilweise auch auf mehr&nbsp;Service und ausgefeiltere Technik in den&nbsp;Fahrzeugen bauen.<br />&bdquo;Die Digitalisierung h&auml;lt derzeit in allen&nbsp;Gesch&auml;ftsbereichen Einzug - auch wir als&nbsp;Nutzfahrzeugvermieter setzen uns damit&nbsp;intensiv auseinander&ldquo;, betont Martin Kehnen,&nbsp;Leiter der Mercedes-Benz Charter-Way Miete. Seit M&auml;rz dieses Jahres werde&nbsp;&nbsp;demnach in allen schweren Lkw von Mercedes-Benz das &bdquo;Truck Data Center&ldquo; verbaut,&nbsp;ein neues&nbsp; Vernetzungsmodul, das die Basis f&uuml;r bereits bestehende und k&uuml;nftige&nbsp;Konnektivit&auml;tsl&ouml;sungen bildet. &bdquo;Charter-Way hat damit den Grundstein gelegt, sein&nbsp;Angebot um neue digitale L&ouml;sungen zu&nbsp;erweitern, die Mercedes-Benz und Fleet-Board auf den Markt bringen&ldquo;, so Kehnen.&nbsp;<br /><br /><b>Digitale R&uuml;cknahme</b>&nbsp;<br />Dar&uuml;ber hinaus wurde ein digitales System&nbsp;zur R&uuml;cknahme der Fahrzeuge eingef&uuml;hrt.&nbsp;&bdquo;Kunden erhalten wesentlich&nbsp;schneller das R&uuml;cknahmeprotokoll,&nbsp;gleichzeitig steht das Fahrzeug fr&uuml;her f&uuml;r&nbsp;eine Anschlussvermietung zur Verf&uuml;gung&ldquo;,&nbsp;so Kehnen. Auch MAN Financial&nbsp;Services setzt eigenen Angaben zufolge auf&nbsp;innovative Produkte, um Mehrwerte f&uuml;r&nbsp;die Kunden zu schaffen. &bdquo;So spielen Digitalisierung,&nbsp;elektrische Antriebe und Trailer&nbsp;der Zukunft auch im Vermietgesch&auml;ft&nbsp;eine wichtige Rolle, auf die wir uns derzeit&nbsp;stark konzentrieren&ldquo;, sagt der neue Euro-Leasing-Chef Armin Hofer.<br /><br /><b>Flexibilit&auml;t ist Trumpf<br /></b>Pema derweil will mit flexiblen Angeboten&nbsp;f&uuml;r die Mieter punkten und hat das neue&nbsp;Produkt Rent Plus eingef&uuml;hrt: Nach der&nbsp;vereinbarten Vertragslaufzeit kann der&nbsp;Kunde zwischen den Optionen Verl&auml;ngern,&nbsp;R&uuml;ckgabe oder Erwerb des Fahrzeuges&nbsp;w&auml;hlen. Auch die Vereinbarung einer&nbsp;vorzeitigen R&uuml;ckgabeoption ist m&ouml;glich.&nbsp;&bdquo;Wir besch&auml;ftigen uns immer mit der Erweiterung&nbsp;des Dienstleistungs- sowie Produktportfolios&ldquo;,&nbsp;betont Vertriebsleiter Udo&nbsp;Brestel. &bdquo;Wir wissen, wie wichtig Flexibilit&auml;t&nbsp;in unserem Gesch&auml;ft ist, und setzen&nbsp;alles daran, diese Flexibilit&auml;t unseren Kunden&nbsp;bieten zu k&ouml;nnen.&ldquo;<br />Das Unternehmen beschr&auml;nkt sich &uuml;brigens&nbsp;nicht nur auf die Vermietung von&nbsp;Fahrzeugen, sondern ist zudem mit einer&nbsp;hauseigenen Akademie auch im Bereich&nbsp;der Aus- und Weiterbildung unterwegs.&nbsp;Zu den Erweiterungen im Kursangebot&nbsp;z&auml;hlt Unternehmensangaben zufolge&nbsp;unter anderem ein Fachkundelehrgang&nbsp;gef&auml;hrlicher Abfall.&nbsp;<br /><br /><b>Personalkarussel dreht sich&nbsp;</b><br />Neuigkeiten gab es aber nicht nur im Bereich&nbsp;Flotte und Service, sondern auch in&nbsp;Sachen Personal. Am meisten getan hat&nbsp;sich in der F&uuml;hrungsetage von Euro-Leasing/MAN Rental, wo zuletzt gleich mehrere&nbsp;Schl&uuml;sselpositionen neu besetzt wurden.&nbsp;So wurde nicht nur Armin Hofer,&nbsp;bislang Volkswagen Bank, zum neuen&nbsp;CEO berufen. Er l&ouml;st Nils Uphoff ab, der&nbsp;nach dem Ausscheiden Marco Reichweins&nbsp;als Interims-Gesch&auml;ftsf&uuml;hrer diente. Auch&nbsp;die Verantwortlichkeiten im Vertrieb&nbsp;haben sich ge&auml;ndert. Matthias Szupories&nbsp;hat als Leiter Vertrieb und Marketing das&nbsp;Unternehmen verlassen, die Vertriebsleitung&nbsp;obliegt nun Marco Herre. Im Sommer&nbsp;wurde zudem die Position des Leiters&nbsp;Vertrieb Norddeutschland mit dem ehemaligen&nbsp;Volvo-Mann Holger Albermann&nbsp;besetzt. Er k&uuml;mmert sich nun gemeinsam&nbsp;mit Wolfgang Kromer, Leiter Vertrieb Retail&nbsp;Deutschland, um die Anliegen der&nbsp;deutschen Kunden.<br />Auch bei KLVrent hat ein Wechsel an der&nbsp;Unternehmensspitze stattgefunden. So&nbsp;wurde die Gesch&auml;ftsf&uuml;hrung der deutschen&nbsp;Division an den nunmehrigen Alleingesellschafter&nbsp;Thomas Eberl &uuml;bergeben.&nbsp;Eberl, Gesch&auml;ftsf&uuml;hrer der gleichnamigen&nbsp;Spedition im oberbayerischen Aiging,&nbsp;hatte Ende 2016 alle Anteile der&nbsp;deutschen KLVRent &uuml;bernommen.</p>\r\n<p><i>Mareike Haus</i></p>",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/4494/Fotolia_116569852_Subscription_Yearly_XXL_620x385.jpg",
    "image_copyright": "Fotolia/Assetseller",
    "image_caption": "Die meisten Lkw-Vermieter melden gleich groß\r\ngebliebene oder gewachsene Flotten",
    "headline_howto": "Marktübersicht: Miete Leasing",
    "text_howto": "Wählen Sie die für Sie interessanten Merkmale aus der Liste aus und starten Sie den Vergleich mit dem Button \"Filter aktivieren\". In der Tabelle können Sie noch einmal die Marken selektieren und sich eine individuelle Ansicht erstellen.",
    "headline_attribute": "Miete Leasing Vergleich - Aktivieren Sie Ihren Filter!",
    "headline_items": "Marken-Vergleich",
    "attributes": [
        {
            "id": "1015824",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Marktsegment",
            "type": "Trenner",
            "sorting_index": 10,
            "published": 1
        },
        {
            "id": "1016858",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Kurzzeitmiete",
            "type": "Flag",
            "sorting_index": 20,
            "published": 1
        },
        {
            "id": "1015963",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Langzeitmiete",
            "type": "Flag",
            "sorting_index": 30,
            "published": 1
        },
        {
            "id": "1710717",
            "online_date": "2015-10-21 13:53:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Mietkauf",
            "type": "Flag",
            "sorting_index": 40,
            "published": 1
        },
        {
            "id": "1015964",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Leasing",
            "type": "Flag",
            "sorting_index": 50,
            "published": 1
        },
        {
            "id": "1015965",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Fullservice-Leasing",
            "type": "Flag",
            "sorting_index": 60,
            "published": 1
        },
        {
            "id": "1303934",
            "online_date": "2013-11-11 09:43:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Mindestmietdauer",
            "type": "Text",
            "sorting_index": 70,
            "published": 1
        },
        {
            "id": "2038445",
            "online_date": "2017-11-27 13:54:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Höchstmietdauer",
            "type": "Text",
            "sorting_index": 80,
            "published": 1
        },
        {
            "id": "1015966",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Fuhrpark: NFZ ab 3,5t (ziehende/gezogene Einheiten)",
            "type": "Text",
            "sorting_index": 90,
            "published": 1
        },
        {
            "id": "1016859",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Standorte (Zahl/PLZ-Gebiet)",
            "type": "Text",
            "sorting_index": 100,
            "published": 1
        },
        {
            "id": "1016861",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "NFZ-Partner",
            "type": "Text",
            "sorting_index": 110,
            "published": 1
        },
        {
            "id": "1016862",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Mehrwertdienste",
            "type": "Trenner",
            "sorting_index": 120,
            "published": 1
        },
        {
            "id": "1016863",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Komplettzug (Zugmaschine und Trailer)",
            "type": "Flag",
            "sorting_index": 130,
            "published": 1
        },
        {
            "id": "1016864",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:04",
            "title": "Wartung",
            "type": "Flag",
            "sorting_index": 140,
            "published": 1
        },
        {
            "id": "1016865",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Reparatur",
            "type": "Flag",
            "sorting_index": 150,
            "published": 1
        },
        {
            "id": "1016866",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Pannenservice",
            "type": "Flag",
            "sorting_index": 160,
            "published": 1
        },
        {
            "id": "1016867",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Ersatzfahrzeug",
            "type": "Flag",
            "sorting_index": 170,
            "published": 1
        },
        {
            "id": "1016868",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "KFZ-Versicherung",
            "type": "Flag",
            "sorting_index": 180,
            "published": 1
        },
        {
            "id": "1016869",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Reifenservice",
            "type": "Flag",
            "sorting_index": 190,
            "published": 1
        },
        {
            "id": "1016870",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Tankkarten",
            "type": "Flag",
            "sorting_index": 200,
            "published": 1
        },
        {
            "id": "1016871",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Telematik",
            "type": "Flag",
            "sorting_index": 210,
            "published": 1
        },
        {
            "id": "1016872",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "GEZ-Gebühren",
            "type": "Flag",
            "sorting_index": 220,
            "published": 1
        },
        {
            "id": "1016873",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "KFZ-Steuer",
            "type": "Flag",
            "sorting_index": 230,
            "published": 1
        },
        {
            "id": "1016874",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Schadensmanagement",
            "type": "Flag",
            "sorting_index": 240,
            "published": 1
        },
        {
            "id": "1016876",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Mautabrechnung",
            "type": "Flag",
            "sorting_index": 250,
            "published": 1
        },
        {
            "id": "1016877",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Gebrauchthandel",
            "type": "Flag",
            "sorting_index": 260,
            "published": 1
        },
        {
            "id": "1016878",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:05",
            "title": "Pflichtuntersuchungen",
            "type": "Flag",
            "sorting_index": 270,
            "published": 1
        },
        {
            "id": "1016879",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:06",
            "title": "App",
            "type": "Flag",
            "sorting_index": 280,
            "published": 1
        },
        {
            "id": "1848589",
            "online_date": "2016-11-08 14:38:00",
            "change_date": "2017-11-28 12:52:06",
            "title": "Wunschfarbe",
            "type": "Flag",
            "sorting_index": 290,
            "published": 1
        },
        {
            "id": "1848590",
            "online_date": "2016-11-08 14:38:00",
            "change_date": "2017-11-28 12:52:06",
            "title": "Hol- und Bringdienst",
            "type": "Flag",
            "sorting_index": 300,
            "published": 1
        },
        {
            "id": "1016880",
            "online_date": "2012-03-19 02:00:00",
            "change_date": "2017-11-28 12:52:06",
            "title": "weitere Mehrwertdienste",
            "type": "Text",
            "sorting_index": 310,
            "published": 1
        }
    ],
    "item_ids": [
        "1016890",
        "1016894",
        "1016902",
        "1016906",
        "1016915",
        "1016919",
        "1016927",
        "1016935",
        "1016939",
        "1016943",
        "1016947",
        "1016951",
        "1016955",
        "1016959",
        "1016963",
        "1016967",
        "1016971",
        "1016979",
        "1016983",
        "1017004",
        "1017041",
        "1017046",
        "1017052",
        "1017057",
        "1017061",
        "1017065",
        "1017070",
        "1017074",
        "1017078",
        "1101741",
        "1104594",
        "1104624",
        "1104652",
        "1304272",
        "1304305",
        "1304397",
        "1304532",
        "1615441",
        "1615498",
        "1711162",
        "1711190",
        "1711218",
        "1711253",
        "1711286",
        "1847976",
        "1848244",
        "1848273",
        "1848300",
        "1848411",
        "2038707",
        "2038743"
    ],
    "published": 1
}
```

This endpoint retrieves a specific Market Overview.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Market Overview to retrieve

## Get All Attributes from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview-attribute/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "2164290",
    "1035725",
    "1035724",
    "1035723",
    "1035722",
    "1035721",
    "1035720",
    "1035719",
    "1795757",
    "1035726"
]
```

This endpoint retrieves all Market Overview Attributes with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview-attribute/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get specific Attribute


```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview-attribute/detail/2164290"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2164290",
    "online_date": "2018-05-15 14:21:00",
    "change_date": "2018-05-15 15:34:43",
    "title": "Weitere Akzeptanzstellen Europa (Werkstätten etc.)",
    "type": "Text",
    "published": 1
}
```

This endpoint retrieves a specific Market Overview Attribute.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview-attribute/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Market Overview Attribute to retrieve

## Get All Items from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview-item/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "1036302",
    "1960395",
    "1036353",
    "1035944",
    "1119115",
    "1119061",
    "1036404",
    "1673546",
    "1673411",
    "1036455",
    "1036506",
    "1035995",
    "1036608"
]
```

This endpoint retrieves all Market Overview Items with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview-item/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get specific Item


```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview-item/detail/1036302"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1036302",
    "online_date": "2011-06-03 00:00:00",
    "change_date": "2018-05-15 15:27:11",
    "market_overview_id": "1035643",
    "title": "Westfalen Service Card",
    "fields": [
        {
            "id": "1036288",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:07",
            "item_id": "1036302",
            "attribute_id": "1035723",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036256",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035730",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036289",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035714",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036257",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035698",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036290",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035692",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036258",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035731",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036291",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035683",
            "published": 1
        },
        {
            "id": "1036259",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035699",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036260",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035732",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036293",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035715",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036261",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035700",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036294",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035693",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036262",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035685",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036295",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035684",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036263",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035701",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036264",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035717",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036297",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035716",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036265",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035702",
            "value": "on",
            "published": 1
        },
        {
            "id": "1796364",
            "online_date": "2016-05-25 10:39:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1795756",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036298",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035694",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036266",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:08",
            "item_id": "1036302",
            "attribute_id": "1035686",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036267",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035703",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036300",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035727",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036268",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035718",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036301",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035695",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036269",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035704",
            "published": 1
        },
        {
            "id": "1036270",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035687",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036271",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035705",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036272",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035719",
            "published": 1
        },
        {
            "id": "1036273",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035706",
            "published": 1
        },
        {
            "id": "1796365",
            "online_date": "2016-05-25 10:39:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1795757",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036274",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035688",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036275",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035707",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036276",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035720",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036277",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035708",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036278",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035689",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036279",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035709",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036280",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035721",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036281",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035710",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036282",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035690",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036283",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035711",
            "published": 1
        },
        {
            "id": "1036252",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:09",
            "item_id": "1036302",
            "attribute_id": "1035728",
            "published": 1
        },
        {
            "id": "1036285",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035712",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036253",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035696",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036286",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035691",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036254",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035729",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036287",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035713",
            "value": "on",
            "published": 1
        },
        {
            "id": "1036255",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035697",
            "value": "off",
            "published": 1
        },
        {
            "id": "1036292",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035724",
            "published": 1
        },
        {
            "id": "1036299",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035726",
            "published": 1
        },
        {
            "id": "1036284",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035722",
            "value": "0,-",
            "published": 1
        },
        {
            "id": "1036296",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "1035725",
            "value": "k.A.",
            "published": 1
        },
        {
            "id": "2164412",
            "online_date": "2018-05-15 15:24:00",
            "change_date": "2018-05-15 15:27:10",
            "item_id": "1036302",
            "attribute_id": "2164289",
            "value": "5500",
            "published": 1
        },
        {
            "id": "2164413",
            "online_date": "2018-05-15 15:24:00",
            "change_date": "2018-05-15 15:27:11",
            "item_id": "1036302",
            "attribute_id": "2164290",
            "published": 1
        },
        {
            "id": "1036774",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:11",
            "item_id": "1036302",
            "attribute_id": "1036662",
            "value": "Westfalen AG",
            "published": 1
        },
        {
            "id": "1036775",
            "online_date": "2011-06-03 00:00:00",
            "change_date": "2018-05-15 15:27:11",
            "item_id": "1036302",
            "attribute_id": "1036663",
            "value": "www.westfalen.com",
            "published": 1
        }
    ],
    "published": 1
}
```

This endpoint retrieves a specific Market Overview Item.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview-item/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Market Overview Item to retrieve

## Get All Fields from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview-field/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "1036774",
    "1036775",
    "2164413",
    "1036253",
    "1036254",
    "1036255",
    "1036284",
    "1036285"
]
```

This endpoint retrieves all Market Overview Fields with change dates greater than give timestamp.
A Field is a combination of an item and an attribute,

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview-field/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get specific Field


```shell
curl "http://rest-api.verkehrsrundschau.de/market-overview-field/detail/1036388"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1036388",
    "online_date": "2011-06-03 00:00:00",
    "change_date": "2018-05-15 15:15:07",
    "item_id": "1036404",
    "attribute_id": "1035730",
    "value": "on",
    "published": 1
}
```

This endpoint retrieves a specific Market Overview Field.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/market-overview-field/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Market Overview Field to retrieve

# Blog

## Get All Blog Entries from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/blog/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "2051295",
    "2051294"
]
```

This endpoint retrieves all Blog Entries with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Blog Entry


```shell
curl "http://rest-api.verkehrsrundschau.de/blog/detail/2051295"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2051295",
    "online_date": "9999-12-31 00:00:00",
    "change_date": "2018-02-01 16:20:45",
    "title": "Blog: Ladungssicherung",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5709/Logo-LaSiBlog.jpg",
    "teaser": "In unserem Blog zum Thema Ladungssicherung können Sie regelmäßig Beiträge von unserem Blogautor Stephan Bode lesen. Als Autobahnpolizist kennt er viele Tipps und Tricks für die korrekte Ladungssicherung und plaudert in dieser Rubrik für Sie aus dem Nähkästchen.",
    "published": 1
}
```

This endpoint retrieves a specific Blog Entry.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve

## Get All Blog Authors from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/blog-author/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
    "1970018",
    "1948601"
]
```

This endpoint retrieves all Blog Authors with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog-author/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Blog Author


```shell
curl "http://rest-api.verkehrsrundschau.de/blog-author/detail/1970018"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1970018",
    "online_date": "9999-12-31 00:00:00",
    "change_date": "2018-06-19 20:58:23",
    "title": "Mein Titel",
    "name": "Stephan Bode",
    "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5654/Logo-LaSiBlog.png",
    "text": "<p>Mein Text</p>",
    "published": 1
}
```

This endpoint retrieves a specific Blog Author.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog-author/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve

## Get All Blog Lasi Entries from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/blog-entry-lasi/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "2044795",
    "2181263",
    "2179348",
    "2169642",
    "2167709",
    "2163752",
    "2163724",
    "2160593",
    "2157538",
    "2150673",
    "2147539"
]
```

This endpoint retrieves all Blog Lasi Entries with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog-entry-lasi/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Blog Lasi Entry


```shell
curl "http://rest-api.verkehrsrundschau.de/blog-entry-lasi/detail/1970018"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2169642",
    "online_date": "2018-06-04 00:00:00",
    "change_date": "2018-06-04 09:57:48",
    "title": "Was ist Stückgut?",
    "teaser": "Der Begriff „Stückgut“ begegnet uns unter anderem in Fahrzeugaufbauzertifikaten nach DIN EN 12642 unter Nummer 4 (Angaben zur Ladung). Doch was fällt unter den Begriff Stückgut?",
    "text": "<p>Definitionen bzw. Beschreibungen f&uuml;r den Begriff &bdquo;St&uuml;ckgut&ldquo; finden sich in mehreren technischen Regelwerken zur Ladungssicherung bzw. zu begleitenden Regelwerken.</p>\r\n<p><b>VDI 2700 Blatt 6 (Zusammenladung von St&uuml;ckg&uuml;ter)</b></p>\r\n<p>Zu den St&uuml;ckg&uuml;tern z&auml;hlen alle G&uuml;ter, die als St&uuml;ck gehandhabt werden k&ouml;nnen. Dazu z&auml;hlen z. B.: Pakete, Kartonverpackungen und F&auml;sser. St&uuml;ckg&uuml;ter k&ouml;nnen auch in Ballen- oder Rollenform vorliegen. Dies k&ouml;nnen beispielsweise Altpapierballen, Papierrollen oder aufgerollte Metallbleche (Coils) oder auf Spulen aufgerollte Kabel, Rohre oder Schl&auml;uche sein. Weiterhin werden Langg&uuml;ter wie Metallprofile, Stangen, Leimbinder und fl&auml;chige G&uuml;ter, wie Bleche, Holzplatten oder Glasscheiben dem Begriff St&uuml;ckgut zugeordnet.</p>\r\n<p>St&uuml;ckg&uuml;ter k&ouml;nnen sowohl als einzelne St&uuml;cke als auch zu Ladeeinheiten zusammengefasst vorliegen.</p>\r\n<p>Einige Beispiele in Bildern:</p>\r\n<p><img src=\"/sixcms/media.php/springer_fachmedien_01.a.5801.de/sixcms_filename/Stueckgut.png\" border=\"0\" alt=\"(entry 2169634)\" title=\"(entry 2169634)\" width=\"1070\" height=\"803\" cms_gsid=\"springer_fachmedien_01.c.2169634.de\" data-fieldname=\"sixcms_filename\" /></p>\r\n<p>Auch Fahrzeuge, Baumaschinen oder sonstige schwere Einzelg&uuml;ter sind den St&uuml;ckg&uuml;ter zuzurechnen.</p>\r\n<p>Eine weitere Definition (Beschreibung) ist in der DIN 30781 Teil 1 zu finden: &bdquo;<i>St&uuml;ckgut ist individualisiertes Gut, das st&uuml;ckweise gehandhabt wird und st&uuml;ckweise in die Transportinformation eingeht.</i>&ldquo;</p>\r\n<p>Auch damit wird deutlich, dass &bdquo;St&uuml;ckgut&ldquo; nicht zwingend zu Ladeeinheiten zusammengefasst sein muss.</p>\r\n<p>Die DIN-Vorschrift enth&auml;lt noch einen weiteren Begriff, n&auml;mlich des Massenst&uuml;ckgutes: <i>&bdquo;Massenst&uuml;ckgut ist St&uuml;ckgut in gro&szlig;en Mengen (z. B. Stahlpartien, Autos, Sackgutpartien, R&ouml;hren, Fabrikanlagen).&ldquo;</i></p>\r\n<p><b>Herausforderungen bei der Ladungssicherung</b></p>\r\n<p>Hier fallen also gleichartige St&uuml;ckg&uuml;ter in gro&szlig;en Mengen zum Transport an. Diese sind beispielsweise in folgenden Bereichen anzutreffen:</p>\r\n<ul>\r\n<li>Automobilindustrie</li>\r\n<li>Baustoff- und Stahllogistik</li>\r\n<li>Lebensmittel- und Getr&auml;nkelogistik</li>\r\n</ul>\r\n<p>Allen St&uuml;ckg&uuml;tern ist gemeinsam, dass sie sich in Form, Eigenschaften, Abmessungen, Gewicht und Volumen erheblich voneinander unterscheiden k&ouml;nnen. Die Gesamtheit hat erheblichen Einfluss auf die M&ouml;glichkeiten der Ladeeinheitenbildung und der beim Transport erforderlichen Ladungssicherungsma&szlig;nahmen.</p>\r\n<p>Insbesondere das Zusammenladen von unterschiedlichen St&uuml;ckg&uuml;ter ist in Sachen Ladungssicherung h&auml;ufig eine Herausforderung. Dies gilt sowohl f&uuml;r die Erstellung von Beladepl&auml;nen, von der Einhaltung der Lastverteilung und f&uuml;r die Auswahl von Fahrzeug, Ladungssicherungsmittel und Ladungssicherungsverfahren.</p>",
    "author": {
        "id": "1970018",
        "online_date": "9999-12-31 00:00:00",
        "change_date": "2018-06-19 20:58:23",
        "title": "Mein Titel",
        "name": "Stephan Bode",
        "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5654/Logo-LaSiBlog.png",
        "text": "<p>Mein Text</p>",
        "published": 1
    },
    "published": 1
}
```

This endpoint retrieves a specific Blog Lasi Entry.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog-entry-lasi/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve

## Get All Blog Leru Entries from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/blog-entry-leru/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "2181980",
    "2170882",
    "2169116",
    "2167266",
    "2165551",
    "2163887",
    "2163530",
    "2161766",
    "2160433",
    "2156917",
    "2150823",
    "2150264",
    "2145221",
    "2142859",
    "2140711"
]
```

This endpoint retrieves all Blog Leru Entries with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog-entry-leru/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Blog Leru Entry


```shell
curl "http://rest-api.verkehrsrundschau.de/blog-entry-leru/detail/2181980"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2181980",
    "online_date": "2018-06-19 00:00:00",
    "change_date": "2018-06-20 00:03:07",
    "title": "Sonderregelungen für Busfahrer",
    "teaser": "Nach intensiver Intervention der Busverbände haben sich einige Mitglieder des Verkehrsausschusses des Europäischen Parlamentes für abweichende Sonderregelungen für die Lenk- und Ruhezeiten von Busfahrern ausgesprochen. Einige dieser möglichen Sondervorschriften wollen wir in diesem Beitrag vorstellen und objektiv kritisch beleuchten.",
    "text": "<p><b> 1. Verl&auml;ngerung der sog. &bdquo;Schichtzeit&ldquo;</b>: Fahrern im Gelegenheitsverkehr soll es zweimal pro Woche erm&ouml;glicht werden, den 24-Stunden-Zeitraum, in dem die vorgeschriebene T&auml;gliche Ruhezeit liegen muss, um eine Stunde zu verl&auml;ngern. Somit entsteht eine m&ouml;gliche Schichtzeit von 16 Stunden.</p>\r\n<p>Sicher gibt es Tagesfahrten, die mit wenig Lenkzeit, daf&uuml;r viel \"Herumstehen\" des Fahrers verbunden sind. Da diese Ausnahme aber <b>nicht</b> an Lenkzeiten gekoppelt ist, w&uuml;rde sie auch greifen, wenn eben die max. m&ouml;gliche Lenkzeit am Tag ausgesch&ouml;pft wird. <b>Aber selbst das Herumstehen, vielmehr das \"Herumlungern\" macht bekanntlich auch m&uuml;de.</b> Wenn ein Fahrer zwar nicht viel zu fahren hatte, dennoch aber einen heutigen max. 15-Stunden-Tag hinter sich hat, ist er in der Regel m&uuml;de. Wenn die \"Schichtzeit\" auf 16 Stunden erh&ouml;ht wird, dann bedeutet dies eben auch, inkl. Aufstehen, Bad, Fr&uuml;hst&uuml;ck, zur Arbeitsstelle und zur&uuml;ck fahren, <b>mindestens 20 Stunden</b> wach sein.</p>\r\n<p><b>In den Erw&auml;gungsgr&uuml;nden (auch in den neuen) wird immer wieder auf den sozialen Aspekt hingewiesen</b>. Bei der geplanten Neuregelung wird n&auml;mlich in aller Regel aus Unwissenheit vergessen, dass die Fahrer an einem solchen Tag eben nicht 15 oder 16 Stunden Arbeitszeit bezahlt bekommen. <b>&Uuml;blich sind 8 oder max. 10 Stunden pauschal, da der Fahrer ja die meiste Zeit \"Pause\" hat.</b> Ob nochmal eine Stunde l&auml;nger zum gleichen Lohn den Job attraktiver macht, darf wohl zu Recht bezweifelt werden. Die Verb&auml;nde rechtfertigen ihre Forderungen nach mehr Flexibilit&auml;t immer mit dem Fahrermangel und damit, dass viele Fahrer heute lieber Linienverkehr fahren. Das hat nicht etwa mit Angst vor Strafen im Gelegenheitsverkehr zu tun sondern damit, dass es im Linienverkehr geregelte(re) Arbeitszeiten gibt. Gerade junge Fahrer wollen ihre Freizeit genie&szlig;en und nicht <b>16 Stunden f&uuml;r den Arbeitgeber unterwegs sein und davon die H&auml;lfte bezahlt bekommen</b> - speziell im Vergleich zur Industrie bedeutet dies dann doppelte Arbeit zum halben Preis!</p>\r\n<p><b>Statt den Kunden mit gleicher Intensit&auml;t klar zu machen, dass es einfach Geld kostet, wenn sie 16 Stunden unterwegs sein wollen, wird dieser \"kostenlose\" Kundenservice nun auf dem R&uuml;cken der Fahrer ausgetragen.</b></p>\r\n<p><b>2. Ruhezeitensplitting</b>: Busfahrern im Gelegenheitsverkehr soll eine Aufteilung der T&auml;glichen Ruhezeit in drei Teile gestattet werden &ndash; 1 Std. / 2 Std. und 9 Stunden. Das gab es fr&uuml;her in der VO (EG) 3820/85 schon einmal. Hier wird versucht, die Zeiten des Herumstehens des Busfahrers bereits der Ruhezeit zuzurechnen. In der Folge werden die Fahrer <b>w&auml;hrend der Saison generell nur 9 Stunden Nachtruhe</b> haben und k&ouml;nnen daher intensiver eingesetzt werden. Der Fahrers muss in den 9 Stunden jedoch noch heimfahren, ggf. essen, schlafen und wieder zur Arbeit fahren... <b>Wenn man der Meinung ist, dass eine solche gesplittete Ruhezeit f&uuml;r einen Fahrer ausreichend ist, warum nicht auch f&uuml;r LKW-Fahrer?</b></p>\r\n<p><b>3.</b> <b>Flexibilisierung der Pausen:</b> Hierzu hat der Ausschuss f&uuml;r Arbeit und Soziales das Gremium um die Aufnahme eines &Auml;nderungsantrages gebeten. Konkret soll den Busfahrern im Gelegenheitsverkehr erlaubt werden, die aktuelle Reihenfolge bei der aufgeteilten Fahrtunterbrechung auch umgekehrt nehmen zu d&uuml;rfen, also erst 30 Minuten und dann 15 Minuten.</p>\r\n<p><b>Hiermit wird g&auml;ngige Praxis bei allen Busfahrern forciert:</b> Um unterwegs mit den Fahrg&auml;sten flexibler zu sein, fahren die Fahrer morgens 1 Minute um die Halle und legen dann bereits 15 Minuten Pause ein. In der Folge sind somit 9 Stunden Lenkzeit mit lediglich 30 Minuten Unterbrechung dazwischen m&ouml;glich. Nach dem Vorschlag des Ausschusses dann lediglich 15 Minuten!!!</p>\r\n<p><b>Die heutige Regelung zur Fahrtunterbrechung wurde mit Inkrafttreten der 561 im Erw&auml;gungsgrund 16 plausibel und praxisnah dargelegt: </b><b></b></p>\r\n<p><i>(16) Nach den Vorschriften der Verordnung (EWG) Nr. 3820/85 war es m&ouml;glich, die t&auml;glichen Lenkzeiten und Fahrtunterbrechungen so zu planen, <b>dass Fahrer zu lange ohne eine vollst&auml;ndige Fahrtunterbrechung fahren konnten, was zu Beeintr&auml;chtigungen der Stra&szlig;enverkehrssicherheit</b> und schlechteren Arbeitsbedingungen f&uuml;r die Fahrer gef&uuml;hrt hat. Es ist daher angebracht, sicherzustellen, dass aufgeteilte Fahrtunterbrechungen so angeordnet werden, dass Missbrauch verhindert wird.</i></p>\r\n<p><b>4. Die innerdeutsche 12-Tage-Regelung:</b> Im Grunde hat die bisherige Bedingung \"<i>24h Auslandsaufenthalt</i>\" keine Auswirkung auf die Verkehrssicherheit. Wenn diese Bedingung wegf&auml;llt &auml;ndert sich objektiv nicht viel. Allerdings sollte sichergestellt werden, dass die Bedingung \"<i>einzelner Gelegenheitsdienst</i>\" auch &uuml;berwacht werden kann.</p>\r\n<p><b>Fazit:</b></p>\r\n<p><b>Grunds&auml;tzlich laufen zu viele Sonderregelungen dem erkl&auml;rten Ziel der Kommission zu wider, die Regelungen einfacher und verst&auml;ndlicher zu machen. F&uuml;r Ausbilder ergeben sich jedoch viele neue Auftr&auml;ge, um die dann noch viel komplizierteren Regelungen zu schulen ;-) Ganz interessant wird es dann sicher zuk&uuml;nftig f&uuml;r Fahrer, die sowohl LKW als auch Bus fahren. Hier sind Fehler und somit Verst&ouml;&szlig;e aufgrund der unterschiedlichen Regelungen vorprogrammiert.</b></p>\r\n<p></p>",
    "author": {
        "id": "1948601",
        "online_date": "9999-12-31 00:00:00",
        "change_date": "2017-05-17 14:39:31",
        "name": "Olaf Horwarth",
        "image": "https://media1.verkehrsrundschau.de/sixcms/media.php/5654/2017-05-11%20Logo_6.png",
        "text": "",
        "published": 1
    },
    "published": 0
}
```

This endpoint retrieves a specific Blog Leru Entry.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/blog-entry-leru/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve

# Ban On Driving
## Get All Ban On Driving Items from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/ban-on-driving-item/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "2042895",
    "2054188",
    "2039259",
    "2041810",
    "2041812",
    "2041815",
    "2041816",
    "2041817",
    "2041818",
    "2041819",
    "2041820",
    "2041821",
    "2056058",
    "2041804",
    "2050461",
    "2041805",
    "2042205",
    "2042209",
    "2042213"
]
```

This endpoint retrieves all Ban On Driving Items with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/ban-on-driving-item/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Ban On Driving Item


```shell
curl "http://rest-api.verkehrsrundschau.de/ban-on-driving-item/detail/2042895"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
{
    "id": "2050461",
    "title": "Belgien_2018_Sondertransporte_60t_Uhrzeit2",
    "online_date": "2017-12-05 15:43:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2018-06-18 09:28:01",
    "vehicle_class": {
        "id": "2041794",
        "title": "Sondertransporte (Transporte bei denen die Maße und/oder Gewichte überschritten werden)",
        "online_date": "2017-12-05 15:42:00",
        "offline_date": "9999-12-31 00:00:00",
        "change_date": "2017-12-05 15:42:54",
        "published": 1
    },
    "calc_from_date": "2018-01-01 16:00:00",
    "calc_to_date": "2018-01-01 18:00:00",
    "calc_iteration_interval": "wöchentlich",
    "calc_last_iteration_date": "2018-12-31 18:00:00",
    "calc_flag_monday": true,
    "calc_flag_tuesday": true,
    "calc_flag_wednesday": true,
    "calc_flag_thursday": true,
    "calc_flag_friday": true,
    "calc_flag_saturday": true,
    "calc_flag_sunday": true,
    "text": "Fahrverbot für Sondertransporte über 60 Tonnen Gewicht, 3,50 Meter Breite und 27 Meter Länge täglich von 7 bis 9 Uhr und von 16 bis 18 Uhr.<br />\r\n<br />\r\n*Angabe bezieht sich auf Strecken, die zum Autobahnnetz gehören sowie auf andere Straßen",
    "type": "Fahrverbot mit Zusatzregeln",
    "route": "auf bestimmten Autobahnen *",
    "country": {
        "id": "1019545",
        "title": "Belgien",
        "online_date": "2011-04-12 15:20:00",
        "offline_date": "9999-12-31 00:00:00",
        "change_date": "2011-04-20 12:03:48",
        "published": 1
    },
    "published": 1,
    "calculated_dates": [
        {
            "startDate": "2018-01-01T16:00:00+0100",
            "endDate": "2018-01-01T18:00:00+0100"
        },
        {
            "startDate": "2018-01-02T16:00:00+0100",
            "endDate": "2018-01-02T18:00:00+0100"
        },
        {
            "startDate": "2018-01-03T16:00:00+0100",
            "endDate": "2018-01-03T18:00:00+0100"
        },
        {
            "startDate": "2018-01-04T16:00:00+0100",
            "endDate": "2018-01-04T18:00:00+0100"
        },
        {
            "startDate": "2018-01-05T16:00:00+0100",
            "endDate": "2018-01-05T18:00:00+0100"
        },
        {
            "startDate": "2018-01-06T16:00:00+0100",
            "endDate": "2018-01-06T18:00:00+0100"
        },
        {
            "startDate": "2018-01-07T16:00:00+0100",
            "endDate": "2018-01-07T18:00:00+0100"
        },
        {
            "startDate": "2018-01-08T16:00:00+0100",
            "endDate": "2018-01-08T18:00:00+0100"
        },
        {
            "startDate": "2018-01-09T16:00:00+0100",
            "endDate": "2018-01-09T18:00:00+0100"
        },
        {
            "startDate": "2018-01-10T16:00:00+0100",
            "endDate": "2018-01-10T18:00:00+0100"
        },
        {
            "startDate": "2018-01-11T16:00:00+0100",
            "endDate": "2018-01-11T18:00:00+0100"
        },
        {
            "startDate": "2018-01-12T16:00:00+0100",
            "endDate": "2018-01-12T18:00:00+0100"
        },
        {
            "startDate": "2018-01-13T16:00:00+0100",
            "endDate": "2018-01-13T18:00:00+0100"
        },
        {
            "startDate": "2018-01-14T16:00:00+0100",
            "endDate": "2018-01-14T18:00:00+0100"
        },
        {
            "startDate": "2018-01-15T16:00:00+0100",
            "endDate": "2018-01-15T18:00:00+0100"
        },
        {
            "startDate": "2018-01-16T16:00:00+0100",
            "endDate": "2018-01-16T18:00:00+0100"
        },
        {
            "startDate": "2018-01-17T16:00:00+0100",
            "endDate": "2018-01-17T18:00:00+0100"
        }
    ]
}
```

This endpoint retrieves a specific Ban On Driving Item.

Important: the returned 'calculated_dates' are no real CMS Objects. They are calculated everytime the Item is changed.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/ban-on-driving-item/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve


## Get All Ban On Driving Countrys from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/ban-on-driving-country/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "1019548",
    "1019571",
    "1778403",
    "1019589",
    "1019573",
    "1019557",
    "1019572",
    "1019556",
    "1019587",
    "1019555",
    "1019586",
    "1019570"
]
```

This endpoint retrieves all Ban On Driving Countrys with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/ban-on-driving-country/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Ban On Driving Country


```shell
curl "http://rest-api.verkehrsrundschau.de/ban-on-driving-country/detail/1019548"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "1019548",
    "title": "Dänemark",
    "online_date": "2011-04-12 15:20:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2018-01-19 13:51:11",
    "published": 1
}
```

This endpoint retrieves a specific Ban On Driving Country.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/ban-on-driving-country/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve


## Get All Ban On Driving Vehicle Classes from given timestamp

```shell
curl "http://rest-api.verkehrsrundschau.de/ban-on-driving-vehicle-class/ids/2"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this (shortened):

```json
[
    "2044255",
    "2044253",
    "2044236",
    "2044197",
    "2043960",
    "2043928",
    "2043915",
    "2043913",
    "2043911",
    "2043836",
    "2043793"
]
```

This endpoint retrieves all Ban On Driving Vehicle Classes with change dates greater than give timestamp.

### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/ban-on-driving-vehicle-class/ids/<TIMESTAMP>`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
timestamp | 0 | Unix Timestamp to start with


## Get a specific Ban On Driving Vehicle Class


```shell
curl "http://rest-api.verkehrsrundschau.de/ban-on-driving-vehicle-class/detail/2044255"  -H "X-Auth-Token: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
    "id": "2044255",
    "title": "Lkw >24t zGG und Lkw > 7t zGG auf einer Achse",
    "online_date": "2017-12-12 10:05:00",
    "offline_date": "9999-12-31 00:00:00",
    "change_date": "2017-12-12 10:05:47",
    "published": 1
}
```

This endpoint retrieves a specific Ban On Driving Vehicle Class.


### HTTP Request

`GET http://rest-api.verkehrsrundschau.de/ban-on-driving-vehicle-class/detail/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Entry to retrieve

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





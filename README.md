# Kudy z nudy Public Content API

Toto repository obsahuje informace k veřejnému API portálu Kudy z nudy. API poskytuje informace o Akcích a Aktivitách publikovaných na portálu [Kudy z nudy](https://www.kudyznudy.cz).

Provozovatelem portálu Kudy z nudy a poskytovatelem API je agentura [CzechTourism](https://www.czechtourism.cz).

## Přístup k API

Kudy z nudy Content API je přístupné pouze pro smluvní partnery CzechTourism. Pro přístup k API je nutné mít klíč (key), kterým je zabezpečen přístup. Klíč obdrží partner od poskytovatele API. Klíč je ve tvaru:

    a77ce76f-53b6-4900-a518-bafg11b7b22d

Klíč je součástí query parametru každého volání API.

## Popis jednotlivých služeb API

Jednotlivé služby popsané níže vrací data ve formátu [JSON](https://www.json.org/).

Base Path pro API je https://www.kudyznudy.cz/services/public/.

### Akce

Akce je jedním z typu obsahu publikovaného na portálu Kudy z nudy (KZN).

#### Seznam akcí

Služba slouží pro získání seznamu akcí.

    https://www.kudyznudy.cz/services/public/events.ashx?key=<auth_key>&updated=2019-11-13

##### Parametry

| Parametr | Popis |
| -------- | ----- |
| key | Autentizační klíč |
| updated | Nepovinný parametr. Datum poslední aktulizace je větší než uvedené datum |

##### Výstup

Pole JSON objektů ve tvaru:

    {
        "id": "f9159930-35ff-4729-a7a1-997ebf3aeda0",
        "name": "Předvánoční dílna pro děti",
        "updated": "2020-01-28T07:01:41.7426751"
    }

| Parametr  | Popis  |
|---------- | ------ |
| id        | Interní ID (guid) akce na portálu Kudy z nudy. Slouží pro získání detailu akce. Viz služba Detail Akce. |
| name      | Název akce |
| updated   | Datum poslední aktualizace akce na portálu KZN |

#### Detail akce

Služba slouží pro získání detailu konkrétní akce.

    https://www.kudyznudy.cz/services/public/event.ashx?key=<auth_key>&id=<guid_akce>

##### Parametry

| Parametr | Popis |
| -------- | ----- |
| key      | Autentizační klíč |
| id       | ID akce ze seznamu akcí |

##### Výstup

JSON objekt ve tvaru:

    {
        "id": "f9159930-35ff-4729-a7a1-997ebf3aeda0",
        "name": "Předvánoční dílna pro děti",
        "updated": "2019-11-15T14:22:31.8709501",
        "created": "2019-11-15T13:26:41.0898742",
        "annotation": "Srdečně vás zveme na předvánoční dílnu, která je určena dětem od 6 do 12 let. Vyrábět se budou vánoční dekorace, děti si vyzkouší jednoduché techniky zdobení skleněných ozdob a dozví se něco o tradičních vánočních zvycích. Dílna je vedena lektorkami, veškerý materiál je zahrnut v ceně dílny.\r\n",
        "url": "https://www.kudyznudy.cz/akce/predvanocni-dilna-pro-deti-1",
        "teaser": "https://www.kudyznudy.cz/files/59/59fdd1b1-1660-47a1-8695-4722720f1682.jpg?v=20191115142230",
        "gps": {
            "latitude": 50.5388919,
            "longitude": 16.2345597999999
        }
        "dateFrom": "2019-12-04T16:30:00",
        "dateTo": "2019-12-04T18:00:00"
    }

| Parametr  | Popis  |
|---------- | ------ |
| id        | Interní ID (guid) akce na portálu Kudy z nudy. |
| name      | Název akce |
| updated   | Datum poslední aktualizace akce na portálu KZN |
| created   | Datum prvního vytvoření akce |
| annotation | Anotace akce, excerpt |
| url       | Adresa stránky na portálu KZN |
| teaser    | Adresa teaser obrázku |
| gps       | GPS pozice akce |
| dateFrom  | Datum konání akce od |
| dateTo    | Datum konání akce do |


### Aktivity

Aktivita je jedním z typu obsahu publikovaného na portálu Kudy z nudy (KZN).

#### Seznam aktivit

Služba slouží pro získání seznamu aktivit.

    https://www.kudyznudy.cz/services/public/activities.ashx?key=<auth_key>&updated=2019-11-13

### Parametry

| Parametr | Popis |
| -------- | ----- |
| key | Autentizační klíč |
| updated | Nepovinný parametr. Datum poslední aktulizace je větší než uvedené datum |

##### Výstup

Pole JSON objektů ve tvaru:

    {
        "id": "37e97f29-b510-47a5-ab71-063b1e97b04d",
        "name": "Zámek Nižbor - poznejte každodenní život Keltů",
        "updated": "2020-01-28T07:01:41.7426751"
    }

| Parametr  | Popis  |
|---------- | ------ |
| id        | Interní ID (guid) akce na portálu Kudy z nudy. Slouží pro získání detailu aktivity. Viz služba Detail aktivity. |
| name      | Název aktivity |
| updated   | Datum poslední aktualizace aktivity na portálu KZN |


#### Detail aktivity

Služba slouží pro získání detailu konkrétní aktivity.

    https://www.kudyznudy.cz/services/public/activity.ashx?key=<auth_key>&id=<guid_aktivity>

##### Parametry

| Parametr | Popis |
| -------- | ----- |
| key      | Autentizační klíč |
| id       | ID aktivity ze seznamu aktivit |

##### Výstup

JSON objekt ve tvaru:

    {
        "id": "37e97f29-b510-47a5-ab71-063b1e97b04d",
        "name": "Zámek Nižbor - poznejte každodenní život Keltů",
        "updated": "2020-01-28T12:41:20.3277463",
        "created": "2008-06-30T10:07:39",
        "annotation": "Na zámku Nižbor je již několik let zřízeno Keltské informační centrum, které se stalo střediskem nejen kultury dávno zaniklé, ale i Keltství nově se probouzejícího. ",
        "url": "https://www.kudyznudy.cz/aktivity/zamek-nizbor-uz-jste-nekdy-byli-na-miste-kde-se",
        "teaser": "https://www.kudyznudy.cz/files/e2/e2b69b52-51ad-40bc-a652-4dab799006dd.jpg?v=20200128124120",
        "gps": {
            "latitude": 50.5388919,
            "longitude": 16.2345597999999
        }
    }
    

| Parametr  | Popis  |
|---------- | ------ |
| id        | Interní ID (guid) aktivity na portálu Kudy z nudy.|
| name      | Název aktivity |
| updated   | Datum poslední aktualizace aktivity na portálu KZN |
| created   | Datum prvního vytvoření aktivity |
| annotation | Anotace aktivity, excerpt |
| url       | Adresa stránky na portálu KZN |
| teaser    | Adresa teaser obrázku |
| gps       | GPS pozice aktivity |

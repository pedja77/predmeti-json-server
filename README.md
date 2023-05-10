## json-server kao backend za školske predmete

Server omogućava dobavljanje niza objekata koji predstavljaju predmete. Svaki predmet sadrži i niz nastavnika koji ga predaju kao i niz učenika koji ga slušaju. Primer objekta:
   
    {
      "id": 1,
      "predmet": "IN quis justo",
      "fond": 10,
      "razred": 1,
      "ucenici": [
        {
          "id": 1,
          "ime": "Marie-noël",
          "prezime": "Raiment",
          "datumRodjenja": "27/12/2018",
          "razred": 7
        },
        {
          "id": 2,
          "ime": "Táng",
          "prezime": "Melesk",
          "datumRodjenja": "02/08/2016",
          "razred": 2
        },
        {
          "id": 3,
          "ime": "Pénélope",
          "prezime": "Crockatt",
          "datumRodjenja": "20/09/2008",
          "razred": 3
        },
        {
          "id": 4,
          "ime": "Aí",
          "prezime": "Glasbey",
          "datumRodjenja": "28/09/2011",
          "razred": 7
        },
        {
          "id": 5,
          "ime": "Noëlla",
          "prezime": "Chisholme",
          "datumRodjenja": "06/12/2014",
          "razred": 7
        }
      ],
      "nastavnici": [
        { "id": 1, "ime": "Mà", "prezime": "Richichi", "nedeljniFond": 17 },
        { "id": 2, "ime": "Méline", "prezime": "Mundell", "nedeljniFond": 30 }
      ]
    }

Postoje nekonzistentnosti kada su podaci u pitanju, npr. godište učenika ne odgovara razredu koji pohadja, razred učenika ne odgovara razredu u kome se predmet sluša... Dummy podaci generisani na sajtu [mockaroo](https://www.mockaroo.com/).

Iskorišćen je [json-server](https://github.com/typicode/json-server).

### Instalacija i korišćenje

Nakon kloniranja ući u napravljeni direktorijum,
    
    npm install

Pokrenuti server sa
    
    npm run start

Server će se pokrenuti na http://localhost:3001, što omogućava istovremeno pokretanje react aplikacije.

Endpoint za pribavljanje niza svih predmeta je http://localhost:3001/api/v1/predmeti.

Endpoint za pretragu po imenu predmeta, case insensitive je http://localhost:3001/api/v1/predmeti?predmet_like=<kriterijum> gde je kriterijum string koji smo dobili iz polja za pretragu.

Predmeti se nalaze u fajlu db.json, apsolutno ih je moguće dodavati, brisati i modifikovati, u zavisnosti od izvršenih izmena moguće je da će se morati modifikovati i fajl routes.json.
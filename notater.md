# Django Tutorial <!-- omit from toc -->

## Table of contents <!-- omit from toc -->

- [Browser debugger console](#browser-debugger-console)
  - [Notater](#notater)
  - [Oppsummering](#oppsummering)
- [Strukturen til en Django applikasjon](#strukturen-til-en-django-applikasjon)
  - [Notater](#notater-1)
    - [Struktur](#struktur)
    - [Request](#request)
  - [Oppsummering](#oppsummering-1)
- [Innstallere Django](#innstallere-django)
  - [Notater](#notater-2)


## Browser debugger console

### Notater

kan se på masse ting for debugging

* Network
    * Requests
    * Status kode
    * Versjon
    * Headers
        * Response
        * Request
    * Disable Cache
* Inspect element
    * Kan endre på siden uten interaction fra serveren

Ikke bruk safari (xd cringe ass nae nae safari imagine ha tilgang i det hele tatt smh my head)

### Oppsummering

Browser debugger console kan hjelpe med å debugge sider. Den kan vise alt som skjer gjennom nettverket og lar deg endre på koden uten å ha serveren involvert.

## Strukturen til en Django applikasjon

### Notater

Django har applikasjoner som du kan bruke mellom prosjekter

#### Struktur

* ``Prosjekt mappe``
    * ``__init__.py``
        : Lar python vite at det er filer som inneholder klasser og objekter
    * ``settings.py``
    * ``urls.py``
    * ``wsgi.py``
    * ``Applicaton mappe``
        * ``__init__.py`` 
            : Lar python vite at det er filer som inneholder klasser og objekter
        * ``admin.py``
        * ``apps.py``
        * ``migrations``
        * ``models.py``
        * ``tests.py``
        * ``urls.py``
            : Inneholder paths til URLs som blir requested, pathen fører til en view
        * ``views.py``
            : Produserer og sender en response tilbake til brukeren


#### Request 

1. Noen klikker på en DOM og browseren sender en GET request
2. ``urls.py`` sier hvilken view i ``views.py`` den skal til
3. View-en henter ut alt data den trenger gjennom en template
4. Hvis vi trenger å lagre data går vi til ``models.py`` som kobler seg til en database og lagrer dataen
5. Sender response tilbake

### Oppsummering

En Django nettside består av applikasjoner, der inneholder de filer som sier hvor en request skal og deretter hva responsen skal være.

## Innstallere Django

### Notater

Skal ikke bruke python anywhere cringe nettside program greie


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
    - [Hvordan sette opp en Django server](#hvordan-sette-opp-en-django-server)
  - [Oppsummering](#oppsummering-2)


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

Uansett lurt å lage en virtual enviroment: https://code.visualstudio.com/docs/python/tutorial-django

``python manage.py check`` command for å sjekke om alt er schpa
``python manage.py migrate`` en annen command

gå tilbake til original directory og lag ny mappe
``django-admin startproject mysite`` lager en ny project
i ``django_projects/mysite/mysite/settings.py`` endre ``ALLOWED_HOSTS = []`` til ``ALLOWED_HOSTS = [ '*' ]``. Det gjør at alle systemer kan snakke med web serveren

Ikke hør på stupid video bruker pythonanywhere?!??!??!?? bruker heller ``python manage.py runserver``. Husk å bruke ``python manage.py migrate`` først. **Bruker localhost**

#### Hvordan sette opp en Django server

1. Run ``python manage.py startapp polls`` for å lage ny app
2. Edit ``polls/views.py`` og legg inn:
    ``` python 
    from django.http import HttpResponse

    def index(request):
      return HttpResponse("Hello, world. You're at the polls index.")
    ```
3. Lag en fil som heter ``urls.py`` i ``mysite/polls`` og skriv inn:
    ``` python 
    from django.urls import path

    from . import views

    urlpatterns = [
      path('', views.index, name='index'),
    ]
    ```
4. Edit ``mysite/mysite/urls.py`` til:
    ``` python 
    from django.contrib import admin
    from django.urls import include, path

    urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
    ]
    ```
      * ``python manage.py check`` kommer til å vise om det er feil i koden og i det tilfelle hvor

5. Nå kan man gå til ``localhost/polls`` og se om det funker

### Oppsummering
Det er mye jobb for å sette opp en Django server, men det er også den vanskligste delen. Det er lurt å ha en virtual enviroment og man må huske å installere alle python add-ons.
# Covid Videoplatform

## Problem

Skalierbaren, leicht repdroduzierbaren Videochat

## Anwendungsfälle

+ Kollaboration
+ Patientengespräche/Annamnese
+ 1on1-Räume per PDF mit Link und QR-Code (Datamatrix, ist Patentfrei :)
    + Flott mit pandoc PDFs zusammenkloppen? 
+ Infizierten Medizinischen Fachpersonal weitere Mitarbeit ermöglichen

## Was muss die Software können?

+ Provider API
    + Stelle Videobridges zur Verfügung, nach bedarf
    + Messe Load
    + Füge neue Videobridges hinzu, falls auslastung konstant hoch
    + (Annahme: nur die Videobridges müssen skaliert werden)
+ User Routing
    + Mappe einen Patienten zu einem Mediziner mit Zeit und Room (extern?)
    + Eventuell:
        + simple web API, HTTP/JSON
        + Request Room and preferred timeslots
        + Return PDF with appointment date, jitsi Link and instructions
            + Give two PDFs, slightly earlier Time for patient (1 min?)

+ Was muss skaliert werden?
    + Videobridges

## Technologien

+ Jitsi Meet
+ Voip / Sip / Jigasi
+ Webserver nginx
+ Instanzierung?
    + Ansible + Terraform?
    + Docker + Swarm?

## andere relevante Projekte

+ Nils Tißen https://de.slideshare.net/MeandCompany/me-company-covcheck-konzeptprsentation
+ https://devpost.com/software/videobesuch


## jitsi api dinge

+ https://github.com/jitsi/jicofo/blob/master/doc/reservation.md
+ https://community.jitsi.org/t/jicofo-health-checks-through-rest-api/14466
+ https://github.com/jitsi/jicofo/blob/master/doc/health-checks.md
+ https://github.com/jitsi/docker-jitsi-meet/blob/master/docker-compose.yml

# notes

+ Whatsapp geht ja mal gar nicht für sowas ++
+ Ok :)
+ Kennt sich hier jemand mit Cloud umgebungen aus? (Patryk: aber bevor man die k8s Keule rausholt, sollte man kleiner denken)
+ Jau, jitsi ist teuer
+ Je weniger indirektionen, desto besser.
* Ich habe bisher nur mit nix/docker gebastelt. Bei docker wäre das ganze mit dem hochziehen auch ziemlich flott, mehr oder weniger eine `docker-compos.yml` abrichten und dann nur einmal `docker-compose up -d`. Ich weiß aber nicht wie gut sich das orchestrieren lässt (Patryk: ich könnte daraus flott nen Docker Swarm machen. orcherstrierung klappt erst gut mit k8s. So muss man die Ressourchen selber abschätzen.)
+ stimme zu
+ Wie kann man Safe wieder runterskalieren? Ok, dann muss das Loadbalncing wohl eher bestehende Instanzen füllen statt gut zu verteilen, damit man ab und an auch wieder runterskalieren kann?
+ Macht einer von euch ein repo auf? 
+ Wählt jitsi von alleine eine Videobrige für neue Konferenzen?
+ ggf am ende dann mal hier eintragen? https://github.com/jitsi/jitsi-meet/wiki/Jitsi-Meet-Instances

+ Welche Sprachen würdet ihr bevorzugen (am besten eine Markierung für die Anzahl machen?
    + Go ++
    + Python ++
  Frage: Gehts hier um die Vermittlung des Gesprächs?

https://jitsi.org/news/tutorial-video-how-to-load-balance-jitsi-meet/ (Anmerkung im Allgemeinen: Warum muss man heute alles im Video erklären?++)

# developer infos

+ github project: https://github.com/covid-videoplattform
+ github main repo: https://github.com/covid-videoplattform/covid-videoplattform
+ wucke13 @github
+ chaotika @github
+ TheReal1604 @github

## devpost

+ https://devpost.com/software/031_digitale_krankheitsanamnese_covid-videoplattform/joins/8B123aMb5-XuhQal023uZw
+ https://devpost.com/software/031_digitale_krankheitsanamnese_covid-videoplattform
+ https://docs.google.com/document/d/1e4VEAU5alIQwYlcRcXoodv66EnWvRbUSOxk6LxM8358/preview
+ https://docs.google.com/document/d/1O1ewO6vhR-CDLPSm7kScPt8-xjsb-hKI2rXISRN8LI4/preview

# Hvordan Sopra Steria drifter NAVs største IT-prosjekt. 

Oktober 2016 startet et av Norges største IT prosjekter. Foreldrepengeprosjektet er en del av Prosjekt 2 i moderniseringen av IKT i NAV. Målet med prosjektet er å lage en moderne saksbehandlingsløsning og nye digitale tjenester, med vekt på forenkling, digitalisering og automatisering. I dag består prosjektet av til sammen ca. 120 mennesker som bidrar med å lage en viktig løsning for samfunnet. I dette innlegget vil jeg beskrive hvordan vi startet fra å drifte en prototype på noen 100 kodelinjer og 4 utviklere til å drifte flere applikasjoner på mange 10.000 kodelinjer og over 60 utviklere.

## Prototypen

Vi startet med en liten prototype som jeg ofte kalte for ’hobby-prosjekt’. Det betyr ikke at vi ikke tok det på alvor, tvert imot. Men, vi viste hva vi måtte fokusere oss på. I stedet for å sette alt på plass for 70 utviklere og flere 10.000 kodelinjer her og nå, forholdte vi oss til det som var viktig i dag, et lite programm som vil bli voksen. Vår oppgave var, og fortsatt er, å hjelpe løsningen med det. Vår viktigste oppgave i miljø teamet er å passe på at applikasjonen altid er produksjonsklar. Det går kun når alle endringer i kodebasen blir øyebblikkelig verifisert, og utviklerne får umiddelbar tilbakemelding om status. En frisør for eksempel må få vite om han eller hun nettopp har barbert vekk en føflekk på hodeskallet og som snart kommer til å blø. Enhver feil trenger attention og må fikses fort.

Jenkins Pipeline er derfor noe av det første vi har satt opp. Pipelinen skulle være enkel og forståelig for alle. Den har tre steg: Init, Build, Deploy. Siste steget deployer appliksjonen til en JBoss server i et av test miljøene i NAV og kjører Flyway skriptene for database oppdatering. Den gir feedback til utviklerne i løpet av veldig kort tid, og apllikasjonen har gått gjennom noen viktige verifiseringssteg. Ett annet viktig verktøy som vi brukte fra dag en var SonarQuebe. SonarQuebe gir oss feedback om kodekvalitet, og er viktig for å sikre stabilitet.

De tre første måneder gikk vedlig fort, og vi brukte tiden til å lære mye om NAV og dens verktøy. Jeg er fortsatt fasinert over det NAV IKT har oppnådd med sine selvbetjeningssystem. For meg var det naturlig å bestille en server og så vente i noen uker. I NAV rekker du ikke en gang å hente kaffe. Selvbetjeningssystemet gjør oss veldig uavhengig fra de som drifter infrastrukturen i NAV, og sparer oss mye tid.

## Monolitten

Tiden floy, og flere utvikler jointe oss. Noen av dem kjente jeg allerede, og det var gøy å se hvor mange i prosjektet kjente hverandre fra før, fra tidligere prosjekter. Samarbeidet i prosjektet er veldig bra, Allikevel så vi at barnet vårt som vokste, ble etterhvert vanskelig å styre. Hovedbranchen feilet oftere. Vi måtte velge en annen branching strategi for å sikre best oppvekst. Hittil har alle pushet til develop branchen, og kun noen valgte feature branches. Vår 2017 gikk hele prosjektet over til feature branches for å sikre at alle teamene ikke merger til develop før den er testet og verifisert. Det var det vi trengte, og fpsak ble stabil igjen.

team miljøer
data migrering - master base
 
## NAV Application Infrastructure Service - nais.io

## Konklusjon

# Hvordan Sopra Steria drifter NAVs største IT-prosjekt. 

**Oktober 2016 startet et av Norges største IT prosjekter, og det største i NAVs historie. Rundt 120 mennesker bytter ut det 40 år gamle kjernesystemet. Hvordan ser prosjektet egentlig ut gjennom IT drifts-briller?**

Foreldrepengeprosjektet er en del av Prosjekt 2 i moderniseringen av IKT i NAV. Målet med prosjektet er å lage en moderne saksbehandlingsløsning og nye digitale tjenester, med vekt på forenkling, digitalisering og automatisering. I dag består prosjektet av til sammen ca. 120 mennesker som bidrar med å lage en viktig løsning for samfunnet. I dette innlegget vil jeg beskrive hvordan vi startet fra å drifte en prototype på noen 100 kodelinjer og 4 utviklere til å drifte flere applikasjoner på mange 10.000 kodelinjer og over 60 utviklere.

## Prototypen

Vi startet med en liten prototype som jeg ofte kalte for ’hobby-prosjekt’. Det betyr ikke at vi ikke tok det på alvor, tvert imot. Men, vi viste hva vi måtte fokusere oss på. I stedet for å sette alt på plass for 70 utviklere og flere 10.000 kodelinjer her og nå, forholdte vi oss til det som var i dag, et lite programm som vil vokse. Vår oppgave var, og fortsatt er, å hjelpe løsningen med dette. I miljø teamet er oppgaven vår å passe på at applikasjonen altid er produksjonsklar. Dette går kun når alle endringene i kodebasen blir øyebblikkelig verifisert, og utviklerne får fortest mulig tilbakemelding. En frisør for eksempel må få vite om han eller hun nettopp har barbert vekk en føflekk på hodeskallen, og som snart vil blø og ødelegge skjorten til personen som sitter i stolen. Enhver feil har konsekvenser og trenger attention og må fikses fort.

Jenkins Pipeline er derfor noe av det første vi har satt opp. Pipelinen skulle være enkel og forståelig for alle. Den har tre steg: Init, Build, Deploy. Siste steget deployer appliksjonen til en JBoss server i et av test miljøene i NAV og kjører Flyway skriptene for database oppdatering. Den gir feedback til utviklerne i løpet av veldig kort tid, og apllikasjonen har gått gjennom noen viktige verifiseringssteg. Ett annet viktig verktøy som vi brukte fra dag en var SonarQuebe. SonarQuebe gir oss feedback om kodekvalitet, og det er viktig for å sikre godt stabilitet.

De tre første måneder gikk vedlig fort, og vi brukte tiden til å lære mye om NAV og dens verktøy. Jeg er fortsatt fasinert over det NAV IKT har oppnådd de siste årene med sine selvbetjeningssystem. For meg var det naturlig å bestille en server og så vente i noen uker. I NAV rekker du ikke en gang å hente kaffe. Selvbetjeningssystemet gjør oss uavhengig fra de som drifter infrastrukturen i NAV.

## Monolitten

Tiden floy, og flere utvikler jointe oss. Noen av dem kjente jeg fra før, og det var gøy å se hvor mange i prosjektet kjente hverandre fra tidligere prosjekter. Samarbeidet i prosjektet var altså veldig bra, Allikevel så vi at applikasjon etterhvert ble vanskelig å styre jo flere commitet endringer og jo større den ble. Hovedbranchen feilet oftere og våre manuelle tester tok ofte mer tid enn planlagt. Vi valgte en annen branching strategi for å sikre bedre stabilitet. Hittil hadde alle pushet til develop branchen, og kun noen valgte feature branches. Vår 2017 gikk hele prosjektet over til feature branches som alltid ble testet før de ble merget inn til develop branchen. Om det var en god ide eller ikke tørr jeg ikke å uttale meg om. Vi fikk nye, og veldig kjente utfordringer.

I dag har vi 6 team, og alle fikk et dedikert miljø de kunne teste i. En server med JBoss på og en Oracle database, en kø og en systembruker. Noen av utviklerne hadde spesielle behov, og trengte derfor egene miljøer. I tillegg spanderte vi våre Jenkins slaver hvert sitt miljø. Til sammen ble det vel omtrent 20 miljøer som vi «vedlikeholdte». Jeg kan kanskje ikke si at vi vedlikeholdte disse, fordi det ikke var noe å gjøre bortsett fra å sette de opp. Det var noen spørsmål her og der inn i blant rundt konfigurasjonen.
 
## NAV Application Infrastructure Service - nais.io

Og så flyttet Docker, Kubernetes og noen andre verktøy som til sammen ble døpt for NAIS, inn i NAV sine kontorer. Med dem kom ett sterkt ønske om færre miljøer, noe som var et problem for oss som jobbet med hver sin feature branch i hvert sitt miljø og som dermed kunne teste uavhengig fra andre. Uavhengighet var hittil luksus skjønte jeg. Fra nå av skulle vi jobbe alle i ett og det samme miljøet. For oss betydde det at vi måtte release oftere, minst en gang i døgnet, for at vi kunne teste endringene våre. I DevOps-verden høres det ikke uvanlig ut, og teknisk  er det ingenting i veien med. Det som var utfordrende er at løsningen stadig var i bevegelse, og det var uvanlig for alle. 

Både NAV og vi tilpasser oss. Vi begynner å jobbe med feature toggles, kortlevende feature branches om nødvendig i det hele tatt, og kontinuerlig manuell testing. Utover det får vi enda flere automatiske tester, og monolitten blir mindre fordi vi splitter den opp i mindre applikasjoner slik at enhetene kan bedre kjøres inn i en Docker kontainer. 

## Konklusjon

Kontinuerlig leferanse - DevOps - står høy på agendaen i NAV i dag. Det er ett ønske, men samtidig en forutsetning for at NAIS fungerer bra. For oss i miljø teamet betyr NAIS mindre jobb. Vi har kun ett miljø, og dette miljøet tar seg NAV selv av.
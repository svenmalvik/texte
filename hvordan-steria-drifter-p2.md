# Hvordan Sopra Steria drifter NAVs største IT-prosjekt. 
Oktober 2016 startet et av Norges største IT prosjekter. Foreldrepengeprosjektet er en del av Prosjekt 2 i moderniseringen av IKT i NAV. Målet med prosjektet er å lage en moderne saksbehandlingsløsning og nye digitale tjenester, med vekt på forenkling, digitalisering og automatisering. I dette innlegget vil jeg beskrive hvordan vi startet fra å drifte en prototype på noen 100 kodelinjer og 4 utviklere til å drifte flere applikasjoner på mange 10.000 kodelinjer og 70 utviklere.

## Prototypen
Alt startet med en liten prototype som jeg likte å kalle for ’hobby-prosjekt’. Det betyr ikke at vi ikke tok det på alvor, tvert imot. Vi viste hva vi måtte fokusere på. I stedet for å sette alt på plass for 70 utviklere og flere 10.000 kodelinjer, forholdte vi oss til det som var nå, et lite programm som vil bli voksen. Vår oppgave var, og fortsatt er, å hjelpe det med det. Den viktigste oppgaven vi har i miljø teamet, det er forresten Mayu og meg, det er å passe på at applikasjonen lever, til enhver tid. I fagspråket heter det „Production-Ready State“. Det går kun når alle som gjør endringer i kodebasen får umiddelbar tilbakemelding. En frisør må få vite om han eller hun nettopp har barbert vekk en føflekk på hodeskallet og som snart kommer til å blø. Enhver feil trenger attention og må fikses fort. Jenkins Pipeline er noe av det første vi har satt opp. Pipelinen skulle være enkel og forståelig for alle. Den har tre enkle steg: Init, Build, Deploy. Siste steget deployer appliksjonen til en JBoss server i et test miljø og kjører Flyway skriptene for database oppdatering.

## Monolitten


## Flere applikasjoner


## Konklusjon

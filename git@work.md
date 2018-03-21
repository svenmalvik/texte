# Git@Work
Jeg er veldig glad i Git. Det er kanskje fordi Git reddet meg så mange ganger.
## Hva er Gitflow?
Gitflow er et verktøy som hjelper utviklerne å håndtere kodestrømmer på, og det kan vi ha mange av i store prosjekter. I dag sitter jeg i ett prosjekt med 40 andre utviklere hvor mesteparten jobber på samme applikasjonen. Det kan bli veldig mange commits utover dagen og som kan resultere i konflikter. Gitflow skal sørge for at dette ikke skjer. Gitflow håndterer i tillegg releases og hotfixes. Kort fortalt, i Gitflow finnes det minst to branches, master-branch og develop-branch. Alt som går ut i produksjon ligger på master-branchen. All utvikling skjer på develop-branchen. Når det for eksempel må rettes en kritisk feil i produksjon, så vil utgangspunktet være master-branchen. Vi bruker den til å opprette en hotfix-branch, hvor vi vil implementere feilrettelsen. Hotfix-branchen vil etterpå merges tilbake til master-branchen (produksjon), og til develop-branchen (utvikling). Når sprinten nærmer seg slutten, så oppretter man med Gitflow som regel en release-branch. Denne kan testes og brukes for eventuelle feilrettelser. I mens det testes kan andre utviklere fortsette å implementere nye features på develop-branchen. Til slutt, når release-branchen er testet ok, så merges alle eventuelle endringer fra release-branchen til master-branchen og tilbake til develop-branchen.
Før likte jeg Gitflow, senere skjønnte jeg ikke poenget. Hva betyr dette?  
 ha sine bruksområder.
## Hvem kan bruke Git?
## Hvordan fungerer Git?
## 

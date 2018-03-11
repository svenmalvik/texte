# The beauty of kontinuerlig dokumentasjon.

**For mange er å skrive dokumentasjon like spennende som å ta kollektiv på morningen. Jeg tror det er fordi vi går ut i fra at ingen vil lese den. De fleste dokumentasjonene inviterer ikke til å lese, de er informative, men ofte tørre og kjedelige. I så fall er det lite som motiverer.**

Jeg har alltid hatt lyst til å publisere en bok. For noen år siden intervjuet jeg Nilanjan Raychaudhuri, forfatteren av "Scala in Action". Vi spiste lunsj sammen. Han ledet en Scala workshop jeg deltok på. "How much time did you spend on writing this book?", spurte jeg. "About two years. You need to have great disiplin", svarte han. Jeg viste at å skrive en bok er utfordrende, men å høre det direkte fra noen som har publisert en bok som folk faktisk leser. Dette var spennende tenkte jeg. 

## Alle kan bli forfattere!
Jeg kan bruke 3, 4 måneder til å skrive en bok. 
Myers–Briggs Type Indikatoren (MBTI) beskriver 16 personlighetstyper. Jeg er typ INTP. For meg betyr det blant annet at jeg elsker å starte med nye prosjekter. Det betyr også at jeg sjeldent avslutter disse, noe som er et problem for mange INTP-ler. Når en INTP-ler har forstått konseptet bak det den forsker på eller undersøker, er prosjektet ikke spennende lenger. Prosjektene bør derfor være begrenset i omfang.
"One more thing", fortsatte han. "I'll never do that again, bad investment and poorly paid too". Det kan ikke stemme helt, tenkte jeg. Han er jo utrolig smart og han vet alt om Scala. Det var i hvertfall det inntrykket jeg fikk av ham. Hvordan kan det være en dårlig investisjon å lære noe? Kanskje det kostet ham noe av privatlivet hans, hvem vet.
Jeg har ennå ikke skrevet en eneste bok man kan ta på alvor. Sannsynlig leter jeg etter en slags snarvei.

Sommer 2016 fikk jeg oppgaven av å vedlikeholde systemdokumentasjonen til det prosjektet jeg sitter i. Først og fremst betyr det å sørge for at utviklerne dokumenterer i det hele tatt. Det er en enkel jobb tenkte jeg, fordi dokumentasjonen genereres helt automatisk. Perfekt! 

Veldig kort fortalt. Vi bruker javadoc for å lese ut data fra kodebasen som f.eks. kommentarer og regler og som vi vil ha med i dokumentasjonen. Dataene bruker vi videre for å generere asciidoc filer. Disse blir konverert til html, og ferdig er websiden - altså dokumentasjonen. Det skjer selvfølgelig litt mer enn jeg beskrev nettopp, og som sikkert hadde vært material til en tutorial. 

Hittil er det ingenting spesielt beautiful. Men hva om vi kunne ta et nesten helt tilfeldig GitHub-prosjekt, legge til javadoc-kode, trykke en autogenerer-dokumentasjonsknapp, og så spyttes det ut en Kindle-bok som ligner Carrie (Stephen King).Det hadde vært stas, tenkte jeg. Det eneste som til slutt mangler er å selge boken på Amazon og blir steinrik. Neida, det er naturligvis ikke mulig å skrive «Carrie» ut i fra Javakode, heller ikke å tjene mye penger på en autogenerert fagbok, men man kan kalle seg for bokforfatter, vel, uten å skrive ett eneste ord. Tanken elsket jeg! Jeg surfte litt på GitHub og fant det perfekte prosjektet. Jeg prøvde ut min teori og lagte min INTP-vennlige snarvei. 

"iluwatar/java-design-patterns"-prosjektet beskriver 100 design patterns. Alt fra de kjente "Gang of Four"-patterns til mange ukjente patterns. Etter noen timer hadde jeg en første versjon av en bok på min kindle-app på telefonen. I stedet for å generere html, genererte jeg til epub, som er en åpen standard for e-bøker. Derfra konverterte jeg til Amazon sitt mobi format. 
Jeg var meget fornøyd. Jeg husker at jeg lå i sengen den kvelden og leste i MIN bok, så kult! Den var ikke perfekt, men jeg viste eksakt hva som måtte endres for å få den bra. Det gikk noen runder med endringer. Til sammen ble det 4, 5 runder med tilpassninger av javadoc-kode, asciidoc og dokumentasjonen som ligger i kodebasen til jeg sjønnte at hvis jeg vil få generert en bok som en dag er bra nok til at noen vil lese i den, så trengs det bedre, mye bedre og mye mer dokumentasjon i kodebasen, altså i prosjektet.

## Konklusjonen av denne erfaringen er denne:
Alle bør ta seg tid når det gjelder dokumentasjon av kodebasen. Alle bør dokumentere slik at leseren forstår teksten ut i fra konteksten. Måten man sikrer dette på er å gi fort tilbakemelding, helst med en gang kodebasen endrer seg, dvs. rett etter hver commit. Dokumentasjonen må i så fall bli en del av en Jenkins Pipeline, kontinuerlig dokumentasjon. 
Vi kan alle bli bokforfattere, men først må vi få det på radaren, og tar denne delen av en leveranse enda mer på alvor. Dokumentasjonen din kan bli den din nye Godfather om du tillater det. Og en ting til slutt. Eksporter dokumentasjonen i ett format du liker å lese i, for meg er det Kindle.

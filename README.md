# JavaCollectionFrameworkTest
Test of different Java Framework Collection types

Uppgifter		

Vad är en array samt dess för/nackdelar?		
Svar: Primitiv container-typ av förbestämd storlek. Snabb att använda, men saknar flexibilitet.

Vad är en vector samt dess för/nackdelar?		
Svar: Objekt med flexibel storlek och med metoder för att manipulera och komma åt data. Inte lika snabb att arbeta med som en array eftersom en vector är synkroniserad och ger då sämre prestanda. Måste instansieras.

Vad är en hash table samt dess för/nackdelar?		
Svar: En hash table kan vara ett mycket effektivt sätt att söka efter objekt i stora mängder data, särskilt om datan annars inte är lätt att söka i.	
Nackdelar: syncronized, sämre prestanda ty bara en tråd i taget	
Fördelar: syncronized(threadsafe)

Vad är en hashfunktion för något?		
Svar: För att kunna spara och hämta objekt från en hastable exempelvis, så måste objekten som används som nycklar implementera hashCode metod och equal metod i java.
En hashfunktion är ett sätt att skapa en kompakt representation av en godtyckligt stor datamängd, som sedan sorteras in i buckets så de lätt kan hittas,
http://stackoverflow.com/questions/3069709/what-is-a-hash-function-in-java
http://eclipsesource.com/blogs/2012/09/04/the-3-things-you-should-know-about-hashcode/

Vad är en datastruktur?		
Svar: En struktur för organisering av data så att den kan användas på ett effektivt sätt.
exempel på datastrukturer: fält, listor, hastabeller, stackar, köer.
https://sv.wikipedia.org/wiki/Datastruktur

Vad är viktigt vid val av datastruktur?		
Svar: Olika typer av datastrukturer är anpassade till olika typer av applikationer, och vissa är mycket specialicerade för vissa uppgifter. Det är därför viktigt att välja just den datastruktur som passar bäst för den specifika uppgiften. 
https://en.wikipedia.org/wiki/Data_structure

Vad innebär "sökning i en osorterad vektor tar linjär tid" (se Hashtable i Java)?		
Svar: Om data är osorterad i en datamängd/struktur, så tar varje element i snitt lika lång tid att leta upp, därav blir söktiden linjär med antal element.

Vad är det för skillnad mellan Hashtable och HashMap?		
Svar: Precis som HashMap, så har HashTable key/value och de båda implementerar interfacet Map<K,V> som betyder just att de är objekt som mappar keys till values. 
En väsentlig skillnad är att HashTable är synchronized vilket inte HashMap är, dessutom tillåter inte HashTable null keys eller values, vilket HashMap gör.

Vad är Dictionary?		
Svar: Dictionary klassen är en abstrakt klass som b.la HashTable är subklass till.
Notera: Denna abstrakta klass är utgående. Istället bör Map interface implementeras.
https://docs.oracle.com/javase/8/docs/api/java/util/Dictionary.html

Vad är Java Collections Framework? Berätta kort om historiken, dess för/nackdelar och innehåll. Vad ville man uppnå med JCF? Vilka problem fanns det innan på de samlingsdatastrukturer som var tillgängliga?		
Svar: En collection framework (samlings-ramverk) är en enad struktur som är byggd för att manipulera flera olika collections (objekt som representerar en grupp av andra objekt), alltså ett slags bibliotek. Alla samlings-ramverk innehåller tre viktiga delar: gränssnitt, implementationer (klasser) och algoritmer.
Med JCF ville man uppnå flera mål, bland annat att ramverket skulle vara effektivt, att flera olika collections skulle fungera någorlunda likadana och att de är kompatibla med varandra samt att det skulle vara enkelt att extenda och vidareutveckla en collection.
De första objekten/klasserna före JCF (Array, Vector och HashTable), var inte särskilt flexibla, var svåra att vidareutveckla (extend), och implementerade inga övergripande gränssnitt (“standard member interface”), vilket gjorde att de inte var särskilt inter-kompatibla (de var olika i sin struktur).
http://www.tutorialspoint.com/java/java_collections.htm
https://en.wikipedia.org/wiki/Java_collections_framework
http://www.javatpoint.com/collections-in-java
http://docs.oracle.com/javase/7/docs/technotes/guides/collections/overview.html

Vad är ett interface?		
Svar: Ett interface i java är ett slags kontrakt mellan olika klasser och världen utanför. Ett interface kan användas till att begränsa tillgången till en klass och som ett slags lovord om att de metoderna som den utlovar faktiskt finns tillgängliga i klassen.

Vilka interfaces ingår i JCF? Övergripande gränssnitt? Gränssnitt för traversering? För sortering?		
Svar: Utöver bilden CollectionHierarchy.jpg så ingår även ListIterator (extendar Iterator), som används för traversering. Övergripande interface blir Object, Collection, Map och Iterator. Sorterings-interface är List, SortedSet, SortedMap.

Vilka implementationer finns på dessa interfaces?		
Svar: Se svar från föregående fråga.

Har ni fått med alla? List, ArrayList, LinkedList, Vector, Set, HashSet, LinkedHashSet, TreeSet, Map, HashMap, TreeMap, LinkedHashMap, Iterator, ListIterator (har jag fått med alla?)		
Svar: Iterator  och ListIterator har bara nämnts bland svaren.

Titta på bilden CollectionTable.png och förklara den. Implementationer markerade med en asterisk (*) är meningslösa i någon bemärkelse. Varför då?		
Svar: En lista använder sig av index och behöver därför ingen hash (key-values), därför implementerar den inte Set eller Map. På samma sätt behöver en hashad Map eller Set vanligtvis ingen index, och implementerar därför inte List. 

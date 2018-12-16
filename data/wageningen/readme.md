# Wageningen open data

De gemeente wageningen biedt een aantal kaartservices aan via het platform arcgis.com, beschikbaar op de url 
https://www.arcgis.com/home/search.html?q=owner%3AGemeente_Wageningen&start=1&sortOrder=true&sortField=relevance

Deze QGIS project file refereert direct naar de diverse services

# Kinderopvanglocaties in Wageningen

kinderopvang.csv is een extract van https://www.landelijkregisterkinderopvang.nl op basis van [scraping](https://nl.wikipedia.org/wiki/Scrapen)

Scrapen op basis van jquery javascript (copy/paste in f12 dev console)

```
$(".aankeiler").each(function(){
	q={};
	q.tp=$(this).find("h2").text().split("(")[1].split(")")[0];
	q.nm=$(this).find("h2 a").text();
	q.ad=$(this).find("span").first().text();
	q.pc=$(this).find("span").next().text().split(" ")[0];
	console.log(q.nm+";"+q.tp+";"+q.ad+";"+q.pc+";")
});
```

CSV is op adres gekoppeld met [BAG](http://nationaalgeoregister.nl/geonetwork/srv/metadata/aa3b5e6e-7baa-40c0-8972-3353e927ec2f) extract, koppeling via postcode+huisnummer

Resultaat: kinderopvang.gpkg

## of als csv.

Snapshots van het LRK zijn ook als csv beschikbaar via https://data.overheid.nl/data/dataset/gegevens-kinderopvanglocaties-lrk. De licentie van de data is CC-0 (geen beperkingen).


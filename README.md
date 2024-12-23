## Overview

As part of the Developing Data Products course, I used the Leaflet package in R to produce a list of 13 Portuguese Monuments worth visiting scattered along the country (some more worthy of visiting than others...).

## Interactive Map using Leaflet

```{r, echo = TRUE}
library(leaflet)
PM <- data.frame(lat=c(39.659402130663196, 39.5483248919416, 38.698083458718486, 38.69377312260483, 39.46220014924232, 38.71403474387595, 38.78768542583135, 41.555484847279196, 42.03014119609886, 41.448054308798255, 38.372499885058, 38.56602262593241, 38.641634311073936),lng=c(-8.824145155946121, -8.979628162237303, -9.20647859907021, -9.205057045650861, -8.383182143758042, -9.132907576333624, -9.390608904610373, -8.373129879104528, -8.644543028261891, -8.289932866375253, -8.513754200382737, -8.9004797818874, -8.217401962844225), name=c("Mosteiro da Batalha", "Mosteiro de Alcobaça", "Mosteiro dos Jerónimos", "Padrão dos Descobrimentos", "Castelo de Almourol", "Castelo de São Jorge", "Palácio da Pena", "Bom Jesus de Braga", "Fortaleza de Valença", "Castelo de Guimarães", "Castelo de Alcácer do Sal", "Castelo de Palmela", "Castelo de Montemor-o-Novo"))
PM_map <- PM %>% leaflet() %>% 
  addTiles() %>% 
  addMarkers(popup = PM$name, clusterOptions = markerClusterOptions())
PM_map
```

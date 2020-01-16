# Project Salesforecasting op sales van meubelen en kantoorartikelen

In dit project maak ik een voorspelling van de sales van kantoorartikelen en meubelen van een bedrijf. Deze worden nadien ook vergeleken.
Als extra heb ik ook in dit project verschillende grafieken nagemaakt die ook tijdens de lessen statistics for Big Data aanbod kwamen.

## Het project

* Verschillende imports om het project te doen werken.
  * 
  * Import itertools voor efficiënt loopen
  * Import Numpy is een open-source uitbreiding op de programmeertaal
  * Import matplotlib is een plotbibliotheek voor python
  * Import pandas makkelijk te gebruiken data structures en data analyses tools voor python
  
  ![SP1](https://user-images.githubusercontent.com/38683024/72526403-9bcdd900-3866-11ea-97a1-9ab69d5fc92b.PNG)

* De dataset die ik gebruik is Superstore.xls waarin de sales van meubelen en kantoorartikelen van januari 2014 tot december 2017 staan.
![SP2](https://user-images.githubusercontent.com/38683024/72527345-dafd2980-3868-11ea-89cb-47ca790a4ab0.PNG)

* De Dataset bevat naast sales en dates nog andere data deze gebruiken we niet. Daarom droppen we de overbodige data.
![SP3](https://user-images.githubusercontent.com/38683024/72527975-44316c80-386a-11ea-8f08-b0b262f1529d.PNG)

* Omdat de dataset de sales van verschillende dagen per maand weergeeft nemen we het gemiddelede per maand, dit maakt rekenen en intrepreteren gemakkelijker.
![SP4](https://user-images.githubusercontent.com/38683024/72528154-af7b3e80-386a-11ea-9daa-d29edd0e5bde.PNG)

* In onderstaande afbeelding worden verschillende begrippen getoont die invloed hebben op het voorspellen van onze data.
  * Observed: de werkelijk gemeten data. (bv.: sales 2017-01-01 -> 2133)
  * Trend: de Trend die de sales volgen
  * Seasonality: Hoe hard een bepaalde periode invloed heeft op de data/voorspelde data (bv.: tijdens de zomer worden er meer ijsjes verkocht dus seasonality is hoger.)
  * Residual: Het verschil tussen de gemeten data en de voorspelde data. (bv.: gemeten sales 2017-01-01 -> 2133 MAAR voorspelling sales 2017-01-01 -> 3000 DUS residual = -867
![SP4 2](https://user-images.githubusercontent.com/38683024/72531273-6a0e3f80-3871-11ea-9477-f0cb40705ada.PNG)

* Voorspellen met ARIMA (Autoregressive integrated moving average)
  * ARIMA heeft 3 parameters (seaonality, trend, noise) (Lees: Noise = Residual)
  * Nu gaan we zoeken welk models de laagste AIC waarde hebben. AIC schat het relatieve aantal aan waarde/informatie die verloren gaat met het model. dus hoe LAGER die AIC hoe BETER het model. In onderstaande afbeelding is te zien dat de laagst voorkomende AIC waarde 297,78 is, dus ons "beste" model is "ARIMA(1, 1, 1)x(1, 1, 0, 12)12 - AIC:297.7875439553055"

![SP5](https://user-images.githubusercontent.com/38683024/72532998-aabb8800-3874-11ea-824a-2646094c1538.PNG)

* Implementeren van het gekoze ARIMA model.
* In onderstaande afbeelding worden de residual values voorgesteld op verschillende manieren.
![SP6](https://user-images.githubusercontent.com/38683024/72536358-6206cd80-387a-11ea-9a3e-1352bd22797a.PNG)

* Om the checken of onze code tot nu toe foutloos werkt, laten we een voorspelling maken vanaf 2017 en vergelijken we die met data die we al hebben uit 2017
  * We zien dat onze observed (werkelijk gemeten data) en onze voorspelde data ongeveer overeen komen. Exact hetzelfde zullen deze twee nooit zijn.
![SP7](https://user-images.githubusercontent.com/38683024/72536504-a85c2c80-387a-11ea-89f9-eac2b79bf825.PNG)

* Berekenen van MSE (Mean square error) en RSME (root mean square error)
  * De MSE verteld ons het aantal keren onze voorspelling afweek van de actuele waardes
  * De RSME verteld ons het gemiddelde van de afwijking
![SP8](https://user-images.githubusercontent.com/38683024/72538353-00e0f900-387e-11ea-96b5-33663d4a2339.PNG)

* Nu we al deze informatie weten gaan we onze voorspelling maken





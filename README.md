# CUSTOM-SCRIPTS
# Algoritmos para la prevención y gestión de desastres
----
Este repositorio contiene una colección de scripts personalizados para [Sentinel Hub](https://www.sentinel-hub.com/), que se puede alimentar a los servicios a través de la URL

# Sentinel-2
Dedicado a suministrar datos para [Copernicus services](http://www.esa.int/Our_Activities/Observing_the_Earth/Copernicus/Sentinel-2), Sentinel-2 lleva una cámara multiespectral con una franja de 290 km. El generador de imágenes proporciona un conjunto versátil de 13 bandas espectrales que abarcan desde el infrarrojo visible e infrarrojo cercano al infrarrojo de onda corta, con cuatro bandas espectrales a 10 m, seis bandas a 20 my tres bandas a una resolución espacial de 60 m. Como los índices tratan principalmente de combinar varias reflectancias de banda, la tabla de 13 bandas se proporciona aquí como referencia (Inf: [aquí](https://sentinel.esa.int/web/sentinel/technical-guides/sentinel-2-msi/msi-instrument){:target="_blank"} for details). los nombres de las bandas de Sentinel-2 estan dispuestas asi *B01*, *B02*, *B03*, *B04*, *B05*, *B06*, *B07*, *B08*, *B8A*, *B09*, *B10*, *B11* and  *B12*. 

#### Combinaciones RGB frecuentes
 - [Color_Natural](Sentinel-2/natural_color) producto calculado correctamente para que coincida con el color percibido por el ojo humano.
 - [Color_verdadero](Sentinel-2/true_color) imagen simplista en color verdadero de bandas rojas, verdes y azules.
 - [Visualización_de_Incendios](Sentinel-2/markuse_fire) (Desarrollado por Pierre Markuse, tomado del [blog](https://pierre-markuse.net/2017/08/07/visualizing-wildfires-sentinel-2-imagery-eo-browser/){:target="_blank"})
#### Algoritmos para la prevención y gestión de desastres
 - [Perimetro_incendio](Sentinel-2/fire_boundary)
 - [Indice_de_Area_Quemada_para_Sentinel-2](Sentinel-2/bais2)
 - [Analisis_Multitemporal_de_Area_Quemada](Sentinel-2/burned_area)
 - [Visualización_de_Incendios](Sentinel-2/markuse_fire) (Desarrollado por Pierre Markuse, tomado del [blog](https://pierre-markuse.net/2017/08/07/visualizing-wildfires-sentinel-2-imagery-eo-browser/){:target="_blank"})
 - [Visualización_del_Area_Quemada](Sentinel-2/burned_area_ms)
-----

| <img width=10>Nombre del Satelite</img><img width=150> </img> | Descripcion | 
| ----------- | ------------------------------------------------------------------------------------------------------- |
| Sentinel-1 | Maritime and land monitoring emergency response climate change |
| Sentinel-2 | Land-cover maps land-change detection maps vegetation monitoring monitoring of burnt areas |
| Sentinel-3 | Surface topography observations ocean and land surface colour observation and monitoring|  
|Sentinel-3  |OLCI instrument ensures the continuity of Envisat Meris |
 |Sentinel-5P |Monitoring the concentration of carbon monoxide (CO) nitrogen dioxide (NO2) and ozone (O3) in the air. Monitoring the UV aerosol index (AER_AI) and various geophysical parameters of clouds (CLOUD)
 |ESAs archive of Landsat 5/7 and 8 |vegetation monitoring land use land cover maps change monitoring global coverage of Landsat 8 - Envisat Meris and old data |
 |Proba-V |The observation of land cover vegetation growth climate impact assessment water resource management agricultural monitoring and food security estimates inland water resource monitoring and tracking the steady spread of deserts and deforestation. |
 |MODIS |Monitoring of land clouds ocean colour at a global scale (by ESA) |
 |GIBS |Global image browser service with over 600 satellites made available by NASA |

---
## How to publish your own product

* Fork the repository to get your own copy of the custom-scripts   
  _It is easiest to fork the repository on GitHub, but as some of you might not have GitHub account, or don't want to bother with all this versioning and collaboration tools, you can also just download the whole repository as Zip file and work from there._
  
* Create a new directory entry for your custom script   
  *Copy the `example` directory to proper directory, based on which datasource (satellite) you are publishing the product for, to something that describes what the product is about, say `my_algorithm`.*   
  *Preferably use ["snake_case"](https://simple.wikipedia.org/wiki/Snake_case) (underscores instead of spaces) if more than one word is used.*
  
* Fill in the details about the project in the `README.md` file.   
  *Obviously, you'll want to remove this chapter, but use the rest of the file as a template.*   
  *Have a look around at other `README.md` files to see how to include images, format the text and generally use the GitHub [markdown](https://help.github.com/categories/writing-on-github/) (e.g. [here](../sentinel-2/cby_cloud_detection/README.md) for mathematical formulas or [here](../sentinel-2/ndvi_uncertainty/README.md) for adding images).*
  
* Implement the product in the `script.js` file.   
  *The most work is of course the JavaScript implementation of the product. The `example` folder includes an empty custom script with comments that will hopefully help you build your own custom script. Of course the easiest is to do the custom script building/testing on [Sentinel Playground](https://apps.sentinel-hub.com/sentinel-playground/).*
  
* Add an entry pointing to your script to the [main](../README.md) readme file.   
  *A link and a short description will do.*
  
* And create a pull request :).
  *There is extensive help on creating pull requests on GitHub [help](https://help.github.com/categories/collaborating-with-issues-and-pull-requests/), but if you feel overwhelmed by this step and would still like to contribute, send us the folder you've created and we will take care of it for you.*

Publishing your product should be easy, nevertheless, any feedback and ideas how to improve or make the process simpler is very appreciated.

---

<a href="#" id='togglescript'>Show</a> script or [download](script.js){:target="_blank"} it.
<div id='script_view' style="display:none">
{% highlight javascript %}
      {% include_relative script.js %}
{% endhighlight %}
</div>

## Evaluate and visualize
 - [Sentinel Playground](https://apps.sentinel-hub.com/sentinel-playground/?source=S2&lat=41.9027835&lng=12.496365500000024&zoom=12&evalscripturl=https://raw.githubusercontent.com/sentinel-hub/customScripts/master/example/script.js){:target="_blank"}    
 - [EO Browser](http://apps.sentinel-hub.com/eo-browser/#lat=41.9&lng=12.5&zoom=10&datasource=Sentinel-2%20L1C&time=2017-10-08&preset=CUSTOM&layers=B01,B02,B03&evalscripturl=https://raw.githubusercontent.com/sentinel-hub/customScripts/master/example/script.js){:target="_blank"}   

## General description of the script

## References
 - possible references (scientific articles, wiki/web references, ...)

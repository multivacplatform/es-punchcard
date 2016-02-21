# es-punchcard


##Description
Make punchcard charts based on Elasticsearch [histogram] (https://www.elastic.co/guide/en/elasticsearch/reference/master/search-aggregations-bucket-histogram-aggregation.html) or [date histogram] (https://www.elastic.co/guide/en/elasticsearch/reference/master/search-aggregations-bucket-datehistogram-aggregation.html) aggregations

##Documentation

Set some settings before calling the init() function:

```javascript
punchcard.width = 500;
punchcard.top = 50;
punchcard.svgID = "myFristChart";
```

You can set these settings anytime and call the init() again to initiate the SVG with new config.

```javascript
punchcard.init();
```

All charts would be removed whenever init() is called. (possible to only remove svg with a specific ID if you set one)

Now it is time for loading data:

```javascript
punchcard.draw(data);
```

##Installation
###Git clone
```
git clone https://github.com/maziyarpanahi/es-punchcard.git
```

or

```
git clone https://maziyar_sh@bitbucket.org/iscpif/es-punchcard.git
```

###Bower
```
bower install --save es-punchcard
```

(OPTIONAL) You may want to have a .bowerrc file and change it to:

```javascript
{
  "directory": "js/"
}
```

This way you can use the demo.html right away. Otherwise you have to fix the paths to the required files.

e.g. chage this to where ever you keep your D3 library.

```javascript
 <script src="js/d3/d3.min.js"></script>
```



##Example
Climate at ISCPIF [https://climate.iscpif.fr/playground] (https://climate.iscpif.fr/playground)

![Climate Demo](https://github.com/maziyarpanahi/es-punchcard/raw/master/demo-climatechange.png "Climate Demo")


##Credits
###Inspired by

Repository [https://github.com/mutanthumb/ETD_bubbles] (https://github.com/mutanthumb/ETD_bubbles)


Example [http://neuralengr.com/asifr/journals] (http://neuralengr.com/asifr/journals/)

###Used Libraries
Bootstrap [https://github.com/twbs/bootstrap] (https://github.com/twbs/bootstrap)

D3 [https://github.com/mbostock/d3] (https://github.com/mbostock/d3)

jQuery [https://github.com/jquery/jquery] (https://github.com/jquery/jquery)

Moment [https://github.com/moment/moment] (https://github.com/moment/moment)

##TODO
* Updating documentations
* Connect mouse events to custome functions defined by user
* Customized date format based on Elasticsearch Histogram results
* Set start and end date dynamically from result by default

##Copyright and License
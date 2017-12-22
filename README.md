# es-punchcard


## Description
Make punchcard charts based on Elasticsearch [histogram] (https://www.elastic.co/guide/en/elasticsearch/reference/master/search-aggregations-bucket-histogram-aggregation.html) or [date histogram] (https://www.elastic.co/guide/en/elasticsearch/reference/master/search-aggregations-bucket-datehistogram-aggregation.html) aggregations


## Installation
### Bower

This is a recommended way and it will install everything you need:

```
bower install --save es-punchcard
```

(OPTIONAL) You may want to have a .bowerrc next to your bower.json file and change it to:

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


### Git clone
```
git clone https://github.com/maziyarpanahi/es-punchcard.git
```

or

```
git clone https://maziyar_sh@bitbucket.org/iscpif/es-punchcard.git
```

You need these JS libraries if you installing this manually:


D3 [https://github.com/mbostock/d3] (https://github.com/mbostock/d3)

Moment [https://github.com/moment/moment] (https://github.com/moment/moment)

jQuery [https://github.com/jquery/jquery] (https://github.com/jquery/jquery)

Optional for the demo file:

Bootstrap [https://github.com/twbs/bootstrap] (https://github.com/twbs/bootstrap)


## Documentation

You can install these by simply using bower install:
```javascript
  <link rel="stylesheet" href="style.css" /> <!-- load punchcard css (OPTIONAL) -->
  <script src="/path-to-jquery/jquery.min.js" />
  <script src="/path-to-bootstrap/bootstrap.min.js" />
  <script src="/path-to-d3/d3.min.js" /> <!-- (REQUIRED) -->
  <script src="/path-to-moment/moment.js" /> <!-- (REQUIRED) -->
  <script src="/path-to-es-punchcard/es-punchcard.js" /> <!-- (REQUIRED) -->
```


Set some settings before calling the init() function:

```javascript
punchcard.width = 500;
punchcard.top = 50;
punchcard.svgID = "myFristChart";
punchcard.custom_start_year = "2015-05";
punchcard.custom_end_year = "2015-12";
punchcard.d3DateFormat = "%Y-%m";
punchcard.dataDateFormat = "YYYY-MM";
punchcard.customTickFormat = "%Y-%m";
```

You can set these settings anytime and call the init() again to initiate the SVG with new config.

```javascript
punchcard.init();
```

All charts would be removed whenever init() is called. (possible to only remove svg with a specific ID if you set one)

Now it is time for loading some data:

```javascript
punchcard.draw(data);
```

## Data Structure

This is a sample of one of the keys. The buckets refer to (date) histogram aggregation to fill the punchcard. 

```javascript
{"key":"carbon emissions","doc_count":320001,"score":52.34230602030492,"bg_count":519874,"monthly":{"buckets":[{"key_as_string":"2015-03-01T00:00:00.000Z","key":1425168000000,"doc_count":1916},{"key_as_string":"2015-04-01T00:00:00.000Z","key":1427846400000,"doc_count":28383},{"key_as_string":"2015-05-01T00:00:00.000Z","key":1430438400000,"doc_count":31190},{"key_as_string":"2015-06-01T00:00:00.000Z","key":1433116800000,"doc_count":32671},{"key_as_string":"2015-07-01T00:00:00.000Z","key":1435708800000,"doc_count":44745},{"key_as_string":"2015-08-01T00:00:00.000Z","key":1438387200000,"doc_count":31513},{"key_as_string":"2015-09-01T00:00:00.000Z","key":1441065600000,"doc_count":24680},{"key_as_string":"2015-10-01T00:00:00.000Z","key":1443657600000,"doc_count":18625},{"key_as_string":"2015-11-01T00:00:00.000Z","key":1446336000000,"doc_count":43595},{"key_as_string":"2015-12-01T00:00:00.000Z","key":1448928000000,"doc_count":62683}]}}
```

Right way to send aggregation to Elasticsearch to get proper response:


## Example
### Live Demo
Climate at ISCPIF [https://climate.iscpif.fr/playground] (https://climate.iscpif.fr/playground)

![Climate Demo](https://github.com/maziyarpanahi/es-punchcard/raw/master/demo-climatechange.png "Climate Demo")


### JSFiddle

It is also available on JSFiddle [https://jsfiddle.net/maziyar/73da0urn/] (https://jsfiddle.net/maziyar/73da0urn/)

### Native Demo

Simply run "bower install" to install required libraries and open demo.html file.

## Code of Conduct

This, and all github.com/multivacplatform projects, are under the [Multivac Platform Open Source Code of Conduct](https://github.com/multivacplatform/code-of-conduct/blob/master/code-of-conduct.md). Additionally, see the [Typelevel Code of Conduct](http://typelevel.org/conduct) for specific examples of harassing behavior that are not tolerated.


## Credits
### Inspired by

Repository [https://github.com/mutanthumb/ETD_bubbles] (https://github.com/mutanthumb/ETD_bubbles)


Example [http://neuralengr.com/asifr/journals] (http://neuralengr.com/asifr/journals/)

### Used Libraries
Bootstrap [https://github.com/twbs/bootstrap] (https://github.com/twbs/bootstrap)

D3 [https://github.com/mbostock/d3] (https://github.com/mbostock/d3)

jQuery [https://github.com/jquery/jquery] (https://github.com/jquery/jquery)

Moment [https://github.com/moment/moment] (https://github.com/moment/moment)

## TODO
* Updating documentations
* Connect mouse events to custome functions defined by user
* Customized date format based on Elasticsearch Histogram results
* Set start and end date dynamically from result by default

## Copyright and License

Code and documentation copyright 2015-2016 [ISCPIF - CNRS](http://iscpif.fr). Code released under [the MIT license](https://github.com/multivacplatform/es-punchcard/blob/master/LICENSE.md).

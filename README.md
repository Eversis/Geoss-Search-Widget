# Geoss Search Widget
Easy access to Earth Observation resources on your website!

![Search bar](/images/widget-search-bar.png)

## About
### Who might be interested?
Widget is particularly recommended for people who:
  - own a website with a map in it,
  - wish to present GEOSS resources,
  - don't want to implement search bar from the scratch.

### Advantages
Geoss Search Widget:
  - provides **essential features of GEOSS**,
  - is a **lightweight** application,
  - is **free**,
  - is **easily customizable**.

![Results](/images/widget-results.png)

## Getting Started
1. Get [access key](http://geoss.sit.esaportal.eu/register-widget),
2. Follow [installation instruction](http://geoss.sit.esaportal.eu/install-widget):
    - import css/js dependencies,
    - import GEOSS library,
    - adjust configuration,

    ![Configuration file](/images/widget-config.png)
3. Try it out!

## Project Demo - Hands On!
1. Enable Cross-Origin Resource Sharing (CORS):
    - for Firefox - install [CORS Everywhere add-on](https://addons.mozilla.org/en-US/firefox/addon/cors-everywhere/),
    - for Chrome - install [Allow-Control-Allow-Origin add-on](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi),
    - for Safari - select "Disable Cross-Origin Restrictions" from the developers console,
    - *alternatively* install XAMPP and put the package to the server,
2. Download the [package](http://geoss.sit.esaportal.eu/documents/20181/0/Geoss+Search+Widget/7f2034a2-b5e3-4df2-9467-fd300dea85d0), extract it and open index.html,
3. Add access key (provided at the workshop or obtained from [here](http://geoss.sit.esaportal.eu/register-widget)) to Geoss.accessKey in configuration (inside js/sitecustom.js or via web console),
4. Try out searching, map interactions, custom download, WMS layers,
5. Take a closer look at Widget API:
    - callbacks:
    ```javascript
    Geoss.initSearchBarCallback();
    Geoss.actionBeforeRequest();
    Geoss.successCallback(data);
    Geoss.failureCallback(error);
    Geoss.metadataCallback();
    Geoss.downloadBoxCallback();
    Geoss.addBBoxInteraction(map);
    Geoss.addLayerCallback(layer, checkbox);
    Geoss.synchronizeLayerList();
    ```
    - filling the searchform via script:
    ```javascript
    var params = new Object();
    params.query = "Water";
    params.sources = "geodabgbifid"
    params.aoiOption = "Coordinates";
    params.aoiBoundingBox = "-100,-60,0,20";
    params.aoiRelation = "bbox_contains";
    params.datePeriod = "last-year";
    Geoss.search(params);
    ```

## Feedback
If you test the widget on your website and want contribute to its further development, please share your suggestions with us by filling [this form](https://docs.google.com/forms/d/e/1FAIpQLSetnuRiBe-g1XDmSyjmlQ8wXZPXbOB5UIr7DzgNUGKJvchn8g/viewform?c=0&w=1).

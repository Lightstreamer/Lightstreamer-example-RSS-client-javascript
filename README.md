# Lightstreamer RSS Demo Client for JavaScript #

This project includes a simple web client front-end example for the Lightstreamer RSS Demo Adapter.

## RSS News Reader Demo ##

<table>
  <tr>
    <td style="text-align: left">
      &nbsp;<a href="http://demos.lightstreamer.com/RSSDemo/" target="_blank"><img src="http://www.lightstreamer.com/img/demo/screen_rss.png"></a>&nbsp;
      
    </td>
    <td>
      &nbsp;An online demonstration is hosted on our servers at:<br>
      &nbsp;<a href="http://demos.lightstreamer.com/RSSDemo/" target="_blank">http://demos.lightstreamer.com/RSSDemo</a>
    </td>
  </tr>
</table>

The RSS News Reader Demo is a simple news aggregator that allows the user to subscribe to several RSS feeds and have the news pushed in real-time without refreshing the page or polling the server under the hood.<br>
This page uses the <b>JavaScript Client API for Lightstreamer</b> to handle the communications with Lightstreamer Server and the demo starts with some feeds already subscribed to. You can add your own feeds or click on "+" to add random feeds.<br>

The demo includes the following client-side technologies:
* A [Subscription](http://www.lightstreamer.com/docs/client_javascript_uni_api/Subscription.html) containing 1 item, subscribed to in <b>DISTINCT</b> mode feeding a [DynaGrid](http://www.lightstreamer.com/docs/client_javascript_uni_api/DynaGrid.html) containing the news.
* A [Subscription](http://www.lightstreamer.com/docs/client_javascript_uni_api/Subscription.html) containing 1 item, subscribed to in <b>COMMAND</b> mode feeding a [DynaGrid](http://www.lightstreamer.com/docs/client_javascript_uni_api/DynaGrid.html) containing the list of feeds currently subscribed to.

# Deploy #

Before you can run the demo some dependencies need to be solved:

-  Get the lightstreamer.js file from the [latest Lightstreamer distribution](http://www.lightstreamer.com/download) 
   and put it in the src/js folder of the demo (if that is the case, please create it). Alternatively you can build a lightstreamer.js file from the 
   [online generator](http://www.lightstreamer.com/distros/Lightstreamer_Allegro-Presto-Vivace_5_1_1_Colosseo_20130305/Lightstreamer/DOCS-SDKs/sdk_client_javascript/tools/generator.html).
   In that case be sure to include the LightstreamerClient, Subscription, DynaGrid, and StatusWidget modules and to use the "Use AMD" version.
-  Get the require.js file form [requirejs.org](http://requirejs.org/docs/download.html) and put it in the src/js folder of the demo.

You can deploy this demo in order to use the Lightstreamer server as Web server or in any external Web Server you are running. 
If you choose the former case please create the folders "<LS_HOME>/pages/demos/RSSDemo" then copy here the contents of the /src folder of this project.<br>
The client demo configuration assumes that Lightstreamer Server, Lightstreamer Adapters and this client are launched on the same machine. Hence the [RSS_ADAPTER]() and [RSSMetadataAdapter]() Adapters have to be deployed in your local Lightstreamer server instance.<br>
If you need to targeting a different Lightstreamer server please search this line:
```js
var lsClient = new LightstreamerClient(protocolToUse+"//localhost:8080","DEMO");
```
in js/lsClient.js file and change it accordingly. For example if you want to target the adapter deployed in our server you should substitute with this:
```js
var lsClient = new LightstreamerClient(protocolToUse+"//push.lightstreamer.com","DEMO");
```
<br>
The demo are now ready to be launched.

# See Also #

## Lightstreamer Adapters needed by these demo clients ##

* (To be add: Lightstreamer Race Telemetry Demo Adapter)
* [Lightstreamer Reusable Metadata Adapter in Java](https://github.com/Weswit/Lightstreamer-example-ReusableMetadata-adapter-java)

## Similar demo clients that may interest you ##

* [Lightstreamer Chat Demo Client for JavaScript](https://github.com/Weswit/Lightstreamer-example-Chat-client-javascript)
* [Lightstreamer Portfolio Demo Client for JavaScript](https://github.com/Weswit/Lightstreamer-example-Portfolio-client-javascript)

# Lightstreamer Compatibility Notes #

- Compatible with Lightstreamer JavaScript Client library version 6.0 or newer.
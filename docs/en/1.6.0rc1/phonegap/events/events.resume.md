resume
===========

This is an event that fires when a Cordova application is retrieved from the background.

    document.addEventListener("resume", yourCallbackFunction, false);

Details
-------

Cordova consists of two code bases: native and JavaScript. While the native code pulls the application from the background the resume event is fired.  

Typically, you will want to attach an event listener with `document.addEventListener` once you receive the Cordova 'deviceready' event.

Supported Platforms
-------------------

- Android
- BlackBerry WebWorks (OS 5.0 and higher)
- iOS

Quick Example
-------------

    document.addEventListener("resume", onResume, false);

    function onResume() {
        // Handle the resume event
    }

Full Example
------------

    <!DOCTYPE html>
    <html>
      <head>
        <title>Cordova Resume Example</title>

        <script type="text/javascript" charset="utf-8" src="cordova-1.6.0.js"></script>
        <script type="text/javascript" charset="utf-8">

        // Call onDeviceReady when Cordova is loaded.
        //
        // At this point, the document has loaded but cordova-1.6.0.js has not.
        // When Cordova is loaded and talking with the native device,
        // it will call the event `deviceready`.
        //
        function onLoad() {
            document.addEventListener("deviceready", onDeviceReady, false);
        }

        // Cordova is loaded and it is now safe to make calls Cordova methods
        //
        function onDeviceReady() {
            document.addEventListener("resume", onResume, false);
        }

        // Handle the resume event
        //
        function onResume() {
        }

        </script>
      </head>
      <body onload="onLoad()">
      </body>
    </html>

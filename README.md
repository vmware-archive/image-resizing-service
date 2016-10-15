# A simple image resizing service

## How it works
Accepts HTTP GET or POST, with two parameters:
* urlBase64: Base64 encoded URL
* size: size of a square bounding box, in pixels
Returns the resized image, or an image of the original size if size is less than the original size

## Try it out locally
* Get a base64 encoded version of an image URL:
  `echo -n "http://storage.googleapis.com/gcp-pcf-demo/Parliament_Big_Ben.jpg" | base64`
* Use curl to access the service:
  `time curl http://localhost:18080/?size=800&urlBase64=aHR0cDovL3N0b3J...bi5qcGc= > output.jpg`

## Run on Cloud Foundry


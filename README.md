# image-resizing-service is no longer actively maintained by VMware.

# A simple image resizing service

## How it works
Accepts HTTP GET or POST, with two parameters:
* urlBase64: Base64 encoded URL
* size: size of a square bounding box, in pixels
Returns the resized image, or an image of the original size if size is less than the original size

## Try it out locally (see note below on dependencies)
* Get a base64 encoded version of an image URL:
  `echo -n "http://storage.googleapis.com/myBucketName/Image_Name.jpg" | base64`
* Use curl to access the service, providing that base64 encoded URL value:
  `time curl http://localhost:18080/?size=800&urlBase64=aHR0cDovL3N0b3J...bi5qcGc= > output.jpg`

## Run on Cloud Foundry
* Edit ./manifest.yml to suit your application
* `cf push`

## Installation of dependencies, for running locally (Ubuntu 14.04)
```
sudo apt-get build-dep python-imaging
sudo apt-get install libjpeg8 libjpeg62-dev libfreetype6 libfreetype6-dev
sudo apt-get install python-pip
sudo pip install Pillow
```

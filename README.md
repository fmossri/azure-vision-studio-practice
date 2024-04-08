# azure-vision-studio-practice
Practicing with Azure AI Vision Studio - Detect Face

## Introduction
In this exercise we practiced using Azure AI Vision Studio's Face recognition service. This service detects faces in photos, returning a text or JSON list with the detected faces and some features about it, like if it's covered by a facemask of any kind. A facemask, in this service, is any kind of partial or full obstruction of a person's face, supposedly caused by some kind of wearable, like a mask, sunglasses, a scarf covering the mouth, a hat covering eyebrows, etc.
To do this, we followed Microsoft Learn's [guidelines](https://aka.ms/ai900-face).

## Setup Steps
1. With a properly configured Azure Signature, navigate to portal.azure.com, click "+ New resource", browse for "Azure AI Service" and select "create" bellow. Fill in the form with a resource group, a unique name, a region of your preference and "S0" pricing tier. Check the acknowledgment box and create the resource.
2. Navigate to [Vision Studio](https://portal.vision.cognitive.azure.com), make sure you are in the same directory as your newly created resource, which is displayed on the top right corner of the page; if you are not already connected with your resource, click on "view all resources" and select your newly created resource as default.
3. Navigate back to Vision Studio's main page and select the tab "Face":

![image](https://github.com/fmossri/azure-vision-studio-practice/assets/82612595/f7e817d5-10f7-4e89-a657-227560fbd29c)

## How it works

Detect face samples Azure AI Vision's face recognition capabilities, and although they offer sample images to test the service, we chose to use randomly picked photos from the internet, so that we could test the service's limits. Detect face looks for face patterns in an image, returning a modified image containing the detected faces inside blue squares. It also returns a text or JSON list containing each of the detected faces with numbers and face covering details. 

![image](https://github.com/fmossri/azure-vision-studio-practice/assets/82612595/83a87b5d-0cb9-485b-a496-de1ff48e02d3)
![image](https://github.com/fmossri/azure-vision-studio-practice/assets/82612595/03613600-c173-4996-b642-98e29d8ba53e)

It's actually not clear to me what exactly the service considers a facemask; so I couldn't tell if, using the above image as an example, the service was failing in its assessment, or if it was considering something on the girls' image as a facemask; maybe the medals.
It also struggles when people's faces are too obstructed, specially if they are crunched togheter in a small area:

![image](https://github.com/fmossri/azure-vision-studio-practice/assets/82612595/45fd370e-29a2-4345-8709-51eb8546638f)

Detect Face seems to work better when people are evenly distributed in the photo; it also apparently have an easier time with people closer to the camera, specially in a frontal position.

![image](https://github.com/fmossri/azure-vision-studio-practice/assets/82612595/e844a733-d2cf-4b94-93d9-ba5163b5df25)

In this sample service, it seems to be capped to a maximum of 64 face detections per picture.

![image](https://github.com/fmossri/azure-vision-studio-practice/assets/82612595/75b236d8-08ab-4429-8c18-9e84144254e9)

## Conclusion

Detect face is a sample of Azure AI Vision face recognition capabilities. After testing it, users are encouraged to integrate Azure AI Vision services into their own applications. With propper tunning, the face detection service could be very useful for security, tracking and authentication services.

Image sources: 
- https://www.portugal.com/wp-content/uploads/2022/01/zeg-young-_0KJ4A_i4CA-unsplash-696x449.jpeg
- https://en.wikipedia.org/wiki/Podium#/media/File:2010_Olympic_ladies_podium.jpg
- https://thumbs.dreamstime.com/z/fluminense-palmeiras-6858024.jpg?ct=jpeg
- https://www.toledo.pr.gov.br/old/sites/default/files/images/g.r.d_02_carlos_rodrigues_.jpg

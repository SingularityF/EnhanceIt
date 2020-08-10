# EnhanceIt
A containerized API service that will **enhance** an image for you with the help of image super-resolution(SR). 

# Highlights
1. Very cost-effective. Image super-resolution is a very time-intensive and resource-intensive task. The API can run on Kubernetes so that running a powerful yet expensive server is not required. Furthermore, the API taps into serverless technologies so that zero cost will be incurred when idling.

2. Very responsive. Kubernetes automatically launch new containers so that one user will not steal resources from another user.

# Caveats
1. Processing can be slow for large images.

# Prerequisites
1. A Google Cloud Platform account

2. Google Cloud Storage

3. Google Cloud Run

# Architecture
1. Users send requests providing an image url

2. Cloud run starts the built container

3. Requests are handled by a python server

4. Python downloads the image with the provided url

5. Image super-resolution algorithm is started to generate the enhanced image

6. The enhanced image is stored temporarily in a Cloud Storage bucket (image will be automatically deleted after some time as configured)

7. The url of the stored image is returned to the user
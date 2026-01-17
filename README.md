## dockerizing js app and running with docker compose

### This project consist of a nodejs app which is just a simple js app, a dockerfile to create a image out of nodejs app and a docker compose file which listed 3 images, one image is the custome nodejs image created form dockerfile and other 2 images are for mongodb database and mongo-express ui which are private images hosted on dockerhub private repository


### First build the custom nodejs image 
``` docker build -t my-app:1.0 . ```


### To run the application from docker compose
``` docker compose -f docker-compose.yaml up ```

### To deploy the image into the server, server needs to login to pull image, the custom nodejs image from private repository but for the public images like mongo and mongo-express,dockerlog is not needed

### Every time we changes to our application code, we need to rebuid the images

### To rename the image or tag the image
``` docker tag my-app:1.0 docker-registry-address/my-app:1.0 ```

### To push it to remote repository
``` docker push docker-registry-address/my-app:1.0 ```


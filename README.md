# Docker

### Command
Push an image to registory: ```docker push```

Pull an image from registory ```docker pull```

Build command: ```docker build -t <image-name>:<version> <project path of docker file>```

Run Command: ```docker run -d -p 8080:80 <image-name>```

Docker process: ```docker ps -a ```

Docker Image list: ```docker image ls``` , ```docker image ls -a ``` -a used to include intermediate image. SO if we pull image from docker hub and it will also use base image and so on and to see overall image include use -a

To stop container: ```docker stop <image_id>```

Get Detaild Information about image: ```docker image inspect <image>```

To get particular field out of inspect image: ```docker image inspect <image> --format <template >``` We can use GO template here Ex: docker image inspect nginx:1.14.0 --format "{{.Architecture}} {{.Os}}"

To delete an Image: ```docker rmi <image>``` or ```docker image rm <image>```. To delete a image if image has tag delete them first. or use -f force to remove all the tag and delete the image but the tag which is in use will not be deleted but it will get untag

If we have a image not been refrenced by any tag or any refrence we can remove by ```docker image prune```

To see the layer created by image ```docker image history <image_name>```

To export the docker image: Run the image and run cmd: ```docker export <image_name> > sample.tar```

To import the docker image : ```docker import - <image_name>:<version> sample.tar```

For Flatterning an image : So to combine multiple image layer into single layer we can flattern an image using following step:
1. Run the container from image
2. Exort the image
3. Import the image
Image with few layer can work better then image with multipe layer. But its good to have different layer

SSH termination ```Press enter . Type `~```

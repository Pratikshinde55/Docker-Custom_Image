# Docker-Custom_Image
Create Custom image on Docker:

![Screenshot 2024-02-25 181110](https://github.com/Pratikshinde55/Docker-Custom_Image/assets/145910708/6c34203b-d812-41cd-997f-6a311f533730)

 - Purpose of creating Custom image:
 
 When requirement is to create container with lot of custom settings. In container world we share images but not share container.

### There are two ways to Create Custom image using Docker:
  1. Docker Commit command
  2. Docker Build command (Dockerfile)

## Method:1 -[Custom image by Docker commit command]

In this method of Creating custom image, 1st we launch container & what we want to changes or add anything that on Container, Then create image from precreated container.
      
![Screenshot 2024-02-20 180117](https://github.com/Pratikshinde55/Docker-Custom_Image/assets/145910708/35dae902-cda1-4f0d-b6b2-446f54305eda)
     
Using this "commit" command for create Custom image:
     
    docker commit commitOs1  myos1:v1

Run container from Custom own image(myos1:v1)
    
    docker run -it --name mycontainer myos1:v1
             
![Screenshot 2024-02-20 180315](https://github.com/Pratikshinde55/Docker-Custom_Image/assets/145910708/e6d02b36-5a78-45c4-8e93-3ab0a48ca579)

           
## Method:2 - [Custom image by Dockerfile]
This method of creating Custom image use code(YAML), Creating own image by Code is fully Automatic way.
 
In this process of creating custom image, We put all code in one file that is "Dockerfile"

    docker build -t myOwnimage:v1 .
        
& we also put code in custom name file but at Building image time we need to mention File name & path / directory

    docker build -t myOwnimage:v1 -f myYmlcode /mycodefolder/ 
        
" -t " --> To Declare name to custom image(tag).
   
" -f " --> Name of file where code kept(file).
   
" . " --> Current directory.

- Note:
 
In code when use interactive command then need to pass argument. example: yum install httpd -y
      
"FORM" is a keyword in code file to tell about base image.(from base image we create new image)

"RUN" is keyword in code file for running commands.

Use commad to build image from Code(Dockerfile):

     docker build -t myimage:v1 .
           
Running container from own custom image(myimage:v1):

     docker run -it --name myos1 myimage:v1

![Screenshot 2024-02-20 185049](https://github.com/Pratikshinde55/Docker-Custom_Image/assets/145910708/56be20a1-8464-41c9-becd-5ddf2a4fa8ee)
         

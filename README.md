# Wordpress_website_AWS_Docker
Deploying a wordpress Website on AWS infrastructure using Docker

WordPress is a popular web hosting site that is very easy to use and setup. The platform allows users to create and setup websites for blogs, eCommerce stores, and other types of businesses. The popularity of WordPress has enabled it to be the web hosting platform of choice for over 40% of all the websites out there on the web!

Docker is a PaaS(Platform as a service) that uses local images to deliver software applications in the form of containers. Companies such as Google, Adobe, AT&T, PayPal… just to name a few all use Docker to build and manage their popular applications that are widely used around the globe. You can learn more here.

If you are someone who is looking to start a business and host your website on a safe and reliable platform, look no further than WordPress! Let’s dive into the Cloud and get things going!

What you will need

AWS account
Personal computer
Desire to learn something new
OBJECTIVES:

(1.) Launch EC2 instance(Ubuntu) 
(2.) Connect to instance via SSH 
(3.) Install Docker on Instance 
(4.) Verify Docker is properly installed 
(5) Install Docker Compose Service 
(6.) Verify Docker compose Service is successfully installed (7.) Create a New Directory for WordPress & Setup Docker Compose File(8.) Start WordPress Container(9.) Access WordPress Site

Step 1: Login AWS account and Launch EC2 instance

Login into your AWS account and type “EC2” in the search box to bring up the Instance management console.
Choose a name of your liking for your instance and select the “Ubuntu Server 22.04 LTS(HVM)” for the AMI
Create or select a key pair. If you are creating a new pair make sure to download it and save it to your local machine(saves to downloads folder by default depending on your machine).
Open port “22” and “80” to allow traffic to and from the instance. Port 22 will allow us to be able to SSH into the instance.
Leave the rest of the default settings as is and click “Launch” to officially deploy the instance.

<img width="986" alt="Screenshot 2023-05-17 at 07 44 26" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/1e551820-46e3-4d6c-a633-cbd7156cd48c">

                                                               
<img width="1134" alt="Screenshot 2023-05-17 at 07 45 17" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/86d7d4ca-803a-4e81-8c25-c28eec8b7099">

<img width="1003" alt="Screenshot 2023-05-17 at 07 45 41" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/39a2e1a1-8c7a-4a6a-a01a-a251f74051de">


Step 2: Connect to the instance via SSH

SSH into the new deployed instance. Your instance window should look like mine

<img width="723" alt="Screenshot 2023-05-17 at 07 48 51" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/2db1ef5b-d0f7-404d-8fe8-0d2d60985f24">

After successfully connecting your local machine to the instance, we need to update the instance before we can go through the process of installing docker.
Run the following command:

sudo apt-get update

Update screen ✅


<img width="727" alt="Screenshot 2023-05-17 at 07 49 29" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/7748c2ef-cc51-4c00-ab4d-e05fd4edba17">

Step 3: Install Docker on instance

Now that the instance has been successfully updated with all new packages we can now start the docker installation.
Run the following command to install docker:

sudo apt-get install docker.io

<img width="746" alt="Screenshot 2023-05-17 at 07 50 40" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/b63d9502-dc0e-4fbb-9c5a-72ac052b0c97">

Step 4: Verify that Docker Successfully Installed

In the previous step we ran the appropriate command to install docker. Let’s verify that the installation was successful.
Run the following command:

sudo docker --version 

docker version signifying a successful installation ✅


<img width="649" alt="Screenshot 2023-05-17 at 07 51 19" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/9ae1a1ff-9375-4374-8156-42a5759b783f">

Step 5: Install Docker Compose on the instance

Docker compose is a configuration tool use to define, deploy and manage docker containers using a YAML file.
The powerful and efficient advantage of Docker compose is that it enables engineers and developers to effortlessly build containers and destroy containers using a single command, thus saving them lots of time and energy.
Run the following command:

sudo apt install docker-compose


<img width="694" alt="Screenshot 2023-05-17 at 07 52 03" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/2d35d743-00c3-4a78-b460-71d9aeec3cb7">


Step 6: Verify Docker compose installation

Run the following command:

sudo docker-compose --version

docker-compose version ✅

<img width="722" alt="Screenshot 2023-05-17 at 07 52 30" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/e519cfcb-db93-41a5-8557-cd8a2706b517">

Step 7: Create a New Directory for WordPress & Setup Docker Compose

We are going to create a new directory for WordPress. The Directory will contain our docker compose YAML file that will be use to contain all the necessary services needed to deploy WordPress.
Create directory running the command “mkdir wordpress”. Change directory “cd wordpress”.

<img width="681" alt="Screenshot 2023-05-17 at 07 55 34" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/0f7fe884-1ffe-4ce5-9e18-cb3934f1a34d">

On the CLI run the command “nano docker-compose.yml” and paste the following code into the YAML file, save and close the file.

Step 8: Start the WordPress Container

Run the following command to start the WordPress Container:

sudo docker-compose up -d


green is good ✅


<img width="735" alt="Screenshot 2023-05-17 at 07 55 51" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/b9246c78-217e-48d8-811e-f19bc90974df">


<img width="700" alt="Screenshot 2023-05-17 at 07 56 33" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/ce7e7868-9cf4-498a-94c5-e5a91b4ae20a">

Step 9: Access The WordPress Site

Navigate back to the instance console, copy and paste your instance public IP address into your web browser address bar. You should see the setup window for WordPress.

You should see the WordPress installation screen. You can now follow the prompts to complete the installation.

Follow the prompts to complete the installation

<img width="1272" alt="Screenshot 2023-05-17 at 07 57 22" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/ea5e2a79-e04a-4775-a069-9f0951f13b64">

<img width="1241" alt="Screenshot 2023-05-17 at 07 57 41" src="https://github.com/Mamiololo01/Wordpress_website_AWS_Docker/assets/67044030/a5b6451c-c8ba-485e-88d2-cd08b5bf92f0">



Congratulations! You have successfully deployed a WordPress website on AWS using Docker! Be sure to delete all the resources needed to complete this project!!

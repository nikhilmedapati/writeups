# Amazon Web Services (AWS)

## 1. Create a free account

- Go to https://aws.amazon.com/.


- Sign in, if you already have an account.


- Otherwise, create an account by following the steps that include giving your personal details, getting your mobile number verified and adding a payment option, 


- Once logged in, you will see the AWS console like below:

![Screenshot from 2017-10-15 22-21-38](/home/nikhil/Pictures/Screenshot from 2017-10-15 22-21-38.png)



## 2. Use Amazon Simple Storage Service (Amazon S3) to store digital files on AWS

- Go to the site https://s3.console.aws.amazon.com and sign in to console.

- Once done, you will see the console showing you your buckets. Buckets are how the files are stored after they are uploaded on the S3. In this case, there aren't any buckets like shown in the image below.

  ![Screenshot from 2017-10-16 03-37-59](/home/nikhil/Pictures/Screenshot from 2017-10-16 03-37-59.png)


- You'll see a button saying "Create bucket". Click on it to create your first bucket.

- There are 4 tabs where options have to be selected to proceed with creating a bucket.

  - [x] **Name and region:** You'll be asked to choose a unique DNS name, that will be the primary part of your URL, after the file is hosted on S3. Also, you will be asked to enter other details like the region
  - [x] **Set properties:** You are free to explore the options here. But, I suggest lets leave the defaults as they are.
  - [x] **Set permissions:** You can choose to make the file public or add other users to have specific read or write permissions in this tab. Since we will be dealing with making a file public in the next section, lets leave the defaults here also.
  - [x] **Review:** We will be shown a review of the options we have chosen for the new bucket and we can choose to edit any of them or move forward.

- Once done, you are done creating a new bucket.

- Now, we can upload the files to S3. Click on a bucket you have created to navigate into it. You will have options to create a new folder of upload files directory.

- I am choosing to create a new folder and then upload files into it now.

  ![Screenshot from 2017-10-16 03-48-35](/home/nikhil/Pictures/Screenshot from 2017-10-16 03-48-35.png)


- Now that "demo-folder" has been created, move ahead and upload a file.
- Here are also, you will come across the 4 tabs as discussed previously. Just let the defaults stay and proceed to upload.
- You can see the uploaded files clearly. We are done with this step.

## 3. Make the file public (i.e. give URL)

- Just navigate to the file you want to make public. Click on it to show options as shown below.

![Screenshot from 2017-10-16 03-53-39](/home/nikhil/Pictures/Screenshot from 2017-10-16 03-53-39.png)

- Just click on the option "Make public" and the file is public. Just copy the link available below after making the file public and you just got the URL of the file.
- If you want to make a folder or a bucket public, just right click on them and select "make public". You can get the URL for the files later either by right-clicking them or going to the "overview" tab shown above. This can also be applied to make individual files public.

## 4. View a file stored on AWS (using web browser)

- Just paste the URL you just copied and paste into a browser. You will be able to view the file.
- Someone else who opens this URL remotely can view the file as well as download it.

## 5. Make a file private

- For example, once a file has been made public, if you want to remove access to it, you can do that just by changing the permissions of the files.
- Just go to the "Permissions" tab as shown in the image.

![Screenshot from 2017-10-16 03-53-39](/home/nikhil/Pictures/Screenshot from 2017-10-16 03-53-39.png)

- Then go to the section "Public access" and remove the reading permissions to "Everyone" as shown below.

![Screenshot from 2017-10-16 04-01-32](/home/nikhil/Pictures/Screenshot from 2017-10-16 04-01-32.png)

- Just uncheck on "Read object" access to "Everyone" and the file is private. 
- Try accessing the URL you opened previously. You probably will get an xml file saying that access is denied.

## 6. Delete a file (& bucket)

- Deleting files, folders and buckets is pretty easy on S3.
- Just right-click on the file or folder or bucket you want to delete, enter the confirmation if you are deleting or emptying a bucket and it is deleted.

## 7. Run a virtual Server on Amazon Elastic cloud compute (EC2)

- Go to https://aws.amazon.com/ec2/ and sign in to the console
- Once done, click on "Launch Instance" as shown in the image below.

![Screenshot from 2017-10-16 04-06-44](/home/nikhil/Pictures/Screenshot from 2017-10-16 04-06-44.png)

- Then, choose the operating system of the server you are launching now.
- Since we are on free trial, choose an operating system that is free-tier available. I am choosing Ubuntu 14.04 server here.
- Select the purpose of the instance, again, choosing "General purpose" for free tier.
- You can directly proceed to launching the instance, leaving the default settings.
- You will be asked for a key pair before the instance is launched. You may choose to use an existing one or create a new one. 
- This key pair will be needed to access the instance remotely using a service like Secure Shell(SSH)
- Download the key pair by giving it a name and you are good to launch the instance.
- Now that the instance is up and running, lets proceed to the next step of connecting to the machine.

## 8. Connect to virtual server (using SSH, like Java SSH client)

- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html#ec2-connect-to-instance-linux
- The above link is an excellent guide to connecting to the launched instance.

![Screenshot from 2017-10-19 16-02-43](/home/nikhil/Pictures/Screenshot from 2017-10-19 16-02-43.png)

- Make sure all inbound traffic is allowed.
- Click on "Connect" as shown in the above image after the instance is launched.
- You can see steps clearly that enable you to connect to the instance remotely.
- Use "ssh" to connect using the .pem file you have downloaded.
- If everything goes fine, you will get connected to your instance. If things aren't working out, go to the following link https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesConnecting.html

## 9. Terminate a virtual server

- After you connect to the instance using ssh from your terminal, the next step is to terminate the running instance.

- The following reference will be very helpful.

  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html#ec2-clean-up-your-instance

- You just have to navigate to the list of page with list of instances in EC2 dashboard, select an instance, right click on it to view the actions menu, hover over "instance state" and click on "terminate".

- That's all. The selected instance will be terminated.

## 10. Static website: Deploy a static website using Amazon S3

- Just move the following URL

  https://console.aws.amazon.com/quickstart-website/hom

- You can either choose to host the example website provided by AWS or upload your own code.

- It usually takes a little time to configure the CDN(Content Delivery Network) in which the source code of our website is uploaded to different servers, so that it can be delivered efficiently.

- The whole source code is actually uploaded to S3.

- So, you can upload your own code into a new bucket on S3, allow it for website hosting. 

- You'll be done.
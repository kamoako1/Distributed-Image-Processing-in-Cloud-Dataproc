# Distributed-Image-Processing-in-Cloud-Dataproc
With the integration of Vision API for image recognition

Project functionalities include:
  -Creating a managed Cloud Dataproc cluster with Apache Spark pre-installed
  -Building and running jobs that use external packages that aren't already installed on cluster
  
 # First Step: Create a development machine in Compute Engine
 Using Google Cloud Platform, create a Virtual Machine (VM) instance
 # Second Step: Install necessary software
 In this specific project, I am using sbt, an open source build tool. 
 With sbt, I will build the JAR for the job I'm submitting to the Cloud Dataproc cluster. 
 My job for this project is to detect faces in a set of image files stored in a Google Cloud Storage (GCS) bucket that I will create. Then,  write out image files with the faces outlined to the same Cloud storage bucket.
 This JAR contains:
  -The program needed to run my job.
  -Required packages to run my job.
  # Third step: Create a GCS bucket and collect images
  The aforemented bucket is created at this step. After building the feature detector files, I create a GCS bucket and add preferable sample images. For this project, I used the sample images provided in Qwiklabs along with a picture of a family in the city. I chose this additional picture to further explore the intricacies of Distributed Image Processing and recognition in regard to Sentiment.
  # Fourth step: Create a Cloud Dataproc cluster
  Following commands in the SSH window of my VM instance to name my cluster and set the MYCLUSTER variable.
  # Fifth step: Submit your job to Cloud Dataproc
  The job I am running is a facial detector, so I will use the haar classifier, a XML file that is used to describe features that the     program will detect.
  As input to the Feature detector, use the set of images I uploaded into the imgs directory in my GCS bucket.
  # Sixth step: Monitor the job
  Now on the Google Cloud Platform in the Navigation menu > Dataproc > Jobs you can check the status of your job to see if distribution was successful. Along with JOB ID, Cluster, Region, Type, Start time, and Elapsed Time.
  # Seventh step: Locate your Bucket
  On the Google Cloud Platform  in the Navigation menu > Storage you can locate your bucket you created. In the out directory, download all images in your bucket. They will download onto your local computer and you can save them anywhere you would like. File name should resemble something like "out_{name of image file}"
  # Eigth Step: Vision API
  On the google Vision API website, you can upload images that were downloaded from your bucket. Once you upload, you can quickly see   results of the image detection! With such sophisticated machine learning algorithms, you can see several different results. 
  
![The first picture I chose was a dance picture. All the dancers looked happy and excited to be in class and the facial detector was great at accurately indentifying that. It detected that sentiment: happiness  was highly likely with 96% confidence. I was also curious to see if they would be able to decipher ballet attire in the image which it most certainly did, so that was fascinating to see. ](https://i.ibb.co/8XGv4ZN/ballet-Results1.png)

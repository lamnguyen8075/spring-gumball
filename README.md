# CMPE 172 - Lab #10 - DevOps CI/CD Notes

### Reflection: 
In this project, I really enjoy learning how to create the CI/CD pipeline to build the code quickly using Github Action. In the past, I worked as a SWE Intern at the company usingg Bamboo Continuous and Deployment Build, I saw lots of policy and test cases that my code had to ran through everytime I pushed my code. However, I didn't really understand how did they set up these system.. Finally, until today! After finish this assignment, I learnt from how to configuring the yaml file for both the Building JAVA with Gradle and Building with GKE. One of the difficulty was the region for the cluster, the given regiion on Canvas didn't have enough resources so I had to create a couple of cluster with different region and finally I found the us-west4-c is working. It was timeconsuming because everytime creating the cluster, It tok quite amount of time... But I figured it out myself by reading the error note and researched on Google to find the solution for my issue. 

### Part 1 CI Workflow:
#### Description: In this project, I will create the workflow performing the CI using Gumball project with gradle building tool. Everytime I trigger the commit to be built and test the failure on the default branch. The goal is to make sure the code in the repos are always quality and error-free. 

- Gradle build processing new push from local environmnet 
![Screen Shot 2022-11-28 at 3 27 31 PM](https://user-images.githubusercontent.com/48584294/204402119-8b054cbf-3f51-4101-9284-5ebc32cd9537.png)
![Screen Shot 2022-11-28 at 3 27 45 PM](https://user-images.githubusercontent.com/48584294/204402144-9985ad5c-5d0d-4f9d-b9cd-49aa889cdcf8.png)
![Screen Shot 2022-11-28 at 3 27 52 PM](https://user-images.githubusercontent.com/48584294/204402163-788360be-ecf2-4eb4-9482-0c2cf5aa58c0.png)
![Screen Shot 2022-11-28 at 3 28 03 PM](https://user-images.githubusercontent.com/48584294/204402177-132342bd-f97b-4fac-83ad-302fe79bc54a.png)
![Screen Shot 2022-11-28 at 3 28 15 PM](https://user-images.githubusercontent.com/48584294/204402206-333d7cfc-a5c0-46ac-bd3c-4599193cdb41.png)

- Gradle build output from Github Action
![Screen Shot 2022-11-28 at 3 28 27 PM](https://user-images.githubusercontent.com/48584294/204402228-348a10b3-344b-4237-abda-e8a7056f3ac0.png)


### Part 2 Workflow GKE: 
#### Description: In the second part, I create the container for the application to push on the Google Container Registry to deploy on Google Kubernetes Engine and deploy the application on GKE using Load balancer with 2 pods. 

- My cluster is up and running 
![Screen Shot 2022-11-28 at 3 02 18 PM](https://user-images.githubusercontent.com/48584294/204399014-7d16c9a7-62a0-4440-90bc-994b9a926c2e.png)

- Update the configuration on google.yaml file
![Screen Shot 2022-11-28 at 3 02 54 PM](https://user-images.githubusercontent.com/48584294/204399089-528b9773-8b9f-49ad-8c34-31af2c1356bf.png)

- Adding service accounts
![Screen Shot 2022-11-28 at 3 04 55 PM](https://user-images.githubusercontent.com/48584294/204399349-f15cd5fb-476f-4a63-96c3-f297b8a00a04.png)

- Creating Key for the new service account
![Screen Shot 2022-11-28 at 3 05 27 PM](https://user-images.githubusercontent.com/48584294/204399402-b157ed5d-72b0-4ceb-8343-d0f0f4bc0410.png)

- Update the Git Secrets
![Screen Shot 2022-11-28 at 3 04 12 PM](https://user-images.githubusercontent.com/48584294/204399258-1c01fb62-5ee9-45fe-b319-a3f859be57ae.png)

- Grant permission to Kubernetes Engine Developer and Storage Admin
![Screen Shot 2022-11-28 at 3 07 33 PM](https://user-images.githubusercontent.com/48584294/204399627-563cd7c2-0f75-4e06-a309-97af0b7c3b56.png)

- Trigger CD pipeline by creating a new release
![Screen Shot 2022-11-28 at 3 08 37 PM](https://user-images.githubusercontent.com/48584294/204399764-79a139be-d219-4890-8c65-fffad3da8024.png)

- Output of the deployment
![Screen Shot 2022-11-28 at 3 09 04 PM](https://user-images.githubusercontent.com/48584294/204399826-24a1e76d-8ee6-4abd-9535-f17c16ac029a.png)

- GKE - Workload is up and running
![Screen Shot 2022-11-28 at 3 13 31 PM](https://user-images.githubusercontent.com/48584294/204400375-17dc54f5-16bd-453e-9410-47565669f1d1.png)

- GKE - Service&Ingress
![Screen Shot 2022-11-28 at 3 15 20 PM](https://user-images.githubusercontent.com/48584294/204400584-5295bb70-ba9a-4930-a845-7b9405cb4a0c.png)

- GKE - Ingressing is running 
![Screen Shot 2022-11-28 at 3 30 06 PM](https://user-images.githubusercontent.com/48584294/204402426-7ad7a83b-7942-4e55-ba51-39d105568921.png)

- Deploymnet output from browser.. At this point the Docker image is stored in the registry of Google Kubernetes
![Screen Shot 2022-11-28 at 3 30 33 PM](https://user-images.githubusercontent.com/48584294/204402475-6ae84d1f-b53a-41c0-8dde-a11c6a3a20e8.png)






















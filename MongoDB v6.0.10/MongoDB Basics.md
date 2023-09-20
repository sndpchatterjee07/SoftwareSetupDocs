# MongoDB Basics

## Connect to a Deployment

- **Connect to a Local Deployment on the Default Port**

   To connect to a MongoDB deployment running on localhost with default port 27017, run `mongosh` without any options which is equivalent to `mongosh "mongodb://localhost:27017"`


   ![1](https://github.com/sndpchatterjee07/SoftwareSetupDocs/assets/3818950/afda3aa4-a58b-493d-b425-090235dddda1)



 
- **Connect to a Cloud Deployment on [MongoDB Cloud](https://cloud.mongodb.com/)**

   `mongosh "mongodb+srv://my-default-cluster.nopctvg.mongodb.net/" --apiVersion 1 --username sandeepc`

   ![Screenshot from 2023-09-21 00-00-39](https://github.com/sndpchatterjee07/SoftwareSetupDocs/assets/3818950/c76f9481-ad99-4c0c-8c6f-fdb3a9c4b734)


  ![Screenshot from 2023-09-21 00-03-27](https://github.com/sndpchatterjee07/SoftwareSetupDocs/assets/3818950/1cf83915-3740-4c15-8725-6c7753c84f20)

   









**References**

1. [MongoDB Docs](https://www.mongodb.com/docs/v6.0/tutorial/manage-users-and-roles/).

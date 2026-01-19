### 1. Create an IAM Role for SageMaker

Go to the IAM Console: 
1. On the left sidebar, click Roles → Create role
2. Choose Trusted entity type: Select AWS service → Choose Use case: Select SageMaker
<img width="1583" height="826" alt="image" src="https://github.com/user-attachments/assets/5f03b466-ac31-457f-9e50-b38a43a6d730" />
3. Click Next, In the permissions list, attach the `AmazonSageMakerFullAccess` policy
4. Click Next → Name it something like: `SageMakerCybersecurityRole`
<img width="1144" height="431" alt="image" src="https://github.com/user-attachments/assets/4d372d74-bf3c-41ca-b314-b6d3b8d4390b" />
5. Click Create Role
6. Add S3 Permissions (After Role Creation)
7. From the IAM console, find your newly created role
8. Click on the role → Go to Permissions tab- Click Add permissions → Attach policies
9. Search and attach AmazonS3FullAccess
<img width="1178" height="324" alt="image" src="https://github.com/user-attachments/assets/b1b6dc8b-4d9a-440b-abab-accf9e7f3dcf" />

Note: For some reason, AWS doesn't allow attaching AmazonS3FullAccess during the initial creation for SageMaker roles. You'll need to add it manually afterward.

### 2. Public Dataset: 
You need real-world data for threat detection. We'll use a public dataset from UNSW-NB15, which contains normal and malicious network activities.

Dataset: UNSW-NB15
For simplicity, we’ll use a cleaned CSV version of the dataset:
* Download: [UNSW_NB15_training-set.csv](https://drive.google.com/file/d/1Htj29YYCVHtcXFuhHy1YeFnObEv7Q3Ma/view?usp=sharing)
* Upload to S3: Go to Amazon S3 → Click Create Bucket (name it something like security-ml-data-twy)
* Note: S3 bucket names must be globally unique. Use a variation like security-ml-data-yourname.


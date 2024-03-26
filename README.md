## 👉 aws-pipeline-demo

Like production based pipeline with codecommit, integration, build and test, Quality check, Code deploy, monitoring.
for that configuration we have used devops tools as.
1. Git
2. Jenkins
3. mvn,npm
4. Sonarqube
5. Docker
6. trivy
7. Kubernetes
8. Argocd
9. Hashi Corp Vault
10. Prometheus and Grafana
11. Terraform


Similarly, we are going to deploy same functionality pipeline for source code but with AWS resources on cloud platform.Here we need only AWS account and source code.

🎯 CI/CD pipeline on AWS -Part-1

➡️ CodeCommit

 ✍️ Task-1:  Set up a code repository on CodeCommit and clone it on your local.
 
 ✍️ Task-2: You need to setup Git Credentials in your AWS IAM.
 
 ✍️ Task-3: Add a new file from local and commit to your local branch
 
 ✍️ Task-4: Push the local changes to CodeCommit repository.


🎯 CI/CD pipeline on AWS -Part-2

➡️ CodeBuild

✍️ Task-1: Push source code to repo in code commit and read about the Buildspec file for Codebuild.

✍️ Task-2: Add buildspec.yaml file to CodeCommit Repository and complete the build process.

✍️ Task-3: Store artifact into S3 bucket

🎯 CI/CD pipeline on AWS -Part-3

➡️ CodeDeploy

✍️ Task-1: Read about Appspec.yaml file for CodeDeploy.

✍️ Task-2: Add appspec.yaml file to CodeCommit Repository and complete the deployment process.


🎯 CI/CD pipeline on AWS -Part-4

➡️ CodePipeline

✍️ Task-1: Create a Deployment group of EC2 Instance.

✍️ Task-2: Install code deploy agent on EC2

✍️ Task-3: Finally in full view create a CodePipeline that gets the code from CodeCommit, Builds the code using CodeBuild and deploys it to a Deployment Group.

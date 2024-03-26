Task-01 :
Read about the Buildspec file for Codebuild.

A Buildspec file is a YAML file that defines the build process for your CodeBuild project. It contains a series of commands that CodeBuild will execute to build and package your application.

Create a simple index.html file in CodeCommit Repository.



you have to build the index.html using nginx server

Create a code commit repository
![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/17114535971602120865382832364647.jpg)

Copy clone HTTPS url
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/17114536042676415166975994591861.jpg)

In git bash, clone the repository to your local machine using the git clone command.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/171145361164477586233821721.jpg)


Inside code commit repository create a index.html file

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/1711453619079238138071737875581.jpg)

Save the file and commit the changes to the repository using the git add and git commit commands.
```
git add <file-name>
```
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/17114536252161975241423392912687.jpg)
```
git commit -m "commit message"
```
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/1711453631516611936119564807955.jpg)

Push the changes to the repository using the git push command.
```
git push origin master
```
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/1711453641651706647128211171579.jpg)

You have a simple index.html file in your CodeCommit repository

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part-2/17114536478216404259542343031508.jpg)

Task-02 :
Add buildspec.yaml file to CodeCommit Repository and complete the build process.

Create a Buildspec file to build the file using an nginx server.


buildspec.yml file


Here’s what each step of the build does:

version: 0.2 specifies the version of the Buildspec syntax we’re using.
phases contains the build phases for our project.
install: Installs nginx on the build environment using the apt-get package manager.
build: Copies the index.html file to the default web root directory for nginx.
post_build: Performs any additional configuration for nginx, if necessary.
artifacts: Specifies the location of the index.html file to be included in the build artifact.
Save the file and commit the changes to the repository using the git add and git commit commands.



Push the changes to the code commit repository


You have a buildspec.yml and index.html file in your CodeCommit repository


Create build project:

Go to the CodeBuild service. Click the “Create build project” button.


Fill in the details of your build project, including the project name, source provider (CodeCommit), repository, and branch.


In source section, select source provider AWS CodeCommit, select Repository that you created earlier and select branch master.


In Environment section, choose operating system, runtime ad image.


Create a new service role and Under the “Buildspec” section, choose “Use a buildspec file”.


Click “Create build project” to create your project.


Successfully build project is created.

Click the “Start build” button to start a new build.


Check status of build which is Succeeded.


All the phase steps also succeeded.


Task-03: To add artifacts to a CodeBuild project and store them in an S3 bucket.

Click on ‘edit’ and select ‘Artifacts’.


First create S3 bucket.



bucket is successfully created.


In Artifacts, select type Amazon S3 and select bucket name that you created in above step.


Click on ‘Update artifacts’.

After updating artifacts, click the “Start build” button again to start a new build.


After the build process is complete, the artifacts will be uploaded to the specified S3 bucket location.


In buildspec.yml file, inside artifacts phase there is a location of file which is /var/www/html/index.html. you can check that folders and index.html file inside s3 bucket.


Inside bucket, demo_build folder is created.





You can see inside /var/www/html there is index.html file.


Click on ‘index.html’ file, below you can see properties of file.

Click on ‘open’ on right-hand side.


Here is an output of index.html file.



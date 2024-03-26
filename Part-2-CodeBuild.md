## Task-01 :Read about the Buildspec file for Codebuild.

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

## Task-02 : Add buildspec.yaml file to CodeCommit Repository and complete the build process.

Create a Buildspec file to build the file using an nginx server.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547113774948188941236025751.jpg)

                         buildspec.yml file

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547186974312492558118580084.jpg)

Here’s what each step of the build does:

version: 0.2 specifies the version of the Buildspec syntax we’re using.
phases contains the build phases for our project.
install: Installs nginx on the build environment using the apt-get package manager.
build: Copies the index.html file to the default web root directory for nginx.
post_build: Performs any additional configuration for nginx, if necessary.
artifacts: Specifies the location of the index.html file to be included in the build artifact.
Save the file and commit the changes to the repository using the git add and git commit commands.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547375087975509721650166791.jpg)

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547449806745603523752259234.jpg)

Push the changes to the code commit repository

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547513715765125292468371737.jpg)

You have a buildspec.yml and index.html file in your CodeCommit repository

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547597344871825517468354745.jpg)


Create build project:

Go to the CodeBuild service. Click the “Create build project” button.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547666975096515312913245601.jpg)

Fill in the details of your build project, including the project name, source provider (CodeCommit), repository, and branch.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547746016564052602446272539.jpg)

In source section, select source provider AWS CodeCommit, select Repository that you created earlier and select branch master.

![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114547834228215013218076141643.jpg)
In Environment section, choose operating system, runtime ad image.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/1711454791854735279552924522528.jpg)

Create a new service role and Under the “Buildspec” section, choose “Use a buildspec file”.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114548138184815183047437606977.jpg)

Click “Create build project” to create your project.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114549504874873786184068356351.jpg)

Successfully build project is created.

Click the “Start build” button to start a new build.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114549583498154120108592828775.jpg)

Check status of build which is Succeeded.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114549678595426416492775699594.jpg)

All the phase steps also succeeded.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part2a/17114549764803355757526166297171.jpg)

## Task-03: To add artifacts to a CodeBuild project and store them in an S3 bucket.

Click on ‘edit’ and select ‘Artifacts’.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114597179895117820606390097284.jpg)

First create S3 bucket.

![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114597365322974699990926147804.jpg)


![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114597461496557616906468887337.jpg)

bucket is successfully created.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/1711459752677703525044964789288.jpg)

In Artifacts, select type Amazon S3 and select bucket name that you created in above step.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114597649366996475312311948823.jpg)

Click on ‘Update artifacts’.

After updating artifacts, click the “Start build” button again to start a new build.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114597815303335119744294689043.jpg)

After the build process is complete, the artifacts will be uploaded to the specified S3 bucket location.
![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598047511788987272489300104.jpg)

In buildspec.yml file, inside artifacts phase there is a location of file which is /var/www/html/index.html. you can check that folders and index.html file inside s3 bucket.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598157675536807795528312643.jpg)

Inside bucket, demo_build folder is created.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598475483579400588340177004.jpg)

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598571492708842167592669070.jpg)

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598647635284156661471633061.jpg)

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598777054465857032097117665.jpg)

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598884558451606303116800283.jpg)


You can see inside /var/www/html there is index.html file.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/17114598971827413964945174749052.jpg)

Click on ‘index.html’ file, below you can see properties of file.

Click on ‘open’ on right-hand side.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/Part2b/1711459905204134255873580672491.jpg)
Here is an output of index.html file.



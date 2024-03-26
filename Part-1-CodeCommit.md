## What is CodeCommit?

Overall, CodeCommit provides developers with a reliable and efficient way to manage their codebase and set up a CI/CD pipeline for their software development projects.


## Task-01 : Set up a code repository on CodeCommit and clone it on your local.


Log in to the AWS Management Console and navigate to CodeCommit.

Click on Create Repository.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114421333049127667631684455305.jpg)

Enter a name for your repository and click on ‘Create’
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114421472736142380584481669075.jpg)
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114421619747248613192802958925.jpg)


Repository is successfully created.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114421719164887670126854897603.jpg)

You need to setup Git Credentials in your AWS IAM.
Go to the IAM console
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114421814297370581318621414267.jpg)
Click on Users in the left-hand menu, and then click on your username.
Scroll down to the Security credentials section.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114421922654049310732604512426.jpg)

In ‘HTTPS Git credentials for AWS CodeCommit’ section, click on ‘Generate credentials’

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114422150461634421286555925973.jpg)
Click on the Download credentials button to download your Git credentials and click on ‘close’.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114422274747054284241599923289.jpg)
Git credentials is created.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114422484606893200580683051067.jpg)
Use those credentials in your local and then clone the repository from CodeCommit

In Code Commit, Go inside your repository that you created in above steps, in right-hand side click on ‘Clone URL’ and choose ‘Clone HTTPS’.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114422884498673032346891211904.jpg)
Open a terminal on your local machine.

Navigate to the directory where you want to clone the repository.

Run the following command:
```
git clone <your-codecommit-repo-clone-https-url>

```
You will be prompted to enter your Git credentials. Enter the username and password that you downloaded earlier.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114423006958393725100909271482.jpg)
You have now set up a CodeCommit repository and cloned it on your local machine using Git Credentials in AWS IAM.

![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/Part-1/17114423127588713896442539460599.jpg)

## Task-02 : Add a new file from local and commit to your local branch

Create a new file in the local repository directory.

![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520181045940416386530328758.jpg)

Check status using command 

```git status```

![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520280932298130353837620251.jpg)

Add the new file to your local branch using the following command:

```
git add <filename>
```
![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520362126277315065496932400.jpg)

Commit the changes to your local branch using the following command:
```
git commit -m "added new file"
```
![](
https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520427632978915340616696705.jpg)

Push the local changes to CodeCommit repository.

Push the changes from your local branch to the CodeCommit repository using the following command:
```
git push origin master
```
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520503233092122354037925053.jpg)
Verify that the changes have been pushed to the CodeCommit repository:

Go to the code commit repository that you created earlier, you should see the new file listed in the repository’s files.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520567878882558560591652366.jpg)

You can see content of the file.
![](https://github.com/smitwaman/aws-pipeline-demo/blob/main/images/images/17114520635432228890935110674166.jpg)




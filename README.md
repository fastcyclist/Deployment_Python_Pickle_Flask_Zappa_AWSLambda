# Deployment of Python (sklearn) model using Pickle, Flask, and Zappa to AWS Lambda
This is an example of deploying a sklearn ML model using [Pickle](https://docs.python.org/3.6/library/pickle.html), [Flask](https://flask.palletsprojects.com/en/1.1.x/), & [Zappa](https://github.com/Miserlou/Zappa) to [AWS Lambda](https://en.wikipedia.org/wiki/AWS_Lambda).

This was compilation of the following:
- [Saving Sklearn Model to Pickle](https://medium.com/@pemagrg/saving-sklearn-model-to-pickle-595da291ec1c)
- [Deploying a Scikit-Learn Model on AWS Using SKLearn Estimators, Local Jupyter Notebooks, and the Terminal](https://towardsdatascience.com/deploying-a-scikit-learn-model-on-aws-using-sklearn-estimators-local-jupyter-notebooks-and-the-d94396589498)
- [How to deploy a Serverless Machine Learning Microservice with AWS Lambda, AWS API Gateway and scikit-learn](https://medium.com/@patrickmichelberger/how-to-deploy-a-serverless-machine-learning-microservice-with-aws-lambda-aws-api-gateway-and-d5b8cbead846)
- [What are the different use cases of joblib versus pickle?](https://stackoverflow.com/questions/12615525/what-are-the-different-use-cases-of-joblib-versus-pickle)

## I do most of my work on a [Linux](https://releases.ubuntu.com/18.04.5/) machine and connect to it via [SecureCRT](https://www.vandyke.com/products/securecrt/index.html) from a Windows machine.
If your development environment is different (i.e., MacOS or Windows only), you'll need a little bit more [digging](https://www.google.com).

## Step 1. Open an AWS account (it's free, for the most part)
Go to [AWS](https://aws.amazon.com/) and open an account if you don't have one already.<br />
It will ask your credit card information in case you go over the [Free Tier](https://aws.amazon.com/free/) limit, but as you can see here, the [Free Tier](https://aws.amazon.com/free/) provides plenty.

![Free Tier](https://github.com/fastcyclist/Deployment_Python_Pickle_Flask_Zappa_AWSLambda/blob/master/AWS_FreeTier.PNG)


## Step 2. [Download AWS command-line interface (CLI)](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)
Try <code>aws --version</code> to see if you have it already.
If you have it, it will return something similar to this:<br />
<code>aws-cli/2.0.46 Python/3.7.3 Linux/4.15.0-112-generic exe/x86_64.ubuntu.18</code>

I'm using AWS CLI [version 2 for Linux](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html).


## Step 3. [Configure](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) your aws (on Linux) with correct credentials.
This is necessary for later steps. When you deploy your model using Zappa, it won't ask you to type in credentials. It will use whatever is already configured and saved.

An important thing to remember is that you don't want to use your root credentials. You need to creat a new user and a user group to separate day-to-day activities from the root account.
Think of this as not using <code>sudo</code> all the time everytime on your Linux.

While working on this section, I learned the AWS documentations were pretty confusing. This is how I did it.<br />
<ol>
<li>[Creating your first IAM admin user and group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html) <b>Note</b>: make sure you save the Access Key ID and Secret Access Key. They are like your ID and PW to interact with AWS. If you forgot to download/save it, delete the Access keys and create a new one.</li>
<li>[Configuration and credential file settings](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)<br />
<b>tldr</b>: type <code>aws configure</code>. When it asks <code>AWS Access Key ID [None]:</code> and <code>AWS Secret Access Key [None]:</code><br />
supply what you saved in the first step. I set my <code>Default region name [None]: us-east-2</code> and <code>Default output format [None]: json</code>.</li>
<li>3. Type <code>aws configure list</code>. If it returns something other than <code><not set></code>, you're good to go.</li>
</ol>









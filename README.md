# Deployment of Python (sklearn) model using Pickle, Flask, and Zappa to AWS Lambda
This is an example of deploying a sklearn ML model using [Pickle](https://docs.python.org/3.6/library/pickle.html), [Flask](https://flask.palletsprojects.com/en/1.1.x/), & [Zappa](https://github.com/Miserlou/Zappa) to [AWS Lambda](https://en.wikipedia.org/wiki/AWS_Lambda).

This was compilation of the following:
- [Saving Sklearn Model to Pickle](https://medium.com/@pemagrg/saving-sklearn-model-to-pickle-595da291ec1c)
- [Deploying a Scikit-Learn Model on AWS Using SKLearn Estimators, Local Jupyter Notebooks, and the Terminal](https://towardsdatascience.com/deploying-a-scikit-learn-model-on-aws-using-sklearn-estimators-local-jupyter-notebooks-and-the-d94396589498)
- [How to deploy a Serverless Machine Learning Microservice with AWS Lambda, AWS API Gateway and scikit-learn](https://medium.com/@patrickmichelberger/how-to-deploy-a-serverless-machine-learning-microservice-with-aws-lambda-aws-api-gateway-and-d5b8cbead846)
- [What are the different use cases of joblib versus pickle?](https://stackoverflow.com/questions/12615525/what-are-the-different-use-cases-of-joblib-versus-pickle)

## I do most of my work on a Linux machine and connect to it via SecureCRT from a Windows machine.
If your development environment is different (i.e., MacOS or Windows only), you'll need a little bit more [digging](https://www.google.com).

# Step 1. Open an AWS account (it's free, for the most part)
Go to [AWS](https://aws.amazon.com/) and open an account if you don't have one already.
It will ask your credit card information in case you go over the [Free Tier](https://aws.amazon.com/free/) limit, but as you can see here, the [Free Tier](https://aws.amazon.com/free/) provides plenty.
![Free Tier](AWS_FreeTier.png)













**Node.js project to AWS Lambda**

This project demonstrates how to deploy a large-scale Node.js application to AWS Lambda by separating business logic from dependencies.

**Deployed URL**: https://4wke5ccrlp3hvppkowzjcwv7dy0qomuu.lambda-url.eu-north-1.on.aws

**Deployment Steps**

**Step 1:** Prepare Dependencies as a Layer

Create a folder for dependencies:

mkdir nodejs
cd nodejs
npm install <your-dependencies>
cd ..
zip -r nodejs.zip nodejs

Upload nodejs.zip as a Lambda Layer in AWS Console.


**Step 2:** Prepare Business Logic for Lambda

Keep only your application logic files (without node_modules).

Zip them for deployment:

zip -r function.zip .

Deploy function.zip to your Lambda function.


**Step 3:** Attach Layer to Lambda

In AWS Console, go to your Lambda function → Layers → Add the previously created layer.

Then Running the Project

Once deployed, trigger your Lambda via API Gateway, S3 events, or manual test events.


**Changes Done**


* Changed app.js to *index.js*
* To make this Serverless used *serverless-http* package
* Connected to personal mongodb and Redis Clients


**Current Request Timeout**: 2sec

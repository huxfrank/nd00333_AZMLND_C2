# Operationalizing Machine Learning - Bank Marketing

# Table of Contents
1. [Overview](#overview)
2. [Architectural Diagram](#architecture)
3. [Future Work](#future-work)
4. [Key Steps](#screenshots)
	1. [MLStudio](#ml-studio)
	2. [Jupyter Notebook](#jupyter)
5. [Screencast Link](#screencast)
6. [Standout Suggestions](#standsugg)


## Overview <a name="overview" />
This project is a part of the Udacity Azure ML Nanodegree.
The main goal of this project was to demonstrate the capabilities of Azure ML Studio regarding authentication, deployment and endpoint consumption.
In this project, we build and deploy a model in two different ways: via the Azure ML Studio and via the Azure Python SDK. There is an emphasis on proper security and authentication as well as making sure that as an endpoint is deployed,
it can be properly monitored with sufficient and meaningful logs. The model created is then deployed and consumed using Swagger, taking JSON payloads and returning appropriate results.
Finally, a screencast showcasing the entire process of the working ML application was made.


## Architectural Diagram <a name="architecture" />
<img src="architecture.JPG"
     alt="System Architecture" />
	 
## Future Work <a name="future-work" />


## Key Steps <a name="screenshots" />
**ML Studio Steps** <a name="ml-studio" />

	 The first step was to upload the dataset and register it to Azure ML Studio so it is available for use.
<img src="Screenshots/dataset.PNG"
     alt="Dataset" />

	 The next step was to create a AutoML run using the bankmarketing dataset in order to find the best model so we can deploy it.
<img src="Screenshots/run-complete.PNG"
     alt="Run Complete" />
	 
	 This is the best model we found. It's a VotingEnsemble comprised of XGBoostClassifier and LightGBM with accuracy 0.91927.
<img src="Screenshots/bestmodel1.PNG"
     alt="Best Model" />	 
<img src="Screenshots/bestmodel2.PNG"
     alt="Best Model cont." />
	 
	 Once we had our best model, we deployed our model with authentication and application insights enabled so we would be able to create and monitor our endpoint via logging.
<img src="Screenshots/appinsight-true.PNG"
     alt="Application Insights Enabled" />
	 
	 This is an example of the logging we would see as different requests hit our endpoint.
<img src="Screenshots/logs2.PNG"
     alt="Logs" />
	
	 Once the endpoint was deployed and running, this is the JSON API that was created by Swagger. The following screenshots show the different HTTP requests and responses available.
<img src="Screenshots/swagger1.PNG"
     alt="Swagger" />	 
<img src="Screenshots/swagger2.PNG"
     alt="Swagger" />
<img src="Screenshots/swagger3.PNG"
     alt="Swagger" />
	 
	 This is the result of the Apache Benchmark. You can see when we used the endpoint.py to pass it JSON objects and the results returned ie. yes/no. It also gives metrics on connection
times and how long it took for requests to be served.
<img src="Screenshots/benchmark1.PNG"
     alt="Benchmark" />
<img src="Screenshots/benchmark2.PNG"
     alt="Benchmark cont." />
	 
	 
**Jupyter Notebook Steps** <a name="jupyter" />
<img src="Screenshots/Notebook/notebook-dataset.PNG"
     alt="Notebook Dataset" />
	 
	 
<img src="Screenshots/Notebook/pipeline.PNG"
     alt="Pipeline" />
	 
	 
<img src="Screenshots/Notebook/pipeline-run.PNG"
     alt="Pipeline Run" />	

	 
<img src="Screenshots/Notebook/pipeline-running.PNG"
     alt="Pipeline Running" />
	 
	 
<img src="Screenshots/Notebook/pipeline-endpoint.PNG"
     alt="Pipeline Endpoint" />
	 
	 
<img src="Screenshots/Notebook/pipeline-publishedoverview.PNG"
     alt="Pipeline Published Overview" />
	 
	 
<img src="Screenshots/Notebook/notebook-details.PNG"
     alt="Notebook Details" />
	 
## Screencast Link <a name="screencast" />
**https://youtu.be/LDm8n7IbfDA**

## Standout Suggestions <a name="standsugg" />
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.

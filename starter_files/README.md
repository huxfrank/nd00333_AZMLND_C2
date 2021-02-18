# Operationalizing Machine Learning - Bank Marketing

# Table of Contents
1. [Overview](#overview)
2. [Architectural Diagram](#architecture)
3. [Future Work](#future-work)
4. [Key Steps](#screenshots)
	1. [MLStudio](#ml-studio)
	2. [Jupyter Notebook](#jupyter)
5. [Screencast Link](#screencast)


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
Now that we have a working pipeline, pipeline endpoint, and AutoML endpoint, there are a few steps that can be taken to improve the project overall.
One possible avenue of improvement would be to set up dataset monitors that would trigger training of the model if the accuracy of it falls below a certain point or if the dataset it was trained on becomes obselete or outdated.

Another possible avenue of improvement is to flesh out a front end for the endpoints so that anyone seeking to use the model for their own purposes has an easy way to access it. This would include granting certain permissions to
anyone who wanted to use the model but not giving them full access to the model itself.

The model itself is not 100% accurate so further work could be done on tuning the hyperparameters to increase accuracy of the model itself. The confusion matrix below shows that it still gives false positives and false negatives
indicating that the model is not perfect and requires further fine tuning. Depending on the intended purpose for the model, perhaps this degree of accuracy is good enough but there is always room for improvement.

<img src="Screenshots/Notebook/confusionmatrix.PNG"
     alt="Matrix" />

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
	 
	 This is the result of running endpoint.py in the terminal.
<img src="Screenshots/endpoint_result.PNG"
     alt="Swagger" />	
	
	 Once the endpoint was deployed and running, this is the JSON API that was created by Swagger. The following screenshots show swagger running on localhost URLs as well as the different HTTP requests and responses available.
<img src="Screenshots/swagger-run.PNG"
     alt="Swagger" />	
<img src="Screenshots/swagger1.PNG"
     alt="Swagger" />	 
<img src="Screenshots/swagger2.PNG"
     alt="Swagger" />
<img src="Screenshots/swagger3.PNG"
     alt="Swagger" />
	 
	 This is the result of the Apache Benchmark. You can see when we used the endpoint.py to pass it JSON objects and the results returned ie. yes/no. It also gives metrics on connection times and how long it took for requests to be served.
<img src="Screenshots/benchmark1.PNG"
     alt="Benchmark" />
<img src="Screenshots/benchmark2.PNG"
     alt="Benchmark cont." />
	 
	 
**Jupyter Notebook Steps** <a name="jupyter" />

	 The notebook used the same dataset as the previous AutoML run, that's why there's only a single dataset registered.
<img src="Screenshots/Notebook/notebook-dataset.PNG"
     alt="Notebook Dataset" />
	 
	 This screenshot shows the two different pipeline runs. Run 56 is the notebook run that uses the same experiment as our AutoML run and Run 1 is the pipeline rerun triggered by hitting the REST API endpoint.
<img src="Screenshots/Notebook/pipeline.PNG"
     alt="Pipeline" />
	 
	 The next two screenshots show the triggered pipeline run.
<img src="Screenshots/Notebook/pipeline-run.PNG"
     alt="Pipeline Run" />	
<img src="Screenshots/Notebook/pipeline-running.PNG"
     alt="Pipeline Running" />
	 
	 This is the REST endpoint for our published pipeline.
<img src="Screenshots/Notebook/pipeline-endpoint.PNG"
     alt="Pipeline Endpoint" />
	 
	 This is the overview for our published pipeline.
<img src="Screenshots/Notebook/pipeline-publishedoverview.PNG"
     alt="Pipeline Published Overview" />
	 
	 This is the run details for the endpoint triggered run. As the RunDetails widget wasn't very verbose, I also included the execution summary.
<img src="Screenshots/Notebook/rundetails1.png"
     alt="Notebook Details" />
<img src="Screenshots/Notebook/rundetails2.png"
     alt="Notebook Details2" />
	 
	 I wanted to include the original pipeline run and best model compared to the triggered pipeline run and best model.
	 
	 Original Run
<img src="Screenshots/Notebook/extra3.PNG"
     alt="Original Run" />
<img src="Screenshots/Notebook/extra6.PNG"
     alt="Original Best Model" />
<img src="Screenshots/Notebook/original-bestmodel.PNG"
     alt="Original Best Model Details" />
	 
	 Triggered Run
<img src="Screenshots/Notebook/extra4.PNG"
     alt="Triggered Run" />
<img src="Screenshots/Notebook/extra5.PNG"
     alt="Triggered Best Model" />
<img src="Screenshots/Notebook/rerun-bestmodel.PNG"
     alt="Triggered Best Model Details" />
	 
	 The AUC_weighted is slightly better on the rerun and accuracy goes up slightly as well.
	 
## Screencast Link <a name="screencast" />
**https://youtu.be/9IxFIbo_TBw**


# Problem 5 - ML Cloud Platforms 15 points

In this question you will analyze different ML cloud platforms and compare their service offerings. In particular, you will consider ML cloud offerings from IBM, Google, Microsoft, and Amazon and compare them on the basis of following criteria:

1. Frameworks: DL framework(s) supported and their version. (4)
Here we are referring to machine learning platforms which have their own inbuilt images for different frameworks.
### Answer: 

- IBM 

  IBM WATSON is optimized for these frameworks and versions
TensorFlow 2.4, 2.1,  Spark 2.4, PMML 3.0 and 4.3, XGBoost 1.3
PyTorch 1.3.1, 1.7, and Keras(depriciated however) as well AutoAI

- Google cloud 

  Google cloud can host all versions according to their website
TensorFlow, pytorch, and SkLearn and autoML similar to IBM AutoAI

- Amazon

  On Amazon sagemaker website it says all images are "up to date". The supported offerings are: 
Hugging Face,
Chainer,
PyTorch,
MXNet,
TensorFlow, as well as Azure which is an automated ml pipeline like autoAI and AutoML
- Microsoft
  Microsoft uses ONXX runtime, but also utilizes the standard models of PyTorch 1.1, TensorFlow 2.4, LightGBM-XGboost 1.4, and SkLearn 1.0. Microsoft is the only to run on onnx runtime. Microsft Azure is there ML cloud offering. 

2. Compute units: type(s) of compute units offered, i.e., GPU types. (1)
### Answer: 

IMB: refered to as CUH, offers NVIDIA Tesla V100, NVIDIA Tesla K80
Google: NVIDIA K80, P100, P4, T4, V100, and A100
Microsoft:NVIDIA Tesla V100 NVIDIA Tesla P100 NVIDIA Tesla P40
Amazon: Tesla V100, Tesla A100, Tesla M60, T4, A10G

All platforms can do most deep learning jobs, specific GPU's and share in a cluster will help for specific tasks like computer vision orparallelized tasks

3. Model lifecycle management: tools supported to manage ML model lifecycle. (2)
### Answer: 

- IBM: 
The IBM Cloud supports the Collection, Organization, Analysis, and Infusion phases of AI Model Lifecycle Management. For this, IBM offers several software bundles named CloudPaks. These contain CloudPak for Data, CloudPak for Integration, CloudPak for Security, CloudPak for Watson AIOps, CloudPak for Business Automation, and CloudPak for Network Automation. CloudPak for Data can meet all lifecycle management requirements with tools like Watson Studios, but other CloudPaks can be used in concurrency. For example, CloudPak for Watson AIOps is a strong tool for providing and monitoring the health of the Kubernetes infrastructure keeping these lifecycle management services. Although these are IBM products, they offer multi-cloud services, suggesting they can be used to manage model lifecycle management on other cloud services such as the one below. 

- Google: 
Google GCP's Vertex AI together with the AI Platform has numerous model lifecycle management features. These contain training, testing, hyperparameter optimization, and hosting a model on the cloud, as well as pre/postprocessing for data. Hosting a model on GCP demands that the model be uploaded to a Cloud Storage bucket, a model resource to be created on the AI Platform, and a Cloud Storage path to the saved model be specified. Customble prediction routines are set up to determine how the model operates prediction requests. Google GCP supports both online forecast (HTTP requests) and batch prediction. GCP also offers APIs and tools such as Cloud Logging and Cloud Monitoring to monitor running jobs. AI Platform also has several interfaces for handling models and versions (a REST API, g-cloud ai-platform command-line tool, and Google Cloud console). 

- Microsoft: 
Microsoft Azure supports the train & test, package, validate, deploy, and monitor/retrain model management lifecycle. Azure Machine Learning has an MLOps framework to handle the ML lifecycle from data processing to deployment. Azure Machine Learning contains tools for customized pipeline construction, reusable software environments for replicating a project's software dependencies, and recording/storing/versioning a model in an Azure Cloud workspace to deploy, optimize, and analyze models. 

- Amazon:
 Amazon SageMaker is one of AWS's central ML platforms. SageMaker supports data preparation, training & tune, deploying, and monitoring functionalities. Tools include:

 SageMaker Data Wrangler for data cleaning and preparation;

 SageMaker Clarify for bias detection;

 SageMaker ML Lineage Tracking for artifact lineage tracking;

 SageMaker Model Registry for storing metadata on the model's lifecycle;

SageMaker Pipelines to streamline the automated ML pipeline process, and others. 

4. Monitoring: availability of application logs and resource (GPU, CPU, memory) usage monitoring data to the user. (2)
### Answer: 

Monitoring can be divided into three types:
Metrics – collecting numerical information from the application and platform. This may be a number that is calculated by the application (e.g., how many items are in a queue) or exposed by the platform (e.g., how much memory is the process consuming).
Logging – collecting textual information (e.g., an error message generated by the application).
Synthetic monitoring – sending an outer message to the application and analyzing the response to decide the component’s status (e.g., dispatching a ping to a server or simulating an total customer transaction).


IBM Monitoring: 

IBM offers a number of monitoring solutions for cloud platforms, including Application Performance Management (APM), Netcool Operations Insight (NOI), and Cloud Event Management (CEM). These solutions are designed to help organizations monitor and manage their cloud, on-premises, and hybrid applications and IT infrastructure.

APM is an intelligent monitoring solution that can watch, analyze, and manage a wide range of workloads, including cloud, on-premises, and hybrid applications and infrastructure/platforms. It provides visibility into the performance and health of your applications and infrastructure, helping you to identify and resolve potential issues before they impact your users.

NOI and CEM are event management and incident management solutions that can collect, correlate, and consolidate millions of events and alarms from your on- and off-premise environments. They help you leverage siloed monitoring systems and gather information and events from across your organization, providing a comprehensive view of your IT environment.

IBM Cloud also has a status console that displays the state of the IBM Cloud platform, services, and runtimes. This provides real-time information about the availability and performance of IBM Cloud, so you can quickly identify any potential issues and take appropriate action.

Google Monitoring:

Vertex AI exports metrics to Cloud Monitoring, and also shows some of these metrics in the Vertex AI Google Cloud console. You can use Cloud Monitoring to create dashboards and configure alerts based on these metrics, such as alerts for high prediction latency or other performance issues.

When you perform custom training with Vertex AI, you can monitor the resource usage of each training node, including CPU or GPU utilization, memory utilization, and network usage. This can help you understand how your training is using resources and identify any potential performance bottlenecks.

After you deploy a model to an endpoint, you can also monitor the performance and resource usage of the endpoint. This can help you understand how your model is responding to requests and identify any potential performance issues or other problems. You can track metrics such as traffic patterns, error rates, latency, and resource utilization to ensure that your model is consistently and predictably responding to requests. You can then use this information to make decisions about how to optimize your model's performance, such as redeploying your model with a different machine type to optimize for cost.

Micorsoft Monitoring:

Here are some specific examples of how Azure ML can be used for monitoring resources:
Monitor CPU and memory usage: Azure ML allows users to monitor the CPU and memory usage of their machine learning models in real-time. This can help organizations to identify bottlenecks and optimize their use of resources. For example, if a model is using too much memory, Azure ML can automatically scale up the number of resources (e.g. CPU cores) to improve performance.
Monitor network traffic: Azure ML can also be used to monitor the network traffic of machine learning models. This can help organizations to identify trends and patterns in network usage, and to optimize their network infrastructure accordingly. For example, if a model is generating a large amount of network traffic, Azure ML can help to identify the cause and suggest ways to reduce the traffic.
Monitor model performance: In addition to monitoring the resources used by machine learning models, Azure ML can also be used to monitor the performance of the models themselves. This can help organizations to identify models that are not performing well, and to take corrective action. For example, Azure ML can automatically retrain a model if it is not achieving the desired level of accuracy, or it can alert users if a model is not meeting its performance targets.


AWS Monitoring: 

Amazon SageMaker is a fully managed service for building, training, and deploying machine learning models. It provides an end-to-end solution for developing and deploying machine learning models, including tools for data preparation, model training and evaluation, and deployment. With SageMaker, you can quickly and easily build, train, and deploy ML models at any scale, and use SageMaker Model Monitor to continuously monitor the quality of your models in real time.

Model Monitor offers four different types of monitoring capabilities to detect and mitigate model drift in real time: data quality monitoring, model quality monitoring, model bias monitoring, and model explainability monitoring. These capabilities help you ensure that your models are performing well, without unwanted bias, and that the relative importance of feature attributions remains consistent over time. By monitoring the quality of your models in real time, you can quickly detect and mitigate any issues, ensuring that your models continue to deliver accurate and reliable results.

5. Visualization during training: performance metrics like accuracy and throughput (2)

- IBM: 
The IBM Cloud does offer several data visualization tools, including the ones you mentioned. The Data Refinery is a tool for preparing and cleaning data for analysis, Cognos Dashboard Embedded allows users to create and share dashboards with data visualizations, AutoAI is a tool that helps users rank and visualize model candidates, and SPSS Modeler is a tool for creating graphical models and visualizing data. These tools can be used in combination to help users analyze and understand their data, as well as build and evaluate machine learning models.

- Google: 
Training jobs on Google GCP can be monitored in several ways. One way is to use the Cloud Logging service, which allows users to view logs and monitor the status of their training jobs. Users can also use the gcloud command-line tool to request job details or stream logs in real time. Additionally, users can programmatically make requests to the training service to check the status of their jobs. These methods can help users track the progress of their training jobs and identify any issues that may arise.

- Microsoft: 
Microsoft Power BI is a popular tool for creating and sharing data visualizations on the Azure platform. Additionally, Azure's Machine Learning studio provides access to training job logs, which can be used to monitor the performance of machine learning models as they are being trained. Azure Machine Learning Integration also allows users to access model training information from external applications, such as Slingshot, which can be used to retrieve model training metrics. These tools can be used together to help users monitor and understand the performance of their machine learning models on Azure.

- Amazon: 
Amazon SageMaker provides several tools and features for visualizing and analyzing training data and metrics. SageMaker Experiments and SageMaker Debugger allow users to save training metrics to an Amazon S3 bucket for easy access and analysis. These metrics can then be visualized using SageMaker Studio, which provides a "go-to" interface for understanding the performance of machine learning models during training. SageMaker Studio allows users to track metrics such as accuracy and throughput in real time, giving them a clear view of how their models are performing. These tools can help users understand their training data and make informed decisions about how to improve their models.

6. Training job description: training job description file format. Show how the same training job is specified in different ML platforms. Identify similar fields in the training job file for the 4 ML platforms through an example. (4)

- IBM's Watson Machine Learning service allows users to define and train machine learning models using a YAML file with three main parts: model definition, training data, and training results. In the model definition section, users can specify the name, description, framework, and execution details of their model. In the training data section, users can specify the name, connection details, type, and source of the data that will be used to train the model. And in the training results section, users can specify the name, connection details, type, and source of the results that will be generated by the training process. This YAML file can be used to specify all of the details of a machine learning model and its training process, making it easy to replicate and share with others.

``` yaml
##### The ID of the project.
project_id: my-wml-project

##### The location of the project's resources.
location: us-south

##### The credentials to use for authenticating with IBM Watson Machine Learning.
credentials:
  api_key: my-api-key
  instance_id: my-instance-id

##### The details of the training job.
training_job:
  name: my-training-job
  algorithm:
    image: my-wml-project/my-algorithm:1.0
    mode: file
  role: my-wml-role
  input_data:
    channel: train
    data_source:
      cos_data_source:
        bucket: my-bucket
        file_path: train
  output_data:
    cos_output_path: my-bucket/output
  resource_config:
    machine_type: ml.m4.xlarge
    instance_count: 1
    volume_size_gb: 50
  hyperparameters:
    parameter_1: value_1
    parameter_2: value_2

```
-  Google Cloud also uses a YAML file to define and configure machine learning jobs. This file is typically named "config.yaml" and it contains various properties that specify the details of the job. Some of the properties that can be defined in a Google Cloud YAML file include the name of the job, the cluster configuration, the disk configuration, the training package, the module name, the region and job directory, the runtime and Python versions, the maximum wait time, and the service account that will be used to run the job. These properties can be used to configure and customize the behavior of a machine learning job on Google Cloud.

```yaml
##### The ID of the project.
project_id: my-gcp-project

##### The location of the project's resources.
location: us-central1

##### The credentials to use for authenticating with GCP.
credentials:
  client_id: my-client-id
  client_secret: my-client-secret
  refresh_token: my-refresh-token

##### The details of the training job.
training_job:
  name: my-training-job
  algorithm:
    image: gcr.io/my-project/my-algorithm:1.0
    mode: file
  role: my-gcp-role
  input_data:
    channel: train
    data_source:
      gcs_data_source:
        uri: gs://my-bucket/train
        data_type: prefix
  output_data:
    gcs_output_path: gs://my-bucket/output
  resource_config:
    machine_type: n1-standard-4
    instance_count: 1
    volume_size_gb: 50
  hyperparameters:
    parameter_1: value_1
    parameter_2: value_2

```

- Amazon instead uses JSON files. You can specify name, AlgorithmSpecification, hyperparameter, input/output/resource data config, EnableManagedSpotTraining, rolearn, StoppingCondition, environment, and retry strategy
```json
{
  "TrainingJobName": "my-training-job",
  "AlgorithmSpecification": {
    "TrainingImage": "123456789012.dkr.ecr.us-east-1.amazonaws.com/my-algorithm:1.0",
    "TrainingInputMode": "File"
  },
  "RoleArn": "arn:aws:iam::123456789012:role/SageMakerRole",
  "InputDataConfig": [
    {
      "ChannelName": "train",
      "DataSource": {
        "S3DataSource": {
          "S3Uri": "s3://my-bucket/train",
          "S3DataType": "S3Prefix"
        }
      },
      "CompressionType": "None",
      "RecordWrapperType": "None"
    }
  ],
  "OutputDataConfig": {
    "S3OutputPath": "s3://my-bucket/output"
  },
  "ResourceConfig": {
    "InstanceType": "ml.m4.xlarge",
    "InstanceCount": 1,
    "VolumeSizeInGB": 50
  },
  "HyperParameters": {
    "parameter_1": "value_1",
    "parameter_2": "value_2"
  }
}
```

Microsoft Azure uses a YAML file to define and configure machine learning jobs. This file can contain various parameters that specify the details of the job, such as the schema, the name, the type, the display name, the experiment name, the description, the tags, the command, the code, the environment, the environment variables, the compute settings, the resource allocation, the limits, the inputs, the outputs, and the identities. Additionally, there may be additional parameters that are specific to the platform that is being used for the job, such as PyTorch or TensorFlow. These parameters can be used to customize the behavior of a machine learning job on Azure, allowing users to specify the details of their training process and configure it to meet their specific needs.

```yaml
##### The ID of the project.
project_id: my-azure-project

##### The location of the project's resources.
location: eastus

##### The credentials to use for authenticating with Microsoft Azure.
credentials:
  client_id: my-client-id
  client_secret: my-client-secret
  tenant_id: my-tenant-id
  subscription_id: my-subscription-id

##### The details of the training job.
training_job:
  name: my-training-job
  algorithm:
    image: my-azure-project.azurecr.io/my-algorithm:1.0
    mode: file
  role: my-azure-role
  input_data:
    channel: train
    data_source:
      azure_blob_data_source:
        container_name: my-container
        file_path: train
  output_data:
    azure_blob_output_path: my-container/output
  resource_config:
    vm_size: Standard_D4_v3
    instance_count: 1
    volume_size_gb: 50
  hyperparameters:
    parameter_1: value_1
    parameter_2: value_2
```
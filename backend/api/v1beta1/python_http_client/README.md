# kfp-server-api-v1beta1
This file contains REST API specification for Kubeflow Pipelines. The file is autogenerated from the swagger definition.

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 2.0.0-alpha.6
- Package version: 2.0.0-alpha.6
- Build package: org.openapitools.codegen.languages.PythonClientCodegen
For more information, please visit [https://www.google.com](https://www.google.com)

## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import kfp_server_api_v1beta1
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import kfp_server_api_v1beta1
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
from __future__ import print_function

import time
import kfp_server_api_v1beta1
from kfp_server_api_v1beta1.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = kfp_server_api_v1beta1.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: Bearer
configuration = kfp_server_api_v1beta1.Configuration(
    host = "http://localhost",
    api_key = {
        'authorization': 'YOUR_API_KEY'
    }
)
# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['authorization'] = 'Bearer'


# Enter a context with an instance of the API client
with kfp_server_api_v1beta1.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = kfp_server_api_v1beta1.ExperimentServiceApi(api_client)
    id = 'id_example' # str | The ID of the experiment to be archived.

    try:
        # Archives an experiment and the experiment's runs and jobs.
        api_response = api_instance.archive_experiment(id)
        pprint(api_response)
    except ApiException as e:
        print("Exception when calling ExperimentServiceApi->archive_experiment: %s\n" % e)
    
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ExperimentServiceApi* | [**archive_experiment**](docs/ExperimentServiceApi.md#archive_experiment) | **POST** /apis/v1beta1/experiments/{id}:archive | Archives an experiment and the experiment&#39;s runs and jobs.
*ExperimentServiceApi* | [**create_experiment**](docs/ExperimentServiceApi.md#create_experiment) | **POST** /apis/v1beta1/experiments | Creates a new experiment.
*ExperimentServiceApi* | [**delete_experiment**](docs/ExperimentServiceApi.md#delete_experiment) | **DELETE** /apis/v1beta1/experiments/{id} | Deletes an experiment without deleting the experiment&#39;s runs and jobs. To avoid unexpected behaviors, delete an experiment&#39;s runs and jobs before deleting the experiment.
*ExperimentServiceApi* | [**get_experiment**](docs/ExperimentServiceApi.md#get_experiment) | **GET** /apis/v1beta1/experiments/{id} | Finds a specific experiment by ID.
*ExperimentServiceApi* | [**list_experiment**](docs/ExperimentServiceApi.md#list_experiment) | **GET** /apis/v1beta1/experiments | Finds all experiments. Supports pagination, and sorting on certain fields.
*ExperimentServiceApi* | [**unarchive_experiment**](docs/ExperimentServiceApi.md#unarchive_experiment) | **POST** /apis/v1beta1/experiments/{id}:unarchive | Restores an archived experiment. The experiment&#39;s archived runs and jobs will stay archived.
*HealthzServiceApi* | [**get_healthz**](docs/HealthzServiceApi.md#get_healthz) | **GET** /apis/v1beta1/healthz | Get healthz data.
*JobServiceApi* | [**create_job**](docs/JobServiceApi.md#create_job) | **POST** /apis/v1beta1/jobs | Creates a new job.
*JobServiceApi* | [**delete_job**](docs/JobServiceApi.md#delete_job) | **DELETE** /apis/v1beta1/jobs/{id} | Deletes a job.
*JobServiceApi* | [**disable_job**](docs/JobServiceApi.md#disable_job) | **POST** /apis/v1beta1/jobs/{id}/disable | Stops a job and all its associated runs. The job is not deleted.
*JobServiceApi* | [**enable_job**](docs/JobServiceApi.md#enable_job) | **POST** /apis/v1beta1/jobs/{id}/enable | Restarts a job that was previously stopped. All runs associated with the job will continue.
*JobServiceApi* | [**get_job**](docs/JobServiceApi.md#get_job) | **GET** /apis/v1beta1/jobs/{id} | Finds a specific job by ID.
*JobServiceApi* | [**list_jobs**](docs/JobServiceApi.md#list_jobs) | **GET** /apis/v1beta1/jobs | Finds all jobs.
*PipelineServiceApi* | [**create_pipeline**](docs/PipelineServiceApi.md#create_pipeline) | **POST** /apis/v1beta1/pipelines | Creates a pipeline.
*PipelineServiceApi* | [**create_pipeline_version**](docs/PipelineServiceApi.md#create_pipeline_version) | **POST** /apis/v1beta1/pipeline_versions | Adds a pipeline version to the specified pipeline.
*PipelineServiceApi* | [**delete_pipeline**](docs/PipelineServiceApi.md#delete_pipeline) | **DELETE** /apis/v1beta1/pipelines/{id} | Deletes a pipeline and its pipeline versions.
*PipelineServiceApi* | [**delete_pipeline_version**](docs/PipelineServiceApi.md#delete_pipeline_version) | **DELETE** /apis/v1beta1/pipeline_versions/{version_id} | Deletes a pipeline version by pipeline version ID. If the deleted pipeline version is the default pipeline version, the pipeline&#39;s default version changes to the pipeline&#39;s most recent pipeline version. If there are no remaining pipeline versions, the pipeline will have no default version. Examines the run_service_api.ipynb notebook to learn more about creating a run using a pipeline version (https://github.com/kubeflow/pipelines/blob/master/tools/benchmarks/run_service_api.ipynb).
*PipelineServiceApi* | [**get_pipeline**](docs/PipelineServiceApi.md#get_pipeline) | **GET** /apis/v1beta1/pipelines/{id} | Finds a specific pipeline by ID.
*PipelineServiceApi* | [**get_pipeline_by_name**](docs/PipelineServiceApi.md#get_pipeline_by_name) | **GET** /apis/v1beta1/namespaces/{namespace}/pipelines/{name} | Finds a pipeline by Name (and namespace)
*PipelineServiceApi* | [**get_pipeline_version**](docs/PipelineServiceApi.md#get_pipeline_version) | **GET** /apis/v1beta1/pipeline_versions/{version_id} | Gets a pipeline version by pipeline version ID.
*PipelineServiceApi* | [**get_pipeline_version_template**](docs/PipelineServiceApi.md#get_pipeline_version_template) | **GET** /apis/v1beta1/pipeline_versions/{version_id}/templates | Returns a YAML template that contains the specified pipeline version&#39;s description, parameters and metadata.
*PipelineServiceApi* | [**get_template**](docs/PipelineServiceApi.md#get_template) | **GET** /apis/v1beta1/pipelines/{id}/templates | Returns a single YAML template that contains the description, parameters, and metadata associated with the pipeline provided.
*PipelineServiceApi* | [**list_pipeline_versions**](docs/PipelineServiceApi.md#list_pipeline_versions) | **GET** /apis/v1beta1/pipeline_versions | Lists all pipeline versions of a given pipeline.
*PipelineServiceApi* | [**list_pipelines**](docs/PipelineServiceApi.md#list_pipelines) | **GET** /apis/v1beta1/pipelines | Finds all pipelines.
*PipelineServiceApi* | [**update_pipeline_default_version**](docs/PipelineServiceApi.md#update_pipeline_default_version) | **POST** /apis/v1beta1/pipelines/{pipeline_id}/default_version/{version_id} | Update the default pipeline version of a specific pipeline.
*PipelineUploadServiceApi* | [**upload_pipeline**](docs/PipelineUploadServiceApi.md#upload_pipeline) | **POST** /apis/v1beta1/pipelines/upload | 
*PipelineUploadServiceApi* | [**upload_pipeline_version**](docs/PipelineUploadServiceApi.md#upload_pipeline_version) | **POST** /apis/v1beta1/pipelines/upload_version | 
*RunServiceApi* | [**archive_run**](docs/RunServiceApi.md#archive_run) | **POST** /apis/v1beta1/runs/{id}:archive | Archives a run.
*RunServiceApi* | [**create_run**](docs/RunServiceApi.md#create_run) | **POST** /apis/v1beta1/runs | Creates a new run.
*RunServiceApi* | [**delete_run**](docs/RunServiceApi.md#delete_run) | **DELETE** /apis/v1beta1/runs/{id} | Deletes a run.
*RunServiceApi* | [**get_run**](docs/RunServiceApi.md#get_run) | **GET** /apis/v1beta1/runs/{run_id} | Finds a specific run by ID.
*RunServiceApi* | [**list_runs**](docs/RunServiceApi.md#list_runs) | **GET** /apis/v1beta1/runs | Finds all runs.
*RunServiceApi* | [**read_artifact**](docs/RunServiceApi.md#read_artifact) | **GET** /apis/v1beta1/runs/{run_id}/nodes/{node_id}/artifacts/{artifact_name}:read | Finds a run&#39;s artifact data.
*RunServiceApi* | [**report_run_metrics**](docs/RunServiceApi.md#report_run_metrics) | **POST** /apis/v1beta1/runs/{run_id}:reportMetrics | ReportRunMetrics reports metrics of a run. Each metric is reported in its own transaction, so this API accepts partial failures. Metric can be uniquely identified by (run_id, node_id, name). Duplicate reporting will be ignored by the API. First reporting wins.
*RunServiceApi* | [**retry_run**](docs/RunServiceApi.md#retry_run) | **POST** /apis/v1beta1/runs/{run_id}/retry | Re-initiates a failed or terminated run.
*RunServiceApi* | [**terminate_run**](docs/RunServiceApi.md#terminate_run) | **POST** /apis/v1beta1/runs/{run_id}/terminate | Terminates an active run.
*RunServiceApi* | [**unarchive_run**](docs/RunServiceApi.md#unarchive_run) | **POST** /apis/v1beta1/runs/{id}:unarchive | Restores an archived run.


## Documentation For Models

 - [JobMode](docs/JobMode.md)
 - [PipelineSpecRuntimeConfig](docs/PipelineSpecRuntimeConfig.md)
 - [ProtobufAny](docs/ProtobufAny.md)
 - [ProtobufNullValue](docs/ProtobufNullValue.md)
 - [ReportRunMetricsResponseReportRunMetricResult](docs/ReportRunMetricsResponseReportRunMetricResult.md)
 - [ReportRunMetricsResponseReportRunMetricResultStatus](docs/ReportRunMetricsResponseReportRunMetricResultStatus.md)
 - [RunMetricFormat](docs/RunMetricFormat.md)
 - [V1beta1CronSchedule](docs/V1beta1CronSchedule.md)
 - [V1beta1Experiment](docs/V1beta1Experiment.md)
 - [V1beta1ExperimentStorageState](docs/V1beta1ExperimentStorageState.md)
 - [V1beta1GetHealthzResponse](docs/V1beta1GetHealthzResponse.md)
 - [V1beta1GetTemplateResponse](docs/V1beta1GetTemplateResponse.md)
 - [V1beta1Job](docs/V1beta1Job.md)
 - [V1beta1ListExperimentsResponse](docs/V1beta1ListExperimentsResponse.md)
 - [V1beta1ListJobsResponse](docs/V1beta1ListJobsResponse.md)
 - [V1beta1ListPipelineVersionsResponse](docs/V1beta1ListPipelineVersionsResponse.md)
 - [V1beta1ListPipelinesResponse](docs/V1beta1ListPipelinesResponse.md)
 - [V1beta1ListRunsResponse](docs/V1beta1ListRunsResponse.md)
 - [V1beta1Parameter](docs/V1beta1Parameter.md)
 - [V1beta1PeriodicSchedule](docs/V1beta1PeriodicSchedule.md)
 - [V1beta1Pipeline](docs/V1beta1Pipeline.md)
 - [V1beta1PipelineRuntime](docs/V1beta1PipelineRuntime.md)
 - [V1beta1PipelineSpec](docs/V1beta1PipelineSpec.md)
 - [V1beta1PipelineVersion](docs/V1beta1PipelineVersion.md)
 - [V1beta1ReadArtifactResponse](docs/V1beta1ReadArtifactResponse.md)
 - [V1beta1Relationship](docs/V1beta1Relationship.md)
 - [V1beta1ReportRunMetricsRequest](docs/V1beta1ReportRunMetricsRequest.md)
 - [V1beta1ReportRunMetricsResponse](docs/V1beta1ReportRunMetricsResponse.md)
 - [V1beta1ResourceKey](docs/V1beta1ResourceKey.md)
 - [V1beta1ResourceReference](docs/V1beta1ResourceReference.md)
 - [V1beta1ResourceType](docs/V1beta1ResourceType.md)
 - [V1beta1Run](docs/V1beta1Run.md)
 - [V1beta1RunDetail](docs/V1beta1RunDetail.md)
 - [V1beta1RunMetric](docs/V1beta1RunMetric.md)
 - [V1beta1RunStorageState](docs/V1beta1RunStorageState.md)
 - [V1beta1Status](docs/V1beta1Status.md)
 - [V1beta1Trigger](docs/V1beta1Trigger.md)
 - [V1beta1Url](docs/V1beta1Url.md)


## Documentation For Authorization


## Bearer

- **Type**: API key
- **API key parameter name**: authorization
- **Location**: HTTP header


## Author

kubeflow-pipelines@google.com



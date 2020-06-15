# RabbitMQ Steps

This step allows you to get information related to your RabbitMQ queues.

---------

<kbd>
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</kbd>

---------

# Files

* [RabbitMQSteps.zip](RabbitMQSteps.zip) - Workflow zip file with the step and example flow
* [rabbitmq.png](/rabbitmq.png) - RabbitMQ logo

# How it works
This step uses the RabbitMQ HTTP API for getting information on queues. It uses the `/api/queues` path.


# Installation

## RabbitMQ Setup
Make sure the HTTP API is enabled within RabbitMQ. This will probably require the management plugin which can be installed with `sudo rabbitmq-plugins enable rabbitmq_management`

## xMatters Setup
1. Download the [RabbitMQSteps.zip](RabbitMQSteps.zip) file onto your local computer
2. Navigate to the Workflows tab of your xMatters instance
3. Click Import, and select the zip file you just downloaded
4. Create an endpoint for RabbitMQ. By default it is on port 15672, so if using the xMatters Agent, the endpoint would be `http://localhost:15672`. Also, by default, basic authentication is used and a user `guest` with the password `guest` is usable for any local request.


## Usage
The **RabbitMQ - Get Queue Metrics** step is now available in your custom steps. So navigate to the appropriate canvas so you can add the step there. If you'd like to experiment with it, the **Get Queue Info** workflow has a canvas that can be triggered via HTTP call. 

### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Queue Name | Yes | 0 | 2000 | Queue Name to get metrics for. | | No |
| All Queues | Yes | 0 | 2000 | Either (true) or (false). Whether you would like to get all queue information or just one. | false | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| json | JSON output of request |
| Queue Length | Messages currently in queue |
| Queue Publish Rate | Rate of messages being published |
| Queue Deliver Rate | Rate of messages being delivered |


## Example
This is the provided flow that includes the **RabbitMQ - Get Queue Metrics** Step.

<kbd>
	<img src="/media/ExampleFlow.png">
</kbd>


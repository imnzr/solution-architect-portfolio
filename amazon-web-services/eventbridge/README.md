# Amazon EventBridge

![This is an alt text.](/amazon-web-services/eventbridge/EventBridge.png "This is a sample image.")

## Introduction to Amazon EventBridge
Amazon EventBridge is a serverless event bus service from AWS that connects applications using events (occurrences or state changes). It receives events from various sources, then routes them to the right targets based on rules you define. EventBridge is the evolution of CloudWatch Event.

A simple analogy: EventBridge is like a smart public announcement system. When an announcement (event) is made, it automatically delivers it only to the people who need a hear it.

### How it works 
1. An event source generates an event, such as an AWS service (EC2, S3), your own application, or a third-party SaaS application.
2. The event bus receives the event 
3. A rule matches the event againts a pattern you define 
4. Matching events are sent to a target, such as Lambda, SQS, SNS, Step Function, or an API endpoint.

Example: When a file is uploaded to S3, an event is sent to EventBridge, and a rule triggers a Lambda function to process the file 

### Key Components 
1. Event Bus: the channel where events arrive. There is a default bus, custom buses, and partner buses for SaaS
2. Rule: filters that decide which events go to which targets 
3. Target: the destinations for events, and one rule can have multiple targets
4. EventBridge Scheduler: runs scheduled task (link cron) at scale
5. EventBridge Pipes: connects a sources to a target point-to-point, with optional filtering and data transformation
6. Schema Registry: stores event structures so developers can generate code more easily
7. Archive&Reply: stores events and replays them for debugging or recovery 

### Use Case
1. Event driven architecture: building loosely coupled systems that are easier to evolve.
2. Operational automation: for example, triggering automatic actions when an EC2 instance changes state
3. Scheduled tasks: replacing cron jobs, such as running a report every day at 08:00 AM.
4. SaaS integration: receiving events from services like Zendesk, Datadog, or Shopify
5. Monitoring and security: reacting automatically to configuration changes or suspicious activity 
6. Microservices orchestration: connecting many services without having them call each other directly

### Price
Generally billed based on the number of custom events published to a bus (per million event). Events from AWS services to the default bus are usually free. Other feature such as Scheduler and Pipe have their own pricing.
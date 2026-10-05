# Amazon Simple Queue Service 

![This is an alt text.](/amazon-web-services/ec2/EC2.png "This is a sample image.")

## Introduction to Amazon Simple Queue Service
Amazon SQS (Simple Queue Service) is fully managed message queuing service from AWS. It allows one part of an application to send message to a queue, and another part to retrive and process them whenever it is ready. This way, application component don't have to wait for each other or be directly connected (decoupling).

A simple analogy: SQS is like the order ticket rail in a restaurant kitchen. The waiter places order slips on the rail, and the cheft picks them up on by one at their own pace, without the waiter having to wait in the kitchen.

### How it works ?
1. A producer send a message to the queue 
2. The message is stored securely and redudantly across multiple availability zone 
3. A customer (such as EC2, Lambda, or a container) retrives the message from the queue 
4. After processing is complete, the customer deletes the message from the queue 

While a message is being processed, it is temporarily hidden through the visibility timeout. If the consumer fails to delete it in time, the message reappears and can be processed again.

### Queue types
1. Standard Queue: nearly unlimited throughput, at-least-once delivery (a message may be delivered more than once), and ordering is not strictly guaranteed. Suitable for most use cases.
2. FIFO Queue: message order is preserved (first-in-first-out) and supports exactly-once processing. Suitable for transactions or processes where order matters, with more limited throughput than Standard.

### Use case
1. Decoupling microservices: each service works independently.
2. Traffic spike buffering: the queue holds messages when load increases, then they are processed gradually.
3. Background task processing: such as sending emails, generating reports, or processing images.
4. Order processing: ensuring every order is processed and none are lost.
5. Integration with other services: for example, Lambda can process SQS messages automatically, or EventBridge and SNS can send events to a queue.

### Example use case
In an online store, when a customer checks out, the application sends an order message to SQS. Several workers pick up that message to process payment, reduce stock, and send a confirmation email. During a big sale when orders flood in, the queue holds everything so no orders are lost.

### Quick comparison with similar services
1. SQS vs SNS: SQS is pull-based (consumers retrieve messages), while SNS is push-based (messages are pushed to many subscribers at once).
2. SQS vs EventBridge: EventBridge focuses on routing events based on rules, while SQS focuses on storing messages until they are processed.

### Price 
Billed based on the number of requests, per million requests, with different rates for Standard and FIFO. A monthly free tier is usually available.
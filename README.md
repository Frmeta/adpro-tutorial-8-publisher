a. How many data your publlsher program will send to the message broker in one run?
- The publisher program will send 5 messages to the message broker in one run because there are 5 calls to publish_event method with UserCreatedEventMessage in the main function.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
- it means both programs (subscriber & publisher) are connecting to the same message broker. This URL is used to create a new queue publisher.
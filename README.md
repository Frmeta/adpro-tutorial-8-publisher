a. How many data your publlsher program will send to the message broker in one run?
- The publisher program will send 5 messages to the message broker in one run because there are 5 calls to publish_event method with UserCreatedEventMessage in the main function.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
- it means both programs (subscriber & publisher) are connecting to the same message broker. This URL is used to create a new queue publisher.

Screen of running RabbitMQ
![Screen of running RabbitMQ](img/image.png)

Screenshot terminal
![alt text](img/image-2.png)
Ini adalah screenshot terminal subscriber dimana telah berhasil menerima 5 event message broker dari publisher
![alt text](img/image-1.png)
Ini adalah screenshoot terminal publisher dimana telah berhasil menjalankan `cargo run` untuk mengirim 5 event memalui message broker yang kemudian akan diproses oleh subscriber.
![alt text](img/image-3.png)
Ini adalah screenshot interface RabbitMQ dimana ada spike pada message rates yang disebabkan karena saya menjalankan publisher berkali-kali. Spike pada chart menandakan bahwa saya menjalankan program publisher

What can be improved from this code:
- Error Handling: Currently, the results of `publish_event` are being ignored with `_ =`. It would be better to handle these potential errors.
- Code Duplication: The `publish_event` method is called multiple times with similar arguments. This could be refactored into a loop or a function to reduce code duplication.
- Hardcoded Values: The connection string and the event name are hardcoded. It would be better to move these to a configuration file or environment variables.
- Unimplemented Method: The `get_handler_action` method is currently not implemented (todo!()). This should be implemented or removed if not needed.
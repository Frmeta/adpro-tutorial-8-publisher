a. How many data your publlsher program will send to the message broker in one run?
- The publisher program will send 5 messages to the message broker in one run because there are 5 calls to publish_event method with UserCreatedEventMessage in the main function.

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
- it means both programs (subscriber & publisher) are connecting to the same message broker. This URL is used to create a new queue publisher.

Screen of running RabbitMQ
![Screen of running RabbitMQ](img/image.png)

Screenshot terminal
![alt text](image-2.png)
Ini adalah screenshot terminal subscriber dimana telah berhasil menerima 5 event message broker dari publisher
![alt text](image-1.png)
Ini adalah screenshoot terminal publisher dimana telah berhasil menjalankan `cargo run` untuk mengirim 5 event memalui message broker yang kemudian akan diproses oleh subscriber.
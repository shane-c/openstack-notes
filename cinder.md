Cinder 

cinder-api
>Accepts API requests, and routes them to the cinder-volume for action.

cinder-volume
>Interacts directly with the Block Storage service, and processes such as the cinder-scheduler. It also interacts with these processes through a message queue. The cinder-volume service responds to read and write requests sent to the Block Storage service to maintain state. It can interact with a variety of storage providers through a driver architecture.

cinder-scheduler daemon
>Selects the optimal storage provider node on which to create the volume. A similar component to the nova-scheduler.

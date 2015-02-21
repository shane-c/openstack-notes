Nova Compute notes
----
API services

nova-api service
>Accepts and responds to end user compute API calls. The service supports the OpenStack Compute API, the Amazon EC2 API, and a special Admin API for privileged users to perform administrative actions. It enforces some policies and initiates most orchestration activities, such as running an instance.

nova-api-metadata service
>Accepts metadata requests from instances. The nova-api-metadata service is generally used when you run in multi-host mode with nova-network installations.

Compute services

nova-compute service
>A worker daemon that creates and terminates virtual machine instances through hypervisor APIs. For example:
>XenAPI for XenServer/XCP
>libvirt for KVM or QEMU
>VMwareAPI for VMware
>Processing is fairly complex. Basically, the daemon accepts actions from the queue and performs a series of system commands such as launching a KVM instance and updating its state in the database.

nova-scheduler service
>Takes a virtual machine instance request from the queue and determines on which compute server host it runs.

nova-conductor module
>Mediates interactions between the nova-compute service and the database. It eliminates direct accesses to the cloud database made by the nova-compute service. The nova-conductor module scales horizontally. However, do not deploy it on nodes where the nova-compute service runs.

Networking services
nova-network worker daemon
>Similar to the nova-compute service, accepts networking tasks from the queue and manipulates the network. Performs tasks such as setting up bridging interfaces or changing IPtables rules.

Console services
nova-consoleauth daemon
>Authorizes tokens for users that console proxies provide. See nova-novncproxy and nova-xvpnvcproxy. This service must be running for console proxies to work. You can run proxies of either type against a single nova-consoleauth service in a cluster configuration. For information, see About nova-consoleauth.

nova-novncproxy daemon
>Provides a proxy for accessing running instances through a VNC connection. Supports browser-based novnc clients.

nova-spicehtml5proxy daemon
>Provides a proxy for accessing running instances through a SPICE connection. Supports browser-based HTML5 client.

nova-xvpnvncproxy daemon
>Provides a proxy for accessing running instances through a VNC connection. Supports an OpenStack-specific Java client.

nova-cert daemon
>x509 certificates.

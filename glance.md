Glance

glance-api
>Accepts Image API calls for image discovery, retrieval, and storage.

glance-registry
>Stores, processes, and retrieves metadata about images. Metadata includes items such as size and type.

Database
>Stores image metadata and you can choose your database depending on your preference. Most deployments use MySQL or SQLite.

Storage repository for image files
>Various repository types are supported including normal file systems, Object Storage, RADOS block devices, HTTP, and Amazon S3. Note that some repositories will only support read-only usage.

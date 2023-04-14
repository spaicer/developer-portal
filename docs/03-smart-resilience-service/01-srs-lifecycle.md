# Lifecycle Management of Smart Resilience Services

After the building blocks of an SRS (AI modules, backend application, and user interface) have been developed, the AI models must be trained before the service can be used. When training the models, the following approaches are distinguished:
- Ready to use (supported): The underlying AI model is trained accordingly during the development of the SRS and can already be used after the deployment of the SRS to a target platform.
- Remote updates (supported): The SRS already in use is supplied with new AI model versions periodically or as needed. However, the models are trained by the software provider in its own development environment.
- Bring your own storage (supported): An SRS must be trained after deployment based on customer-specific raw data. In doing so, this data resides outside the SPAICER platform on a storage solution managed by the customer. The SPAICER platform gains access to this storage, reads the data and trains the AI models based on it.
- Internal storage (not supported): The bulk data necessary for training the AI models is persisted within the SPAICER platform.

The last approach (Internal storage) is not supported by the SPAICER platform due to the following basic assumptions:
- For the platform-internal persistent storage of mass data, hardware capacities are required that exceed the costs of using a specialized cloud service in terms of acquisition and operation.
- For the platform-internal storage of structured and unstructured data, the operation (e.g. backup, restore, monitoring, disaster recovery, high-availability, etc.) of specialized data services (e.g. database management systems, object stores, etc.) is necessary. The required skills and implied operational costs exceed the cost of using a specialized cloud service.

Regarding the location of the training of AI models, the following approaches are distinguished:
- Run: The SRS must be delivered ready to use by the software provider and does not need to be trained in the runtime environment of the SPAICER platform.
- Train and run: The SRS must be trained with customer-specific data within the SPAICER platform.
- Train platform and runtime platform: For the training of AI models with customer-specific data, a central training instance with corresponding hardware capacities is operated. The trained models are distributed to runtime instances.
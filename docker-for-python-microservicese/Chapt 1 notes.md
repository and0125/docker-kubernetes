# Making the Move to Microservices

## Traditional Approach

a monolithic approach is the typical approach to projects, because they start off small, and divisions can be inconvinient and sometimes non-sensical.

As things change and grow, having a big ball of code is probably not the best way of structuring a big project. Some limitations as the project grows include:

- lines of code increases
- inefficient utilization of resources
- issues with development scalability
- Deployment limitations
- Interdependency of technologies
- A bug in a small part of the system can bring down the whole system

## Microservice Approach

A system following this approah is a colleciton of loosely coupled specialized serivces that work in unison to provide a more comprehensive service.

- A collection of services means there are different well-defined modules.
- loosely coupled means services can be deployed and updated independently. This indepdence is the main benefit from this approach, and services must be kept as independent as possible to ensure this is useful. Otherwise, you are just building smaller monolithic services.
- work in unison means the services are capable of communicating with each other.
- providing a comprehensive service means that the system will replicate the same functionalites available from a monolithic system.

Containers are a way to configure microservices, and its best to keep the containers small and with a single purpose.

## Container Orchestration

an orchestrator handles the whole cluster of services, and for managing a cluster, kubernetes is the software tool for the job.

## Example - MyThoughts

The book will create a simple blog site as an example of how to create and design a microservice system.

based on chapter one's analysis, the structure of the system will be:

- a users backend
- a thoughts backend for blog posts
- a search backend to search the thoughts
- an HTML front-end and potentially a mobile app can access these backends
- A web server will handle the static files.

Any real-world system will be more complicated than this, and in transitioning a monolith to a microservice system, you will have to look at the divisions in the system, and double-check the existing system works the way you think it's working.

The ability to know how a live system is working is called observability. The main tools for this assessment are metrics and logs.

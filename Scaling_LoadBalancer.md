# Scaling and Load Balancer
***
## Introduction
In a software industry when a product is designed, Industry want it to reach to the large number of users. reaching to the large number of users means the given software should be able to maintain its response time same as when number of users were less. if the response time is significantly large, then users might lose patience and leave your product. that is why Scaling is required.

Scalability is the property of a system to handle a growing amount of work by adding resources to the system.
***
## scalability
The ability of software to handle increases of traffic and/or load through its design and resources is basically what is meant by “scalability”. In a very basic sense it is being able to handle load by having multiple instances of the software running.

How to scale up a system? There are two primary ways to scale up a system: Vertical scaling and horizontal scaling.

---
## Vertical scaling
Vertical scaling means that you scale up the system by deploying the software on a computer with higher capacity than the computer it is currently deployed on. The new computer may have a faster CPU, more memory, faster and larger hard disk, faster memory bus etc. than the current computer. This is also called scaling up.

The easiest way to scale up your software from a developer perspective is vertical scalability. You just deploy on a bigger machine, and the software performs better. However, once you get past standard hardware requirements, buying faster CPUs, etc. gets expensive compared to the extra performance you get. Also, if you add more CPUs to a computer, and your software is not explicitly implemented to take advantage of them, you will not get any increased performance out of the extra CPUs.
___
## Horizontal scaling
Horizontal scaling means that you scale up the system by adding more computers with your software deployed on. The added computers typically have about the same capacity as the current computers the system is running on. This is also called scaling out.

In order to make your software take advantage of multiple computers (or even multiple CPUs within the same computer), your software need to be able to parallelize its tasks.

parallization of tasks can be done at differnt levels:-

    Distributing separate tasks onto separate computers.
    Distributing separate tasks onto separate CPUs on the same computer.
    Distributing separate tasks onto separate threads on the same CPU.
Distribution of tasks onto separate computers is managed by Load Balancer.

---
## Vertical Scaling vs Horizontal scaling
* Horizontal scaling means scaling by adding more machines to your pool of resources, whereas vertical scaling refers to scaling by adding more power (e.g. CPU, RAM) to an existing machine.
* The differences between the two is that horizontal scaling requires breaking a sequential piece of logic into smaller pieces so that they can be executed in parallel across multiple machines. In many respects, vertical scaling is easier because the logic really doesn’t need to change. You are running the same logic on bigger machines.
*Horizontal scaling involves distributing jobs across machines over the network. Several patterns associated with this model: Master/Worker. on the other hand, In vertical scaling, concurrent programming on multi-core machines is often performed via multi-threading and inter process communication

---
## Load balancing
Load balancing is a method for distributing tasks onto multiple computers. For instance, distributing incoming HTTP requests (tasks) for a web application onto multiple web servers. There are a few different ways to implement load balancing.

The primary purpose of load balancing is to distribute the work load of an application onto multiple computers, so the application can process a higher work load. Load balancing is a way to scale an application.

A secondary goal of load balancing is often to provide redundancy in your application. That is, if one server in a cluster of servers fail, the load balancer can divide the load onto the functioning servers. Having multiple servers help each other in this way is called "redundancy".

Load balancer is implemented onto a server. To implement the load balancer, the common algorithms (schemes) are given below.
##### 1. Even Task Distribution Scheme:-
An even task distribution scheme means that the tasks are distributed evenly between the servers in the cluster.This also means all the servers will have equal amount of load if incoming task require same amount of work. This scheme is thus very simple. This makes it easier to implement. the algorithms used here is called **'Round Robin'**

Even task distribution ignores the difference in the work required to process each task. That means, that even if each server is given the same number of tasks, you can have situations where one server has more tasks requiring heavy processing than the others. This may happen due to the randomness of incoming tasks. this randomness of assigning task is limiting of this algorithm.

##### 2. Weighted Task Distribution Scheme:-
 A weighted task distribution load balancing scheme distributes the incoming tasks onto the servers in the cluster using weights. That means that you can specify the weight (ratio) of tasks a server should receive relative to other servers. This is useful if the servers in the cluster do not all have the same capacity.

 For instance, lets say there are three servers, two of them has the same capacity say 'C' whcich is handling C task per unit of time. Last one has 2/3rd of their capacity. if incoming number of task is N, then task can be distributed as C , C , 2C/3. where C + C + 2C/3 = N.

 ---
 ### References
 * [Load Balancer Schemes](https://kemptechnologies.com/load-balancer/load-balancing-algorithms-techniques/)
 * [Scaling Horizontal vs Vertically](https://www.section.io/blog/scaling-horizontally-vs-vertically/)

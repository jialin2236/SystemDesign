# Knowledge Points and Examples
This folder includes knowledge points and examples specifically for the initial high level discussion. 

## Initial High Level Discussion Goal
The goal for this initial high level discussion is to 
1. get buy in
2. get a rough understanding of the requirement the system has for various component
3. Identify potential bottlenecks
4. shedding some lights on future deep dive, potential optimization that needs
to be done later on to overcome bottlenecks

## High Level Concepts
### Servers
Computers in a distributed system that concurrently process incoming requests from clients

### Read/Write
**Read:** 
  - Client requests that involve system to extract information and return to client
  - Example: browsing your feed on instagram, requesting item catalog data from catalog metadata

**Write:** 
  - Client requests that involve system to store/record information in system itself
  - Example: posting new story/post on instagram, changing item attribute on catalog metadata

### Single Point of Failure
A component within a system that could cause the entire system going offline if that component fails. 
It's something we should avoid via good system design. 

### Latency and Throughput
**Latency:** amount of time the system takes to perform a single action/process a single request

**Throughput:** number of requests in a unit of time a system could process

## Consistency and Availability
### Consistency 
always return source of truth, the latest information. Or returns error. 

example: any relational database, realtime conference call

#### Consistency Pattern

<details>
  <summary>strong consistency</summary>

  System is always consistent at any given time, typical used for system that needs transactions
  
  examples: relational data base
</details>

<details>
  <summary>eventual consistency</summary>
  
  It could be implemented in highly available systems, it guarantees that information will be consistent after 
  a period of time, but not instantly

  examples: DNS and email. Data is replicated asynchronously. 
</details>

<details>
  <summary>weak consistency</summary>

  Information that's been lost cannot be retrieved. But latest available information will be delivered. 
  Mostly used for real time communication, memcached. 

  Example: Video calls, online gaming, etc...
</details>



### Availability 
Guarantee information return to client, but information isn't necessarily the latest

example: instance messaging app, fb/instagram feed

<details>
  <summary>fail over</summary>
  
  **Active-Passive**: primarily request/information is sent to active server. Active server shares heartbeat
  with passive server. If passive server fails to detect heartbeat, it takes over and become active.

  **Active-Active**: both servers managing traffic, spreading the load between them. 
</details>

<details>
  <summary>replication</summary>

  **Master-Slave**: single direction replications, from master to slave

  **Master-Master**: bi-directional replications, masters share replications
</details>

#### Availability Pattern

## Vertical vs. Horizontal Scaling
What does it solve? Scalability

When an internet service start to grow beyond its capacity to handle all the requests, it needs to start scaling. 
To be able to continuously handle incoming requests without interruption and severe loss of data.

**Vertical Scaling**: Replace existing machine with more powerful machine 
<details>
  <summary>pros</summary>

  - service is still intact in a single machine, no need to worry about modifying architecture
  - no need to worry about consistency
  - interprocess communication (fast)
  - could work great if we know service growth limit would fit in additional resources
</details>
  
<details> 
  <summary>cons</summary>

  - single point of failure
  - no availability guarantee
  - technology constraints on machine performance (only so much money can buy for a machine)
</details>

**Horizontal Scaling**: Add additional machines of the same calibre as the current machine to work together
<details>
  <summary>pros</summary>

  - eliminate single point of failure
  - can achieve very high availability
  - prevent overloading
  - linear growth of performance when adding more machines 
</details>
  
<details>
  <summary>cons</summary>

  - hard to achieve consistency
  - additional complexity
  - network calls (i/o, slower)
</details>


- Latency and Throughput
    - what each of them is
    - what's QPS
- Traffic, Storage and Memory consumption
- Cache, on disk storage

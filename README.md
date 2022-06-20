# For System Design Notes
## Get Started
To get started, these materials can provide high level
introduction of the majority of concepts used in the system design
interviews. A lot of concepts seem overwhelming at the beginning, but 
most are concepts/techniques that we use on a regular basis at our job. 
we just need to map them to the right terminology, and learn any additional
aspects of each concept that we're not familiar with. (I ordered them based on 
my opinion of read/watch sequence)

[great breadth coverage and analogies]("https://www.youtube.com/playlist?list=PLMCXHnjXnTnvo6alSjVkgxV-VH6EPyvoX") 
[lecture about scalability]("https://www.youtube.com/watch?v=-W9F__D3oY4") \
[with comprehensive introduction and examples]("https://github.com/donnemartin/system-design-primer/) \
[very useful discussion template]("https://leetcode.com/company/facebook/discuss/229177/My-System-Design-Template")

## Phase 1 Knowledge Points
After reading/watching through the above videos, the following concepts/terminologies
should not be foreign to you. Make sure that at any given time, you're able to
speak to what each of them is, why it's important, and how it should be used/not used
during distributed system deisgn

### For Initial High Level Design
Be able to describe the following terminologies and concepts.

- Vertical vs. Horizontal Scaling
- Servers
- Latency and Throughput
  - what each of them is
  - what's QPS
- Read and Write Volume, Ratio
- Traffic, Storage and Memory consumption
- Cache, on disk storage
- Single Point of Failure
- Consistency and Availability
  - strong, weak, eventual consistency
  - Fail over, replication approaches

## Phase 2 For More Detailed Design (not deep dive)
Describe the following terminologies and when to use it, pros and cons if applicable

### DNS and CDN
1. What do they stand for?
2. How does DNS work? High level system graph
3. What is the purpose of CDN? Why is it useful? Pros and Cons? 

### Load Balancer
1. What does load balancer do? 
2. Where can an LB sit in our design? 
3. How do we avoid Single Point of Failure? 

### Reverse Proxy
1. What does a Reverse Proxy do? 
2. Who owns/controls the Reverse Proxy? 
3. What's the difference between LB and Reverse Proxy?
4. What's the difference between a Proxy and Reverse Proxy? 

### ACID and CAP
1. What do they stand for? 
2. Where in a System Design do they apply? 
3. How to choose which one to use/follow?

### Database
1. What's the main difference between RDBMS and NoSQL? (no detail) 
2. Key indicators of choosing one over the other?

### Cache
1. Where in System Design can we use it? 
2. Major functionality and benefits? 
3. Stateful vs. Stateless? 

### Asynchronism
1. What is message/task queue? 
2. Possible issues? 

### Communication
1. What does Layer4 and Layer7 represent in the 7 layers of OSI (Open System Interconnection) model
2. What's HTTP? What does it do? 
3. What's TCP? What does it do? Characteristics? 
4. What's UDP? 
5. RPC
6. REST

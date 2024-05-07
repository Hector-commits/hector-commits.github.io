## Exercise 1

### Event Driven versus Orchestration-Driven Service Oriented architecture

| Architecture Name | Event Driven | Orchestration-Driven Service Oriented|
|-------|--------|--------|
|Partitioning type|Technically partitioned architecture. Domains are spread across multiple event processors and communicated through mediators, queues, and topics.| Extremely focused on technical partitioning.| 
|Number of quanta|Vary from 1 to many. This is based on the database interaction within each event processor and request-reply processing.| 1.  Due to the centralized nature of this architecture with one to few databases and with the orchestration engine acting as a giant coupling point.|
|Deployability|⭐⭐⭐ The services can be deployed independently and impact on the other services can be addressed,but it could lead to complex scenarios.|⭐ Extremely difficult deployments which require high coordination and holistic testing.|
|Elasticity|⭐⭐⭐ Highly elastic but with less control over processing flow.|⭐⭐⭐ Rate high as per the vendor provided tools for its implementation.|
|Evolutionary|⭐⭐⭐⭐⭐ The independence of the services make it easier to implement evolutions of the system independently. |⭐ Quite monolithic for evolutionary deployments.|
|Fault tolerance|⭐⭐⭐⭐⭐ In terms of system independence, in the event of a failure, the remaining components of the system can remain operational. |⭐⭐⭐ Compromised due to its centralized nature.|
|Modularity|⭐⭐⭐⭐ Enhanced modularity by structuring processing events into distinct, independently functioning components.|⭐⭐⭐ Structuring services into different layers facilitating the development of reusable components, this aligns with the goal of enterprise-level reuse.|
|Overall Cost|⭐⭐⭐ Involve trade-offs between increased workflow control, error handling capabilities and potential higher development and maintenance expenses versus the benefits of improved system responsiveness and recoverability.|⭐ Impacted by its intricated technical partitioning, high complexity, challenges on incremental change, all this leads to elevated development and maintenance expenses.|
|Performance|⭐⭐⭐⭐⭐ Asynchronous communications combined with parallel processing.|⭐⭐ Each business request was split across so much of the architecture.|
|Reliability|⭐⭐⭐ Involve trade-offs between its good fault tolerance versus its low control flow. |⭐⭐ Again the intricate technical partitioning may introduce complexities that challenges the overall system dependability.|
|Scalability|⭐⭐⭐⭐⭐ Very efficient handling diverse inputs and workloads as per the independent distribution and processing of events, this enables seamless expansion to accommodate increasing demands.|⭐⭐⭐⭐ This architecture's goal <b>was not scalability</b>, yet IT distributors invest substantial resources to enhance the systems' somehow scalable.|
|Simplicity|⭐ There are no clear paths, flows are nondeterministic and it's difficult to know before hand how the system is going to react.|⭐ Reduced simplicity as per intricate technical partitioning, centralized orchestration engine.|
|Testability|⭐⭐. Event-driven architectures are difficult to test due to the unpredictable nature of event flows, which can lead to complex and ever-growing test scenarios. |⭐ On this architectural system it's quite difficult to made isolated testing of individual services, it needs to be highly coordinated and holistic. |

### Suggest examples of application which fits with each architectonic style

* <b>Event Driven architecture:</b> an use case for this kind of architecture would be IoT Applications. Let's consider an IpT meteorological monitoring system: it'll have different sensors measuring temperature, wind speed and so on, these sensors provide metrics, but the event it's only triggered based on sudden increase in wind speed plus temperature surpassing a certain threshold. We may have different event processors which in the end revert on an alerting system.
* <b>Orchestration-Driven Service Oriented architecture:</b> a typical example of this architecture use would be an ad hoc created ERP system with just the relational database on the backend and the application layer with modules for finance, purchases, sales, supply chain and so on.

## Exercise 2
Considering the premises and project restrictions, the most suitable architectonic style for this projects would be monolithic. More precisely it would be ***Layered Architecture***. As pointed out on the reference book: <i>"The layered architecture style is a good choice for small, simple applications or websites. It is also a good architecture choice, particularly as a starting point, for situations with very tight budget and time constraints."</i>

| Requirements | Restrictions | Pros | Cons |
|-------|--------|--------|--------|
| Basic functionality |Limited budget|Simplicity|May have difficult maintenance|
| Quick and low-cost solution | Small development team: 1 UI + 2 PHP | Low Cost| Lack of modularity |
| Low traffic expected | "On premise" infrastructure | Fit with small projects with basic requisites | Limited scalability |

## Exercise 3

According to the project initial and new requirements we first discard any monolithic architectures. Any of the three monolithic architectures (layered, pipeline and microkernel) lack scalability (all of them rank just 1 star on this attribute), this is due to the  components being tightly coupled, making it difficult to scale individual parts independently.

Another point is the deployability, on the exercise we are pointing towards continuous deployments. Deployments on these architectures rank badly (especially on the layered architecture), but even on best case scenarios with monolithic architecture we are speaking on an average rate of 3 stars. 

On top of that we have the scarce elasticity of these architectures. As per this exercise requirements we are speaking on very different functional requirements, very specialized with very specific domains which cannot be attended by a small development team, but specialized domain teams using newer programming techniques. Thus, monolithic architectures are discarded, and we'll focus only on the distributed ones, which offer greater scalability, deployability, and adaptability to specialized domains.

If we focus on the attributes that we are looking for on this project, the main challenges we face are:
* Deployability: it's required to implement/deploy new functionality very quickly, ideally without manual intervention, the services might require several deployments on daily basis.
* Elasticity: the inherent variability and scalability needs of the project suggest that elasticity would be highly beneficial, so we are going to focus on this attribute as well.
* Evolutionary: continuous improvement is's suggested, the project requirements are pointing to a system which high adaptability to change and with the capacity to evolve over time.
* Modularity: very specialized and very different domain specific requirements are suggested, which remarks the need for a modular system.
* Scalability: fluctuating demand and seasonal variations as well as growth and expansion needs are stated. Therefore we'll prioritize architectures that excel in this aspect.

Here we have the Star rating of these architectures on the these attributes:

|Architecture characteristic|Service-based|Event-driven|Space-based|Service-oriented|Microservices|
|-------|--------|--------|--------|--------|--------|
|Deployability|⭐⭐⭐⭐|⭐⭐⭐|⭐⭐⭐|⭐|⭐⭐⭐⭐|
|Elasticity|⭐⭐|⭐⭐⭐|⭐⭐⭐⭐⭐|⭐⭐⭐|⭐⭐⭐⭐⭐|
|Evolutionary|⭐⭐⭐|⭐⭐⭐⭐⭐|⭐⭐⭐|⭐|⭐⭐⭐⭐⭐|
|Modularity|⭐⭐⭐⭐|⭐⭐⭐⭐|⭐⭐⭐|⭐⭐⭐|⭐⭐⭐⭐⭐|
|Scalability|⭐⭐⭐|⭐⭐⭐⭐⭐|⭐⭐⭐⭐⭐|⭐⭐⭐⭐|⭐⭐⭐⭐⭐|

It seems clear that the microservices architecture is the best choice for this project. Due to the application growth and the performance issues detected. The microservices architecture allow us to fragment the application into independent and scalable components. Each microservice can be developed, deployed and scaled independently, this also fits with the purpose of tackling concurrence and overload current problems.

Overall microservices seems to be the best fit as per the project main challenges, but we also have some cons which, in the case of this architecture are the <b>costs, performance</b> and <b>simplicity</b>: let's analysis them one by one.

* **Overall cost**: while cost is a significant trade-off, it's worth noting that this project does not specify any budget constraints. Therefore, the potential higher cost of microservices may be manageable given the project's flexibility in financial resources.
* **Performance**: while performance is a significant trade-off in microservices, addressing performance concerns could involve optimization strategies within services, such as ERP installation for back-office users, while acknowledging that some latency is inherent in front-end operations for external users.
* **Simplicity**: due to increased complexity in managing distributed systems and communication between services, it's important to recognize that microservices still offer significant advantages for Photo&Film4You project. 

By carefully managing complexity through effective design, deployment, and monitoring strategies, the benefits of microservices can outweigh the trade-offs, making them the preferred architectural choice for the project. 

## Exercise 4
### Top 3 fallacies of distributed computing
|Fallacy|Example|Why it was selected|
|-------|--------|--------|
|The Network is Reliable|Given a e-commerce system working on a distributed network, shop or web-shop servers need to communicate to a backend server which has online inventory availability information. On a given day, due to issues on the infrastructure or unplanned maintenance, the network between these services are interrupted, as result, customers who try to shop experience slowness during the purchase process as the shop/webshop cannot verify the availability of items.|Nowadays, we live in a world dominated by cloud computing, where network connectivity is often taken for granted, yet it's far from guaranteed. Networks consist of multiple layers, and even if a particular software or service provider is operational, our own network infrastructure may encounter disruptions periodically. Software vendors increasingly offer Point of Sale (POS) solutions that rely on cloud-based systems. These systems tightly link sales transactions to network reliability, which could prove to be a significant mistake should an unforeseen network outage occur.|
|The Network is Secure|The recent cyberattack on Air Europa, compromising the credit card data of over 100,000 customers, serves as a stark example highlighting the fallacy of "The Network is Secure." As an airline, Air Europa likely relied on distributed computing systems to manage various modules such as flight operations, reservations, passenger services, and more, distributed across multiple locations. However, this incident underscores the vulnerability of such interconnected systems to security breaches, emphasizing the importance of robust cybersecurity measures across distributed networks.|I choose this fallacy as top two as I have the feeling that this is a common misconception. If we speak to many average users//TODO|
|||
### Architect responsibilities versus development team responsibilities
|Architect|Development Team|
|-------|--------|
|Creating a state diagram for the order process|Creating a user interface prototype to verify user experience before development (although architect may provide insights regarding design principles)|
|Defining how infrastructure handles increased usage during marketing campaigns|Defining how infrastructure handles increased usage during marketing campaigns|
|Test automation|Test automation|
|Defining the best technology for implementing processes||
### Example of microservices architecture where is no feasible to maximize ALL of these architecture characteristics
### Architect role expectations

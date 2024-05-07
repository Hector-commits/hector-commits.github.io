---
title: Microservices Pattern
date: 2024-04-06 12:00:00 000
categories: [Architecture]
tags: [Microservices, Architecture]
published: false
---
# **Software Architecture**
# Part II. Architecture Styles
The difference between an architecture style and an architecture pattern can be confusing. We define an <i>architecture style</i>as the overarching structure of how the user interface and backend source code are organized (such as within layers of a monolithic deployment or separately deployed services) and how that source code interacts with a datastore. <i>Architecture patterns</i>, on the other hand, are lower-level design structures that help form specific solutions within an architecture style (such as how to achieve high scalability or high performance within a set of operations or between sets of services).

Understanding architecture styles occupies much of the the time and effort for new architects because they share importance and abundance. Architects must understand the various styles and the trade-offs encapsulated within each to make effective decisions; each architecture style embodies a well-known set of trade-offs that help an architect make the right choice for a particular business problem.

## Chapter 9. Foundations
Architecture styles, sometimes called architecture patterns, describe a named relationship of components covering a variety of architecture characteristics. An architecture style name, similar to design patterns, creates a single name that acts as shorthand between experienced architects. For example, when an architect talks about a layered monolith, their target in the conversation understands aspects of structure which kinds of architecture characteristics work well (and which ones can cause problems), typical deployment models, data strategies, and a host of other information. Thus, architects should be familiar with the basic names of fundamental generic architecture styles.
Each name captures a wealth of understood detail, one of the purposes of design patterns. An architecture style describes the topology, assumed and default architecture characteristics, both beneficial and detrimental. We cover many common modern architecture patterns in the remainder of this section of the book (Part II). However, architects should be familiar with several fundamental patterns that appear embedded within the larger patterns.
### Fundamental Patterns
Several fundamental patterns appear again and again throughout the history of software architecture because they provide a useful perspective on organizing code, deployments, or other aspects of architecture. For example, The concept of layers in architecture, separating different concerns based on functionality, is as old as software itself. Yet, the layered pattern continues to manifest in different guises, including modern variants discussed in Chapter 10.

### Big Ball of Mud
Architects refer to the absence of any descernible architecture structure as a <i>Big Ball of Mud</i>, named after the eponymous anti-pattern defined in a paper released in 1997 by Brian Foote and Joseph Yoder:
<i>A Big Ball of Mud is a haphazardly structured, sprawling, sloppy, duct-tape-and-baling-wire, spaghetti-code jungle. These systems show unmistakable signs of unregulated growth, and repeated, expedient repair. Information is shared promiscuously among distant elements of the system , often to the point where nearly all the important information becomes. global or duplicated.

The overall structure of the system may never have been well defined.

If it was , It might have eroded beyond recognition. Programmers with a shred of architectural sensibility shun these quagmires. Only those who are unconcerned about architecture, and, perhaps, are comfortable with the inertia of the day-to-day chore But in the holes in this failing dikes, are  content to work on such systems.
- Briam Foote and Joseph Yoder. </i>

In modern terms, A <i>big ball of mud</i> might describe a simple scripting application with event handles were directly to database calls, with no real internal structure. Many trivial applications start like this, then become unwieldy as they continue to grow. 

In general. Architects Want to avoid this type of architecture at all costs. The lack of a structure makes change in increasingly difficult. This type of architecture also suffers from problems in deployment, stability, scalability and performance 

Unfortunately, this architecture anti-pattern Of course, quite commonly in the real world. Few architects intend to create one, But many projects inadvertently manage to create a mess because of lack of governance around code quality and structure. For example, Neal worked with a client project whose structure appears in next figure:
![A big ball of mud](/images/Architecture/A_big_ball_of_mud.png)

The client (whose name is withheld for obvious reasons) created a Java-based web application as quickly as possible over several years. The technical visualization shows their architectural coupling: each dot on the perimeter of the classes, where bolder lines indicate stronger connections. In this code base, any change to a class makes it difficult to predict rippling side effects to other classes, making change a terrifying affair.

### Unitary Architecture
When software originated, there was only the computer, and software ran on it. Through the various eras of hardware and software evolution, the two started as a single entity, then split as the need for more sophisticated capabilities grew. For example, mainframe computers started as singular systems, then gradually separated data into its own kind of system. Similarly, when personal computers first appeared, much of the commercial development focused on single machines. As networking PCs became common, distributed systems (such as client/server) appeared.

Few unitary architectures exist outside embedded systems and other highly constrained environments. Generally, software systems tend to grow in functionality over time, requiring separation of concerns to maintain operational architecture characteristics, such as performance and scale.

### Client/Server
Over time, various forces required partitioning away from a single system; how to do that forms the basis for many of these styles. Many architecture styles deal with how to efficiently separate parts of the system.

A fundamental style in architecture separates technical functionality between frontend and backend, called a <i>two-tier</i>, or <i>client/server</i>, architecture. Many different flavors of this architecture exist, depending on the era and computing capabilities.

#### Desktop + database server
An early personal computer architecture encouraged developers to write rich desktop applications in user interfaces like Windows, separating the data into a separate database server. This architecture coincided with the appearance of standalone database servers that could connect via standard network protocols. It allowed presentation logic to reside on the desktop, while the more computionally intense action (both in volume and complexity) ocurred on more robust database servers.

#### Browser + web server
Once modern web development arrived, the common split became web browser connected to web server (which in turn was connected to a database server). The separation of responsibilities was similar to the desktop variant but with even thinner clients as browsers, allowing a wider distribution both inside and outside firewalls. Even though the database is separate from the web server, architects often still consider this a two-tier architecture because the web and database servers run on one class of machine within the operations center and the user interface runs on the user's browser.

#### Three-tier
An architecture that became quite popular during the late 1990s was a three-tier architecture, which provided even more layers of separation. As tools like application servers became popular in Java and .NET, companies started building even more layers in their topology: a database tier using an industrial-stength database server, an application tier managed by an application server, frontend coded in generated HTML, and increasingly, JavaScript, as its capabilities expanded.

The three-tier architecture corresponded with network-level protocols such as Common Object Request Broker Architecture (CORBA) and Distributed Component Object Model (DCOM) that facilitated building distributed architectures.

Jus as developers today don't worry about how network protocols like TCP/IP work (they just work), most architects don't have to worry about this level of plumbing into distributed architectures. The capabilities offered by such tools in that era exist today as either tools (like message queues) or architecture patterns (such as event-driven architecture).

##### Three-tier, language design, and long-term implications

During the era in which the Java language was designed, three-tier computing was all the rage. thus, it was assumed that, in the future, all systems would be three-tier architectures. One of the common headaches with existing languages such as C++ was how cumbersome it was to move objects over the network in a consistent way between systems. Thus, the designers of Java decided to build this capability into the core of the language using a mechanism called <i>serialization</i>. Every Object in Java implements an interface that requires it to support serialization. The designers figured that since three-tiered architecture would forever be the architecture style, baking it into the language would offer a great convenience. Of course, that architectural style came and went, yet the leftovers appear in Java to this day, greatly frustrating the language designer who wants to add modern features that, for backward compatibility, must support serialization, which virtually no one uses today.

Understanding the long-term implications of design decisions has always eluded us, in software, as in other engineering disciplines. The perpetual advice to favor simple designs is in many ways defense against future consequences.

### Monolithic Versus Distributed Architectures

Architecture styles can be classified into two main types: monolithic (single deployment unit of all code) and <i>distributed</i> (multiple deployment units connected through remote access protocols). While no classification scheme is perfect, distributed architectures all share a common set of challenges and issues not found in the monolithic architecture styles, making this classification scheme a good separation between the various architecture styles. In this book we will describe in detail the following architecture styles:
*  Monolithic
    - Layered archiecture.
    - Pipeline architecture.
    - Microkernel architecture.
* Distributed
    - Service-based architecture.
    - Event-driven architecture.
    - Space-based architecture.
    - Service-oriented architecture.
    - Microservices architecture.

Distributed architecture styles, while being much more powerful in terms of performance, scalability, and availability than monolithic architecture styles, have significant trade-offs for this power. The first group of issues facing all distributed architectures are described in the fallacies of distributed computing, first coined by L. Peter Deutsch and other colleagues from Sun Microsystems in 1994. A <i>fallacy</i> is something that is believed or assumed to be true but is not. All eight of the fallacies of distributed computing apply to distributed architectures today. The following sections describe each fallacy.

#### Fallacy #1: The Network is Reliable
![The network is reliable](/images/Architecture/Fallacy_1.png)
Developers and architects alike assume that the network is reliable, but it is not. While networks have become more reliable over time, the fact of the matter is that networks still remain generally unreliable. This is significant for all distributed architectures because all distributed architecture styles rely on the network for communication to and from services, as well as between services. As illustrated on above figure, Service B may be totally healthy, but Service A cannot reach it due to a network problem; or even worse, Service A made a request to Service B to process some data and does not receive a response because of a network issue. This is why things like timeouts and circuit breakers exist between services. The more a system relies on the network (such as microservices architecture), the potentially less reliable it becomes.

#### Fallacy #2: Latency is Zero
![Latency is Zero](/images/Architecture/Fallacy_2.png)
As above figure shows, when a local call is made to another component via a method or function call, that time (t_local) is measured in nanoseconds or microseconds. However, when the same call is made through a remote access protocol (such as REST, messaging, or RPC). the time measured to accss that service (t_remote) is measured in milliseconds. Therefore, t_remote will always be greater than t_local. Latency in any distributed architecture is not zero, yet most architects ignore this fallacy, insisting that they have fast networks. Ask yourself this question: do you know what the average round-trip latency is for a RESTful call in your production environment? Is it 60 milliseconds? Is it 500 milliseconds?

When using any distributed architecture, architects must know this latency average. It is the only way of determining whether a distributed architecture is feasible, particularly when considering microservices due to the fine-grained nature of the services and the amount of communication between those services. Assuming an average of 100 milliseconds of latency per request, chaining together 10 service calls to perform a particular business function adds 1,000 milliseconds to the request! Knowing the average latency is important, but even more important is also knowing the 95th to 99th percentile. While an average latency might yield only 60 milliseconds (which is good), the 95th percentile might be 400 milliseconds! It's usually this "long tail" latency that will kill performance in a distributed architecture. In most cases, architects can get latency values from a network administrator (see "Fallacy #6: There Is Only One Administrator").

#### Fallacy #3: Bandwidth Is Infinite
//TODO








## Event-Driven
The event-driven architecture style is a popular distributed asynchronous architecture style used to produce highly scalable and high-performance applications. It is also highly adaptable and can be used for small applications and as well as large, complex ones. Event-driven architecture is made up of decoupled event processing components that asynchronously receive and process events. It can be used as a standalone architecture style or embedded within other architecture styles (such as an event-driven microservices architecture).
Most applications follow what is called a request-based model:
![Request-based model](/images/Architecture/request-based_model.png)
In this model, requests made to the system to perform some sort of action are send to a request orchestrator. The request orchestrator is typically a user interface, but it can also be implemented through an API layer or enterprise service bus. The role of the request orchestrator is to deterministically and synchronously direct the request to various request processors. The request processors handle the request, either retrieving or updating information in a database.
A good example of the request-based model is a request from a customer to retrieve their order history for the past six months. Retrieving order history information is a data-driven, deterministic request made to the system for data within a specific context, not an event happening that the system must react to.
An event-based model, on the other hand, reacts to a particular situation and takes action based on that event. An example of an event-based model is submitting a bid for a particular item within an online auction. Submitting the bid is not a request made to the system, but rather an event that happens after the current asking price is announced. The system must respond to this event by comparing the bid to others received at the same time to determine who is the current highest bidder.

## Chapter 16. Orchestration-Driven service-Oriented Architecture

Architecture styles, like art movements, must be understood in the context of the era in which they evolved, and this architecture exemplifies this rule more than any other. The combination of external forces that often influence architecture decisions, combined with a logical but ultimately disastrous organizational philosophy, doomed this architecture to irrelevance. However, it provides a great example of how a particular organizational idea can make logical sense yet hinder most important parts of the development process.

### History and Philosophy

This style of service-oriented architecture appeared just as companies were becoming enterprises in the late 1990s: merging with smaller companies, growing at a break-neck pace, and requiring more sophisticated IT to accommodate this growth. However, computing resources were scarce, precious, and commercial. Distributed computing had just become possible and necessary, and many companies needed the variable scalability and other beneficial characteristics.

Many external drivers forced architects in this era toward distributed architectures with significant constraints. Before open source operating systems were thought reliable enough for serious work, operating systems were expensive and licensed per machine. Similarly, commercial database servers came with Byzantine licensing schemes, which caused application server vendors (which offered database connection pooling) to battle with database vendors. Thus, architects were expected to reuse as much as possible. In fact, <i>reuse</i> in all forms became the dominant philosophy in this architecture, the side effects of which we cover in "Reuse...and Coupling".

This style of architecture also exemplifies how far architects can push the idea of technical partitioning, which had good motivations but bad consequences.

## Topology

The topology of this type of service-oriented architecture is shown in below figure.
![Topology of service oriented architecture](/images/Architecture/Topology-service-oriented-orquestration-driven.png)

Not all examples of this style of architecture had the exact layers illustrated in this figure, but they all followed the same idea of establishing a taxonomy of services within the architecture, each layer with a specific responsibility.

Service-oriented architecture is a distributed architecture; the exact demarcation of boundaries isn't shown in above figure because it varied based on organization.

## Taxonomy

The architect's driving philosophy in this architecture centered around enterprise-level reuse. Many large companies were annoyed at how much they had to continue to rewrite software, and they struck on a strategy to gradually solve that problem. Each layer of the taxonomy supported this goal.

### Business Services

<i>Business services</i> sit at the top of this architecture and provide the entry point. For example, services like ```ExecuteTrade``` or ```PlaceOrder``` represent domain behavior. One litmus test common at the time - could an architect answer affirmatively to the question "Are we in the business of..." for each of these services?

These service definitions contained no code - just input, output, and sometimes schema information. They were usually defined by business users, hence the name business services.

### Enterprise Services

The <i>enterprise services</i> contain fine-grained, shared implmentations. Typically, a team of developers is tasked with building atomic behavior around particular business domains: ```CreateCustomer```, ```CalculateQuote```, and so on. These services are the building blocks that make up the coarse-grained business services, tied together via the orchestration engine.

This separation of responsibility flows from the reuse goal in this architecture. If developers can build fine-grained enterprise services at just the correct level of granularity, the business won't have to rewrite that part of the business workflow again. Gradually, the business will build up a collection of reusable assets in the form of reusable enterprise services.

Unfortunately, the dynamic nature of reality defies these attempts. Business components aren't like construction materials, where solutions last decades. Markets, technology changes, engineering practices, and a host of other factors confound attempts to impose stability on the software world.

### Application services

Not all services in the architecture require the same level of granularity or reuse as the enterprise services. <i>Application services</i> are one-off, single-implementation services. For example, perhaps one application needs geo-location, but the organization doesn't want to take the time or effort to make that a reusable service. An application service, typically owned by a single application team, solves these problems.

### Infrastructure services

<i>Infrastructure services</i> supply the operational concerns, such as monitoring, logging, authentication, and authorization. These services tend to be concrete implementations, owned by a shared infrasturcture team that works closely with operations.

### Orchestration Engine

The <i>orchestration engine</i> forms the heart of this distributed architecture, stitching together the business service implementations using orchestration, including features like transactional coordination and message transformation. This architecture is typically tied to a single relational database, or a few, rather than a database per service as in microservices architectures. Thus, transactional behavior is handled declaratively in the orchestration engine rather than in the database.

The orchestration engine defines the relationship between the business and enterprise services, how they map together, and where transaction boundaries lie. It also acts as an integration hub, allowing architects to integrate custom code with package and legacy software systems.

Because this mechanism forms the heart of the architecture, Conway's law (see "Conway's law") correctly predicts that the team of integration architects responsible for this engine become a political force within an organization, and eventually a bureaucratic bottleneck.

While this approach might sound appealing, in practice it was mostly a disaster. Off-loading transaction behavior to an orchestration tool sounded good, but finding the correct level of granularity of transactions became more and more difficult. While building a few services wrapped in a distributed transaction is possible, the architecture becomes increasingly complex as developers must figure out where the appropriate trnasction boundaries lie between services.

### Message Flow

All requests go through the orquestration engine - it is the location within this architecture where logic resides. Thus, message flow goes through the engine even for internal calls, as shown on figure below:

![Message Flow](/images/Architecture/Message-flow.png)

In above figure, the ```CreateQuote``` business-level service calls the service bus, which defines the workflow that consists of calls to ```CreateCustomer``` and ```CalculateQuote```, each of which also has calls to application services. The service bus acts as the intermediary for all calls within this architecture, serving as both an integratin hub and orchestration engine.

### Reuse...and Coupling

A major goal of this architecture is reuse at the service level - the ability to gradually build business behavior that can be incrementally reused over time. Architects in this architecture were instructed to find reuse opportunities as aggressively as possible. For example, consider the situation illustrated here:

![Seeking reuse opportunities in service-oriented architecture](/images/Architecture/Reusing-opportunities.png)

In above figure, an architect realizes that each of these divisions within an insurance company all contain a notion of ```Customer```. Therefore, the proper stategy for service-oriented architecture entails extracting the customer parts into a reusable service and allowing the original services to reference the canonical ```Customer``` service, shown in below:

![Building canonical representations in service-oriented architecture](/images/Architecture/Canonical-customer.png)

Here, the architect has isolated all customer behavior into a single ```Customer``` service, achieving obvious reuse goals.

However, architects only slowly realized the negative trade-offs of this design. First, when a team builds a system primarily around reuse, they also incur a huge amount of coupling between components. For example, in above figure, a change to the ```Customer``` service ripples out to all the other services, making change risky. Thus, in service-oriented architecture, architects struggled with making incremental change - each change had a potential huge ripple effect. That in turn led to the need for coordinated deployments, holistic testing, and other drags on engineering efficiency.

Another negative side effect of consolidating behavior into a single place: consider the case of auto and disability insurance in above figure. To support a single ```Customer```service, it must include all the details the organization knows about customers. Auto insurance requires a driver's license, which is a property of the person, not the vehicle. Therefore, the ```Customer```service will have to include details about driver's licenses that the <i>disability insurance division</i> cares nothing about. Yet, the team that deals with disability must deal with the extra complexity of a single customer definition.

Perhaps the most damaging revelation from this architecture came with the realization of the impracticality //TODO
 
## Chapter 17. Microservices Architecture
Microservices is an extremely popular architecture style that has gained significant momentum in recent years. In this chapter, we provide an overview of the important characteristics that set this architecture apart, both topologically and philosophically.

### History
Most architecture styles are named after the fact by architects who notice a particular pattern that keeps reappearing - there is no secret group of architects who decide what the next big movement will be. Rather, it turns out that many architects end up making common decisions as the software development ecosystem shifts and changes. The common best ways of dealing with an profiting from those shifts become architecture styles that others emulate.

Microservices differs in this regard - it was named fairly early in its usage and popularized by a famous blog entry by Martin Fowler and James Lewis entitled "Microservices", published in March 2014. They recognized many common characteristics in this relatively new architectural style and delineated them. Their blog post helped define the architecture for curious architects and helped them understand de underlying philosophy.

Microservices is heavily inspired by the ideas in domain-driven design (DDD), a logical design process for software projects. One concept in particular form DDD, bounded context, decidedly inspired microservices. The concept of bounded context represents a decoupling style. When a developer defines a domain, that domain includes many entities and behaviors, identified in artifacts such as code and database schemas. For example, an application might have a domain called CatalogCheckout, which includes notions such as catalog items, customers, and payment. In a traditional monolithic architecture, developers would share many of these concepts, building reusable classes and linked databases. Within a bounded context, the internal parts, such as code and data schemas, are coupled together to produce work; but they are never coupled to anything outside the bounded context. This allows each context to define only what it needs rather than accommodating other constituents.

While reuse is beneficial, remember the First Law of Software Architecture regarding trade-offs. The negative trade-off of reuse is coupling. When an architect designs a system that favors reuse, they also favor coupling to achieve that reuse, either by inheritance or composition.

However, if the architect's goal requires high degrees of decoupling, then they favor duplication over reuse. The primary goal of microservices is high decoupling, physically modeling the logical notion of bounded context.

## Topology

The topology of microservices is shown here:
![Microservices](/images/Architecture/Microservices_01.png)
As illustrated here, due to its single-purpose nature, the service size in microservices is much smaller than other distributed architectures, such as the orchestration-driven service-oriented architecture. Architects expect each service to include all necessary parts to operate independently, including databases and other dependent components. The different characteristics appear in the following sections.

## Distributed
Microservices form a <i>distributed architecture</i>: each service runs in its own process, which originally implied a physical computer but quickly evolved to virtual machines and containers. Decoupling the services to this degree allows for a simple solution to a common problem in architectures that heavily feature multitenant infrastructure for hosting applications. For example, when using an application server to manage multiple running applications, it allows operational reuse of network bandwidth, memory, disk space, and a host of other benefits. However, if all the supported applications continue to grow, eventually some resources becomes constrained on the shared infrastructure. Another problem concerns improper isolation between shared applications.

Separating each service into its own process solves all the problems brought on by sharing. Before the evolutionary development of freely available open source operating systems, combined with automated machine provisioning, it was impractical for each domain to have its own infrastructure. Now, however, with cloud resources and container technology, teams can reap the benefits of extreme decoupling, both at the domain and operational level.

Performance is often the negative side effect of the distributed nature of microservices. Network calls take much longer than method calls, and security verification at every endpoint adds additional processing time, requiring architects to think carefully about the implications of granularity when designing the system.

Because microservices is a distributed architecture, experienced architects advise against the use of transactions across service boundaries, making determining the granularity of services the key to success in this architecture.

## Bounded Context
The driving philosophy of microservices is the notion of <i>bounded context:</i> each service models a domain or workflow. Thus, each service includes everything necessary to operate within the application, including classes, other subcomponents, and database schemas. This philosophy drives many of the decisions architects make within this architecture. For example, in a monolith, it is common for developers to share common classes, such as `Address`, between disparate parts of the application. However, microservices try to avoid coupling, and thus an architect building this architecture style prefers duplication to coupling.

Microservices take the concept of a domain-partitioned architecture to the extreme. Each service is meant to represent a domain or subdomain; in many ways, microservices is the physical embodiment of the logical concepts in domain-driven design.

### **Granularity**

Architects struggle to find the correct granularity for services in microservices, and often make the mistake of making their services too small, which requires them to build communication links back between the services to do useful work.

<p><i>The term "microservice is a label, not a description.</i></p>
<p align="right">Martin Fowler</p>
In other words, the originators of the term needed to call this new style <i>something</i>, and they chose "microservices" to contrast it with the dominant architecture style at the time, service-oriented architecture, which could have benn called "gigantic services". However, many developers take the term "microservices" as a commandment, not a description, and create services that are too fine-grained.

The purpose of service boundaries in microservices is to capture a domain or workflow. In some applications, those natural boundaries might be large from some parts of the system - some business processes are more coupled than others. Here are some guidelines architects can use to help find the appropriate boundaries:

<i>Purpose</i>

>>> The most obvious boundary relies on the inspiration for the architecture style, a domain. Ideally, each microservice should be extremely functionally cohesive, contributing one significant behavior on behalf of the overall application.

<i>Transactions</i>

>>> Bounded contexts are businss workflows, and often the entities that need to cooperate in a transaction show architects a good service boundary. Because transactions cause issues in distributed architectures, if architects can design their system to avoid them, they generate better designs.

<i>Choreography</i>

>>> In an architect builds a set of services that offer excellent domain isolation yet require extensive communication to function, the architect may consider bundling these services back into a larger service to avoid the communication overhead.

Iteration is the only way to ensure good service design. Architects rarely discover the perfect granularity, data dependencies, and communication styles on their first pass. However, after iterating over the options, an architect has a good chance of refiningh their design.

### **Data Isolation**

Another requirement of microservices, driven by the bounded context concept, is data isolation. Many other architecture styles use a single database per persistence. However, microservices tries to aoid all kinds of coupling, including shared schemas and database uses as integration points.

Data isolation is another factor an architect must consider when looking at service granularity. Architects must be wary of the entity trap (discussed in "Entity trap") and not simply model their services to resemble single entities in a database.
//TODO


## Chapter 24. Developing a Career Path

Becoming an architect takes time and effort, but based on the many reasons we've outlined throughout this book, managing a career path after becoming an architect is equally tricky. While we can't chart a specific career path for you, we can point you to some practices that we have seen work well.

An architect must continue to learn throughout their career. The technology world changes at a dizzying pace. One of Neal's former coworkers was a world-renowned expert in Clipper. He lamented that he couldn't take the enormous body of (now useless) Clipper knowledge and replace it with something else. He also speculated (and this is still an open question): has any group in history learned an thrown away so much detailed knowledge within their lifetimes as software developers?

Each architect should keep an eye out for relevant resources, both technology and business, and add them to their personal stockpile. Unfortunately, resources come and go all too quickly, which is why we don't list any in this book. Talking to colleagues or experts about what resources they use to keep current is one good way of seeking out the latest newsfeeds, websites, and groups that are active in a particular area of interest. Architects should also build into their day some time to maintain breadth utilizing those resources.

### The 20-Minute Rule
//TODO


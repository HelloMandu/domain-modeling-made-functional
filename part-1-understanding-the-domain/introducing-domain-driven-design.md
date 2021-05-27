# Introducing Domain-Driven-Design

- software development "garbage in garbage out" rule applies
    - how to minimize the "garbage in"
    - focused on clear communication and shared domain knowledge
    
## The Importance of as Shared Model

- Obviously our understanding of the problem is incomplete or distorted
- how can we ensure that we, as developers, do understand the problem?
  1. Some software development processes address this by using written specifications or requirements documents to try to capture all the details of a problem (aka A cry of silence)
        - problem: this approach often creates distance between the people who understand the problem
  2. A much better solution is to eliminate the intermediaries and encourage the domain experts to be intimately involved with the development process, introducing a feedback loop between the development team and the domain expert (aka agile)
      - problem: even this approach the developer acts as a translator, translating the domain expert's mental model into code
  3. the source code itself all share the same model?
      - no translation
      - the code is designed to reflect the shared mental model directly
  
- Aligning the software model with the business domain gas a number of benefits
  - faster time to market
  - more business value
  - less waste
  - easier maintenance and evolution
  
- So we need to create a shared model
  - Focus on business events and workflows rather than data structures
  - Partition the problem domain into smaller subdomains
  - Create a model of each subdomain in the solution
  - Develop a common language that si shared between everyone involved in the project and is used everywhere in the code
  

## Understanding the Domain Through Business Events

- A DDD approach to gathering requirements will emphasize building a shared understanding between developers and domain experts

- business events rather than data structure
    - business doesn't just have data
    - Static data--data that is just sitting there unused--is not contributing anything
  
### Using Event Storming to Discover the Domain
- Event Storming: To get all the attendees to participate in posting what they know and asking questions about what they don't know

### Discovering the Domain
- A shared model of the business
    - a key benefit of Event Storming is that the participants develop a shared understanding of the business
    - Event Storming has an emphasis on communication and shared models and avoiding "us" vs "them" thinking
    
- Awareness of all the teams
    - easy to focus on just one aspect of the business but if all the stakeholders are in the room, anyone who is being overlooked can speak out
    
- Finding gaps in the requirements
    - if the question doesn't have a clear answer, then the question itself should be posted on the wall as a trigger for further discussion
    
- Connections between teams
    - The events can be grouped in a timeline, which often makes it clear that one team's output is another team's input
    
- Awareness of reporting requirements
    - it's easy to focus only on processes and transactions when trying to understand the domain
    - any business needs to understand what happened in th past--reporting is always part of the domain
  
### Expanding the Events to the Edges
- To start, you might ask if any events occur before the leftmost event
- we might extend the events on the shipping side of the business
- Extending the events out as far as you can in either direction is another great way of catching missing requirements

### Documenting Commands
- For example, the customer wanted us to receive an order form, or your boss asked you to do something. We call these requests commands in DDD terminology
- Commands are always written in the imperative
- An event triggers a command, which initiates dome business workflow. The output of the workflow is come more events
- This way of thinking about business processes--a pipeline with an input and some outputs--is an excellent fit with the way that functional programming works
- By the way, not all events need be associated with a command. Some events might be triggered by a scheduler or monitoring system

### Partitioning the Domain into Subdomains
- The big picture is still quite chaotic. We'll have to tame it before we start writing any code
- When faced with a large problem, it's natural to break it into smaller components that can be addressed separately
- We all Know what a "domain expert" is; as programmers we ourselves are often experts in a number of domains // game, web, network, language

### Creating a Solution Using bounded Contexts
- Understanding the problem doesn't mean that building a solution is easy
- We should only capture the information that is relevant to solving a particular problem
- We therefore need to create a distinction between a "problem space" and a "solution space", and they must be treated as two different things
- To build the solution we will create a model of the problem domain

- subdomain -> bounded contexts
  - why context?
    - each context represents some specialized knowledge in the solution
    - information taken out of context can be confusing or unusable
  - why bounded?
    - In the world of software we want to reduce coupling between separate subsystems so that they can evolve independently
    - can do this using standard software practices // explicit APIs between subsystems, avoiding dependencies such as shared code
    - domain model will never be as rich as the real world, but tolerate this in exchange for less complexity and easier maintenance
  
- domain and bounded context does not always 1:1 relationship, possible 1:N || N:1
- It's important that each bounded context have a clear responsibility

### Getting the Contexts Right
- one of the important challenges of a domain-driven design is to get these context boundaries right
- Listen to the domain experts
- Pay attention to existing team and department boundaries
- Don't forget the "bounded" part of a bounded context (aka Good fences make good neighbors)
- Design for autonomy, If thw groups contribute to the same bounded context, they might end up pulling the design in different directions as it evolves
- Design for friction-free business workflows, always focus on business and customer value rather than any kind of "pure" design

### Creating Context Maps
- It focuses only on the main routes so that you can plan your journey
- Context map shows the various bounded contexts and their relationships at a high level. The goal is not to capture every detail but to provide a view of the system as a whole

### Focusing on the Most Important Bounded Contexts
- Generally, some domains are more important than others. These are the core domains--the ones that provide a business advantage, the ones that bring in the money
- It is important to prioritize and not to attempt to implement all the bounded contexts at the same time--the often leads to failure
- Focus instead on those bounded contexts that add the most value, and then expand from there

### Creating a Ubiquitous Language
- Code and the domain expert must share the same model
- We should not have things in our design that do not represent something in the domain expert's model
- The language that defines the shared mental model for the business domain. this language should used everywhere in the project
- The construction of the ubiquitous language is not a one-way process dictated by the domain expert, it is a collaboration between everyone on the team

### Wrapping Up
- Focus on events and processes rather than data
- Partition the problem domain into smaller subdomains
- Create a model of each subdomain in the solution
- Develop an "everywhere language" that can be shared between everyone involved in the project
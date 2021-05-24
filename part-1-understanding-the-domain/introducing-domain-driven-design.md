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
    

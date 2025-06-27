2100180234920644631Common Models Internal Contract.drawio33https://orignals.atlassian.net/wikiCommon Models Internal Contract.drawio01285809

 **Canonical Data Model (CDM)**  pattern, which is a specialized form of the  **Enterprise Integration Pattern** . Here's how it fits:


### 🧩  **Canonical Data Model (CDM) Pattern** 
This pattern introduces a  **common, standardized data format** , the  _Common Library Models_ —to mediate communication between disparate systems.

 **Key characteristics in your diagram:** 


* Each external system has its own  **Data Access Layer (DAL)**  that maps to the  **Common Model** .


* Internal services (like  _Business Logic Service_ ) consume and produce data in this shared format.


* The  **Common Library Models**  (e.g., DTOs for user, time/date, business) act as the canonical schema.



 **Benefits:** 


* Reduces point-to-point transformations.


* Promotes consistency and reuse.


* Simplifies onboarding of new systems.




### 🧱 Supporting Patterns Also Present:

*  **Adapter Pattern** : Each DAL acts as an adapter, translating external formats into the common model.


*  **Layered Architecture** : Clear separation between external interfaces, business logic, and shared models.


*  **Shared Kernel (from Domain-Driven Design)** : The Common Library Models represent a shared kernel used across bounded contexts.







*****

[[category.storage-team]] 
[[category.confluence]] 

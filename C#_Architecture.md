## Architecture

- Api
    - Controllers 
- Core
    - Domain
        - what problem we are solving ? 
        - Business Models (Prodcut, Order)

    - Application
        - Domain Entity interation with infra layer
        - Services, DTOs (application and api), Validators

- Infrastructure
    - Repo for data access


## My project struct CQRS 
- Controller 
- using Mediater call the method 
- in applciation feator the mediader resolve the query and send to respect repo
- Repo using dbcontext and mapper map to the dto and send back to user

- For Mediater i think we inherit IRequest
- Also use IRequestHandler
 
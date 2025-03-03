## CQRS
- Seperate Read and Write models 
- For Read use DTOs

- C : Command (Update model in db)
- Q : Query (Read from db)

## Why : 
- Upadate and Read need different optimization
- Update need validation
- Read does not need all the data 


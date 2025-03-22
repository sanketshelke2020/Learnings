## Unit of work yt

Create Solution

3 Projects : 
API : Endpoint (Api project)
Domain : Logical business (Class Library)
DataAccess : Repo (Class Library)

```
- Add data directly in db context 
OnModelCreating (ModelBuilder builder)
builder.entity<Actro>.HasData(){
    new Actor{id=1, name = 3}
}

```
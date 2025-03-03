## Typescript 
- Add type to javascript
- name : string = "hello"

```
# Javascript 
const user = {
    name : "Ket", 
    id : 3,
}

#Typescript 

interface User {
    name : string;
    id : int;
}

const user : User {
    name : "Ket",
    id : 3,
}
```

## Composing Types 

- Combining types

```
type MyBool = true |  false ;
type WindowStates = "open" | "closed" | "minimized";

function getLength(obj: string | string[]) {
  return obj.length;
}
```

type StringArray = Array<string>;
type NumberArray = Array<number>;
type ObjectWithNameArray = Array<{ name: string }>;

## Decorater
- Its like [httpget] in c#
- [Authorize]


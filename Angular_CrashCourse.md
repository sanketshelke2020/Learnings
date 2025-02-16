# Angular Crash Course 

# Intro
- Single Page Application
- Build by Google 

# Benefits 
- Faster Development
- CLI
- Unit-test ready

# Angular vs React 
- Framework
- React => Library
- React require installation
- No CLI React

# Core Concepts
- Components, Services
- Directive, Pipes
- Data-Binding, Event Handler
- Http Module, Form Module
- Routing, Animations
- Testing and Prod

# Creating Angular App 

```
- npm install -g @angular/cli
- ng --version
- ng new first-ng-app
- ng new first-ng-app --inline-style --inline-template
```

# Flow
- Start => index.html

# Components
- Header component 
- Home component

Create Componets
```
ng g c header 
ng g c components/header  # inside component folder
```

# How to render component
- app.components => add ur component in imports
- any component if u wanna use another components add inside imports
- use componentes in template

# Data-Binding
- signal 
- without signal 
- suggested use signals


```
# without signal
var title = "hello"
{{ title }}

# with signal 
var title = signal("hello")
{{ title() }}

```

# Passing value from parent component to child component

```
message = input("Hello hello")
# message = input().required;

<app-greeting message = "Hello world">
<app-greeting [message] = "{{message}}">
[] for message need javascript if not then string

```

# Event Listners

```
 <input (keyup) = "keyuphandler()" />
 <input (keyup) = "keyuphandler($event)" />

 keyuphandler(event: KeyupEvent){

 }

```

# Routing

- If other pages add routing 
- Create other page in seperate folder

- app.routes.ts
- path and loadcomponents 
- refer google for roruting code

router-outlet import
routerlink="/todos"

# Angular Services
- Data, Http calls, not related to rendering

```
ng g service services/todos
```

provider : 'root' 
provide service in all componentes

todoService = Inject(toservice)
ngOnit = 

# Http APi call 

- App.config.ts => provideHttpClient()
- http = inject(HtttpClient);

# Directives
- Addition Behavious

Type 
- componets
- Attribute 
- Structural

```
ng g directive directives/highlight-complete-todo
```
*ngIf

now 
```
@if(){

}
```

# Pipes

Usefull for : 
| uppercase
currency 
date 
time 

we can create
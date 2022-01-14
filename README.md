# Back-end-Test

### Challenge

| Basically, the challenge is to create two simple microservices with REST API and the microservices needs to communicate

### Requirements
- Microservice needs to be do in NodeJS
- Typescript
- MongoDB

_The communication between microservices you can do how you prefer_



## Project details

The project objective is to create a simple group of TODO Lists

### Microservice #1 - `task`

The first microservice needs to be a CRUD of TODO List (called as tasks).

You can follow the model below
```ts
type Task = {
    title: string;
    project: ObjectId & Ref<Project>;
    status: 'PENDING' | 'DONE';
    createdAt: Date;
    updatedAt: Date;
}
```

### Microservice #2 - `project`

The second microservices needs to be a CRUD of tasks group (called as project), but, you need to create one route to get tasks of the project.

And create another route to get all projects with their child tasks (using aggregate)

You can follow the model below
```ts
type ProjectWithTasks = {
    title: string;
    tasks: Task[];
    completedTasks: number;
    createdAt: Date;
    updatedAt: Date;
}
```
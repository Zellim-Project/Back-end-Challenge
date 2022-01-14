# Zellim Backend Challenge

### Challenge

| Basically, the challenge is to create two simple microservices with REST API and the microservices has to communicate with each other

### Requirements
- Microservice needs to be do in NodeJS
- Typescript
- MongoDB
- Docker
- Tests
- CI/CD (CircleCI or Github Actions)
- Upload to one Cloud Service (AWS, GCP, Azure, Vercel, OVH)

_The communication between microservices you can do however you prefer_

## Project details

The project objective is to create a simple group of TODO Lists

### Microservice #1 - `task`

The first microservice needs 

- CRUD of TODO List (called as tasks)
- One route to bulk edit
- One route to bulk delete

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
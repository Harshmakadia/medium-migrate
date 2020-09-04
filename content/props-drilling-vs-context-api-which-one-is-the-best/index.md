---
title: "Props drilling v/s Context API which one is the best"
description: "Is shortcut i.e context API only the best?"
date: "2020-09-04T10:10:49.397Z"
categories: []
published: false
---

  

Is shortcut i.e context API only the best?

React was initially released in 2013 and one thing that hasn’t changed so far is the way data is passed with props in the nesting level. But the good news is there are some other ways in which data can be passed to the child from the parent. Context API is especially useful when you have multiple levels of the nested child. 

Let’s start with the basics to get more ideas about it. 

### What is Props?

React is a library which helps us divide the UI into small reusable pieces which we call it as a component. In order to pass data between the components, we make use of Props. Data is passed to the component with the help of props.   
Thus props help us pass the data from one component to another.

Now the data in props are read-only meaning it cannot be changed by the child who is consuming the data. Thus it is a unidirectional flow. (one way from parent to child). We can however pass data from child to parent making use of the function passing it via props. 

### What is Prop drilling?

Prop drilling refers to the passing the data from parent to all the nested child in the React Tree. Let’s look at the diagram above how data has to be passed from parents to all its child.

  

### When can prop drilling cause a problem?

**1\. Updating data format**  
Let’s assume that you passed data to the nested child and now you want to refactor the data that is passed for example 

```
<Profile user="Harsh">
```

Let’s assume that we now need to pass an object as we also need to pass profile status if it’s expired or not. so here is how the component will look like

```
<Profile user={"name": "Harsh", "status": "Expired"}
```

During such cases, you have to change the data format which is accessed by each of them.

**2\. Renaming props  
**Let assume that later in the state of application there comes a time to rename the prop as you are removing some data or passing more. It has to be changed at all the places down the hierarchy.

Let’s take a look at how we can solve this problem by making use of React Context.

### React Context

Context provides an awesome way to pass data through the component tree without having to pass props down manually at every level in your application.

![](./asset-1.png)

### Context has 3 main blocks:

#### Context Object

You can define the Context object in a separate file or right next to a component in a component file if you wish. Having multiple contexts within the component is also possible. Thus you can store any data you want in the context object which will be accessed globally in your application.

#### Context Provider

The provider provides the values in all the components within the application that needs to access this context object.

Context Consumer  
  

### When can context API cause a problem?

1.  **Unnecessary re-rendering in Application  
    **Though context API seems to be an amazing feature overusing it might lead to unnecessary re-rendering in your application whenever the state of the provider changes it will re-render all it’s the child no matter even if they are customing the data from the provider or not. 

  

When to use

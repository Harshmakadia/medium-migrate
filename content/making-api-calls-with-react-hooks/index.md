---
title: "Making API calls with React Hooks"
description: "With the new updates coming up in the React library, it’s indeed impossible to use all the new React features in your application. It’s…"
date: "2019-08-05T14:06:20.461Z"
categories: []
published: true
canonical_link: https://medium.com/@MakadiaHarsh/making-api-calls-with-react-hooks-748ebfc7de8c
redirect_from:
  - /making-api-calls-with-react-hooks-748ebfc7de8c
---

With the new updates coming up in the React library, it's indeed impossible to use all the new React features in your application. It’s been 6 months since the official release of React Hooks which was released with React 16.8.0 (February 6, 2019)

This article will help you take the baby steps in using React Hooks, it will explain all the basic approach which you can take to make the most out of this beautiful feature.

![React Hooks \[ Icon Credit — [wanicon](https://www.flaticon.com/authors/wanicon), [freepik](https://www.freepik.com/) \]](./asset-1.jpeg)

Let’s start with Quick Introduction to React Hooks

Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work in classes — they let you use React without classes.

#### useState 😄

`useState` is a _Hook,_ We call it inside a function component when we want to add some local state to it. The good thing about this is that the state will be preserved during re-rendering.

`useState` returns a pair: the **_current state value_** and a **_function_** that lets you update your component. Calling a function will work similarly to `this.setState` where it will update the values of the state, except it will not merge old and new state.

#### useEffect 😄

The Effect Hook, `useEffect` adds the ability to perform side effects from a function component.

The purpose of useEffect is similar to the purpose of Lifecycle methods in the class component like `componentDidMount` , `componentDidUpdate` and `componentWillUnMount`

You can also decide when to re-render. Consider below the example where we have passed a count array after the useEffect.

```
useEffect(() => {
  document.title = `You clicked ${count} times`;
}, [count]); // Only re-run the effect if count changes
```

Let’s consider if the count value is 60 and if the component re-renders with the count value being unchanged i.e. 60, React will compare the previous render value and decide whether to call effect or not. If values are different then only the effect is called. Now that’s a way to increase performance and avoid unnecessary calls. 💯 🚀

If there are multiple items in the array, React will re-run the effect even if just one of them is different.

---

#### Converting Class Component into a Functional Component with Hooks ⚖️

Let’s look at the example of how we can get the same behavior as a class component in a function component using Hooks.

**_Example:_** Consider an example where you need to make API calls and fetch the data and populate in our component and clicking on the _load_ more button would fetch more data from the server.

Until the Release of React 16.8.0(Hooks), it wasn't possible to achieve these using functional components as lifecycle methods aren’t accessible in the functional component and it wasn’t possible to manage the state inside a functional component.

For making API calls we will use Github APIs [https://developer.github.com/v3/search/#search-commits](https://developer.github.com/v3/search/#search-commits)

Here is what a typical React code looks like for both ordinary class component and functional component using Hooks.

![API call code \[ Icon Credit — R[oundicons](https://www.flaticon.com/authors/roundicons) \]](./asset-2.png)

Whenever API calls are involved we need multiple state values —

-   Holding that data that is to be rendered
-   Page count to make API call
-   Loading state (show loading screen/component until the data is received from server)
-   Error state (show error message when something goes wrong while fetching data)

Thus above image with Class component and the functional component does the same thing of loading the commits from the Github. Thus this simple example will help you understand how easy it is to start using hook into your application. With hooks, you can use write code neatly and sort.

![API Calls with React Hooks](./asset-3.gif)

---

**Code Snippet  
 —** Class Component API calling Code

— Hooks API calling Code

**Links to Live Demo**

[**Class Component API calls - CodeSandbox**  
_CodeSandbox is an online editor tailored for web applications._codesandbox.io](https://codesandbox.io/embed/class-component-api-calls-bwg4n "https://codesandbox.io/embed/class-component-api-calls-bwg4n")[](https://codesandbox.io/embed/class-component-api-calls-bwg4n)

[https://codesandbox.io/s/functional-component-api-calls-qgho3](https://codesandbox.io/s/functional-component-api-calls-qgho3)

---

Here are the rules you should keep in mind while working with React Hooks

1.  Don’t try to convert the old code written in class components into Hooks. However, it is recommended you can try using Hooks in the new implementation
2.  [useState](https://reactjs.org/docs/hooks-overview.html#state-hook) and [useEffect](https://reactjs.org/docs/hooks-overview.html#effect-hook) are the two new concepts which you should know to master Hooks
3.  Only call Hooks **at the top level**. Don’t call Hooks inside loops, conditions, or nested functions.
4.  Only call Hooks **from React function components**. Don’t call Hooks from regular JavaScript functions.

Thus this is how React Hooks can be useful in making API calls, sometimes we have to convert a functional component into a class component only because of not being able to manage the state inside the functional component.

**Reference**  
\- [https://reactjs.org/](https://reactjs.org/)

Happy Learning 💻 😄

---

#### THE PLATFORM FOR COMPONENT DRIVEN DEVELOPMENT

If building with React, try [**Bit**](https://bit.dev) — the platform for modern components.



It makes it easy & simple to build modular components, reuse them with your team and between applications, collaborate on updates, and stay in sync.

Bit helps teams make sure they can reuse components together, share them between projects, and always keep everything consistent for users. If your team is seeking a way to share components or working on a great UI library, you should definitely check out Bit — and [try it](https://bit.dev) for free.

[**teambit/bit**  
_Documentation \* Tutorials \* Quick start guide \* Workflows \* bit.dev components cloud \* Video demo Bit is an open-source…_github.com](https://github.com/teambit/bit "https://github.com/teambit/bit")[](https://github.com/teambit/bit)

---

### Related Stories

[**5 Tools for Faster Development in React**  
_5 tools to speed the development of your React application, focusing on components._blog.bitsrc.io](https://blog.bitsrc.io/5-tools-for-faster-development-in-react-676f134050f2 "https://blog.bitsrc.io/5-tools-for-faster-development-in-react-676f134050f2")[](https://blog.bitsrc.io/5-tools-for-faster-development-in-react-676f134050f2)

[**11 React UI Component Playgrounds for 2019**  
_Useful online playgrounds and editors for your UI components_blog.bitsrc.io](https://blog.bitsrc.io/11-react-ui-component-playgrounds-for-2018-eef5a87a1bf8 "https://blog.bitsrc.io/11-react-ui-component-playgrounds-for-2018-eef5a87a1bf8")[](https://blog.bitsrc.io/11-react-ui-component-playgrounds-for-2018-eef5a87a1bf8)

[**How to Easily Share and Consume React Components Using Bit**  
_Learn how to easily create, share and consume react components with the awesome power of Bit_blog.bitsrc.io](https://blog.bitsrc.io/how-to-easily-share-and-consume-react-components-using-bit-f53fb9463105 "https://blog.bitsrc.io/how-to-easily-share-and-consume-react-components-using-bit-f53fb9463105")[](https://blog.bitsrc.io/how-to-easily-share-and-consume-react-components-using-bit-f53fb9463105)

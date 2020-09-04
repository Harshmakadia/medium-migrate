---
title: "Yes, you are right you can return an array of components like you mention <tr> tag with React15."
description: "This was not possible in React15 since you need a parent wrapper to this two different blocks."
date: "2018-09-15T05:27:26.665Z"
categories: []
published: true
canonical_link: https://medium.com/@MakadiaHarsh/yes-you-are-right-you-can-return-an-array-of-components-like-you-mention-tr-tag-with-react15-665a1805d1ee
redirect_from:
  - /yes-you-are-right-you-can-return-an-array-of-components-like-you-mention-tr-tag-with-react15-665a1805d1ee
---

Yes, you are right you can return an array of components like you mention <tr> tag with React15.   
In React15 it was not possible to keep two divs without wrapping it in parent component. It would throw an error.  
For example,  
Consider the render part of the component as below

```
render(){
 return(
  <div className="block-1" key="block1"> I'm block 1 </div>
  <div className="block-2" key="block2"> I'm block 2 </div>
 )
}
```

This was not possible in React15 since you need a parent wrapper to this two different blocks.

But with React16 you can pass an array in render and achieve this

The syntax would be,

```
render(){
 return[
  <div className="block-1" key="block1"> I'm block 1 </div>,
  <div className="block-2" key="block2"> I'm block 2 </div>
  ];
 )
}
```

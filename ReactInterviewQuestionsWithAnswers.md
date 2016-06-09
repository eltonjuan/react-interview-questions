# React Interview Questions

This is a collection of general questions about React that can be used when interviewing a candidate claiming React experience. Most of these questions are pulled directly from the React documentation and are questions that I feel every React developer should know the answer to. 

- Why might you use `react.cloneElement` when building an application?
- Explain the concept of ownership in React
  - In React, an owner is the component that sets the `props` of other components. More formally, if a component `X` is created in component `Y`'s `render()` method, it is said that `X` is owned by `Y`.
- How would a parent programatically reference its child components
  - `this.props.children`
- Can you manipulate `this.props.children`? If so, how? 
  - Yes. Use the `React.Children` utilities
- What is the `key` attribute used for?
  - It is useful when you have a list of components (e.g. search results) where the identity and state of each child must be maintained across render passes
- How do you tell React to skip the processing of a sub-tree when it is rendering? 
    - Override `shouldComponentUpdate` and return `false`
- Explain the concept of `propTypes`
  - `React.propTypes` exports a range of validators that can be used to make sure the data you receive is valid.
  - `propTypes` is only checked in development mode
- Why might you use a mixin? 
  - Sometimes very different components share common functionality. (e.g. setTimeout that taps into lifecycle methods to register and clear timeouts)
- When is the `...` (Object Rest Spread) syntax useful?
  - Tranferring props (i.e. `<Component {...this.props} more="values" />`
- Name two ways you can find a component once it has been mounted to the DOM.
  - `ReactDOM.findDOMNode` 
  -  Attach a `ref` to the DOM node
  - Should you use `findDOMNode`? No, probably not. 
- How would you render React components in a server environment? 
  - `ReactDOM.renderToString`
- When might you use `refs`?
  - Provide references to backing instances 
  - Refs are the only practical way of performing DOM measurements
  - Generally, you shouldn't use `refs` but rely on reactive data flow to make things happen in your application. 

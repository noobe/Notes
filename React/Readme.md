React:
- React is a Javascript library for building UI

Components:
- React Apps are made up of components
- A component is is a peice of UI that has its own logic and appearnace.
- A component can be as small as a button and as large as a page.

Component Code:
- A React Component is a function that returns markup.
- The important thing to note here is all component names should start with Caps while all native html elements should be in small letters.
- Another important thing is that the component can not return multiple sibling elements - it should return only one element that can have levels of nesting inside.
- This often leads to un-necessary containers in code and React provides fragments to avoid it.
- The fragement tags <></> gets removed while rendering.
```js
const MyComponent = () => <h1>Hello World!</h1>;

const MyComplexComponent = () => <div>
  <h1>Hello World!</h1>
  <p>How are you</p>
</div>;

const MyComplexComponentWithFragment = () => <>
  <h1>Hello World!</h1>
  <p>How are you</p>
</>;
```

Adding Component to a page:
- React components can be added into any HTML page by using the render method of the  ReactDOM library OR by using createRoot method in ReactDOM(latest way).
```html
<div id="root"></div>
```
```js
ReactDOM.render(<Component />, document.getElementById('root'));

// OR

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Component />);
```


Props:
- Props stands for properties and they are values that we pass into the component while invoking it.
```js
const MyComponent = (props) => <h1>{props.text}!</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Component text="Hello World"/>);
</>;
```

Nesting Component:
React allows us to create components of all sizes, hence the best appraoch is to create 
components for each entity in the page and then grouping them together to form the page (view)
```js
const Content = () => <h1>Hello World!</h1>;
const Page = () => <div>
  <Content />
</div>;
```

JSX:
JSX stands for Javascript as XML
Its a stricter version of HTML hence all tags should either be self closing or should have corresponding closing tag. Eg: `<br />`
Since JSX gets converted to JS, some of the html attribute that has same name as JS keywords, are replaced. Eg: `className` instead of 'class', `htmlFor` instead of 'for' (label attribute)

Styling:
Like in regular HTML, we can add styles as inline or as independent css.
```js
// Inline
const Content = () => (
  // Properties are comma separated and ppty names are in camel case
  <div style={{ color: red, backgroundColor: blue }}>
    Hello World!
  </div>
);

// Independent CSS
const Content = () => (
  // Assing a css class and define it in the css file
  <div className='content'>
    Hello World!
  </div>
);
```

Displaying data (Templating)
JSX allows us to embed markup in JS, and using curly braces allows us to escape back into JS.
Hence we can use it to run JS code in between markup.
It could be variables, function calls, conditionals, looping constructs
```js
const pptys = {
  color: 'red',
  bgColor: 'blue',
  title: 'Test',
  values: ['ABC', 'DEF', 'GHI'],
  isValueVisible: true,
  details: 'shdjashdjshdsjadhjsahdasj',
  isDetailsVisible
};
const Content = () => (
  <div style={{ color: pptys.color, backgroundColor: pptys.bgColor }}>
    {pptys.title}
    {pptys.isValueVisible ?
      <ul>
      {pptys.values.map(item => <li key={item}>{item}</li>)}
      </ul>
      :
      <h3>Not visible</h3>
    }
    {isDetailsVisible && <p>{pptys.details}</p>}
  </div>
);
```


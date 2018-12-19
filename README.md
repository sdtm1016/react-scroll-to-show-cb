# react-scroll-to-show-cb

React component that fires a callback when the wrapped dom scroll into the visible area

## install
```npm
npm install react-scroll-to-show-cb --save
```
## usage
support:  
  - Before React v16.0 
  - After React v16.0 
  - preact (preact-compat) - need to set alias: **react** -> **preact-compat** , **react-dom** -> **preact-compat** 

```javascript

import React from 'react';
import ReactDOM from 'react-dom';
import ReactScrollToShowCb from'react-scroll-to-show-cb';

class App extends React.Component {
    
    render() {
        return <div>
            <ReactScrollToShowCb scrollToShowCb={this.handleShow} once={true} wait={500}>
                <div>1</div>
                <div>2</div>
                <div>3</div>
                <div>4</div>
                <div>5</div>
                <div>6</div>
                <div>7</div>
            </ReactScrollToShowCb>
        </div>
    }

    handleShow(index, dom) {
        console.log(`index: ${index}`);
        console.log('dom:', dom);
    }

}


ReactDOM.render(<App />, document.body);

```

## run the example
```npm
npm install --save
npm run dev
```
The demo app is running at  [http://localhost:8080](http://localhost:8080).

## API
```javascript
<ReactScrollToShowCb
    scrollToShowCb={(index, dom) => {}} 
    once={Boolean} 
    update={Boolean}
    wait={Number}> 
    {children}     
</ReactScrollToShowCb>
```

#### scrollToShowCb

**required**

When the wrapped children are scrolled into visible view, this callback function will be triggered with two parameters : the index of the child and the dom of the child.

#### update

**default:false**

When set to true, **the change of child's count** will trigger the update of **react-scroll-to-show-cb** so that when the new children scroll into view , the callback will also be triggered.

#### once

**default: false** 

When set to true, every time the dom showed, the callback will be triggered.


#### wait

**default: 500**

The throttle wait time for the callback.

#### children

**required**

- HTML elements, such as `div`, `p`, `section` , are supported.

- **Class react component** is supported.

- **Functional react component** is **not** supported.

- If given an Array, every element of the array should be the same type(the same html element or the same react component);













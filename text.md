#### 下面代码分别使用 ES5 和 ES6 来表示react的引用、导出、以及定义组件。
#### 引用
在ES5里，如果使用CommonJS标准，引入React包基本通过require进行，代码如下:

```js
//ES5
var React = require("react");
var {
   Component,
   PropTypes
} = React;  //引用React抽象组件

var ReactNative = require("react-native");
var {
   Image,
   Text,
} = ReactNative;  //引用具体的React Native组件
```
在ES6里，import写法更为标准，代码如下:
```js
import React, {
    Component,
    PropTypes,
} from 'react';
import {
    Image,
    Text
} form 'react-native'
```
#### 导出单个类
在ES5里，要导出一个类给别的模块用，一般通过module.exports来导出，代码如下:
```js
//ES5
var MyComponent = React.createClass({
     ...
});
module.exports = MyComponent;
```js
在ES6里，通常用export default来实现相同的功能,代码如下:
```js
export default class MyComponent extends Component{
     ...
}
```
引出的时候如下:
```js
//ES5
var MyComponent = require("./MyComponent");
//ES6
import MyComponent from "./MyComponent";
```
#### 注意导入和导出的写法必须配套，不能混用!

#### 定义组件
在ES5里，通常通过React.creactClass来定义一个组件类，如下:
```js
//ES5
var Phote = React.createClass({
   render: function() {
    return (
     <Image source={this.props.source} />
    );
  },
});
```
在ES6里，我们通过定义一个继承自React.Component的class来定义一个组件类，如下:
```js
//ES6
class Photo extends React.Component {
  render(){
    return (
     <Image source={this.props.source} />
    );
  }
}
```


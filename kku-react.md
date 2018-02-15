# KKU React

### Let's create new Simple HTML
```html
<html>
    <head></head>
    <body>
        <app id="root"></app>
    </body>
    <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
    <script src="index.js"></script>
</html>
```

### Hello World :)
```js
class Hello extends React.Component{
    render(){
        return React.createElement('div', null, `Hello ${this.props.name}`);
    }
}

ReactDOM.render(
    React.createElement(Hello, {"name":"Tossapon"}, null),
    document.getElementById('root')
);
```


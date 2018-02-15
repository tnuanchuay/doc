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

### Hello ...
```js
class App extends React.Component{
    onInputNameChange(text, t){
        var value = document.getElementById("name").value;
        document.getElementById("welcomeText").innerHTML = "Hello " + value;
    }

    render(){
        var name = React.createElement('input', { id: "name", "type":"text", onChange:this.onInputNameChange});
        var welcomeText = React.createElement('div', { id: "welcomeText"}, `Hello ...`);
        return React.createElement('div', null, [name, welcomeText]);
    }
}

ReactDOM.render(
    React.createElement(App, null, null),
    document.getElementById('root')
);
```

### Hello with State
```js
class App extends React.Component{
    constructor(){
        super();
        this.state = {}
    }

    onInputNameChange(){
        var name = document.getElementById("name").value;
        this.setState({guestName:name});
    }

    render(){
        var name = React.createElement('input', { id: "name", key: "name", "type":"text", onChange:this.onInputNameChange.bind(this)});
        var welcomeText = React.createElement(WelcomeText, { key: "welcomeText", guestName:this.state.guestName }, null);
        return React.createElement('div', null, [welcomeText, name]);
    }
}

class WelcomeText extends React.Component{    
    render(){
        if(this.props.guestName)
            return React.createElement('div', { id:"welcomeText" }, `Hello ${this.props.guestName}`);
        else
            return "";
        
    }
}

ReactDOM.render(
    React.createElement(App, null, null),
    document.getElementById('root')
);
```

### References
- https://reactjs.org/docs/cdn-links.html
- https://reactjs.org/docs/react-api.html

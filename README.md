<p align="center"><img src="https://raw.githubusercontent.com/joon610/react-prism-ui/main/logo.svg"></p>

<p align="center">
  <!-- <a href="https://github.com/arvindra1/react-prism-ui><img src="https://github.com/joon610/react-prism-ui/workflows/React%20Card%20Component%20CI/badge.svg" alt="Build Status"></a>
  <a href="https://github.com/joon610/react-prism-ui"><img src="https://cdn.jsdelivr.net/gh/nikku/works-on-my-machine@v0.2.0/badge.svg" alt="myPc"></a>
  <a href="https://github.com/joon610/react-prism-ui"><img src="https://img.shields.io/badge/license-MIT-lightgrey.svg" alt="license"></a> -->
</p>

<h1 align="center">react-prism-ui</h1>

## Don't Support this package

## License

- MIT License

## Install

```
  npm i react-prism-ui
```

## CARD-1

## `Props`

### glass, glassOption

```js
  import { Card } from 'react-prism-ui';

  // default blur:4, transparency:0.2
  const NewCard = () => <Card glass><div>HelloWorld</div></Card>);

  const NewCard = () => <Card glass glassOption={{blur:5,transparency: 0.1}}><div>HelloWorld</div></Card>);
```

### style

```js
  import Card from 'react-prism-ui';
  const NewCard = () => <Card style={{"color":"red"}}><div>HelloWorld</div></Card>);
```

### background

```js
  import Card from 'react-prism-ui';
  const NewCard = () => <Card background={"red"}><div>HelloWorld</div></Card>);
```

### hoverType

```js
  type hoverMoveType = 'up' | 'left' | `right` | `down` | 'zoom'

  import Card from 'react-prism-ui';
  const NewCard = () => <Card hoverType={"zoom"}><div>HelloWorld</div></Card>);
```

### bordered

```js

  import Card from 'react-prism-ui';
  const NewCard = () => <Card bordered><div>HelloWorld</div></Card>);
```

### outlined

```js

  import Card from 'react-prism-ui';
  const NewCard = () => <Card outlined><div>HelloWorld</div></Card>);
```

## ColorPallets

## ColorProvider

```js
import { ColorProvider } from "react-prism-ui";

// default blur:4, transparency:0.2
const App = () => {
  <ColorProvider>
    <Layout />
  </ColorProvider>;
};
```

### useColor()

```js
import { useColor, Card } from "react-prism-ui";

const component = () => {
  const { color, handleColorChange } = useColor();

  return (
    <div className={` bg-gradient-t from-[${color.colors[1]}] to-[${color.colors[0]}] transition-all duration-400`}>

     {Array.from({length:5}).map(_, index)=><Card key={index} onMouseEnter={()=>handleColorChange()}>}
    </div>
  )
};
```

## Hover-Bg 

### Index.js
```bash
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import { ColorProvider } from 'react-prism-ui';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <ColorProvider>
    <App />
    </ColorProvider>
  </React.StrictMode>
);
reportWebVitals();
```

### App.js
```bash
import './App.css';
import { Card, ImageMag, useColor } from 'react-prism-ui';

function App() {
  const { color, handleColorChange } = useColor();
  return (
    <div className='h-screen'>
      <div style={{ width: 'calc(100% + 4rem)', transition: 'background 1s ease', backgroundImage: `linear-gradient(to bottom, ${color?.colors[0]} 0%, ${color?.colors[0]} 10%, ${color?.colors[1]} 100%)` }} className={`h-20 opacity-30 flex gap-9 transition-all duration-100 rounded-lg`}>        {color?.colors[0]}
      </div>
      <div className='grid grid-cols-2 p-20 gap-20'>
        {Array.from({ length: 2 }).map((_, index) => (
          <Card key={index}>
            <div onMouseOver={() => handleColorChange()} className="flex flex-col items-center justify-center text-white p-4">
              Card {index + 1}
              <ImageMag src='' />
            </div>
          </Card>
        ))}
      </div>
    </div>
  );
}

export default App;
```

# Live-Preview Demo & Examples

Visit [Spotify-Clone](https://anuxr4g-spotify-clone-react.vercel.app/) for live preview.



# react-prism-ui

## Magnify-image (e-commerce)

# `Props`

### src, alt, width, height

600px is the default width and height.

```js
import { Card, ImageMag } from "react-prism-ui";
  const NewCard = () => <ImageMag src="path/url" alt="alternative" width={600} height={600} >);
```
#
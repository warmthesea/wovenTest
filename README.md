# WovenJS
<p align="center">
  <img src="https://user-images.githubusercontent.com/4038732/35308567-17f72930-005d-11e8-9134-c21c741f0cc7.png">
</p>

WovenJS abstracts away the architectural complexity of multi-threading and utilizes optimization metrics to guide your application through the most performant process. Based on client technical information and network strength, WovenJS dynamically runs intensive processes on the server or on the client. When running on the client, WovenJS leverages the Web Workers API to prevent blocking of the web browser's single thread.


## Installing
First `npm install` woven-js in your web application 

```
npm install woven-js --save
npm install --save-dev woven-loader worker-loader babel-loader
```

Next, in your express server file, insert the following:

```javascript

const app = require('express')();
const woven = require('woven-js');
const functions = require(/* "path to your functions file" */);

woven.configure(functions, /* { client options } */);
app.use(woven.optimize);

```
In the front end of your App:

```javascript

import Woven from 'woven-js/client';
import wovenWorker from 'worker-loader?inline=true&name=woven-worker.js!babel-loader!woven-loader!<path to your functions>';
const woven = new Woven();

woven.connect(wovenWorker);

woven.run('function name', payload)
  .then(output => /* do something with output */)

```
## Usage

<p>
  <img src="https://user-images.githubusercontent.com/4038732/35308543-0315f870-005d-11e8-82fa-17aede333138.png">
  &nbsp &nbsp &nbsp &nbsp
  <img src="https://user-images.githubusercontent.com/4038732/35308546-05bdf154-005d-11e8-9877-ceabb6a07424.png">
  &nbsp &nbsp &nbsp &nbsp
  <img src="https://user-images.githubusercontent.com/4038732/35308554-09e7228c-005d-11e8-9329-f49ab7580292.png">
  &nbsp &nbsp &nbsp &nbsp
  <img src="https://user-images.githubusercontent.com/4038732/35308551-07f95ea4-005d-11e8-8d81-4b8ade2db02f.png">
  &nbsp &nbsp &nbsp &nbsp
  <img src="https://user-images.githubusercontent.com/4038732/35312963-d4709d20-0072-11e8-80f2-57423e8ac1d1.png">
</p>



## Contributing



## Versioning

 

## Authors
<table>
  <tbody>
    <tr>
      <td align="center" valign="top">
        <img width="150" height="150" src="https://github.com/sokra.png?s=150">
        <br>
        <a href="https://github.com/sokra">Tobias Koppers</a>
        <p>Core</p>
        <br>
        <p>Founder of webpack</p>
      </td>
      <td align="center" valign="top">
        <img width="150" height="150" src="https://github.com/jhnns.png?s=150">
        <br>
        <a href="https://github.com/jhnns">Johannes Ewald</a>
        <p>Loaders &amp; Plugins</p>
        <br>
        <p>Early adopter of webpack</p>
      </td>
      <td align="center" width="20%" valign="top">
        <img width="150" height="150" src="https://github.com/TheLarkInn.png?s=150">
        <br>
        <a href="https://github.com/TheLarkInn">Sean T. Larkin</a>
        <p>Public Relations</p>
        <br>
        <p>Founder of the core team</p>
      </td>
      <td align="center" valign="top">
        <img width="150" height="150" src="https://github.com/bebraw.png?s=150">
        <br>
        <a href="https://github.com/bebraw">Juho Vepsäläinen</a>
        <p>Documentation</p>
        <br>
        <p>Author</p>
        <a href="https://leanpub.com/survivejs-webpack">
          <img height="15" src="https://cloud.githubusercontent.com/assets/1365881/20286923/93e325c0-aac9-11e6-964d-cabe218c584c.png">
        </a>
		<br>
      </td>
 
     </tr>
  </tbody>
</table>



## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

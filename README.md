# WovenJS
![WovenJS](https://user-images.githubusercontent.com/4038732/35308559-0f5c6e3e-005d-11e8-82c1-70db0505ed68.png)
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




## Contributing



## Versioning

 

## Authors



## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

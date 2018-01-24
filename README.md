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
  <img src="https://user-images.githubusercontent.com/4038732/35308546-05bdf154-005d-11e8-9877-ceabb6a07424.png">
  <img src="https://user-images.githubusercontent.com/4038732/35308554-09e7228c-005d-11e8-9329-f49ab7580292.png">
  <img src="https://user-images.githubusercontent.com/4038732/35308551-07f95ea4-005d-11e8-8d81-4b8ade2db02f.png">
  <img src="https://user-images.githubusercontent.com/4038732/35312963-d4709d20-0072-11e8-80f2-57423e8ac1d1.png">
</p>
<div id="thumbs">
    <a id="single_image1" href="#"><img src="https://user-images.githubusercontent.com/4038732/35308543-0315f870-005d-11e8-82fa-17aede333138.png" alt=""/></a>
    <a id="single_image2" href="#"><img src="https://user-images.githubusercontent.com/4038732/35308546-05bdf154-005d-11e8-9877-ceabb6a07424.png" alt=""/></a>
    <a id="single_image3" href="#"><img src="https://user-images.githubusercontent.com/4038732/35308554-09e7228c-005d-11e8-9329-f49ab7580292.png" alt=""/></a>
    <a id="single_image3" href="#"><img src="https://user-images.githubusercontent.com/4038732/35308551-07f95ea4-005d-11e8-8d81-4b8ade2db02f.png" alt=""/></a>
    <a id="single_image3" href="#"><img src="https://user-images.githubusercontent.com/4038732/35312963-d4709d20-0072-11e8-80f2-57423e8ac1d1.png" alt=""/></a>
    <span class="stretch"></span>
</div>


## Contributing



## Versioning

 

## Authors



## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

# QubeProx
#### An unblockable and undetectable proxy made for schools and for deploying on webservers. Built on [Ultraviolet](https://github.com/titaniumnetwork-dev/Ultraviolet-Node).

## How to deploy?
```
$ git clone https://github.com/chunkban/qubeprox --recursive
$ cd qubeprox
$ npm install
$ npm start
```

## Config
Location: `uv.config.js`
```javascript
self.__uv$config = {
    prefix: '/sw/', // Proxy url prefix
    bare: '/bare/', // Bare server location
    encodeUrl: Ultraviolet.codec.xor.encode, // URL Encoding function
    decodeUrl: Ultraviolet.codec.xor.decode, // Decode URL function
    handler: '/uv.handler.js', // Handler script
    bundle: '/uv.bundle.js', // Bundled script
    config: '/uv.config.js', // Configuration script
    sw: '/uv.sw.js', // Service Worker Script
};
```
| Configuration | Options and Explanation |
| ------------- | ----------------------- |
| Prefix | The prefix is the prefix that you want users to see. Ex: `https://example.com/service.` The default prefix is `service`. |
| Bare | Bare Servers can run on directories. For example, if the directory was /bare/ then the bare origin would look like `http://example.org/bare/`. The bare origin is passed to clients. |
| encodeUrl| EncodeUrl is how you want the URL a proxy site's visitors has to be encoded. Options include `Ultraviolet.codec.base64.encode`, `Ultraviolet.codec.plain.encode`, or `Ultraviolet.codec.xor.encode`. It is recommended that you use `xor` or `base64` as it hides the queries your visitors are searching and visiting.
| decodeURL | DecodeUrl is how you want the url to be decoded. It is recommended you keep it the same as `encodeUrl`. |
| Handler | Handler is the path to the UV handler. The default name and path to this file is `static/uv/uv.handler.js`. |
| Bundle | Bundle is the path to the UV bundle file. The default name and path to this file is `static/uv/uv.bundle.js`. |
| Config | Config is the path to the UV config file. The default name and path to this file is `static/uv/uv.bundle.js`. |
| SW | SW is the path to the UV Service Worker script. The default name and path to this file is `static/uv/uv.sw.js`. |

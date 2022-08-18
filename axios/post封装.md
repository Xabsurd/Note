### 格式化post请求中的参数并指定传递方式
```js
import axios from "axios";
import qs from 'qs';
const request = axios.create({
  baseURL: main.$config.serverUrl,
  // timeout: 10000,
});
request.interceptors.request.use(
  (config) => {
    config.headers["Authorization"] = getItem("token");
    if (config.method.toLocaleLowerCase() === "post") {
      if (typeof config.data === "object") {
        if (config.data instanceof FormData) {
          config.headers["Content-Type"] = "multipart/form-data";
        } else {
          config.data = qs.stringify(config.data);
          console.log(config.data);
          config.headers["Content-Type"] = "application/x-www-form-urlencoded";
        }
      }
    }
    return config;
  },
  (error) => {
    console.log(error);
  }
);
```
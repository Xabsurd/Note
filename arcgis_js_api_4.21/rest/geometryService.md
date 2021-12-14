### 引用几何服务
```js
 import * as geometryService from "@arcgis/core/rest/geometryService";
 const { lengths, simplify, areasAndLengths,... } = geometryService;
```
### simplify 真实的调用方式
```js
/**
*	url : 几何服务地址(String)
*	geometry : 几何数据(Array)
*/
simplify(url, geometry).then(function (simplifiedGeometries) {});
```

> #### 例子：获取多边形的面积和边长
>
> ```js
> simplify(url,geometry).>then(function(simplifiedGeometries) {
>   const areasAndLengthParams = new AreasAndLengthsParameters({
>     areaUnit: "square-kilometers",
>     lengthUnit: "kilometers",
>     polygons: simplifiedGeometries,
>   });
>   areasAndLengths(url, areasAndLengthParams).then(function(results){
>     console.log("area: ", results.areas[0]);
>     console.log("length: ", results.lengths[0]);
>   });
> });
> ```
> #### 例子: 获取几何的周长
> ```js
> simplify(url, geometry).then(function(simplifiedGeometries) {
>	 const lengthsParameters = new LengthsParameters({
>		 lengthUnit: 9001, //米
>		 polylines: simplifiedGeometries,
>	 });
>	lengths(window.config.mapGeoServer, lengthsParameters).then(function(results) {
>		callback(geometry, results);
>	 });
> });
> ```

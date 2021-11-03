### simplify 真实的调用方式

```js
simplify(url, [polygon]).then(function (simplifiedGeometries) {});
```

> #### 例子：获取多边形的面积和边长
>
> ```js
> simplify(url, [graphic.geometry]).>then(function(simplifiedGeometries) {
>   const areasAndLengthParams = new >AreasAndLengthsParameters({
>     areaUnit: "square-kilometers",
>     lengthUnit: "kilometers",
>     polygons: simplifiedGeometries,
>   });
>   areasAndLengths(url, >areasAndLengthParams).then(function(results){
>     console.log("area: ", results.areas[0]);
>     console.log("length: ", results.lengths[0]);
>   });
> });
> ```

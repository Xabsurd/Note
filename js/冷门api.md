### 监控dom尺寸变化
```js
const resizeObserver = new ResizeObserver((entries) => {
 	for (let entry of entries) {
 		console.log("size change");
 	}
 });
resizeObserver.observe(this.$refs["custom-table-body"]);
```
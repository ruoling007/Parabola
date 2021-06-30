# Parabola
javascript封装的一个简单的抛物线动画插件
## 使用说明：
### 运动位移的起点元素必须设置position: absolute;本插件通过控制定位元素的left和top实现运动动画。
使用示例：
```javascript
import Parabola from 'Parabola.js';
new Parabola({
   el,
   target,
   duration: 1000,
   movement: 'cubic-bezier(0.49, -0.29, 0.75, 0.41)',
   callback: function () {
      console.log("运动结束了");
   },
   stepCallback: function (x, y) {
      console.log(`x轴偏移量${x}px,y轴的偏移量${y}px`);
   },
   autostart: true,
});
```
## 参数说明：
|参数名|数据类型|默认值|描述|
| :---: | :---: | :---: | :---: |
|el|HTMLElement|null|起点元素,必须传入一个html元素
|target|HTMLElement|null|目标元素,必须传入一个html元素
|duration|Number|500|运动的时间，默认500毫秒|
|movement|String|cubic-bezier(0.49, -0.29, 0.75, 0.41)|运动的函数，默认的函数为贝塞尔曲线函数cubic-bezier(0.49, -0.29, 0.75, 0.41),支持贝塞尔曲线,支持css运动函数|
|callback|Function|null|运动后执行的回调函数，this指向该对象|
|stepCallback|Function|null|运动过程中执行的回调函数，this指向该对象，接受x，y参数，分别表示X，Y轴的偏移位置|
|autostart|Boolean|false|是否自动开始运动，默认为false|
## 实例方法：
start()

开始执行动画

reset()

重置元素的位置

stop()

停止动画


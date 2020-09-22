### el-time-picker时间选择组件中is-range属性更改：

1、使用minTim、maxTime、default-value等附加属性【不生效】;

2、使用两个el-time-picker实现开始时间与结束时间拆分与先后选择顺序[样式不对]；

3、timepicker对应的rules里加一个validator: 比如timeValidator，在timeValidator里判断选择时间是否大于当前时间，然后返回true或者false；

4、页面中使用computed与watch属性计算当前数值变化；

5、使用@focus事件，给this.event.eventTime默认值；

6、element-ui组件源码修改（不建议）：

7、vue操作虚拟DOM动态添加/移除active；
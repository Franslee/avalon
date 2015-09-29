#avalon1.5.3(各种奇葩BUG修复及更快的parser)

1. 全新的parser
2. 修正$watch的监控
3. fix 使用数组clear方法清空数组后，再push元素报错
4. fix ms-duplex在modern版本的错误
5. fix uuid引发的错误 https://github.com/RubyLouvre/avalon/issues/1060
6. 将所有编译函数的地方抽象成一个方法cspCompile https://github.com/RubyLouvre/avalon2/commit/4169422645466d0f036aa7ad48e1b9dd6c874106
7. fix toJson在IE6的BUG https://github.com/RubyLouvre/avalon/issues/1063
8. fix avalon(window).width()在IE6下 取值不正确的BUG

#avalon1.5.2(主要在自定义标签上进行简化)

1. configs 改名为 config
2. $extends  改名为 $extend
3. fix loader不能正确处理url path map之后带query的BUG
4. fix ms-if 与 HTML5 form validation共用时的BUG
5. fix $watch回调this指向BUG
6. fix ms-if 碰到子对象的属性不存在时不插入节点的 BUG
7. fix ms-include不存在动画时不会移除旧节点的BUG

#avalon1.5.1
1. 精简自定义标签的设计
2. fix cache内存泄漏
3. 添加$fire("all!xxx")的支持
4. fix ms-duplex使用拦截器时触发多次的BUG
5. 公开openTag, closeTag到avalon.config


# avalon1.5

1. 添加动画指令 ms-effect avalon.effect http://avalonjs.github.io/#zh/bindings/effect.html
2. 添加基于自定义标签的组件指令 http://avalonjs.github.io/#zh/bindings/component.html
3. 全新的$watch机制   http://avalonjs.github.io/#zh/concepts/$watch.html
4. 计算属性全部移动$computed对象上集中定义
5. 更优雅便捷地自定义组件  http://avalonjs.github.io/#zh/bindings/directive.html
6. 废掉avalon.define的旧风格定义,只支持新风格
7. 废掉data-duplex-observe辅助指令
8. 废掉ms-widget 详看component/pager/avalon.pager.js 是怎么将原来组件改成新组件的

现在的VM只有第一层上拥有$events, $fire, $watch, $model属性与方法, 它的子对象没有这些属性

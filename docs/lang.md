# lang

语言扩展

## 语言修复

在不支持ES5的环境中实现ES5的一些语言扩展

包括：

* Object.keys
* String.prototype.trim
* Function.prototype.bind
* Date.now
* Array.prototype.every
* Array.prototype.filter
* Array.prototype.forEach
* Array.prototype.indexOf
* Array.prototype.lastIndexOf
* Array.prototype.map
* Array.prototype.some
* Array.prototype.reduce
* Array.prototype.reduceRight
* Array.isArray

## each

遍历对象或数组

    /**
     * 在fn里return false终止遍历
     * fn的参数为item，key，object
     */
    each(object, fn, context)

## mix/extend

相当于jQuery extend

## isWindow

判断参数是否为window对象

    isWindow({}) => false

## isPlainObject

相对于$.isPlainObject(), 判断一个对象是否为纯对象

## isEqual

比较两个参数是否相等，包括数组，对象的比较

    isEqual([1, 2, 3], [2, 3, 1]) => false

## type

返回参数的类型，小写

    type(o) => string/function/....

## makeArray

将参数转成一个原生数组

## memoize

对函数进行封装，对同样的参数缓存计算的结果

    /**
     * fn应当返回一个不为false的值
     * @param [hasher] [function] hasher函数返回缓存的键，默认为function(val) {return val}， 也就是拿fn的第一个参数当做缓存的键
     */
    memoize(fn, hasher)

    var f = memoize(function(val)( return val + 10;));

    f(10) => 20;    // 这次是计算得到的
    f(10) => 20;    // 这次是直接取的缓存的结果

## singleton

单例模式，相当于memoize的特殊情况

## substitute

简单的字符串模板替换

    /**
     * @param str [string] 模板
     * @param o [object/array] 要替换的数据
     * @param [reserve] [boolean] 如果对应的值不存在是否保留{{ }}，默认为false，替换{{ }}为空
     */
    substitute(str, o, reserve)

## uniqueCid

生成唯一id

    uniqueCid() => 0
    uniqueCid() => 1

## isNotEmptyString

判断参数是否是非空字符串

    isNotEmptyString("") => false

## ucfirst

将字符串首字母大写

    ucfirst("abc") => "Abc"

## dasherize

将字符串转为连字符风格

    dasherize("myName") => "my-name"

## random

随机

    /**
     * 生成一个min到max之间的整数随机数
     */
    random(min, max)

    random(0, 10) => 0到10随机一个整数，包括0和10

    /**
     * 从数组中随机一个元素返回
     */
    random(array)

## later

延迟执行函数，对setTimeout和setInterval的一个封装

     /**
     * [later description]
     * @param  {Function} fn       要执行的函数
     * @param  {number}   when     延迟时间
     * @param  {boolean}   periodic 是否周期执行
     * @param  {object}   context  context
     * @param  {Array}   data     传递的参数
     * @return {object}            timer，cancel() and interval
     */
    later: function (fn, when, periodic, context, data) {}

    var timer = tbtx.later(function(){}, 500, true);

    timer.cancel() // 取消定时器

    timer.interval => true

## throttle

与debounce不同的是，函数节流将函数限制在多少ms内只会触发一次

## debounce

一定间隔内没有调用时，才开始执行被调用方法。

当在scroll事件或者resize事件里执行大量操作时，频繁触发会导致浏览器很卡，使用:$(window).on('resize', debounce(function, 300));

例如很短时间内（ms内）第二次触发事件时, 不会执行fn，当停止触发ms后执行fn

## stripTags

去除html中的字符串

    stripTags("<p>123</p>") => 123

## escapeHtml

此函数会对以下符号进行 escape： " < > & 和空格

## unEscapeHtml

此函数会对以下符号进行 unEscape： " < > & 和空格

## truncate(str, length, truncation)

对字符串进行截断，truncation默认为...

    truncate("123456789", 6) => "123..."
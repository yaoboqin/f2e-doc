# uri

uri相关

## param

对象转为query字符串, =号和?号都可以自定义

    param({a: 1, b: 2}) => a=1&b=2

## unparam

query字符串转为对象, =号和?号都可以自定义

    unparam("a=1&b=2") => {a: 1, b: 2}

## isUri

判断是否为uri

    isUri("http://miiee.taobao.com") => true

## parseUri

解析uri，返回uri信息，uri默认为location.href

    // 返回对象
    scheme: 协议，如http
    domain: 域名，如miiee.taobao.com
    port: 端口，如8080
    path: 路径，如/themes
    query: 查询字符串
    fragment: 锚点

## getFragment

获取锚点值

    getFragment(uri)

## get/set/remove/addQueryParam

获取/设置/删除/增加查询参数，url可作为第一个或最后一个参数传入

### getQueryParam

返回解析url的查询字符串的对象，如果提供name，则返回name的值

    getQueryParam(name)

### addQueryParam

对一个url增加查询参数，返回增加后的url

如果有多个参数要增加可以传入一个对象

    addQueryParam(name, value)
    addQueryParam(object)

### removeQueryParam

对一个url删除查询参数，返回删除参数后的url, names可以为数组或键

    removeQueryParam(names)
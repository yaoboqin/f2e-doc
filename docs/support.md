# support

浏览器特性支持

support.xx

    canvas:             // 是否支持canvas
    transition
    transform
    touch: touch        // 是否是触摸设备
    mobile: mobile      // 是否是移动端，包括手机和pad
    pad: pad            // 是否是pad
    phone: phone        // 是否是手机
    placeholder


## prefixed

输出带前缀的属性名

    prefixed("transform") -> "WebkitTransform"

## testPropsAll

测试是否支持某属性

    testPropsAll("transition") -> true/false
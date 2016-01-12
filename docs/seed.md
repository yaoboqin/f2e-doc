# seed

种子文件

## version

版本号

## log

在log环境下输出log信息

    /**
     * @param msg string 消息内容
     * @param src string 消息来源
     * log('hello', 'modA') => modA: hello
     */
    log(msg, src)

## error

抛出错误

    /**
     * @param msg [string|Error]
     */
    error(msg)

## global

全局对象，浏览器下是window

## noop

空函数, 相当于$.noop

## config

写入/读取全局配置

    /**
     * 读取配置
     */
    config(key)

    /**
     * 写入配置
     */
    config(key, value)

    /**
     * 多个配置写入可以合并为对象
     */
    config(object)
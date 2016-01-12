# loader

遵循AMD规范的模块加载器

## define

定义模块，开发者所关注

    define(id, deps, factory)

## require

加载模块，调用者所关注

依赖模块的接口会作为参数传入callback

    require("jquery", function($) {

    });

## Loader.config()

加载器配置，可以配置的项有

    base: 基础路径，默认为静态文件顶层

    // 别名配置，与path配合，配置后可以直接require("jquery")
    alias: {
        "jquery": "jquery/jquery-1.8.3.min.js",
        "handlebars": "miiee/handlebars.js",
        "easing": "plugin/jquery.easing.1.3.js"
    },

    // 路径配置
    paths: {
        'gallery': 'https://a.alipayobjects.com/gallery'
    },

    // 映射配置
    map: [
        ['http://example.com/js/app/', 'http://localhost/js/app/']
    ]
# request

ajax请求代理

只有code为100才返回success，其余返回fail

会自动加上token

可以通过config("tokenName", val)定义cookie名

response有result在成功时默认返回response.result而不是response

为了解决后端删除cookie后请求的cookie不正确的问题，限制同一时刻只处理一个token请求

    require("request", function(request) {
        var data = {id: 123};
        request(url, data).done(function(response) {

        }).fail(function(code, response) {

        });
    });

请求失败时返回状态码-1，msg根据下面的给出

    def: "请求失败！请重试！",
    0: "无法连接到服务器！请检查网络连接！",
    500: "服务器出错!",
    timeout: "请求超时！",
    abort: "请求被终止！",
    parsererror: "服务器出错或数据解析出错！"
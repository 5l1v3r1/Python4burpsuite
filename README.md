# python_for_burpsuite 记录burpsuite的python插件开发和调试方法

## 主要函数
class BurpExtender 和 其中的 registerExtenderCallbacks函数按照案例直接copy即可
###processHttpMessage函数是处理http消息的重点函数
* toolFlag 表示哪个选项会加载该插件(使用if在插件代码中控制),如果不限制则是所有选项都会加载 64表示repeater 4是表示proxy
* messageIsRequest 表示消息体是请求还是响应,true表示是request请求
* messageInfo没有完整的代码分析其结构,目前已知的方法
* response = messageInfo.getResponse()获取response消息体 二进制格式
* analyzedResponse = self._helpers.analyzeResponse(response)  另一个response结构
* analyzedResponse.getBodyOffset() 获取到body的偏移
* headers = analyzedResponse.getHeaders() 可以获取到消息头,一个列表格式数据
* self._helpers.buildHttpMessage(new_headers, new_body) 组合消息体和消息头为一个新的messageInfo格式数据
* messageInfo.setResponse()设置返回消息内容


## 调试方法
* 暂时没有方法进行打断点,可以在extender选项中输出printf
* 代码的报错信息会在Error中输出


http://www.freebuf.com/articles/terminal/106673.html

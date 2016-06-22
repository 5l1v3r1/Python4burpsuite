# python_for_burpsuite 记录burpsuite的python插件开发和调试方法

## 主要函数
class BurpExtender 和 其中的 registerExtenderCallbacks函数按照案例直接copy即可
processHttpMessage函数是处理http消息的重点函数
toolFlag 表示哪个选项会加载该插件(使用if在插件代码中控制),如果不限制则是所有选项都会加载 64表示repeater 4是表示proxy
messageIsRequest 表示消息体是请求还是响应,true表示是request请求
messageInfo没有完整的代码分析其结构


## 调试方法

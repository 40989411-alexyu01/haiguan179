海关179对接终结版

一个exe解决所有问题,兼容所有语言 java,php,c#等
屏蔽了所有的实现细节,只需要按要求组装数据返回便可
只需提供一个获取订单的接口便可
自动加签,自动上报

试用版
可用做一键导出证书编号与标准格式化的证书,直接上传,证书名字包含证书序列号
备注: 卡密码为88888888,密码不一致的慎用,或者联系作者
需要在插有操作员卡的,并安装海关驱动的机器上运行exe
正式版请联系作者,需要配置地址,单独打包

说明 20秒请求一次加签数据 30秒之内上报海关

模拟海关请求地址
http://wyb.qdhuaxun.cn/baoguan/paycheck/debug.php
{"code":"20006","message":"上传失败,入库失败 java.sql.SQLException: ORA-00001: 违反唯一约束条件 (sessionID重复)","total":0,"serviceTime":1567050097628} 接口返回这个表示已通

返回数据格式://
json格式
字段详情请查看海关文档
json里的字段全为字符串型
参考数据如下
{ "initalRequest": "initalRequest", "initalResponse": "initalResponse", "payTransactionId": "4200000306201905223753178715", "totalAmount": "1564.84", "verDept": "3", "tradingTime": "20190522160003", "goods": [ { "gname": "当归口服液 Hemohim ( 4 盒 )", "itemLink": "http:///?a=viewgoods&id=307" } ], "ebpCode": "3PB", "certNo": "0d", "payCode": "31222699S7", "currency": "142", "recpAccount": "3***77", "recpName": "财付通支付科技有限公司", "orderNo": "20190522160021647878953", "SessionID": "20190522160021647878953" }

对接流程
提供两个地址1.订单数据获取,2.上报结果回调 按照格式返回 海关请求需要存相关信息,sessionId,orderid

海关179对接终结版

>>一个exe解决所有问题,兼容所有语言 java,php,c#等<br/>
屏蔽了所有的实现细节,只需要按要求组装数据返回便可<br/>
只需提供一个获取订单的接口便可<br/>
自动加签,自动上报<br/>

>>试用版
可用做一键导出证书编号与标准格式化的证书,直接上传,证书名字包含证书序列号<br/>
备注: 卡密码为88888888,密码不一致的慎用,或者联系作者<br/>
需要在插有操作员卡的,并安装海关驱动的机器上运行exe<br/>
正式版请联系作者,需要配置地址,单独打包<br/>

>>说明 20秒请求一次加签数据 30秒之内上报海关<br/>

>>模拟海关请求地址<br/>
http://wyb.qdhuaxun.cn/baoguan/paycheck/debug.php<br/>
{"code":"20006","message":"上传失败,入库失败 java.sql.SQLException: ORA-00001: 违反唯一约束条件 (sessionID重复)","total":0,"serviceTime":1567050097628} 接口返回这个表示已通

>>返回数据格式:
json格式<br/>
字段详情请查看海关文档<br/>
json里的字段全为字符串型<br/>
参考数据如下<br/>
{ "initalRequest": "initalRequest", "initalResponse": "initalResponse", "payTransactionId": "4200000306201905223753178715", "totalAmount": "1564.84", "verDept": "3", "tradingTime": "20190522160003", "goods": [ { "gname": "当归口服液 Hemohim ( 4 盒 )", "itemLink": "http:///?a=viewgoods&id=307" } ], "ebpCode": "3PB", "certNo": "0d", "payCode": "31222699S7", "currency": "142", "recpAccount": "3***77", "recpName": "财付通支付科技有限公司", "orderNo": "20190522160021647878953", "SessionID": "20190522160021647878953" }

>>对接流程<br/>
http://ceb1.chinaport.gov.cn/<br/>
先在海关后台上传证书填写证书序列号<br/>
提供两个外网可访问地址<br/>
1.订单数据获取,按格式返回<br/>
2.上报结果回调 <br/>
按照格式返回 <br/>
海关请求时在服务器保存存相关信息,sessionId,orderid

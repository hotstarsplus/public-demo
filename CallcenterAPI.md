# Callcenter Programmer's Guide

Version 5.0.x



# 版本修订记录

| **版本号** | **发布日期** | **修订内容**                                                 |
| ---------- | ------------ | ------------------------------------------------------------ |
| V1.0.0     | 2021.5       | 创建此文档                                                   |
| V1.0.1     | 2021.8.31    | 新增以下接口：  5.8：ACD实时数据  5.9：ACD实时排队数据  5.12：坐席状态  5.13：坐席实时数据  5.14：坐席状态数量  修改以下接口：  4.1-4.16, 5.10-5.11返回参数新增jobNum工号参数，调用签入接口时传入，如果未传则返回空  5.10接口新增查询条件ACD号，可以根据ACD号查询ACD下所有坐席  3.1 坐席签入新增jobNum工号参数，用来与坐席关联 |
| V1.0.2     | 2021.9.07    | 新增以下接口：  5.35 自定义坐席状态列表接口   5.36 坐席状态颜色编码列表  5.37 坐席状态历史列表   4.17 坐席注销事件   修改以下接口：  5.10 坐席列表增加ACD号筛选条件  5.13坐席监控提供当前状态持续时长 |
| V1.0.3     | 2021.9.12    | 修改如下接口  4.1-4.16, 5.10-5.11返回参数删除jobNum工号参数  3.10 坐席签入删除jobNum工号参数  4.1-4.17, 5.10-5.11返回参数新增extension分机号参数，调用签入接口时传入，如果未传则返回空  3.1 坐席签入新增extension分机号参数，用来实现坐席分机号分离  4.16新增坐席请求失败事件及对应状态码 |
| V1.0.4     | 2021.9.15    | 新增如下接口  5.38 新增随路数据接口                          |
| V1.0.5     | 2021.9.23    | 修改如下接口  5.13 新增筛选条件ACD号queueName，返回结果新增坐席人员姓名name |
| V1.0.6     | 2021.9.24    | 新增如下接口  4.18 坐席请求提示事件  修改如下接口  3.4坐席示忙休息时新增参数limit指定休息时长 |
| V1.0.7     | 2021.9.26    | 新增如下接口  3.26 接听来电/不接来电  修改如下接口  4.18 提示码新增  2：接听来电   3：不接来电 |
| V1.0.8     | 2021.10.15   | 修改如下接口  5.14坐席状态数量  查询接口当前页与页大小筛选条件改为可选参数 |
| V1.0.9     | 2021.10.19   | 新增如下接口  4.27 心跳请求包  5.19 心跳返回事件  修改如下接口  5.14坐席状态数量 |
| V1.0.10    | 2021.10.21   | 修改如下接口  4.13转接新增挂起转参数                         |
| V1.0.11    | 2021.10.29   | 新增如下接口  6.39 坐席休息排队队列信息  修改如下接口  6.4资源组列表新增休息人数上限返回结果参数  4.13接口新增转队列（ACD）功能 |
| V1.0.12    | 2021.11.09   | 修改如下接口  5.16 新增接口失败事件  5.18 新增接口成功事件   |
| V1.0.13    | 2021.11.17   | 修改如下接口  5.7 拨号事件新增主被叫第三方参数  5.8 来电事件新增主被叫第三方参数 |
| V1.0.14    | 2021.11.17   | 修改如下接口  6.13 新增业务编码类型入参,返回业务编码类型结果  6.14 新增业务编码类型入参，返回业务编码类型对应坐席数量 |
| V1.0.15    | 2021.11.17   | 修改如下接口  6.17 IVR流程详情，删除按键等参数，修改状态对应值属性 |
| V1.0.16    | 2021.12.5    | 修改如下接口  删除连接保持接口  5.10呼叫释放事件增加挂断原因返回  4.9增加成功转  增加成功失败事件 |
| V1.0.17    | 2021.12.14   | 新增如下接口  7.1 修改休息人数上限                           |
| V1.0.18    | 2021.12.18   | 删除7.1修改休息人数上限接口  新增如下接口  6.10分机列表   6.40坐席通话时段统计  6.41休息时间模板列表  7.1发送短信   7.4添加休息时间模板  7.5修改休息时间模板  7.6删除休息时间模板  7.7删除话务记录  7.8删除录音记录  7.9删除队列记录  7.10删除IVR记录 |
| V5.0.x     | 2021.12.22   | 新增如下接口  4.26通话发送按键   4.27通话放音  6.43黑名单列表  6.44 黑名单详情  7.11添加黑名单  7.12删除黑名单  7.13修改黑名单 |
| V5.0.x     | 2021.12.28   | 新增如下接口  6.45号码联络次数  修改如下接口  6.32 坐席通话统计新增呼入呼出的最短最长通话中时长  6.42 休息模板新增业务类型参数 |
| V5.0.x     | 2021.1.5     | 修改如下接口  6.29新增查询条件发送号码接收号码发送内容是否已读等查询条件 |
| V5.0.x     | 2021.1.5     | 修改如下接口  6.30坐席状态统计将自定义状态统计也加上         |
| V5.0.x     | 2021.1.20    | 新增如下接口  7.14删除坐席状态记录接口                       |
| V5.0.x     | 2021.1.26    | 新增如下接口  6.45资源组通话时段统计  6.46坐席通话日统计  删除如下接口  6.40坐席通话时段统计   修改如下接口  6.30坐席状态统计增加筛选条件  6.32坐席通话统计增加筛选条件 |
| V5.0.x     | 2021.1.29    | 修改如下接口  5.15 坐席监控事件 返回结果新增被监控坐席分机号 |
| V5.0.x     | 2021.2.3     | 新增如下接口  6.48查询系统当前时间                           |
| V5.0.x     | 2021.2.19    | 新增如下接口  6.45资源组通话时段统计  6.46ACD通话时段统计  6.47部门通话时段统计  6.48坐席通话时段统计  6.49资源组通话日统计  6.50ACD通话日统计  6.51部门通话日统计  6.52坐席通话日统计  6.53资源组通话月统计  6.54ACD通话月统计  6.55部门通话月统计  6.56坐席通话月统计  6.57资源组状态日统计  6.58ACD状态日统计  6.59部门状态日统计  6.60坐席状态日统计  6.61资源组状态月统计  6.62ACD状态月统计  6.63部门状态月统计  6.64坐席状态月统计 |
| V5.0.x     | 2021.4.9     | 新增如下接口  6.65资源组队列日统计  6.66ACD队列日统计  6.67部门队列日统计  6.68坐席队列日统计 |





# 1.系统架构

![呼叫中心系统架构](media/807709c3207e2ad45ed027125953b23e.jpeg)

- 业务层：调用呼叫中心提供的开发接口，将呼叫功能、历史记录、统计报表、坐席监控等植入到业务系统当中；

- 系统层：实现IP呼叫中心系统所有核心功能，是呼叫中心系统的核心层；

    1. ACD（Automatic CallDistributor）即自动呼叫分配，也叫智能选择座席。ACD成批处理来电呼叫，并将这些来电按指定的转接策略传送给座席，其性能的优劣直接影响到呼叫中心的效率和顾客的满意度。

    2. IVR（Interactive VoiceResponse）即交互式语音应答，是一种功能强大的电话自动服务系统。提供为客户进行语音导航的功能。IP呼叫中心系统还支持TTS转换语音功能。

    3. 外呼控制，系统支持预览式及预测式自动外呼。

    4. 语音通信使用websocket协议，长连接，便于事件的推送；数据查询使用http(s)协议，短连接，快速查询数据。

    5. 除了提供大量报表预定义报表，系统还支持自定义报表生成，用于在现有报表不能满足客户需求时，快速进行报表定制开发。

    6. 对于大容量系统模块可以分布在不同的服务器上。

- 接入层：如客户使用模拟话机、模拟直线、E1线时，需要增加网关设备与呼叫中心对接；

- 终端：可以使用传统电话、软电话、IP话机等支持SIP协议的设备。





# 2.呼叫流程图

![呼出流程图](media/341822b5bb41063f20e892fe711b44f9.png)

![呼入流程图](media/28f245e7f00ad2ff92574b9e62163f30.png)





# 3.WebSocket简介

​		WebSocket是一种在单个TCP连接上进行全双工通信的协议。WebSocket通信协议于2011年被IETF定为标准RFC6455，并由RFC7936补充规范。WebSocket API也被W3C定为标准。

​		WebSocket使得客户端和服务器之间的数据交换变得更加简单，允许服务端主动向客户端推送数据。在WebSocketAPI中，浏览器和服务器只需要完成一次握手，两者之间就直接可以创建持久性的连接，并进行双向数据传输。



## 3.1.优点

- 较少的控制开销。在连接创建后，服务器和客户端之间交换数据时，用于协议控制的数据包头部相对较小。在不包含扩展的情况下，对于服务器到客户端的内容，此头部大小只有2至10字节（和数据包长度有关）；对于客户端到服务器的内容，此头部还需要加上额外的4字节的[掩码](https://baike.baidu.com/item/%E6%8E%A9%E7%A0%81)。相对于http(s)请求每次都要携带完整的头部，此项开销显著减少了。

- 更强的实时性。由于协议是全双工的，所以服务器可以随时主动给客户端下发数据。相对于http(s)请求需要等待客户端发起请求服务端才能响应，延迟明显更少；即使是和Comet等类似的长轮询比较，其也能在短时间内更多次地传递数据。

- 保持连接状态。与http(s)不同的是，Websocket需要先创建连接，这就使得其成为一种有状态的协议，之后通信时可以省略部分状态信息。而http(s)请求可能需要在每个请求都携带状态信息（如身份认证等）。

- 更好的二进制支持。Websocket定义了[二进制](https://baike.baidu.com/item/%E4%BA%8C%E8%BF%9B%E5%88%B6)帧，相对http(s)，可以更轻松地处理二进制内容。

- 可以支持扩展。Websocket定义了扩展，用户可以扩展协议、实现部分自定义的子协议。如部分浏览器支持压缩等。

- 更好的压缩效果。相对于[http(s)压缩](https://baike.baidu.com/item/HTTP%E5%8E%8B%E7%BC%A9)，Websocket在适当的扩展支持下，可以沿用之前内容的上下文，在传递类似的数据时，可以显著地提高压缩率。



## 3.2.背景

​		WebSocket 是 HTML5 开始提供的一种在单个 TCP 连接上进行全双工通讯的协议。

​		WebSocket使得客户端和服务器之间的数据交换变得更加简单，允许服务端主动向客户端推送数据。

​		在WebSocket API中，浏览器和服务器只需要完成一次握手，两者之间就直接可以创建持久性的连接，并进行双向数据传输。

​		在 WebSocket API中，浏览器和服务器只需要做一个握手的动作，然后，浏览器和服务器之间就形成了一条快速通道。两者之间就直接可以数据互相传送。

​		现在，很多网站为了实现推送技术，所用的技术都是 Ajax
轮询。轮询是在特定的的时间间隔（如每1秒），由浏览器对服务器发出http(s)请求，然后由服务器返回最新的数据给客户端的浏览器。这种传统的模式带来很明显的缺点，即浏览器需要不断的向服务器发出请求，然而http(s)请求可能包含较长的头部，其中真正有效的数据可能只是很小的一部分，显然这样会浪费很多的带宽等资源。

​		HTML5 定义的 WebSocket协议，能更好的节省服务器资源和带宽，并且能够更实时地进行通讯。

![](media/0d97990e3077451ba4fc6a2cc8ae93ca.png)



## 3.3.握手协议

WebSocket 是独立的、创建在 TCP 上的协议。

Websocket 通过http(s)/1.1 协议的101状态码进行握手。

为了创建Websocket连接，需要通过浏览器发出请求，之后服务器进行回应，这个过程通常称为“握手”（handshaking）。



## 3.4.API介绍

浏览器通过JavaScript向服务器发出建立WebSocket连接的请求，连接建立以后，客户端和服务器端就可以通过TCP连接直接交换数据。

当你获取WebSocket连接后，你可以通过`send()`方法来向服务器发送数据，并通过onmessage事件来接收服务器返回的数据。

以下API用于创建WebSocket对象。

	var Socket = new WebSocket(url, [protocol] );

以上代码中的第一个参数url,指定连接的URL。第二个参数protocol是可选的，指定了可接受的子协议。

### 3.4.1.WebSocket属性

以下是 WebSocket 对象的属性。假定我们使用了以上代码创建了 Socket 对象：

<figure>
    <table>
        <thead>
            <tr>
                <th style='text-align:center;'>
                    <strong>
                        属性
                    </strong>
                </th>
                <th style='text-align:center;'>
                    <strong>
                        描述
                    </strong>
                </th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style='text-align:center;'>
                    Socket.readyState
                </td>
                <td>
                    只读属性 readyState 表示连接状态，可以是以下值：
                    <br/>
                    0 - 表示连接尚未建立。
                    <br/>
                    1 - 表示连接已建立，可以进行通信。
                    <br/>
                    2 - 表示连接正在进行关闭。
                    <br/>
                    3 - 表示连接已经关闭或者连接不能打开。
                </td>
            </tr>
            <tr>
                <td style='text-align:center;'>
                    Socket.bufferedAmount
                </td>
                <td>
                    只读属性 bufferedAmount 已被 send() 放入正在队列中等待传输，但是还没有发出的 UTF-8 文本字节数。
                </td>
            </tr>
        </tbody>
    </table>
</figure>

### 3.4.2.WebSocket事件

以下是 WebSocket 对象的相关事件。假定我们使用了以上代码创建了 Socket 对象：

| **事件** | **事件处理程序**  | **描述**                    |
|:----------:|:-------------------:|:-----------------------------:|
| open     | Socket.onopen     | 连接建立时触发              |
| message  | Socket.onmessage  | 客户端接收服务端数据时触发  |
| error    | Socket.onerror    | 客户端接收服务端数据时触发  |
| close    | Socket.onclose    | 连接关闭时触发              |

### 3.4.3.WebSocket方法

| **方法**       | **描述**         |
|:----------------:|:------------------:|
| Socket.send()  | 使用连接发送数据 |
| Socket.close() | 关闭连接         |



## 3.5.呼叫

**参数描述**
<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="8">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：200</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">otherDN</td>
      <td>String</td>
      <td>呼叫的目标号码，支持4位分机号，普通手机号和固话号码</td>
   </tr>
   <tr>
      <td rowspan="5">attachDatas</td>
      <td>cti-tenant-id</td>
      <td>String</td>
      <td>呼叫坐席所属的资源组编号，例如："10001"</td>
   </tr>
   <tr>
      <td>ivr_id</td>
      <td>String</td>
      <td>ivr主键id（选填）</td>
   </tr>
   <tr>
      <td>voice_tts</td>
      <td>String</td>
      <td>需要播放的文字内容（选填）</td>
   </tr>
   <tr>
      <td>holdCall</td>
      <td>String</td>
      <td>是否保持外呼 <br/>0 否 <br/> 1 是</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>String</td>
      <td>已经保持通话标识(保持外呼时必传)</td>
   </tr>
</table>

**注：调用此接口，将会主动调用坐席示忙接口（携带的reasonCode为3）;执行此操作的原因，是由于需要占用通信通道，以避免此时有来电呼入而于此呼出操作相冲突。**

**接口调用场景**

- 场景1:坐席A呼叫坐席B

    - 坐席A（坐席号为10001_1001）呼叫坐席B（坐席号为10001_1002）,坐席A需要与坐席B通话，则可以使用呼叫功能；这种情况下，接口传递的参数值为：

```
      thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=10001_1002或1002,message->attachDatas{cti-tenant-id:10001}
```

​      

- 场景2:坐席A呼叫客户手机号

    - 坐席A（坐席号为10001_1001）呼叫客户手机号（手机号为182xxxxxxxx）,坐席A需要与坐席B通话，则可以使用呼叫功能；这种情况下，接口传递的参数值为：

```
      thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->attachDatas{cti-tenant-id:10001}
```

​      

- 场景3:坐席A呼叫客户B转入IVR流程

    - 坐席A（坐席号为10001_1001）呼叫客户B手机号（手机号为182xxxxxxxx）,坐席A需要将客户手机号转入IVR流程，ivr_id参数可以根据IVR流程列表接口获取，值取主键id,则可以使用呼叫功能；这种情况下，接口传递的参数值为：
    
```
      thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->attachDatas{cti-tenant-id:10001,ivr_id:1}
```

​      

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

	var data = {
	  	  		thisDN: "10001_1000",
	   			type: "request",
	    		message: JSON.stringify(
	        		{
	           			 messageId: 200,
	            		 thisDN: "10001_1000",
	            		 otherDN: "18866666666",
						 attachDatas:{"cti-tenant-id":"10001"
	}
	        		})
	  		 };
	     	Socket.onopen=function () {
	     		Socket.send(JSON.stringify(data));
	   	}

### 3.5.1.WebSocket实例

​		WebSocket 协议本质上是一个基于 TCP 的协议。

​		为了建立一个 WebSocket 连接，客户端浏览器首先要向服务器发起一个 http(s)请求，这个请求和通常的 http(s)请求不同，包含了一些附加头信息，其中附加头信息"Upgrade:WebSocket"表明这是一个申请协议升级的 http(s)请求，服务器端解析这些附加的头信息然后产生应答信息返回给客户端，客户端和服务器端的WebSocket连接就建立起来了，双方就可以通过这个连接通道自由的传递信息，并且这个连接会持续存在直到客户端或者服务器端的某一方主动的关闭连接。

**客户端的 HTML 和 JavaScript**

目前大部分浏览器支持 WebSocket() 接口，你可以在以下浏览器中尝试实例： Chrome,Mozilla, Opera 和 Safari。

```
<!DOCTYPE HTML><html>
   <head>
   <meta charset="utf-8">
   <title>代码实例(runoob.com)</title>
    
      <script type="text/javascript">
         function WebSocketTest()
         {
            if ("WebSocket" in window)
            {
               alert("您的浏览器支持 WebSocket!");
               
               // 打开一个 web socket
               websocket具体使用方法参考上一章节
 
                               var ws = new WebSocket("ws://localhost:9998/echo");
                
               Socket.onopen = function()
               {
                  // Web Socket 已连接上，使用 send() 方法发送数据
                  Socket.send("发送数据");
                  alert("数据发送中...");
               };
                
               Socket.onmessage = function (evt) 
               { 
                  var received_msg = evt.data;
                  alert("数据已接收...");
               };
                
               Socket.onclose = function()
               { 
                  // 关闭 websocket
                  alert("连接已关闭..."); 
               };
            }
            
            else
            {
               // 浏览器不支持 WebSocket
               alert("您的浏览器不支持 WebSocket!");
            }
         }
      </script>
        
   </head>
   <body>
   
      <div id="sse">
         <a href="javascript:WebSocketTest()">运行 WebSocket</a>
      </div>
      
   </body></html>
```





# 4.通信接口



## 4.1坐席示忙

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：102</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">reasonCode</td>
      <td>number</td>
      <td>可设置以下值，用于标注坐席忙碌的原因。<br/>
        0：整理（坐席结束通话后，进行文案处理）；<br/>
        1：通话（坐席处于通话中）；<br/>
        2：设备不可用（业务系统发送故障）；<br/>
        3：忙碌（其它的情况下，需要将state设置成3）；<br/>
        4：离开（坐席员离开座位）；<br/>
        5：休息（坐席员进行休息，比如午休）；<br/>
        6：拨号中(调用呼叫接口时的状态)；<br/>
        7：外线振铃；<br/>
        8：呼入振铃；<br/>
        由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方面后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
   </td>
   <tr>
      <td>attachDatas</td>
      <td>limit</td>
      <td>String</td>
      <td>指定坐席休息时长 单位/秒</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
    var data = {
    
    thisDN: "10001_1000",
    
    type: "request",
    
    message: JSON.stringify(
    
    {
    
    messageId: 102,
    
    thisDN: "10001_1000",
    
    reasonCode:3 //可以是可选值中的任意一个
    
    })
    
    };
    
    Socket.onopen=function () {
    
    Socket.send(JSON.stringify(data));
    
    }
```



## 4.2坐席签入

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，签入值固定为"login"</td>
   </tr>
   <tr>
      <td rowspan="6">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：100</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">extension</td>
      <td>String</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td colspan="2">thisQueues</td>
      <td>String[]</td>
      <td>坐席所属ACD编号，例如：["10001_8000"]</td>
   </tr>
   <tr>
      <td rowspan="2">attachDatas</td>
      <td>typeText</td>
      <td>String</td>
      <td>类型描述文本，一般用于业务类型(可选参数)</td>
   </tr>
   <tr>
      <td>typeCode</td>
      <td>String</td>
      <td>类型的编码，一般用于业务类型(可选参数)</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "login",//首次签入为login

message: JSON.stringify({

messageId:100,

thisDN:"10001_1000",

extension:"1000",

thisQueues:["10001_8000"],

attachDatas:{"typeCode":"1"}

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.3.坐席签出

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：103</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>String</td>
      <td>分机号，例如："1000"</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 103,

thisDN: "10001_1000"

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.4.坐席空闲

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="2">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：101</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 101,

thisDN: "10001_1000"

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.5.添加随路数据

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：279</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>attachDatas</td>
      <td>cti-tenant-id</td>
      <td>String</td>
      <td>呼叫坐席所属的资源组编号，例如："10001"</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 279,

thisDN: "10001_1000",

attachDatas:{"cti-tenant-id":"10001"}

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.6.呼叫

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="8">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：200</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">otherDN</td>
      <td>String</td>
      <td>呼叫的目标号码，支持4位分机号，普通手机号和固话号码</td>
   </tr>
   <tr>
      <td rowspan="5">attachDatas</td>
      <td>cti-tenant-id</td>
      <td>String</td>
      <td>呼叫坐席所属的资源组编号，例如："10001"</td>
   </tr>
   <tr>
      <td>ivr_id</td>
      <td>String</td>
      <td>ivr主键id（选填）</td>
   </tr>
   <tr>
      <td>voice_tts</td>
      <td>String</td>
      <td>需要播放的文字内容（选填）</td>
   </tr>
    <tr>
      <td>holdCall</td>
      <td>String</td>
      <td>是否保持外呼<br/>0否 <br/>1是 </td>
   </tr>
   <tr>
  	  <td>callID</td>
      <td>String</td>
      <td>已经保持通话标识(保持外呼时必传)</td>
   </tr>
</table>

**注：调用此接口，将会主动调用坐席示忙接口（携带的reasonCode为3）;执行此操作的原因，是由于需要占用通信通道，以避免此时有来电呼入而于此呼出操作相冲突。**

**接口调用场景**

- 场景1:坐席A呼叫坐席B

    - 坐席A（坐席号为10001_1001）呼叫坐席B（坐席号为10001_1002）,坐席A需要与坐席B通话，则可以使用呼叫功能；这种情况下，接口传递的参数值为：

```
      thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=10001_1002或1002,message->attachDatas{cti-tenant-id:10001}
```

​      

- 场景2:坐席A呼叫客户手机号

    - 坐席A（坐席号为10001_1001）呼叫客户手机号（手机号为182xxxxxxxx）,坐席A需要与坐席B通话，则可以使用呼叫功能；这种情况下，接口传递的参数值为：

```
      thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->attachDatas{cti-tenant-id:10001}
```

​      

- 场景3:坐席A呼叫客户B转入IVR流程

    - 坐席A（坐席号为10001_1001）呼叫客户B手机号（手机号为182xxxxxxxx）,坐席A需要将客户手机号转入IVR流程，ivr_id参数可以根据IVR流程列表接口获取，值取主键id,则可以使用呼叫功能；这种情况下，接口传递的参数值为：
    
```
      thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->attachDatas{cti-tenant-id:10001,ivr_id:1}
```

​      

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 200,

thisDN: "10001_1000",

otherDN: "18866666666",

attachDatas:{"cti-tenant-id":"10001"

}

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.7.呼叫保持

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：204</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>oterDN</td>
      <td>String</td>
      <td>保持目标的号码 例如：“18888888888”</td>
   </tr>
</table>

- 场景1:坐席A呼叫保持通话

    - 坐席A（坐席号为10001_1001）呼叫客户手机号（手机号为182xxxxxxxx）,坐席A当前需要处理其它事务，与客户沟通之后调用保持通话功能,客户与坐席会在保持过程中听到一断音乐，后续可以取回通话，则可以使用呼叫保持功能；这种情况下，接口传递的参数值为：

```
thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->callID=x
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 204,

thisDN: "10001_1000",

callID:""

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.8.呼叫取回

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：217</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>呼叫取回目标的号码例如："10001_1000"或“18888888888”</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>呼叫取回目标的号码例如："10001_1000"或“18888888888”</td>
   </tr>
</table>

- 场景1:坐席A呼叫取回通话

    - 坐席A（坐席号为10001_1001）呼叫客户手机号（手机号为182xxxxxxxx）,坐席A通话过程中调用呼叫保持后，需要与客户继续通话通话，可以调用呼叫取回通话功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->callID=x
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 217,

thisDN: "10001_1000",

callID:""

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.9.呼叫释放

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：203</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>挂断目标，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>挂断号码:例如："18888888888"</td>
   </tr>
</table>

**接口调用场景**

- 场景1:坐席A呼出客户C(号码18888888888)接通之后，坐席A进行挂断操作

    - 坐席A（坐席号为10001_1001）呼出,外线接通,坐席A此时处于振铃或者通话状态；此时坐席A通话完毕打算挂断电话，则可以使用挂断功能；

这种情况下，接口传递的参数值为：

```
thisDN=10001_1001,message->thisDN=10001_1001,message->callID=x,otherDN=18888888888
```

- 场景2:坐席A呼出接通之后，坐席B进行挂断操作

    - 坐席A（坐席号为10001_1001）呼出,外线接通,坐席A此时处于振铃或者通话状态；坐席B（坐席号为10001_1002）打算挂断坐席A,坐席B可以调用开始监控坐席接口获取坐席A的通话callID，之后则可以使用挂断功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1002,message->thisDN=10001_1002,message->callID=x,otherDN=10001_1001
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 203,

thisDN: "10001_1000",

callID:"",

otherDN: "18888888888"

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.10.呼叫转接/拦截/转队列(ACD)

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/>当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="6">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：215</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/>被转接目标坐席号</td>
   </tr>
   <tr>
      <td colspan="2">callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td colspan="2">otherDN</td>
      <td>String</td>
      <td>转接目标的号码</td>
   </tr>
   <tr>
      <td colspan="2">phoneNumber</td>
      <td>String</td>
      <td>isHold值为2传需要转接成功后自动挂断的号码<br/>
		  isHold值为1传保持通话的号码
      </td>
   </tr>
   <tr>
      <td>attachDatas</td>
      <td>isHold</td>
      <td>String</td>
      <td>转接方式<br/>
		  2：转接成功自动挂断,转接失败则恢复通话<br/>
		  1：客户通话结束之后没有挂断继续转回来与坐席通话<br/>
		  0：坐席通话直接挂断
      </td>
   </tr>
</table>

**接口调用场景**

- 场景1:

    - 坐席A（坐席号为10001_1001）与客户B（号码为182xxxxxxxx）在通话过程中有转接第三方C（号码为183xxxxxxxx）的需求，此时调用转接接口，根据转接方式(isHold)的不同，实现不同的转接效果。这种情况下，接口传递的参数值为：
```
thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=183xxxxxxxx,message->callID=x,message->phoneNumber=182xxxxxxxx,message->attachDatas->isHold=1
```

- 场景2:外线呼入转到坐席A，坐席B进行拦截操作

    - 外线呼入，系统分配的callid为x，呼入号码为n，转到坐席A(坐席号为10001_1001),坐席A此时处于振铃或者通话状态；坐席B（坐席号为10001_1002）打算挂断坐席A然后直接与外线直接通话，则可以使用拦截功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1002,message->thisDN=10001_1002,message->callID=x,message->otherDN=10001_1001
```

- 场景3:外线呼入转到坐席A，坐席A将外线转入队列(ACD)

    - 外线呼入，系统分配的callid为x，呼入号码为n，转到坐席A(坐席号为10001_1001),坐席A此时处于振铃或者通话状态；坐席A有事接不了或需要将外线n转入队列，则可以使用转队列（ACD）功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1001,message->thisDN=10001_1001,message->callID=x,message->otherDN=10001_8000
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:215,

thisDN:"10001_1000",

callID:"",

otherDN:targetDN,

phoneNumber:phoneNumber

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.11.通话转IVR

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/>当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="6">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：290</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"<br/> 被转接目标坐席号</td>
   </tr>
   <tr>
      <td  colspan="2">callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td colspan="2">phoneNumber</td>
      <td>String</td>
      <td>本次通话的号码</td>
   </tr>
   <tr>
      <td rowspan="2">attachDatas </td>
      <td>ivrID</td>
      <td>String</td>
      <td>IVR主键ID</td>
   </tr>
     <tr>
      <td>isHold</td>
      <td>String</td>
      <td>转接方式<br/>
         1：是（结束ivr流程之后客户没挂断继续转回来与坐席通话)<br/>
         0：否(坐席通话直接挂断)
      </td>
   </tr>
</table>

- 场景1:坐席A呼叫客户手机号通话中转入IVR流程

    - 坐席A（坐席号为10001_1001）呼叫客户手机号（手机号为182xxxxxxxx）,坐席A需要将客户手机号转入IVR流程，ivr_id参数可以根据IVR流程列表接口获取，值取主键id，isHold参数根据需要取值，结束IVR流程之后客户是否继续与坐席通话,则可以使用通话转IVR功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=182xxxxxxxx,message->callID=x,message->attachDatas{ivr_id:1,isHold:1}
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:290,

thisDN:"10001_1000",

callID:"",

phoneNumber:phoneNumber，

attachDatas:{"ivrID":"12","isHold":"1"}

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```


## 4.12.三方通话/强插/三方求助

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/>当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="5">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：214</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"<br/> 通话中的坐席号</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>第三方的号码</td>
   </tr>
   <tr>
      <td>phoneNumber</td>
      <td>String</td>
      <td>静音号码，转三方前是否静音，如不静音则不传(第三方接听后自动取消静音)</td>
   </tr>
</table>

- 场景1:

    - 坐席A（坐席号为10001_1001）呼叫客户B（号码为182xxxxxxxx）,坐席A与客户B通话过程中需要与第三方C（号码为183xxxxxxxx）建立通话，三方能同时通话，任何一方挂断不影响其它两方，则可以使用磋商呼叫功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1001,message->thisDN=10001_1001,message->otherDN=183xxxxxxxx,message->callID=x
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:214,

thisDN:"10001_1000",

callID:"",

otherDN: phoneNumber

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.13.呼叫监听

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" </br/> 当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：265</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/> 监听坐席号</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>监听目标的号码</td>
   </tr>
</table>

- 场景1:

    - 坐席A（坐席号为10001_1001）呼叫客户B（号码为182xxxxxxxx）,坐席A与客户B通话过程中管理人员坐席C（坐席号为10001_1002）需要监听坐席A与客户B的通话，则可以使用呼叫监听功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1002,message->thisDN=10001_1002,message->otherDN=182xxxxxxxx,message->callID=x
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:265,

thisDN:"10001_1000",

callID:"",

otherDN: otherDN

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.14.静音

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/> 当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：292</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>静音目标（坐席号或手机号）</td>
   </tr>
</table>

- 场景1:

    - 坐席A（坐席号为10001_1001）呼叫客户B（号码为182xxxxxxxx）,管理员坐席C（坐席号为10001_1002）想让坐席A听不到客户的声音，则可以使用静音功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1002,message->thisDN=10001_1002,message->otherDN=10001_1001,message->callID=x
```

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:292,

thisDN:"10001_1000",

callID:"",

otherDN:targetDN

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```


## 4.15.停止静音

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/> 当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：293</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>停止静音目标（坐席号或手机号）</td>
   </tr>
</table>

- 场景1:

    - 坐席A（坐席号为10001_1001）呼叫客户B（号码为182xxxxxxxx）,管理员坐席C（坐席号为10001_1002）想让坐席A取消静音，则可以使用停止静音功能；这种情况下，接口传递的参数值为：
```
thisDN=10001_1002,message->thisDN=10001_1002,message->otherDN=10001_1001,message->callID=x
```
**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:293,

thisDN:"10001_1000",

callID:"",

otherDN:targetDN

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```


## 4.16.开始录音

**参数描述**

<table>
   <tr align="center">
      <th colspan="3">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="3">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/> 当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="3">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="5">message </td>
      <td colspan="2">messageId</td>
      <td>number</td>
      <td>消息ID，取值：277</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" </td>
   </tr>
   <tr>
      <td colspan="2">callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td colspan="2">path</td>
      <td>String</td>
      <td>录音文件存放路径</td>
   </tr>
   <tr>
      <td>attachDatas</td>
      <td>limit</td>
      <td>String</td>
      <td>录音时长</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 277,

thisDN: "10001_1000",

path: "/record/",

callID:"b98171d8-95ad-11ea-a566-836ce3c48c2e",

attachDatas:{"limit":"60"

}

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```


## 4.17.停止录音

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" <br/> 当前登录坐席号</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="4">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：278</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000" </td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>path</td>
      <td>String</td>
      <td>录音文件存放路径</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 278,

thisDN: "10001_1000",

path: "/record/",

callID:"b98171d8-95ad-11ea-a566-836ce3c48c2e",

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```


## 4.18.开始监控坐席

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：266</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >agentDNS</td>
      <td>String[]</td>
      <td>需要监控的坐席号，例如：["10001_1001","10001_1002",...]</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:266,

thisDN:"10001_1000",

agentDNS:["10001_1001","10001_1002"]

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```


## 4.19.停止监控坐席

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：267</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >agentDNS</td>
      <td>String[]</td>
      <td>需要停止监控的坐席号，例如：["10001_1001","10001_1002",...]</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:267,

thisDN:"10001_1000",

agentDNS:["10001_1001","10001_1002"]

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.20.开始监控ACD

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>监控坐席messageId 固定为：275</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >queueDNS</td>
      <td>String[]</td>
      <td>需要监控的ACD编号，例如：["10001_8000","10001_8001",...]</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:275,

thisDN:"10001_1000",

queueDNS:["10001_8000","10001_8001",...]

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.21.停止监控ACD

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：276</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >queueDNS</td>
      <td>String[]</td>
      <td>需要停止监控的ACD编号，例如：["10001_8000","10001_8001",...]</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:276,

thisDN:"10001_1000",

queueDNS:["10001_8000","10001_8001",...]

})

};
```



## 4.22.开始监控IVR

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>监控坐席messageId固定为：301</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >tenantIDS</td>
      <td>String[]</td>
      <td>需要监控的资源组编号，例如：["10001","10002",...]</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:301,

thisDN:"10001_1000",

queueDNS:["10001","10002",...]

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.23.停止监控IVR

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：302</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >tenantIDS</td>
      <td>String[]</td>
      <td>需要停止监控的资源组编号，例如：["10001","10002",...]</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:302,

thisDN:"10001_1000",

queueDNS:["10001","10002",...]

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.24.接听来电/不接来电

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="3">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：294</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >isReject</td>
      <td>String</td>
      <td>是否接听来电(默认接听)：<br/>
		  0：接听来电<br/>
		  1：不接来电
	  </td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId:294,

thisDN:"10001_1000",

isReject:"0"

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.25.心跳请求包

**参数描述**

| **参数名称** | **类型** | **描述**                   |
|:--------------:|:----------:|----------------------------:|
| thisDN       | String   | 坐席号，例如："10001_1000" |
| type         | String   | 消息类型，取值："ping"     |
| message      | String   | 心跳消息                   |

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

message: "ping"

type: "ping"

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.26.通话发送按键

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="5">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：250</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>通话坐席，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>String</td>
      <td>发送按键目标号码:例如："18888888888"</td>
   </tr>
   <tr>
      <td>dtmfDigit</td>
      <td>String</td>
      <td>按键</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 250,

thisDN: "10001_1000",

callID:"xxx",

dtmfDigit:"1",

otherDN: "18888888888"

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```



## 4.27.通话放音

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>类型</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>String</td>
      <td>坐席号，例如："10001_1000"</td>
   </tr>
   <tr>
      <td colspan="2">type</td>
      <td>String</td>
      <td>消息类型，取值："request"</td>
   </tr>
   <tr>
      <td rowspan="5">message </td>
      <td>messageId</td>
      <td>number</td>
      <td>消息ID，取值：274</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>String</td>
      <td>通话坐席，例如："10001_1000"</td>
   </tr>
   <tr>
      <td >callID</td>
      <td>String</td>
      <td>通话ID，从通话事件中进行获取</td>
   </tr>
   <tr>
      <td>path</td>
      <td>String</td>
      <td>音频文件地址</td>
   </tr>
   <tr>
      <td>flag</td>
      <td>String</td>
      <td>放音类型：<br/>
		  1.给主叫放音<br/>
		  2.给被叫放音<br/>
		  4.全部放音  
	  </td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
var data = {

thisDN: "10001_1000",

type: "request",

message: JSON.stringify(

{

messageId: 274,

thisDN: "10001_1000",

callID:"xxx",

path:"/records/xxx.wav",

otherDN: "18888888888"

})

};

Socket.onopen=function () {

Socket.send(JSON.stringify(data));

}
```




# 5.通信事件

​		建立websocket连接后，服务器会推送相关的事件，具体如下：



## 5.1.坐席拨号事件

​		调用呼叫接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：505</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>被叫号码</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
	  	  2:呼入；<br/>
		  3:呼出
  	  </td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td>ANI</td>
      <td>主叫号码</td>
   </tr>
   <tr>
      <td>DNIS</td>
      <td>被叫号码</td>
   </tr>
   <tr>
      <td>thirdDN</td>
      <td>第三方号码</td>
   </tr>
   <tr>
      <td>thirdRole</td>
      <td>第三方类型<br/>
		  3 TransferredBy 转接 
</td>
   </tr>
</table>

**注：收到此事件，将会主动调用坐席示忙接口（携带的reasonCode为1），用于表示坐席已进入通话状态**

**代码示例**
```

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 505){

console.log("拨号中");

}

......

}
```



## 5.2.软电话注册事件

​		注册软电话后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：572</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td>sipIp</td>
      <td>话机注册IP</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 572){

console.log("软电话已注册");

}

......

}
```



## 5.3.软电话注销事件

​		退出软电话后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：574</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 574){

console.log("软电话注销");

}
```



## 5.4.坐席签入事件

​		调用坐席签入接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：580</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>thisQueues</td>
      <td>ACD编号(数据类型为String[])</td>
   </tr>
   <tr>
      <td>state</td>
      <td>坐席状态。<br/>
		  0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
		  1:空闲（坐席可以接听来电）；<br/>
		  2:忙碌（坐席无法接听来电，但可以外呼）
	  </td>
   </tr>
   <tr>
      <td>deviceState</td>
      <td>坐席对应的SIP终端的状态。<br/>0:未知；<br/>1:注册；<br/>2:注销</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td>reasonCode</td>
      <td>state为2（忙碌）的情况下，坐席忙碌的原因。<br/>
        0：整理（坐席结束通话后，进行文案处理）；<br/>
        1：通话（坐席处于通话中）；<br/>
        2：设备不可用（业务系统发送故障）；<br/>
        3：忙碌（其它的情况下，需要将state设置成3）；<br/>
        4：离开（坐席员离开座位）；<br/>
        5：休息（坐席员进行休息，比如午休）。<br/>
        6：拨号中(调用呼叫接口时的状态)<br/>
        7：外线振铃<br/>
        8：呼入振铃<br/>
        由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
	  </td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 580){

console.log("坐席已签入");

console.log("签入坐席号为："+_data.thisDN);

}

......

}
```



## 5.5.坐席签出事件

​		调用坐席签出接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：581</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>thisQueues</td>
      <td>ACD编号(数据类型为String[])</td>
   </tr>
   <tr>
      <td>state</td>
      <td>坐席状态。<br/>
		  0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
		  1:空闲（坐席可以接听来电）；<br/>
		  2:忙碌（坐席无法接听来电，但可以外呼）
	  </td>
   </tr>
   <tr>
      <td>deviceState</td>
      <td>坐席对应的SIP终端的状态。<br/>0:未知；<br/>1:注册；<br/>2:注销</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 581){

console.log("坐席已签出");

console.log("签出坐席号为："+_data.thisDN);

}

......

}
```



## 5.6.坐席空闲事件

​		调用坐席空闲接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：583</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>thisQueues</td>
      <td>ACD编号(数据类型为String[])</td>
   </tr>
   <tr>
      <td>state</td>
      <td>坐席状态。<br/>
		  0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
		  1:空闲（坐席可以接听来电）；<br/>
		  2:忙碌（坐席无法接听来电，但可以外呼）
	  </td>
   </tr>
   <tr>
      <td>deviceState</td>
      <td>坐席对应的SIP终端的状态。<br/>0:未知；<br/>1:注册；<br/>2:注销</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 583){

console.log("坐席已空闲");

console.log("空闲坐席号为："+_data.thisDN);

}

......

}
```



## 5.7.坐席示忙事件

​		调用坐席示忙接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：582</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>thisQueues</td>
      <td>ACD编号(数据类型为String[])</td>
   </tr>
   <tr>
      <td>state</td>
      <td>坐席状态。<br/>
		  0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
		  1:空闲（坐席可以接听来电）；<br/>
		  2:忙碌（坐席无法接听来电，但可以外呼）
	  </td>
   </tr>
   <tr>
      <td>deviceState</td>
      <td>坐席对应的SIP终端的状态。<br/>0:未知；<br/>1:注册；<br/>2:注销</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>reasonCode</td>
      <td>state为2（忙碌）的情况下，坐席忙碌的原因。<br/>
        0：整理（坐席结束通话后，进行文案处理）；<br/>
        1：通话（坐席处于通话中）；<br/>
        2：设备不可用（业务系统发送故障）；<br/>
        3：忙碌（其它的情况下，需要将state设置成3）；<br/>
        4：离开（坐席员离开座位）；<br/>
        5：休息（坐席员进行休息，比如午休）。<br/>
        6：拨号中(调用呼叫接口时的状态)<br/>
        7：外线振铃<br/>
        8：呼入振铃<br/>
        由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
	  </td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>


**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 582){

console.log("坐席示忙事件");

console.log("示忙坐席号为："+_data.thisDN);

if(_data.reasonCode == 0){

console.log("坐席是整理状态");

}else if(_data.reasonCode == 1){

console.log("坐席通话中");

}else if(_data.reasonCode == 2){

console.log("坐席设备不可用");

}else if(_data.reasonCode == 3){

console.log("坐席忙碌");

}else if(_data.reasonCode == 4){

console.log("坐席离开");

}else if(_data.reasonCode == 5){

console.log("坐席休息");

}

}

......

}
```



## 5.8.坐席来电事件

​		当有电话进来时返回该事件

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">messageId</td>
      <td>消息ID，取值：503</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td colspan="2">otherDN</td>
      <td>通话号码</td>
   </tr>
   <tr>
      <td colspan="2">callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td colspan="2">tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td colspan="2">extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td colspan="2">callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
		  2:呼入；<br/>
		  3:呼出
      </td>
   </tr>
   <tr>
      <td colspan="2">ANI</td>
      <td>主叫号码</td>
   </tr>
   <tr>
      <td colspan="2">DNIS</td>
      <td>被叫号码</td>
   </tr>
   <tr>
      <td colspan="2">thirdDN</td>
      <td>第三方号码</td>
   </tr>
   <tr>
      <td colspan="2">thirdRole</td>
      <td>第三方类型<br/>
		  3 TransferredBy 转接 
	  </td>
   </tr>
   <tr>
      <td>attachDatas</td>
      <td>fileNam</td>
      <td> 录音文件名</td>
   </tr>
</table>

**注：收到此事件，将会主动调用坐席示忙接口（携带的reasonCode为1），用于表示坐席已进入通话状态**

**代码示例**

```

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:

Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 503){

console.log("有来电");

}

......

}
```



## 5.9.呼叫建立事件

​		当双方呼叫建立时返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：506</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>对端号码</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
		  2:呼入；<br/>
		  3:呼出
      </td>
   </tr>
  </table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 506){

console.log("通话中");

}

......

}
```



## 5.10.呼叫释放事件

​		当有一方结束通话返回该事件

**参数描述**

<table>
   <tr align="center">
      <th colspan="2">参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td colspan="2">messageId</td>
      <td>消息ID，取值：515</td>
   </tr>
   <tr>
      <td colspan="2">thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td colspan="2">otherDN</td>
      <td>对端号码</td>
   </tr>
   <tr>
      <td colspan="2">callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td colspan="2">tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td colspan="2">extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td colspan="2">callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
		  2:呼入；<br/>
		  3:呼出
      </td>
   </tr>
   <tr>
      <td>attachDatas</td>
      <td>hangupCause</td>
      <td> 挂断原因：<br/>
		  呼叫成功 send_bye:主叫挂断;recv_bye:被叫挂断<br/>
		  呼叫失败 call_failed<br/>
		  被叫拒接 CALL_REJECTED<br/>
		  无应答 NO_ANSWER
	  </td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 515){

console.log("通话结束");

}

......

}
```



## 5.11.录音开始事件

​		当通话开始录音时返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：589</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>对端号码</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
		  2:呼入；<br/>
		  3:呼出
      </td>
   </tr>
   <tr>
      <td>fileName</td>
      <td>录音文件路径</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
  </table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 589){

console.log("录音开始");

}

......

}
```



## 5.12.录音停止事件

​		当有一方结束通话返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：519</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>对端号码</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
		  2:呼入；<br/>
		  3:呼出
      </td>
   </tr>
   <tr>
      <td>duration</td>
      <td>通话中时长 单位/秒</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td>fileName</td>
      <td>录音文件路径</td>
   </tr>
  </table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```

Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 519){

console.log("录音停止");

}

......

}
```



## 5.13.呼叫保持事件

​		调用呼叫保持接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：509</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>对端号码</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 509){

console.log("呼叫保持");

}

......

}
```



## 5.14.呼叫取回事件

​		调用呼叫取回接口后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：513</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>对端号码</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
</table>
**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 513){

console.log("呼叫取回");

}

......

}
```



## 5.15.坐席状态监控事件

​		调用开始监控坐席接口后，通过此事件上报坐席信息

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：588</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>被监控坐席号</td>
   </tr>
   <tr>
      <td>monitorExtension</td>
      <td>被监控坐席分机号</td>
   </tr>
   <tr>
      <td>agentState</td>
      <td>坐席状态。<br/>
		  0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
		  1:空闲（坐席可以接听来电）；<br/>
		  2:忙碌（坐席无法接听来电，但可以外呼）
	  </td>
   </tr>
   <tr>
      <td>reasonCode</td>
      <td>state为2（忙碌）的情况下，坐席忙碌的原因。<br/>
        0：整理（坐席结束通话后，进行文案处理）；<br/>
        1：通话（坐席处于通话中）；<br/>
        2：设备不可用（业务系统发送故障）；<br/>
        3：忙碌（其它的情况下，需要将state设置成3）；<br/>
        4：离开（坐席员离开座位）；<br/>
        5：休息（坐席员进行休息，比如午休）。<br/>
        由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
	  </td>
   </tr>
   <tr>
      <td>callID</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>呼叫类型。<br/>
		  0:未知；<br/>
		  1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
		  2:呼入；<br/>
		  3:呼出
 	  </td>
   </tr>
   <tr>
      <td>otherDN</td>
      <td>被叫号码</td>
   </tr>
   <tr>
      <td>deviceState</td>
      <td>坐席对应的SIP终端的状态。<br/>0:未知；<br/>1:注册；<br/>2:注销</td>
   </tr>
   <tr>
      <td>tenantID</td>
      <td>资源组编号</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>请求坐席</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 588){

console.log("监控到坐席状态改变");

}

......

}
```



## 5.16.ACD状态监控事件

​		调用开始监控ACD接口后，通过此事件上报坐席信息

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：520</td>
   </tr>
   <tr>
      <td>thisQueue</td>
      <td>ACD编号</td>
   </tr>
   <tr>
      <td>queueNum</td>
      <td>排队中通话数量</td>
   </tr>
   <tr>
      <td>queueSum</td>
      <td>队列上的通话总数(等于queueNum加上callingNum)</td>
   </tr>
   <tr>
      <td>callingNum</td>
      <td>队列上正在通话的数量(转到坐席或坐席已接听) </td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>当前登录坐席号</td>
   </tr>
   <tr>
      <td>agentReadyNum</td>
      <td>空闲坐席数。空闲坐席是指坐席状态为空闲,对应的sip终端已注册</td>
   </tr>
   <tr>
      <td>status</td>
      <td>ACD当前通话话务状态<br/>
		  0：进入ACD<br/>
		  1：坐席应答<br/>
		  2：退出ACD<br/>
		  3：转接坐席<br/>
		  4：坐席拒接
	  </td>
   </tr>
   <tr>
      <td>holdTime</td>
      <td>当前通话排队时间</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>当前通话呼叫方向</td>
   </tr>
   <tr>
      <td>callerID</td>
      <td>转接坐席</td>
   </tr>
   <tr>
      <td>ani</td>
      <td>主叫号码</td>
   </tr>
    <tr>
      <td>dnis</td>
      <td>被叫号码</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
   <tr>
      <td>callID</td>
      <td>呼叫标识</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 520){

console.log("监控到ACD状态改变");

}

......

}
```



## 5.17.IVR状态监控事件

​		调用开始监控IVR接口后，通过此事件上报IVR信息

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：605</td>
   </tr>
   <tr>
      <td>callId</td>
      <td>通话ID</td>
   </tr>
   <tr>
      <td>tenantId</td>
      <td>资源组号</td>
   </tr>
   <tr>
      <td>startTime</td>
      <td>开始时间</td>
   </tr>
   <tr>
      <td>endTime</td>
      <td>结束时间</td>
   </tr>
   <tr>
      <td>ani</td>
      <td>主叫号码</td>
   </tr>
    <tr>
      <td>dnis</td>
      <td>被叫号码</td>
   </tr>
   <tr>
      <td>callType</td>
      <td>呼叫方向(2:呼入  3:呼出)</td>
   </tr>
   <tr>
      <td>thisQueue</td>
      <td>转接ACD</td>
   </tr>
   <tr>
      <td>ivrStatus</td>
      <td>Ivr状态：<br/>
		  start:进入IVR<br/>
		  execute_start:进入节点<br/>
		  get_digit:获取按键<br/>
		  play_audio_file:播放语音<br/>
		  execute_end:退出节点<br/>
		  stop:退出IVR
	  </td>
   </tr>
   <tr>
      <td>filename</td>
      <td>节点语音文件名</td>
   </tr>
   <tr>
      <td>ivrDigitType</td>
      <td>转接类型<br/>
		  1:转ACD<br/>
		  2:转节点<br/>
	  	  3:转外线号码<br/>
		  4:直接挂断<br/>
		  5:转语音信箱<br/>
		  6:转分机<br/>
		  9:输入分机<br/>
		  10:tts<br/>
		  11:自定义模块<br/>
		  -4:收集按键<br/>
		  null:直转目标
	  </td>
   </tr>
   <tr>
      <td>ivrDtmfDigit</td>
      <td>按键</td>
   </tr>
   <tr>
      <td>ivrNode</td>
      <td>Ivr节点ID</td>
   </tr>
   <tr>
      <td>name</td>
      <td>节点名称</td>
   </tr>
   <tr>
      <td>eventSequence</td>
      <td>流程序号(顺序由小到大排列)</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>请求坐席</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 605){

console.log("监控到IVR状态改变");

}

......

}
```



## 5.18.坐席请求失败事件

​		调用接口失败后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：9999</td>
   </tr>
   <tr>
      <td>errorMessageId</td>
      <td>错误请求meeageId</td>
   </tr>
   <tr>
      <td>errorCode</td>
      <td>错误码</td>
   </tr>
   <tr>
      <td>errorMessage</td>
      <td>错误信息</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>请求坐席</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

errorCode **错误码描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>4</td>
      <td>未找到callID，可能该通话已经挂断</td>
   </tr>
   <tr>
      <td>14</td>
      <td>未找到该坐席资源</td>
   </tr>
   <tr>
      <td>18</td>
      <td>请求参数错误</td>
   </tr>
   <tr>
      <td>27</td>
      <td>请求过快，两秒内发送了两次相同请求</td>
   </tr>
   <tr>
      <td>31</td>
      <td>签入未指定分机设备</td>
   </tr>
   <tr>
      <td>32</td>
      <td>坐席通话中</td>
   </tr>
   <tr>
      <td>33</td>
      <td>分机已签入</td>
   </tr>
   <tr>
      <td>34</td>
      <td>坐席已签入</td>
   </tr>
   <tr>
      <td>35</td>
      <td>转接失败</td>
   </tr>
   <tr>
      <td>36</td>
      <td>静音失败</td>
   </tr>
   <tr>
      <td>37</td>
      <td>取消静音失败</td>
   </tr>
   <tr>
      <td>38</td>
      <td>异常退出保持</td>
   </tr>
   <tr>
      <td>39</td>
      <td>保持外呼失败</td>
   </tr>
   <tr>
      <td>40</td>
      <td>三方求助失败</td>
   </tr>
   <tr>
      <td>41</td>
      <td>为绑定分机不允许空闲</td>
   </tr>
   <tr>
      <td>300</td>
      <td>授权到期，请联系管理员</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 9999){

console.log("调用接口失败");

}

......

}
```



## 5.19.坐席注销事件

​		坐席被注销后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：4500</td>
   </tr>
   <tr>
      <td>reason</td>
      <td>注销原因<br/>
		  1:坐席在其他位置登陆<br/>
		  2:坐席账号被注销
	  </td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 4500){

console.log("坐席在其他地方登陆");

}

......

}
```



## 5.20.坐席请求提示事件

​		调用配置类接口返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：8888</td>
   </tr>
   <tr>
      <td>succeeMessageId</td>
      <td>提示请求meeageId</td>
   </tr>
   <tr>
      <td>referenceID</td>
      <td>提示码</td>
    </tr>
   <tr>
      <td>thisDN</td>
      <td>请求坐席</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

referenceID**提示码描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>0</td>
      <td>休息时长到期提示</td>
   </tr>
   <tr>
      <td>1</td>
      <td>休息排队提示</td>
   </tr>
   <tr>
      <td>2</td>
      <td>接听来电</td>
   </tr>
   <tr>
      <td>3</td>
      <td>不接来电</td>
   </tr>
   <tr>
      <td>4</td>
      <td>转接成功</td>
   </tr>
   <tr>
      <td>6</td>
      <td>静音成功</td>
   </tr>
   <tr>
      <td>7</td>
      <td>取消静音成功</td>
   </tr>
   <tr>
      <td>8</td>
      <td>保持外呼成功</td>
   </tr>
   <tr>
      <td>9</td>
      <td>三方求助成功</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 8888){

if(_data.referenceID== 0){

console.log("休息时长已到");

}else if(_data.referenceID== 1){

console.log("休息请求排队中");

}

}

......

}
```


## 5.21.心跳返回事件

坐席调用心跳请求包后返回该事件

**参数描述**

<table>
   <tr align="center">
      <th>参数名称</th>
      <th>描述</th>
   </tr>
   <tr>
      <td>messageId</td>
      <td>消息ID，取值：3</td>
   </tr>
   <tr>
      <td>thisDN</td>
      <td>坐席号</td>
   </tr>
   <tr>
      <td>extension</td>
      <td>分机号</td>
   </tr>
</table>

**代码示例**

Websocket详见[《WebSocket简介》](#_WebSocket简介)。以下假设已经创建了Socket对象:
```
Socket.onmessage=function (msg) {

var data=JSON.parse(msg.data);

callback(data);

}

function callback(_data){

if(_data.messageId == 3){

console.log("心跳包");

}

......

}
```






# 6.数据查询接口



## 6.1.未绑定资源组

请求方式：POST

请求url:
```
http(s)://{url}/5.0.x.20210203_release/binduser/unboundTenants
```
示例：
```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/binduser/unboundTenants
```
请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例
```
{

"actionID": "abcd123"

}
```
返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>资源组ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>资源组名称</td>
    </tr>
    <tr>
    	<td>count</td>
        <td>该资源组下ACD数量</td>
    </tr>
</table>

code:
| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |



返回200示例：
```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": [{"id":10000,"name":"xxx","count":"5"}...]

}
```
返回201示例：
```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.2.未绑定ACD

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/binduser/unboundQueues
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/binduser/unboundQueues
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>坐席ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>ACD名称</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>count</td>
        <td>该ACD下坐席数量</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": [{"id":1005,"queueName":"10000_8000",

"name":"默认组","count":"5"}...]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.3.未绑定坐席

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/binduser/unboundUsers
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/binduser/unboundUsers
```

请求体

| 字段      | 类型   | 是否必须 | 备注                        |
|-----------|--------|----------|-----------------------------|
| tenantId  | String | 是       | 资源组编号：如10000         |
| queueId   | String | 否       | ACD组ID                     |
| queueName | String | 否       | ACD编号: 如10000_8000       |
| actionID  | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"tenantId": "10000",

"queueName": "10000_8000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>坐席ID</td>
    </tr>
    <tr>
    	<td>nameCn</td>
        <td>坐席姓名</td>
    </tr>
    <tr>
    	<td>userName</td>
        <td>坐席号</td>
    </tr>
   <tr>
    	<td>queueName</td>
        <td>坐席所属ACD编号</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":
[{"id":1005,"nameCn":"admin","userName":"10000_1000","queueName":"10000_8000"}]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.4.资源组列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantinfos
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantinfos
```

请求体

| 字段        | 类型   | 是否必须 | 备注                          |
|-------------|--------|----------|-------------------------------|
| tenantId    | String | 否       | 资源组编号：如10000           |
| name        | String | 否       | 资源组名称                    |
| status      | String | 否       | 资源组状态。 1：启用  0：注销 |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回   |
| currentPage | String | 否       | 当前页                        |
| pageSize    | String | 否       | 页大小                        |

请求体示例

```
{

"tenantId": "10000",

"name": "xxx",

"status": "1",

"actionID": "abcd123",

"currentPage": "1",

"pageSize": "10"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>资源组ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>资源组名称</td>
    </tr>
    <tr>
    	<td>contact</td>
        <td>资源组负责人</td>
    </tr>
    <tr>
    	<td>gatewayGroup</td>
        <td>网关组ID。<br/>
		  	为-1时表示未绑定任何网关组
		</td>
    </tr>
    <tr>
    	<td>recordType</td>
        <td>录音类型。<br/>
			bridge:通话后录音<br/>
			no:不开启录音
		</td>
    </tr>
    <tr>
    	<td>status</td>
        <td>资源组是否启用。<br/>
			1:启用<br/>
			0:注销
		</td>
    </tr>
    <tr>
    	<td>afterState</td>
        <td>坐席通话后状态。<br/>
			1:空闲（坐席可以接听来电）；<br/>
			2:忙碌（坐席无法接听来电，但可以外呼，忙碌的原因为整理，reasonCode为0）
</td>
    </tr>
    <tr>
    	<td>restNum</td>
        <td>休息人数上限</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": [

{

"id":"1",

"name":"10001_1000",

"contact":"xxx",

"gatewayCroup":"123456@qq.com",

"recordType":"bridge",

"status":"1",

"afterState":"1",

"restNum":"1",}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.5.资源组详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantinfo
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantinfo
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
    <tr>
      <td colspan="2">outAgent</td>
      <td >当前资源组不可用坐席数</td>
   </tr>
   <tr>
      <td colspan="2">startAgent</td>
      <td >当前资源组可用坐席数</td>
   </tr>
   <tr>
      <td rowspan="5">outboundConfig(当前资源组外拨设置)</td>
      <td>maxRatio</td>
      <td>外拨比率限制</td>
   </tr>
   <tr>
      <td>idleTime</td>
      <td>外拨呼叫间隔,单位:毫秒</td>
   </tr>
   <tr>
      <td>hasVgc</td>
      <td>语音群呼权限 <br/>0:无权限;<br/>1:有权限</td>
   </tr>
   <tr>
      <td>ivrIdleTime</td>
      <td>语音群呼间隔,单位:毫秒</td>
   </tr>
   <tr>
      <td>ivrRatio</td>
      <td>语音群呼比率</td>
   </tr>
  <tr>
      <td rowspan="6">tenantFee(当前资源组费率相关)</td>
      <td>balance</td>
      <td>账户余额</td>
   </tr>
   <tr>
      <td>campaignRate</td>
      <td>群呼费率</td>
   </tr>
   <tr>
      <td>inboundRate</td>
      <td>呼入费率</td>
   </tr>
   <tr>
      <td>limitFee</td>
      <td>最低消费</td>
   </tr>
   <tr>
      <td>monthRate</td>
      <td>月租费用</td>
   </tr>
   <tr>
      <td>outboundRate</td>
      <td>手呼费率</td>
   </tr>
   <tr>
      <td rowspan="10">tenantInfo(当前资源组详情)</td>
      <td>id</td>
      <td>资源组ID</td>
   </tr>
   <tr>
      <td>name</td>
      <td>资源组名称</td>
   </tr>
   <tr>
      <td>contact</td>
      <td>资源组负责人</td>
   </tr>
   <tr>
      <td>gatewayGroup</td>
      <td>网关组ID为-1时表示未绑定任何网关组</td>
   </tr>
   <tr>
      <td>recordType</td>
      <td>录音类型 <br/>bridge:通话后录音;<br/>no:不开启录音</td>
   </tr>
   <tr>
      <td>status</td>
      <td>资源组是否启用 <br/>1:启用; <br/>0:注销</td>
   </tr>
    <tr>
      <td>afterState</td>
      <td>坐席通话后状态。<br/>
		  1:空闲（坐席可以接听来电）；<br/>
		  2:忙碌（坐席无法接听来电，但可以外呼，忙碌的原因为整理，reasonCode为0）
	  </td>
   </tr>
   <tr>
      <td>gatewayGroupName</td>
      <td>网关组名称</td>
   </tr>
   <tr>
      <td>hideNumber</td>
      <td>号码隐藏 <br/>1:是;<br/>0:否</td>
   </tr>
   <tr>
      <td>bridgeAnswerTimeout</td>
      <td>外拨振铃时长</td>
   </tr>
</table>


code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"outAgent":"5",

"startAgent":"20",

"outboundConfig":{

"maxRatio":"0.1",

"idleTime":"2000",

"hasVgc":"0",

"ivrIdleTime":"1000",

"ivrRatio":"0.1"

},

"tenantFee":{

"balance":"10000",

"campaignRate":"0.01",

"inboundRate":"0",

"limitFee":"50",

"monthRate":"100",

"outboundRate":"0.04"

},

"tenantInfo":{

"id":"1",

"name":"10001_1000",

"contact":"xxx",

"gatewayCroup":"123456@qq.com",

"recordType":"bridge",

"status":"1",

"afterState":"1"

}

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.6.ACD列表

注意，本接口的使用请联系对接人员

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueues
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueues
```

请求体

| 字段        | 类型   | 是否必须 | 备注                        |
|-------------|--------|----------|-----------------------------|
| tenantId    | String | 是       | 资源组编号：如10000         |
| name        | String | 否       | ACD名或ACD编号              |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回 |
| currentPage | String | 否       | 当前页                      |
| pageSize    | String | 否       | 页大小                      |

请求体示例

```
{

"tenantId": "10000",

"name": "8000",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
	<tr>
    	<td>id</td>
        <td>ACD组ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>ACD名称</td>
    </tr>
    <tr>
    	<td>code</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>ACD全称</td>
    </tr>
    <tr>
    	<td>strategy</td>
        <td>振铃策略,有如下值：<br/>
   random:随机;top-down:顺序;round-robin:轮转;Stringest-idle-agent:最长空闲时间;agent-with-least-talk-time:最少通话时间;agent-with-fewest-calls:最少通话次数;ring-all:同振。
		</td>
    </tr>
    <tr>
    	<td>outboundNumber</td>
        <td>外显号码</td>
    </tr>
    <tr>
    	<td>maxWaitTimeWithNoAgent</td>
        <td>最大排队等待时间,单位：秒</td>
    </tr>
    <tr>
    	<td>count</td>
        <td>成员数</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [

{

"id":"1",

"tenantId":"10001",

"name":"默认组",

"code":"8000",

"queueName":"10001_8000",

"strategy":"random",

"outboundNumber":"1234567",

"maxWaitTimeWithNoAgent":"1",

"count":"25"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.7.ACD详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueue
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueue
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |
| queue    | String | 是       | ACD编号                     |

请求体示例

```
{

"tenantId": "10000",

"queue": "10000_8000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>ACD组ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>ACD名称</td>
    </tr>
    <tr>
    	<td>code</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>ACD全称</td>
    </tr>
    <tr>
    	<td>strategy</td>
        <td>振铃策略,有如下值：<br/>
   random:随机;top-down:顺序;round-robin:轮转;Stringest-idle-agent:最长空闲时间;agent-with-least-talk-time:最少通话时间;agent-with-fewest-calls:最少通话次数;ring-all:同振。
		</td>
    </tr>
    <tr>
    	<td>outboundNumber</td>
        <td>外显号码</td>
    </tr>
    <tr>
    	<td>maxWaitTimeWithNoAgent</td>
        <td>最大排队等待时间,单位：秒</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>成员 {"1":"10001_1000","2":"10001_1001","3":"10001_1002"...}</td>
    </tr>
    <tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"name":"默认组",

"code":"8000",

"queueName":"10001_8000",

"strategy":"random",

"outboundNumber":"1234567",

"maxWaitTimeWithNoAgent":"1",

"agent":["10001_1000","10001_1001"...]

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.8.ACD实时数据

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/callcenter/queryQueueRealtimeData
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/callcenter/queryQueueRealtimeData
```

请求体

| 字段      | 类型   | 是否必须 | 备注                        |
|-----------|--------|----------|-----------------------------|
| actionID  | String | 是       | 唯一值,在响应信息中原样返回 |
| queueName | String | 否       | 监控ACD号，多个ACD逗号隔开  |
| tenantId  | String | 是       | 资源组号                    |

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>thisQueue</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>queueNum</td>
        <td>排队数</td>
    </tr>
    <tr>
    	<td>queueSum</td>
        <td>队列总数(等于queueNum加上callingNum)</td>
    </tr>
    <tr>
    	<td>callingNum</td>
        <td>通话数(转到坐席或坐席已接听)</td>
    </tr>
    <tr>
    	<td>maxHoldTime</td>
        <td>最大排队时长</td>
    </tr>
    <tr>
    	<td>description</td>
        <td>队列名称</td>
    </tr>
    <tr>
    	<td>logoutNum</td>
        <td>坐席离线数量</td>
    </tr>
    <tr>
    	<td>loginNum</td>
        <td>坐席在线数量</td>
    </tr>
    <tr>
    	<td>readyNum</td>
        <td>坐席空闲数量</td>
    </tr>
    <tr>
    	<td>busyNum</td>
        <td>坐席忙碌数量</td>
    </tr>
    <tr>
    	<td>registerNum</td>
        <td>坐席注册数量</td>
    </tr>
    <tr>
    	<td>reasonCodeNum</td>
        <td>不同reasonCode坐席数量</td>
    </tr>
    <tr>
    	<td>estimatedWaitingTime</td>
        <td>估计等待时长</td>
    </tr>
    <tr>
    	<td>inCalls</td>
        <td>当天呼入次数</td>
    </tr>
    <tr>
    	<td>inAnswerCalls</td>
        <td>呼入通话次数</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"queueNum": 0,

"maxHoldTime": 0,

"thisQueue": "10005_8000",

"reasonCodeNum": {

"3": 1

},

"description": "sd",

"readyNum": 0,

"busyNum": 2,

"queueSum": 0,

"callingNum": 0,

"loginNum": 2,

"logoutNum": 3

}

],

"message": "success!",

"totalCount": ""

}
```



## 6.9.ACD实时排队数据

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/callcenter/queryQueueRealtimeQueueData
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/callcenter/queryQueueRealtimeQueueData
```

请求体

| 字段      | 类型   | 是否必须 | 备注                        |
|-----------|--------|----------|-----------------------------|
| actionID  | String | 是       | 唯一值,在响应信息中原样返回 |
| queueName | String | 是       | 监控ACD号                   |

请求体示例

```
{

"queueName": "10000_8000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>thisQueue</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>holdTime</td>
        <td>最大排队时长</td>
    </tr>
    <tr>
    	<td>thisQueue</td>
        <td>ACD号</td>
    </tr>
    <tr>
    	<td>description</td>
        <td>描述</td>
    </tr>
    <tr>
    	<td>thisDN</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>ani</td>
        <td>主叫号码</td>
    </tr>
    <tr>
    	<td>dnis</td>
        <td>被叫号码</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>呼叫标识</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"data": [

{

"callId": "3cfa37e2-e77b-11ea-a1ec-1b3428b01be0",

"thisDN": "",

"extension": "",

"thisQueue": "10003_8000",

"description": "admin",

"dnis": "",

"ani": "",

"holdTime": 14

},

{

"callId": "3d466a36-e77b-11ea-a1f5-1b3428b01be0",

"thisDN": "111774087",

"thisQueue": "10003_8000",

"description": "admin",

"dnis": "2021062801",

"ani": "111774087",

"holdTime": 0

}

],

"message": "success!"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.10.分机列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryExtension
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryExtension
```

请求体

| 字段        | 类型   | 是否必须 | 备注                        |
|-------------|--------|----------|-----------------------------|
| tenantId    | String | 是       | 资源组编号：如10000         |
| status      | String | 否       | 分机状态（1启用，0停用）    |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回 |
| currentPage | String | 否       | 当前页                      |
| pageSize    | String | 否       | 页大小                      |

请求体示例

```
{

"tenantId": "10000",

"status": "1",

"actionID": "abcd123",

"currentPage": "1",

"pageSize": "10"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>坐席ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>status</td>
        <td>账号状态1启用 0注销</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>password</td>
        <td>分机注册密码</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": [

{

"id":"1",

"tenantId":"10001",

"name":"10001_1000",

"nameCn":"xxx",

"status":"1",

"extension":"400001",

"createdTime":"2017-10-10 12:00:00"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.11.坐席列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryUsers
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryUsers
```

请求体

| 字段        | 类型   | 是否必须 | 备注                        |
|-------------|--------|----------|-----------------------------|
| tenantId    | String | 是       | 资源组编号：如10000         |
| queueName   | String | 否       | ACD号                       |
| name        | String | 否       | 坐席号                      |
| nameCn      | String | 否       | 坐席人员姓名                |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回 |
| currentPage | String | 否       | 当前页                      |
| pageSize    | String | 否       | 页大小                      |

请求体示例

```
{

"tenantId": "10000",

"name": "10001_1000",

"nameCn": "xxx",

"actionID": "abcd123",

"currentPage": "1",

"pageSize": "10"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>坐席ID</td>
    </tr>
    <tr>
    	<td>nameCn</td>
        <td>坐席姓名</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>status</td>
        <td>账号状态<br/>1启用 <br/>0注销</td>
    </tr>
    <tr>
    	<td>queue</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>createTime</td>
        <td>创建时间</td>
    </tr>
    <tr>
    	<td>queueId</td>
        <td>ACD组ID</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": [

{

"id":"1",

"tenantId":"10001",

"name":"10001_1000",

"nameCn":"xxx",

"status":"1",

"extension":"400001",

"createdTime":"2017-10-10 12:00:00"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.12.坐席详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryUser
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryUser
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |
| id       | String | 是       | 坐席ID                      |

请求体示例

```
{

"tenantId": "10000",

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>坐席ID</td>
    </tr>
    <tr>
    	<td>nameCn</td>
        <td>坐席姓名</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>status</td>
        <td>账号状态<br/>1启用 <br/>0注销</td>
    </tr>
    <tr>
    	<td>queue</td>
        <td>ACD编号</td>
    </tr>
    <tr>
    	<td>createTime</td>
        <td>创建时间</td>
    </tr>
    <tr>
    	<td>queueId</td>
        <td>ACD组ID</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"name":"10001_1000",

"nameCn":"xxx",

"status":"1",

"extension":"400001",

"createdTime":"2017-10-10 12:00:00"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.13.坐席状态

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/callcenter/queryAgentStates
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/callcenter/queryAgentStates
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
        <td>tenantId</td>
        <td>String</td>
    	<td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
        <td>agent</td>
        <td>String</td>
    	<td>否</td>
        <td>坐席号，多个逗号隔开(与参数extension,queueName可选,只需填一项)</td>
    </tr>
    <tr>
        <td>extension</td>
        <td>String</td>
    	<td>否</td>
        <td>分机号，多个逗号隔开(与参数agent,queueName可选,只需填一项)</td>
    </tr>
    <tr>
        <td>queueName</td>
        <td>String</td>
    	<td>否</td>
        <td>ACD号，多个逗号隔开(与参数extension,agent只需填一项)</td>
    </tr>
    <tr>
        <td>state</td>
        <td>String</td>
    	<td>否</td>
        <td>坐席状态<br/>
			0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
			1:空闲（坐席可以接听来电）；<br/>
			2:忙碌（坐席无法接听来电，但可以外呼）<br/>
			3:在线坐席 
		</td>
    </tr>
    <tr>
        <td>reasonCode</td>
        <td>String</td>
    	<td>否</td>
        <td>tate为2（忙碌）的情况下，坐席忙碌的原因。<br/>
            0：整理（坐席结束通话后，进行文案处理）；<br/>
            1：通话（坐席处于通话中）；<br/>
            2：设备不可用（业务系统发送故障）；<br/>
            3：忙碌（其它的情况下，需要将state设置成3）；<br/>
            4：离开（坐席员离开座位）；<br/>
            5：休息（坐席员进行休息，比如午休）。<br/>
            6：拨号中(调用呼叫接口时的状态)<br/>
            7：外线振铃<br/>
            8：呼入振铃<br/>
由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方面后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
		</td>
    </tr>
    <tr>
        <td>actionID</td>
        <td>String</td>
    	<td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10003",

"agent":"10003_1000,10003_1001,10003_1002,10003_1003,10003_1004,10003_1005",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>坐席名称</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>state</td>
        <td>坐席状态<br/>
			0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
			1:空闲（坐席可以接听来电）；<br/>
			2:忙碌（坐席无法接听来电，但可以外呼）
		</td>
    </tr>
    <tr>
    	<td>reasonCode</td>
        <td>state为2（忙碌）的情况下，坐席忙碌的原因。<br/>
            0：整理（坐席结束通话后，进行文案处理）；<br/>
            1：通话（坐席处于通话中）；<br/>
            2：设备不可用（业务系统发送故障）；<br/>
            3：忙碌（其它的情况下，需要将state设置成3）；<br/>
            4：离开（坐席员离开座位）；<br/>
            5：休息（坐席员进行休息，比如午休）。<br/>
            6：拨号中(调用呼叫接口时的状态)<br/>
            7：外线振铃<br/>
            8：呼入振铃<br/>
            由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方面后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
		</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"data": [

{

"agent": "10003_1000",

"extension": null,

"reasonCode": 3,

"state": 1

},

{

"agent": "10003_1001",

"extension": null,

"state": 0

},

{

"agent": "10003_1002",

"extension": null,

"state": 0

},

{

"agent": "10003_1003",

"extension": null,

"state": 1

},

{

"agent": "10003_1004",

"extension": null,

"state": 1

},

{

"agent": "10003_1005",

"extension": null,

"state": 0

}

],

"message": "success!"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.14.坐席实时数据

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/callcenter/queryAgentRealtimeData
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/callcenter/queryAgentRealtimeData
```

请求体

| 字段      | 类型   | 是否必须 | 备注                                                           |
|-----------|--------|----------|----------------------------------------------------------------|
| tenantId  | String | 是       | 资源组编号：如10000                                            |
| agent     | String | 否       | 坐席号，多个逗号隔开(与参数extension,queueName可选,只需填一项) |
| extension | String | 否       | 分机号，多个逗号隔开(与参数agent,queueName可选,只需填一项)     |
| queueName | String | 否       | ACD号，多个逗号隔开(与参数extension,agent只需填一项)           |
| typeCode  | String | 否       | 业务编码                                                       |
| typeText  | String | 否       | 业务类型                                                       |
| actionID  | String | 是       | 唯一值,在响应信息中原样返回                                    |

请求体示例

{

"tenantId": "10003",

"agent":"10003_1000,10003_1001,10003_1002,10003_1003,10003_1004,10003_1005",

"actionID": "abcd123"

}

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>坐席人员姓名</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>state</td>
        <td>坐席状态<br/>
			0:登出（坐席不再接收通信事件，且无法调用通信API）；<br/>
			1:空闲（坐席可以接听来电）；<br/>
			2:忙碌（坐席无法接听来电，但可以外呼）
		</td>
    </tr>
    <tr>
    	<td>reasonCode</td>
        <td>state为2（忙碌）的情况下，坐席忙碌的原因。<br/>
            0：整理（坐席结束通话后，进行文案处理）；<br/>
            1：通话（坐席处于通话中）；<br/>
            2：设备不可用（业务系统发送故障）；<br/>
            3：忙碌（其它的情况下，需要将state设置成3）；<br/>
            4：离开（坐席员离开座位）；<br/>
            5：休息（坐席员进行休息，比如午休）。<br/>
            6：拨号中(调用呼叫接口时的状态)<br/>
            7：外线振铃<br/>
            8：呼入振铃<br/>
            由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方面后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长
		</td>
    </tr>
    <tr>
    	<td>deviceState</td>
        <td>坐席对应的SIP终端的状态<br/>
			1:注册<br/>
			2:注销
		</td>
    </tr>
    <tr>
    	<td>callID</td>
        <td>呼叫标识</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>通话号码</td>
    </tr>
      <tr>
    	<td>callType</td>
        <td>呼叫方向<br/>
			呼叫类型。<br/>
			1:内部呼叫（坐席互拨；坐席拨打ACD；坐席拨打IVR）；<br/>
			2:呼入；<br/>
			3:呼出
		</td>
    </tr>
    <tr>
    	<td>readyTime</td>
        <td>当天空闲时间 单位/秒</td>
    </tr>
     <tr>
    	<td>readyCount</td>
        <td>当天空闲次数</td>
    </tr>
    <tr>
    	<td>busyTime</td>
        <td>当天忙碌时间 单位/秒</td>
    </tr>
    <tr>
    	<td>busyCount</td>
        <td>当天忙碌次数</td>
    </tr>
    <tr>
    	<td>logoutCount</td>
        <td>当天签出次数</td>
    </tr>
    <tr>
    	<td>loginCount</td>
        <td>当天签入次数</td>
    </tr>
    <tr>
    	<td>outCalls</td>
        <td>当天呼出次数</td>
    </tr>
    <tr>
    	<td>outTalkTime</td>
        <td>当天呼出通话中时长</td>
    </tr>
    <tr>
    	<td>inCalls</td>
        <td>当天呼入次数</td>
    </tr>
    <tr>
    	<td>inTalkTime</td>
        <td>当天呼入通话中时长</td>
    </tr>
     <tr>
    	<td>outAnswerCalls</td>
        <td>呼出通话次数</td>
    </tr>
    <tr>
    	<td>inAnswerCalls</td>
        <td>呼入通话次数</td>
    </tr>
    <tr>
    	<td>callHoldTime</td>
        <td>当前通话持续时长</td>
    </tr>
    <tr>
    	<td>stateHoldTime</td>
        <td>当前状态持续时长</td>
    </tr>
     <tr>
    	<td>typeCode</td>
        <td>坐席业务编码</td>
    </tr>
    <tr>
    	<td>typeType</td>
        <td>坐席业务类型</td>
    </tr>
    <tr>
    	<td>busyReason</td>
        <td>当天忙碌详细</td>
    </tr>
    <tr>
    	<td>thisQueue</td>
        <td>ACD号</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>技能名称</td>
    </tr>
    <tr>
    	<td>inNoAnswerCalls</td>
        <td>呼入未接听数</td>
    </tr>
     <tr>
    	<td>avgTalkTime</td>
        <td>平均通话中时长</td>
    </tr>
    <tr>
    	<td>talkTime</td>
        <td>坐席通话总时长</td>
    </tr>
</table>

busyReason：

<table>
	<tr>
    	<td>reasonCode</td>
        <td>当天操作编码</td>
    </tr>
    <tr>
    	<td>operationCount</td>
        <td>当天操作次数</td>
    </tr>
    <tr>
    	<td>operationTime</td>
        <td>当天操作时长</td>
    </tr>
 </table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"data": [

{

"agent": "10003_1000",

"extension": null,

"inTalkTime": 0,

"logoutCount": 2,

"outCalls": 0,

"loginCount": 0,

"inCalls": 0,

"busyCount": 3,

"readyTime": 296,

"outTalkTime": 0,

"readyCount": 3,

"busyReason": [

{

"operationCount": 1,

"reasonCode": 0,

"operationTime": 2

},

{

"operationCount": 3,

"reasonCode": 3,

"operationTime": 174

},

{

"operationCount": 1,

"reasonCode": 5,

"operationTime": 6

},

{

"operationCount": 0,

"reasonCode": 0,

"operationTime": 0

}

],

"reasonCode": 3,

"state": 2,

"deviceState": 2,

"busyTime": 174

},

{

"agent": "10003_1001",

"extension": null,

"busyReason": [],

"state": 0,

"deviceState": 2

}

],

"message": "success!"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.15.坐席状态数量

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/callcenter/queryAgentStateNum
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/callcenter/queryAgentStateNum
```

请求体

| 字段      | 类型   | 是否必须 | 备注                        |
|-----------|--------|----------|-----------------------------|
| tenantId  | String | 是       | 资源组编号：如10000         |
| queueName | String | 否       | ACD号                       |
| typeCode  | String | 否       | 业务编码                    |
| typeText  | String | 否       | 业务类型                    |
| actionID  | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"tenantId": "10003",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>tenantId</td>
        <td>资源组号</td>
    </tr>
    <tr>
    	<td>thisQueue</td>
        <td>ACD号</td>
    </tr>
    <tr>
    	<td>agentNum</td>
        <td>坐席数量</td>
    </tr>
    <tr>
    	<td>logoutNum</td>
        <td>坐席离线数量</td>
    </tr>
    <tr>
    	<td>loginNum</td>
        <td>坐席在线数量</td>
    </tr>
    <tr>
    	<td>readyNum</td>
        <td>坐席空闲数量</td>
    </tr>
    <tr>
    	<td>busyNum</td>
        <td>坐席忙碌数量</td>
    </tr>
    <tr>
    	<td>registerNum</td>
        <td>坐席话机注册数量</td>
    </tr>
    <tr>
    	<td>agentStateNum</td>
        <td>不同reasonCode坐席数量</td>
    </tr>
    <tr>
    	<td>typeCodeNum</td>
        <td>坐席业务编码数量</td>
    </tr>
     <tr>
    	<td>typeTypeNum</td>
        <td>坐席业务类型数量</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agentNum": 5,

"tenantId": 10005,

"readyNum": 0,

"registerNum": 2,

"busyNum": 1,

"agentStateNum": [

{

"reasonCodeText": "忙碌",

"reasonCodeNum": 1,

"reasonCode": "3"

}

],

"loginNum": 1,

"logoutNum": 4

}

],

"message": "success!",

"totalCount": ""

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.16.IVR流程列表

请求方式：POST

请求url:

```
http://{url}/2.0.5.20210514_release/query/queryRouteInfos
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryRouteInfos
```

请求体

| 字段        | 类型   | 是否必须 | 备注                        |
|-------------|--------|----------|-----------------------------|
| tenantId    | String | 否       | 资源组编号：如10000         |
| name        | String | 否       | 节点名称                    |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回 |
| currentPage | String | 否       | 当前页                      |
| pageSize    | String | 否       | 页大小                      |
| ids         | String | 否       | 主键ID，多个逗号隔开        |
| sort        | String | 否       | 排序字段(传响应的字段)      |
| order       | String | 否       | 排序方式 asc 或 desc        |

请求体示例

```
{

"tenantId": "10000",

"name": "直转",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
	<tr>
    	<td>id</td>
        <td>IVR流程主键ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>IVR流程名称</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>资源组编号</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [{

"id":"1",

"tenantId":"10001",

"name":"直转"

}]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.17.IVR记录列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryIvrHistories
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryIvrHistories
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组号如:10000</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
     <tr>
    	<td>number</td>
        <td>String</td>
        <td>否</td>
        <td>通话号码</td>
    </tr>
    <tr>
    	<td>executeContext</td>
        <td>String</td>
        <td>否</td>
        <td>触发来源<br/>
			inbound_ivr： 呼入路由<br/>
			satisfaction_ivr： 满意度调查<br/>
			incall_ivr：接口调用
		</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫方向 <br/>
			1:内部呼叫<br/>
			2:呼入<br/>
			3:呼出<br/>
			4:双向（包括呼入呼出） 
		</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫标识</td>
    </tr>
    <tr>
    	<td>ivrName</td>
        <td>String</td>
        <td>否</td>
        <td>ivr名称</td>
    </tr>
    <tr>
    	<td>ids</td>
        <td>String</td>
        <td>否</td>
        <td>主键id，多个逗号隔开</td>
    </tr>
    <tr>
    	<td>ivrID</td>
        <td>String</td>
        <td>否</td>
        <td>ivr主键id</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>主键id</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>资源组号</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>结束时间</td>
    </tr>
    <tr>
    	<td>ani</td>
        <td>主叫号码</td>
    </tr>
    <tr>
    	<td>dnis</td>
        <td>被叫号码</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>呼叫方向(2:呼入  3:呼出)</td>
    </tr>
    <tr>
    	<td>thisQueue</td>
        <td>转接ACD</td>
    </tr>
    <tr>
    	<td>executeContext</td>
        <td>触发来源<br/>
			inbound_ivr： 呼入路由<br/>
			satisfaction_ivr： 满意度调查<br/>
			incall_ivr：接口调用
		</td>
    </tr>
    <tr>
    	<td>ivrID</td>
        <td>ivr主键ID</td>
    </tr>
    <tr>
    	<td>ivrName</td>
        <td>ivr名称</td>
    </tr>
    <tr>
    	<td>ivrSessionId</td>
        <td>ivr会话id</td>
    </tr>
    <tr>
    	<td>holdTime</td>
        <td>持续时长</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"ani": "18034613972",

"callId": "2244f18763616c6c00085eca@183.129.179.6",

"callType": 2,

"dnis": "05717171717",

"endTime": "2019-11-06 17:29:23",

"id": 1215,

"startTime": "2019-11-06 17:29:23",

"tenantId": 10002,

"thisQueue": "10002_8000" }

],

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.18.IVR流程详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryIvrHistory
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryIvrHistory
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>callId</td>
        <td>String</td>
        <td>否</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>executeContext</td>
        <td>String</td>
        <td>否</td>
        <td>触发来源<br/>
			inbound_ivr： 呼入路由<br/>
			satisfaction_ivr： 满意度调查<br/>
			incall_ivr：接口调用
		</td>
    </tr>
     <tr>
    	<td>ivrSessionId</td>
        <td>String</td>
        <td>是</td>
        <td>ivr会话id</td>
    </tr>
</table>

请求体示例

```
{

"callId": "2244f18763616c6c00085eca@183.129.179.6",

"ivrSessionId": "251asd887es54d87wqe54156a8we7",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>主键id</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>资源组号</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>结束时间</td>
    </tr>
    <tr>
    	<td>ani</td>
        <td>主叫号码</td>
    </tr>
    <tr>
    	<td>dnis</td>
        <td>被叫号码</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>呼叫方向(2:呼入  3:呼出)</td>
    </tr>
    <tr>
    	<td>thisQueue</td>
        <td>转接ACD</td>
    </tr>
    <tr>
    	<td>ivrStatus</td>
        <td>Ivr状态<br/>
            start:进入IVR<br/>
            start_ivr_route:进入ivr流程<br/>
            start_ivr_node:进入ivr节点<br/>
            start_ivr_component:进入ivr组件<br/>
            end_ivr_component:退出ivr组件<br/>
            stop_ivr_node:退出ivr节点<br/>
            end_ivr_route:退出ivr流程<br/>
            stop:退出IVR<br/>
            satisfaction_start:进入满意度ivr<br/>
            satisfaction_stop:退出满意度ivr<br/>
            incall_start:呼入进入ivr(呼入过程中转IVR)<br/>
            incall_stop:呼入退入ivr(呼入过程中转IVR)
		</td>
    </tr>
    <tr>
    	<td>ivrNode</td>
        <td>Ivr节点ID</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>节点名称</td>
    </tr>
    <tr>
    	<td>eventSequence</td>
        <td>流程序号(顺序由小到大排列)</td>
    </tr>
    <tr>
    	<td>target</td>
        <td>组件执行结果</td>
    </tr>
    <tr>
    	<td>executeContext</td>
        <td>触发来源<br/>
            inbound_ivr： 呼入路由<br/>
            satisfaction_ivr： 满意度调查<br/>
            incall_ivr：接口调用
		</td>
    </tr>
    <tr>
    	<td>ivrID</td>
        <td>ivr主键ID</td>
    </tr>
    <tr>
    	<td>ivrName</td>
        <td>ivr名称</td>
    </tr>
    <tr>
    	<td>ivrDigitType</td>
        <td>组件类型 </td>
    </tr>
    <tr>
    	<td>ivrDtmfDigit</td>
        <td>按键结果</td>
    </tr>
    <tr>
    	<td>componentName</td>
        <td>组件名称</td>
    </tr>
    <tr>
    	<td>stopCause</td>
        <td>组件执行结果<br/>
            失败 FAILED <br/>
            成功 SUCCESS<br/>
		</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"ani": "18034613972",

"callId": "2244f18763616c6c00085eca@183.129.179.6",

"callType": 2,

"dnis": "05717171717",

"endTime": "2019-11-06 17:29:23",

"id": 1215,

"startTime": "2019-11-06 17:29:23",

"tenantId": 10002,

"thisQueue": "10002_8000",

"ivrStatus": "start",

"ivrNode": 1,

"name": "测试",

"eventSequence": "1",

"target": "10002_8000"

}

]

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.19.队列记录列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueHistories
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueHistories
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组号如:10000</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
     <tr>
    	<td>number</td>
        <td>String</td>
        <td>否</td>
        <td>通话号码</td>
    </tr>
     <tr>
    	<td>ids</td>
        <td>String</td>
        <td>否</td>
        <td>主键id，多个逗号隔开</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫标识</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>String</td>
        <td>否</td>
        <td>队列名称,多个值逗号隔开</td>
    </tr>
    <tr>
    	<td>queue</td>
        <td>String</td>
        <td>否</td>
        <td>ACD号,多个值逗号隔开</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫方向 <br/>
			1:内部呼叫<br/>
			2:呼入<br/>
			3:呼出<br/>
			4:双向（包括呼入呼出） 
		</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>String</td>
        <td>否</td>
        <td>转接坐席,多个值逗号隔开</td>
    </tr>
    <tr>
    	<td>holdTime</td>
        <td>String</td>
        <td>否</td>
        <td>排队时长(大于等于)</td>
    </tr>
    <tr>
    	<td>holdTimeMin</td>
        <td>String</td>
        <td>否</td>
        <td>排队时长(小于等于)</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
      <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>主键id</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>资源组号</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>结束时间</td>
    </tr>
    	<tr>
    	<td>callerId</td>
        <td>通话号码</td>
    </tr>
    <tr>
    	<td>thisQueue</td>
        <td>转接的ACD</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>呼叫方向(1:内部呼叫 2:呼入  3:呼出)</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>转接分机</td>
    </tr>
    <tr>
    	<td>holdTime</td>
        <td>排队时间/秒</td>
    </tr>
     <tr>
    	<td>agent</td>
        <td>转接坐席</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>队列名称</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"extension": "",

"callId": "2244f18763616c6c00085eca@183.129.179.6",

"callType": 2,

"callerId": "18034613972",

"endTime": "2019-11-06 17:29:23",

"holdTime": 0,

"id": 129231,

"startTime": "2019-11-06 17:29:23",

"tenantId": 10002,

"thisQueue": "10002_8000"

}

],

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.20.队列流程详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueHistory
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueHistory
```

请求体

| 字段     | 类型   | 是否必须 | 备注                           |
|----------|--------|----------|--------------------------------|
| actionID | String | 是       | 唯一值,在响应信息中原样返回    |
| id       | String | 是       | 队列记录主键ID或呼叫标识callId |

请求体示例

```
{

"id": "1234",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>startTime</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>转接分机</td>
    </tr>
    <tr>
    	<td>queueStatus</td>
        <td>队列状态 <br/>1:退出队列 <br/>2:排队中</td>
    </tr>
    <tr>
    	<td>nodeStatus</td>
        <td>节点状态 <br/>1:转接坐席 <br/>2:坐席拒接 <br/>3:坐席未接</td>
    </tr>
    <tr>
    	<td>sequence</td>
        <td>流程顺序:1,2,3.....</td>
    </tr>
    	<tr>
    	<td>callerId</td>
        <td>通话号码</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>转接坐席</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"agent": "10000_1000",

"extension": "10000_1000",

"callerId": "12345678",

"queueStatus": 2,

"startTime": "2019-11-06 17:29:23",

"nodeStatus": 1,

"sequence": "1"

}, {

"agent": "10000_1001",

"extension": "10000_1001",

"callerId": "12345678",

"queueStatus": 2,

"startTime": "2019-11-06 17:29:26",

"nodeStatus": 1,

"sequence": "2"

}, {

"agent": "10000_1002",

"extension": "10000_1002",

"callerId": "12345678",

"queueStatus": 2,

"startTime": "2019-11-06 17:29:30",

"nodeStatus": 1,

"sequence": "3"

}

]

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.21.话务记录列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryCdrs
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryCdrs
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组号如:10000</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>String</td>
        <td>否</td>
        <td>坐席号 如:10001_1000</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>String</td>
        <td>否</td>
        <td>联系号码：如18565485486</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2019-10-10 11:00:00</td>
    </tr>
     <tr>
    	<td>second</td>
        <td>String</td>
        <td>否</td>
        <td>通话时间(大于等于)</td>
    </tr>
    <tr>
    	<td>secondMin</td>
        <td>String</td>
        <td>否</td>
        <td>通话时间(小于等于)</td>
    </tr>
    <tr>
    	<td>hangupCause</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫成功 send_bye:主叫挂断;recv_bye:被叫挂断<br/>
            呼叫失败 call_failed<br/>
            被叫拒接 CALL_REJECTED<br/>
            无应答 NO_ANSWER<br/>
            被叫无响应 NO_USER_RESPONSE<br/>
            用户忙 USER_BUSY<br/>
            空号 UNALLOCATED_NUMBER<br/>
            正常释放 NORMAL_RELEASE<br/>
            双方都由运营商挂断 NORMAL_CLEARING<br/>
            呼叫线路超时 NORMAL_TEMPORARY_FAILURE<br/>
            超时（一般是SIP超时） TIMEOUT<br/>
            呼叫不可达（空号/无法路由）NO_ROUTE_DESTINATION<br/>
            未注册（网关、电话卡） USER_NOT_REGISTERED<br/>
            一般是线路不通, 可能盲区NORMAL_UNSPECIFIED<br/>
            一般是媒体超时, 异常RECOVERY_ON_TIMER_EXPIRE
		</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫方向<br/> 
            1:内部呼叫<br/>
            2:呼入<br/>
            3:呼出<br/>
            4:双向（包括呼入呼出） 
		</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>ctiCallId</td>
        <td>String</td>
        <td>否</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>campaignId</td>
        <td>String</td>
        <td>否</td>
        <td>项目ID</td>
    </tr>
    <tr>
    	<td>ids</td>
        <td>String</td>
        <td>否</td>
        <td>主键ID，多个逗号隔开</td>
    </tr>
     <tr>
    	<td>isCdrInboundFail</td>
        <td>String</td>
        <td>否</td>
        <td>未接来电<br/>
            1: 转接坐席未接<br/>
            2：进入ivr未接<br/>
            3：进入ACD未接<br/>
            4: 非未接来电<br/>
            5:所有未接 <br/>
            空:查询所有符合以上条件的数据
		</td>
    </tr>
     <tr>
    	<td>isCdrOutboundFail</td>
        <td>String</td>
        <td>否</td>
        <td>未接去电<br/>
            1：未接去电<br/>
            2：非未接去电 <br/>
            空:查询所有符合以上条件的数据
		</td>
    </tr>
     <tr>
    	<td>channelAttr</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫属性<br/>
            transfer 转接呼叫<br/>
            conference 三方呼叫<br/>
            monitor 监听<br/>
            makeCall 接口外呼<br/>
            holdCall 保持外呼 <br/>
		</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>String</td>
        <td>否</td>
        <td>分机号 如:400001</td>
    </tr>
    <tr>
    	<td>ivrDigitType</td>
        <td>String</td>
        <td>否</td>
        <td>组件类型</td>
    </tr>
    <tr>
    	<td>queue</td>
        <td>String</td>
        <td>否</td>
        <td>ACD号</td>
    </tr>
     <tr>
    	<td>ivrID</td>
        <td>String</td>
        <td>否</td>
        <td>ivr主键ID</td>
    </tr>
    <tr>
    	<td>ivrDtmfDigit</td>
        <td>String</td>
        <td>否</td>
        <td>满意度结果</td>
    </tr>
     <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>repeatCallId</td>
        <td>String</td>
        <td>否</td>
        <td>是否callId去重<br/>
            空：不去重<br/>
            1：去重 
		</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"mobile": "18565485486",

"startTime": "2017-10-10 11:00:00",

"endTime": "2019-10-10 11:00:00",

"second": "30",

"hangupCause": "NO_ANSWER",

"callType": "1",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
	<tr>
    	<td>id</td>
        <td>话务记录ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>destinationNumber</td>
        <td>被叫号码</td>
    </tr>
    <tr>
    	<td>callerIdNumber</td>
        <td>主叫号码</td>
    </tr>
    	<tr>
    	<td>campaignId</td>
        <td>活动ID</td>
    </tr>
    <tr>
    	<td>ctiCallType</td>
        <td>呼叫方向 <br/>
            1:内部呼叫<br/>
            2:呼入<br/>
            3:呼出
		</td>
    </tr>
    <tr>
    	<td>startStamp</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>answerStamp</td>
        <td>应答时间</td>
    </tr>
    <tr>
    	<td>endStamp</td>
        <td>结束时间</td>
    </tr>
     <tr>
    	<td>ctiCallId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>filename</td>
        <td>录音文件名</td>
    </tr>
    <tr>
    	<td>duration</td>
        <td>通话中时长(包含振铃时长)</td>
    </tr>
    <tr>
    	<td>billsec</td>
        <td>实际通话中时长</td>
    </tr>
    <tr>
    	<td>hangupCause</td>
        <td>呼叫结果  <br/>
            呼叫成功 send_bye:主叫挂断;recv_bye:被叫挂断<br/>
            呼叫失败 call_failed<br/>
            被叫拒接 CALL_REJECTED<br/>
            无应答 NO_ANSWER<br/>
            被叫无响应 NO_USER_RESPONSE<br/>
            用户忙 USER_BUSY<br/>
            空号 UNALLOCATED_NUMBER<br/>
            正常释放 NORMAL_RELEASE<br/>
            双方都由运营商挂断 NORMAL_CLEARING<br/>
            呼叫线路超时 NORMAL_TEMPORARY_FAILURE<br/>
            超时（一般是SIP超时） TIMEOUT<br/>
            呼叫不可达（空号/无法路由）NO_ROUTE_DESTINATION<br/>
            未注册（网关、电话卡） USER_NOT_REGISTERED<br/>
            一般是线路不通, 可能盲区NORMAL_UNSPECIFIED<br/>
            一般是媒体超时, 异常RECOVERY_ON_TIMER_EXPIRE<br/>
		</td>
    </tr>
    <tr>
    	<td>ivrID</td>
        <td>ivr主键ID</td>
    </tr>
    <tr>
    	<td>ivrName</td>
        <td>ivr名称</td>
    </tr>
     <tr>
    	<td>ivrDtmfDigit</td>
        <td>满意度调查结果</td>
    </tr>
    <tr>
    	<td>channelAttr</td>
        <td>呼叫属性<br/>
            transfer 转接呼叫<br/>
            conference 三方呼叫<br/>
            monitor 监听<br/>
            makeCall 接口外呼<br/>
            holdCall 保持外呼 <br/>  
		</td>
    </tr>
     <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>班组号</td>
    </tr>
     <tr>
    	<td>target</td>
        <td>组件返回结果</td>
    </tr>
     <tr>
    	<td>ivrDigitType</td>
        <td>组件类型</td>
    </tr>
    <tr>
    	<td>ituCode</td>
        <td>挂断编码</td>
    </tr>
     <tr>
    	<td>sipCode</td>
        <td>Sip编码</td>
    </tr>
     <tr>
    	<td>enumeration</td>
        <td>挂机原因</td>
    </tr>
</table>

**备注：呼叫方向为呼入并且应答时间为空就是未接来电**

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [{

"id":"1",

"tenantId":"10001",

"agent":"10001_1000",

"destinationNumber":"1548754542",

"callerIdNumber":"10001_1000",

"campaignId":"8",

"ctiCallType":"1",

"billRate":"0.01",

"duration":"58",

"startStamp":"2017-12-11 16:27:01",

"endStamp":"2017-12-11 16:27:59"

}]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.22.话务记录详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryCdr
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryCdr
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |
| id       | String | 是       | 话务记录ID或通话标识callID  |

请求体示例

```
{

"tenantId": "10000",

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>话务记录ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>destinationNumber</td>
        <td>被叫号码</td>
    </tr>
    <tr>
    	<td>callerIdNumber</td>
        <td>主叫号码</td>
    </tr>
    	<tr>
    	<td>campaignId</td>
        <td>活动ID</td>
    </tr>
    <tr>
    	<td>ctiCallType</td>
        <td>呼叫方向 <br/>
            1:内部呼叫<br/>
            2:呼入<br/>
            3:呼出
		</td>
    </tr>
    <tr>
    	<td>billRate</td>
        <td>通话费用</td>
    </tr>
    <tr>
    	<td>startStamp</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>endStamp</td>
        <td>结束时间</td>
    </tr>
     <tr>
    	<td>ctiCallId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>filename</td>
        <td>录音文件名</td>
    </tr>
    <tr>
    	<td>duration</td>
        <td>通话中时长(包含振铃时长)</td>
    </tr>
    <tr>
    	<td>billsec</td>
        <td>实际通话中时长</td>
    </tr>
    <tr>
    	<td>hangupCause</td>
        <td>呼叫结果  <br/>
            呼叫成功 send_bye:主叫挂断;recv_bye:被叫挂断<br/>
            呼叫失败 call_failed<br/>
            被叫拒接 CALL_REJECTED<br/>
            无应答 NO_ANSWER<br/>
            被叫无响应 NO_USER_RESPONSE<br/>
            用户忙 USER_BUSY<br/>
            空号 UNALLOCATED_NUMBER<br/>
            正常释放 NORMAL_RELEASE<br/>
            双方都由运营商挂断 NORMAL_CLEARING<br/>
            呼叫线路超时 NORMAL_TEMPORARY_FAILURE<br/>
            超时（一般是SIP超时） TIMEOUT<br/>
            呼叫不可达（空号/无法路由）NO_ROUTE_DESTINATION<br/>
            未注册（网关、电话卡） USER_NOT_REGISTERED<br/>
            一般是线路不通, 可能盲区NORMAL_UNSPECIFIED<br/>
            一般是媒体超时, 异常RECOVERY_ON_TIMER_EXPIRE<br/>
		</td>
    </tr>
    <tr>
    	<td>ivrID</td>
        <td>ivr主键ID</td>
    </tr>
    <tr>
    	<td>ivrName</td>
        <td>ivr名称</td>
    </tr>
     <tr>
    	<td>ivrDtmfDigit</td>
        <td>满意度调查结果</td>
    </tr>
    <tr>
    	<td>channelAttr</td>
        <td>呼叫属性<br/>
            transfer 转接呼叫<br/>
            conference 三方呼叫<br/>
            monitor 监听<br/>
            makeCall 接口外呼<br/>
            holdCall 保持外呼 <br/>  
		</td>
    </tr>
     <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>queueName</td>
        <td>班组号</td>
    </tr>
     <tr>
    	<td>target</td>
        <td>组件返回结果</td>
    </tr>
     <tr>
    	<td>ivrDigitType</td>
        <td>组件类型</td>
    </tr>
    <tr>
    	<td>ituCode</td>
        <td>挂断编码</td>
    </tr>
     <tr>
    	<td>sipCode</td>
        <td>Sip编码</td>
    </tr>
     <tr>
    	<td>enumeration</td>
        <td>挂机原因</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"agent":"10001_1000",

"destinationNumber":"1548754542",

"callerIdNumber":"10001_1000",

"campaignId":"8",

"ctiCallType":"1",

"billRate":"0.01",

"duration":"58",

"startStamp":"2017-12-11 16:27:01",

"endStamp":"2017-12-11 16:27:59"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.23.录音记录列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryRecords
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryRecords
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>String</td>
        <td>否</td>
        <td>联系号码：如18565485486</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
     <tr>
    	<td>second</td>
        <td>String</td>
        <td>否</td>
        <td>通话时间</td>
    </tr>
    <tr>
    	<td>campaignId</td>
        <td>String</td>
        <td>否</td>
        <td>项目ID</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>String</td>
        <td>否</td>
        <td>坐席号 如:10001_1000</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫方向 <br/>
			1:内部呼叫<br/>
			2:呼入<br/>
			3:呼出
		</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>String</td>
        <td>否</td>
        <td>分机号 如:400003</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>ids</td>
        <td>String</td>
        <td>否</td>
        <td>主键ID，多个逗号隔开</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"mobile": "18565485486",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"second": "10",

"campaignId": "1",

"agent": "10001_1000",

"callType": "2",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
	<tr>
    	<td>id</td>
        <td>录音记录ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>呼叫号码</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>联络坐席</td>
    </tr>
    	<tr>
    	<td>callType</td>
        <td>呼叫方向 <br/>
            1:内部呼叫<br/>
            2:呼入<br/>
            3:呼出
		</td>
    </tr>
    <tr>
    	<td>duration</td>
        <td>录音时长，单位：秒</td>
    </tr>
    <tr>
    	<td>createTime</td>
        <td>创建时间</td>
    </tr>
    <tr>
    	<td>campaignId</td>
        <td>项目ID 为-1时不属于群呼项目互动的</td>
    </tr>
    <tr>
    	<td>filename</td>
        <td>录音文件路径</td>
    </tr>
     <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [

{

"id":"1",

"tenantId":"10001",

"mobile":"18584628469",

"agent":"10001_1009",

"callType":"2",

"duration":"30",

"campaignId":"1",

"qc":"1",

"qcDescription":"xxx",

"paramMatter":"xxx",

"paramResult":"xxx",

"filename":"6a812a70-71d3-11e7-9764-65cf60b31d6f.wav"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.24.录音记录详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryRecord
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryRecord
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |
| id       | String | 是       | 录音记录ID 或 callId        |

请求体示例

```
{

"tenantId": "10000",

"id": "2621c1ac-768b-11e7-8e4d-5f902b7a99ff",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>录音记录ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>呼叫号码</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>联络坐席</td>
    </tr>
    	<tr>
    	<td>callType</td>
        <td>呼叫方向 <br/>
            1:内部呼叫<br/>
            2:呼入<br/>
            3:呼出
		</td>
    </tr>
    <tr>
    	<td>duration</td>
        <td>录音时长，单位：秒</td>
    </tr>
    <tr>
    	<td>createTime</td>
        <td>创建时间</td>
    </tr>
    <tr>
    	<td>campaignId</td>
        <td>项目ID 为-1时不属于群呼项目互动的</td>
    </tr>
    <tr>
    	<td>filename</td>
        <td>录音文件路径</td>
    </tr>
     <tr>
    	<td>callId</td>
        <td>通话ID</td>
    </tr>
     <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"mobile":"18584628469",

"agent":"10001_1009",

"extension":"10001_1009",

"callType":"2",

"duration":"30",

"campaignId":"1",

"filename":"6a812a70-71d3-11e7-9764-65cf60b31d6f.wav"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.25.黑名单呼叫列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryBlacklistHistories
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryBlacklistHistories
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>String</td>
        <td>否</td>
        <td>坐席号 如:10001_1000</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>String</td>
        <td>否</td>
        <td>联系号码：如18565485486</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2019-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫方向 <br/>
			1:内部呼叫<br/>
			2:呼入<br/>
			3:呼出
		</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>ctiCallId</td>
        <td>String</td>
        <td>否</td>
        <td>通话ID</td>
    </tr>
     <tr>
    	<td>campaignId</td>
        <td>String</td>
        <td>否</td>
        <td>项目ID</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>String</td>
        <td>否</td>
        <td>分机号 如:400001</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"mobile": "18565485486",

"startTime": "2017-10-10 11:00:00",

"endTime": "2019-10-10 11:00:00",

"callType": "1",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
	<tr>
    	<td width="227.75">id</td>
        <td>话务记录ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>所属资源组</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>destinationNumber</td>
        <td>被叫号码</td>
    </tr>
     <tr>
    	<td>callerIdNumber</td>
        <td>主叫号码</td>
    </tr>
    <tr>
    	<td>ctiCallType</td>
        <td>呼叫方向 <br/>
            1:内部呼叫<br/>
            2:呼入<br/>
            3:呼出
		</td>
    </tr>
    <tr>
    	<td>startStamp</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>endStamp</td>
        <td>结束时间</td>
    </tr>
    <tr>
    	<td>ctiCallId</td>
        <td>通话ID</td>
    </tr>
     <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
</table>


code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [{

"id":"1",

"tenantId":"10001",

"agent":"10001_1000",

"destinationNumber":"1548754542",

"callerIdNumber":"10001_1000",

"ctiCallType":"1",

"startStamp":"2017-12-11 16:27:01",

"endStamp":"2017-12-11 16:27:59"

}]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.26.满意度调查列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySatisfactions
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySatisfactions
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
     <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
     <tr>
    	<td>number</td>
        <td>String</td>
        <td>否</td>
        <td>通话号码</td>
    </tr>
     <tr>
    	<td>ivrDtmfDigit</td>
        <td>String</td>
        <td>否</td>
        <td>按键</td>
    </tr>
    <tr>
    	<td>ids</td>
        <td>String</td>
        <td>否</td>
        <td>主键ID，多个逗号隔开</td>
    </tr>
     <tr>
    	<td>routeType</td>
        <td>String</td>
        <td>否</td>
        <td>组件类型</td>
    </tr>
     <tr>
    	<td>callId</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫标识</td>
    </tr>
    <tr>
    	<td>ivrID</td>
        <td>String</td>
        <td>否</td>
        <td>ivr主键id</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫方向 <br/>
			1:内部呼叫<br/>
			2:呼入<br/>
			3:呼出<br/>
            4:双向（包括呼入呼出） 
		</td>
    </tr>
     <tr>
    	<td>ivrResult</td>
        <td>String</td>
        <td>否</td>
        <td>满意度结果</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"ivrDtmfDigit": "1",

"number": "18888888888",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>id</td>
        <td>主键id</td>
    </tr>
    <tr>
    	<td>callId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>资源组号</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>开始时间</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>结束时间</td>
    </tr>
    <tr>
    	<td>ani</td>
        <td>主叫号码</td>
    </tr>
    <tr>
    	<td>dnis</td>
        <td>被叫号码</td>
    </tr>
    <tr>
    	<td>callType</td>
        <td>呼叫方向(2:呼入  3:呼出)</td>
    </tr>
    <tr>
    	<td>ivrDtmfDigit</td>
        <td>收到的按键</td>
    </tr>
     <tr>
    	<td>ivrDigitType</td>
        <td>组件类型</td>
    </tr>
     <tr>
    	<td>stopCause</td>
        <td>组件执行结果<br/>
            失败 FAILED <br/>
            成功 SUCCESS
		</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [{

"ani": "018229785655",

"callId": "74edb94063616c6c008d50a2@183.129.179.6",

"callType": 2,

"dnis": "05717171717",

"endTime": "2021-01-03 14:59:34",

"id": 1968,

"ivrDtmfDigit": "2",

"startTime": "2021-01-03 14:59:34",

"tenantId": 10002,

}],

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.27.满意度调查统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySatisfactionStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySatisfactionStatistics
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组号如:10000，多个值逗号隔开</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
     <tr>
    	<td>ivrDtmfDigits</td>
        <td>String</td>
        <td>是</td>
        <td>按键值，多个逗号隔开</td>
    </tr>
    <tr>
    	<td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>type值为1，填写资源组编号，例如10000；<br/>
            type值为2，填写ACD编号，例如10000_8000；<br/>
            type值为3，填写资源组编号，例如10000；<br/>
            type值为4，填写ACD编号，例如10000_8000；<br/>
            type值为5，填写坐席号，例如10000_1000；<br/>
            type值为6，填写坐席号，例如10000_1000；<br/>
            多个值逗号隔开<br/>
            type值为7，坐席部门键值队，例如{\"部门1\": \"[10000_5000,10000_5001,10000_5002]\",\"部门2\": \"[10000_5003,10000_5004,10000_5005]\"}；
		</td>
    </tr>
    <tr>
    	<td>type</td>
        <td>String</td>
        <td>是</td>
        <td>取值:<br/>
            1：资源组级别 （以资源组为单位，对单个资源组进行统计）<br/>
            2：ACD级别（以ACD为单位，对单个ACD进行统计）<br/>
            3：坐席级别，单个资源组（以坐席为单位，对单个资源组范围内的坐席进行统计）<br/>
            4：坐席级别，单个ACD（以坐席为单位，对单个ACD范围内的坐席进行统计）<br/>
            5：坐席级别，单个坐席（以坐席为单位，对单个坐席进行统计）<br/>
            6：坐席级别，多个坐席（对多个坐席统计累加）<br/>
            7：坐席级别，多个坐席（对数组内多个坐席统计累加,每个数组返回一条数据）
		</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2021-10-10 11:00:00",

"ivrDtmfDigits": "1,2,3,4",

"filter": "10000_8000",

"type": "2",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>按键</td>
        <td>按键数量</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>资源组号</td>
    </tr>
    <tr>
    	<td>name</td>
        <td>坐席名或ACD编号或资源组名或部门名称</td>
    </tr>	
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"agent": "10000_1000",

"1": "12",

"2":"32",

"3":"22",

"4":"0"

}

],

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.28.语音信箱

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryVoicemailMsgs
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryVoicemailMsgs
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| agent       | String | 否       | 需要查询的坐席号                |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| mobile      | String | 否       | 联系号码：如18565485486         |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |
| startTime   | String | 否       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 否       | 结束时间：如2017-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |

请求体示例

```
{

"mobile": "18565485486",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"agent": "10000_1000",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr width="227.75">
    	<td>callId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>cidNumber</td>
        <td>客户手机号</td>
    </tr>
    <tr>
    	<td>createTime</td>
        <td>创建日期</td>
    </tr>
    <tr>
    	<td>userName</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>filePath</td>
        <td>语音留言录音路径</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"data": [{

"callId": "a62c4027aa13b65b@cm9ubnktUEM.",

"cidNumber": "10000_1016",

"createTime": "2019-02-26 11:33:27",

"filePath":
"/sharedfs/webapps/voicemail//msg_1f69ae00-3977-11e9-822f-ffb3ecb4afa5.wav",

"userName": "10000_1017"

}],

"message": "success!"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.29.短信记录列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySmHistories
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySmHistories
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
     <tr>
    	<td>agent</td>
        <td>String</td>
        <td>否</td>
        <td>需要查询的坐席</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>否</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>sendState</td>
        <td>String</td>
        <td>否</td>
        <td>短信状态码<br/>
            -1：未发送<br/>
            -2：发送失败<br/>
            0：发送成功<br/>
            1：号码不正确<br/>
            2：账户欠费<br/>
            3：参数错误<br/>
            4：错误手机号<br/>
            5：模板错误<br/>
            6：提交成功 
		</td>
    </tr>
    <tr>
    	<td>type</td>
        <td>String</td>
        <td>否</td>
        <td>短信类型(多个值逗号隔开)<br/>
            1.挂机短信<br/>
            2.手动发送<br/>
            3.手动快闪<br/>
            4.收件箱 
		</td>
    </tr>
    <tr>
    	<td>sendMobile</td>
        <td>String</td>
        <td>否</td>
        <td>短信发送号码</td>
    </tr>
    <tr>
    	<td>content</td>
        <td>String</td>
        <td>否</td>
        <td>短信内容(模糊查询)</td>
    </tr>
    <tr>
    	<td>stateValue</td>
        <td>String</td>
        <td>否</td>
        <td>是否已读<br/>
            0：未读 <br/>
            1：已读 
		</td>
    </tr>
    <tr>
    	<td>ids</td>
        <td>String</td>
        <td>否</td>
        <td>主键id，多个逗号隔开</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
     <tr>
    	<td>attr</td>
        <td>String</td>
        <td>否</td>
        <td>短信属性(多个值逗号隔开)</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"agent": "10000_1000",

"sendState": "1",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
    <tr>
    	<td>id</td>
        <td>主键id</td>
    </tr>
	<tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>
    <tr>
    	<td>calleeId</td>
        <td>通话ID</td>
    </tr>
    <tr>
    	<td>mobile</td>
        <td>接收短信手机号</td>
    </tr>
    <tr>
    	<td>sourceMobile</td>
        <td>短信来源手机号</td>
    </tr>
    <tr>
    	<td>createdTime</td>
        <td>创建日期</td>
    </tr>
    <tr>
    	<td>extension</td>
        <td>分机号</td>
    </tr>
    <tr>
    	<td>state</td>
        <td>发送状态<br/>
            -1：未发送<br/>
            -2：发送失败<br/>
            0：发送成功<br/>
            1：号码不正确<br/>
            2：账户欠费<br/>
            3：参数错误<br/>
            4：错误手机号<br/>
            5：模板错误<br/>
            6：提交成功
		</td>
    </tr>
    <tr>
    	<td>content</td>
        <td>发送内容</td>
    </tr>
     <tr>
    	<td>type</td>
        <td>短信类型<br/>
            1.挂机短信<br/>
            2.手动发送<br/>
            3.手动快闪<br/>
            4.收件箱 
		</td>
    </tr>
    <tr>
    	<td>stateValue</td>
        <td>是否已读<br/>
            空：未读 <br/>
            1：已读 
		</td>
    </tr>
    <tr>
    	<td>attr</td>
        <td>短信属性(发送短信时的标识)</td>
    </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"calleeId": "",

"content":
"【京东金融】京东京东2，先生/女士您好！京东PINf703，欠款金额：约5100元，请于接到本信息后24小时之内还清款项。若有疑问，请致电0532-81633876退订回T",

"createdTime": "2019-05-21 18:24:28",

"id": 2,

"mobile": "17601541941",

"state": 0,

"stateValue": "",

"tenantId": 10000,

"extension":"400001"

}],

"message": "success!",

"totalCount": "2"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```

短信状态码



## 6.30.坐席状态统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentStatistics
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
     <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>type值为1，填写资源组编号，例如10000；<br/>
            type值为2，填写ACD编号，例如10000_8000；<br/>
            type值为3，填写资源组编号，例如10000；<br/>
            type值为4，填写ACD编号，例如10000_8000；<br/>
            type值为5，填写坐席号，例如10000_1000；<br/>
            type值为6，填写坐席号，例如10000_1000；<br/>
            多个值逗号隔开<br/>
            type值为7，坐席部门键值队，例如{\"部门1\": \"[10000_5000,10000_5001,10000_5002]\",\"部门2\": \"[10000_5003,10000_5004,10000_5005]\"}；
		</td>
    </tr>
    <tr>
    	<td>type</td>
        <td>String</td>
        <td>是</td>
        <td>取值:<br/>
            1：资源组级别 （以资源组为单位，对单个资源组进行统计）<br/>
            2：ACD级别（以ACD为单位，对单个ACD进行统计）<br/>
            3：坐席级别，单个资源组（以坐席为单位，对单个资源组范围内的坐席进行统计）<br/>
            4：坐席级别，单个ACD（以坐席为单位，对单个ACD范围内的坐席进行统计）<br/>
            5：坐席级别，单个坐席（以坐席为单位，对单个坐席进行统计）<br/>
            6：坐席级别，多个坐席（对多个坐席统计累加）<br/>
            7：坐席级别，多个坐席（对数组内多个坐席统计累加,每个数组返回一条数据）
		</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>  
</table>

请求体示例

```
{

"tenantId": "1000",

"type": "3",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
	<tr>
    	<td>name</td>
        <td>坐席名或ACD编号或资源组名或部门名称</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>坐席号或ACD号或资源组号</td>
    </tr>
    <tr>
    	<td>acwCount</td>
        <td>整理次数</td>
    </tr>
    <tr>
    	<td>acwTime</td>
        <td>整理时长 单位/秒</td>
    </tr>
    <tr>
    	<td>avgTalkTime</td>
        <td>平均通话中时长 单位/秒</td>
    </tr>
    <tr>
    	<td>breakCount</td>
        <td>休息次数</td>
    </tr>
    <tr>
    	<td>breakTime</td>
        <td>休息时长 单位/秒</td>
    </tr>
    <tr>
    	<td>busyCount</td>
        <td>忙碌次数</td>
    </tr>	
    <tr>
    	<td>busyTime</td>
        <td>忙碌时长 单位/秒</td>
    </tr>
    <tr>
    	<td>calls</td>
        <td>通话总量</td>
    </tr>
    <tr>
    	<td>inAnswerCalls</td>
        <td>呼入接听数</td>
    </tr>
    <tr>
    	<td>inAvgTalkTime</td>
        <td>呼入平均通话时间 单位/秒</td>
    </tr>
    <tr>
    	<td>inCalls</td>
        <td>呼入数</td>
    </tr>
    <tr>
    	<td>inTalkTime</td>
        <td>呼入通话时间 单位/秒</td>
    </tr>
    <tr>
    	<td>intDay</td>
        <td>日</td>
    </tr>
    <tr>
    	<td>intMonth</td>
        <td>月</td>
    </tr>
    <tr>
    	<td>intYear</td>
        <td>年</td>
    </tr>
    <tr>
    	<td>loginCount</td>
        <td>签入次数</td>
    </tr>	
    <tr>
    	<td>logoutCount</td>
        <td>签出次数</td>
    </tr>
    <tr>
    	<td>outAnswerCalls</td>
        <td>呼出应答数</td>
    </tr>
    <tr>
    	<td>outAvgTalkTime</td>
        <td>呼出平均通话时间 单位/秒</td>
    </tr>
    <tr>
    	<td>outCalls</td>
        <td>呼出数</td>
    </tr>
    <tr>
    	<td>outTalkTime</td>
        <td>呼出通话时间 单位/秒</td>
    </tr>
    <tr>
    	<td>readyCount</td>
        <td>空闲次数</td>
    </tr>
    <tr>
    	<td>readyTime</td>
        <td>空闲时长 单位/秒</td>
    </tr>
    <tr>
    	<td>talkTime</td>
        <td>通话中时长 单位/秒</td>
    </tr>
    <tr>
    	<td>workTime</td>
        <td>登录时长 单位/秒</td>
    </tr>
    <tr>
    	<td>leaveCount</td>
        <td>离开次数</td>
    </tr>	
    <tr>
    	<td>leaveTime</td>
        <td>离开时长 单位/秒</td>
    </tr>
    <tr>
    	<td>operationCount_自定义状态编码</td>
        <td>坐席自定义状态操作次数</td>
    </tr>
    <tr>
    	<td>operationTime_自定义状态编码</td>
        <td>坐席自定义状态操作时长</td>
    </tr>
    <tr>
    	<td>operationName_自定义状态编码</td>
        <td>坐席自定义状态操作名称</td>
    </tr>
    <tr>
    	<td>amountAgentReasonCodes</td>
        <td>坐席自定义状态统计</td>
    </tr>
</table>

amountAgentReasonCodes:

<table>
	<tr>
    	<td>tenantId</td>
        <td>所属资源组号</td>
    </tr>
    <tr>
    	<td>operationCount</td>
        <td>操作次数</td>
    </tr>
    <tr>
    	<td>operationTime</td>
        <td>操作时长 单位/秒</td>
    </tr>
    <tr>
    	<td>reasonCodeId</td>
        <td>自定义状态主键ID</td>
    </tr>	
    <tr>
    	<td>reasonCode</td>
        <td>自定义状态编码</td>
    </tr>
    <tr>
    	<td>reasonCodeName</td>
        <td>自定义状态名称</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>	
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "00:00:37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "00:00:01",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "00:00:04",

"operationTime_6": "0",

"readyTime": "26:49:30",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "00:03:07",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "00:05:16",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "43:07:40",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "00:00:13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "00:00:04",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "00:00:08",

"inAvgRingTime": "00:00:12",

"outAvgRingTime": "00:00:16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "01:55:04",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "00:14:14",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "02:11:35",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```
返回201示例：
```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.31.坐席自定义状态统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentReasonCodeStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentReasonCodeStatistics
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>filter</td>
        <td>String</td>
        <td>否</td>
        <td>type值为1，填写资源组编号，例如10000；<br/>
            type值为2，填写ACD编号，例如10000_8000；<br/>
            type值为3，填写资源组编号，例如10000；<br/>
            type值为4，填写ACD编号，例如10000_8000；<br/>
            type值为5，填写坐席号，例如10000_1000；<br/>
            type值为6，填写坐席号，例如10000_1000；<br/>
            多个值逗号隔开<br/>
            type值为7，坐席部门键值队，例如{\"部门1\": \"[10000_5000,10000_5001,10000_5002]\",\"部门2\": \"[10000_5003,10000_5004,10000_5005]\"}；
		</td>
    </tr>
    <tr>
    	<td>type</td>
        <td>String</td>
        <td>是</td>
        <td>取值:<br/>
            1：资源组级别 （以资源组为单位，对单个资源组进行统计）<br/>
            2：ACD级别（以ACD为单位，对单个ACD进行统计）<br/>
            3：坐席级别，单个资源组（以坐席为单位，对单个资源组范围内的坐席进行统计）<br/>
            4：坐席级别，单个ACD（以坐席为单位，对单个ACD范围内的坐席进行统计）<br/>
            5：坐席级别，单个坐席（以坐席为单位，对单个坐席进行统计）<br/>
            6：坐席级别，多个坐席（对多个坐席统计累加）<br/>
            7：坐席级别，多个坐席（对数组内多个坐席统计累加,每个数组返回一条数据）
		</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "10003",

"filter": "10000",

"type": "1",

"startTime": "2017-10-10 11:00:00",

"endTime": "2021-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
	<tr>
    	<td>tenantId</td>
        <td>所属资源组号</td>
    </tr>
    <tr>
    	<td>operationCount</td>
        <td>操作次数</td>
    </tr>
    <tr>
    	<td>operationTime</td>
        <td>操作时长 单位/秒</td>
    </tr>
    <tr>
    	<td>reasonCodeId</td>
        <td>自定义状态主键ID</td>
    </tr>
     <tr>
    	<td>reasonCode</td>
        <td>自定义状态编码</td>
    </tr>
    <tr>
    	<td>reasonCodeName</td>
        <td>自定义状态名称</td>
    </tr>
    <tr>
    	<td>agent</td>
        <td>坐席号</td>
    </tr>	
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "10003_1000",

"operationCount": 52969,

"operationTime": 6231183,

"reasonCode": 9,

"reasonCodeId": 1,

"reasonCodeName": "免打扰",

"tenantId": 10003

}

],

"message": "success!",

"tenantID": 10003,

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.32.坐席通话统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryIntentionStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryIntentionStatistics
```

请求体

<table>
	<tr>
    	<th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
    </tr>
    <tr>
    	<td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
    </tr>
    <tr>
    	<td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
    </tr>
    <tr>
    	<td>filter</td>
        <td>String</td>
        <td>否</td>
        <td>type值为1，填写资源组编号，例如10000；<br/>
            type值为2，填写ACD编号，例如10000_8000；<br/>
            type值为3，填写资源组编号，例如10000；<br/>
            type值为4，填写ACD编号，例如10000_8000；<br/>
            type值为5，填写坐席号，例如10000_1000；<br/>
            type值为6，填写坐席号，例如10000_1000；<br/>
            多个值逗号隔开<br/>
            type值为7，坐席部门键值队，例如{\"部门1\": \"[10000_5000,10000_5001,10000_5002]\",\"部门2\": \"[10000_5003,10000_5004,10000_5005]\"}；
		</td>
    </tr>
    <tr>
    	<td>type</td>
        <td>String</td>
        <td>是</td>
        <td>取值:<br/>
            1：资源组级别 （以资源组为单位，对单个资源组进行统计）<br/>
            2：ACD级别（以ACD为单位，对单个ACD进行统计）<br/>
            3：坐席级别，单个资源组（以坐席为单位，对单个资源组范围内的坐席进行统计）<br/>
            4：坐席级别，单个ACD（以坐席为单位，对单个ACD范围内的坐席进行统计）<br/>
            5：坐席级别，单个坐席（以坐席为单位，对单个坐席进行统计）<br/>
            6：坐席级别，多个坐席（对多个坐席统计累加）<br/>
            7：坐席级别，多个坐席（对数组内多个坐席统计累加,每个数组返回一条数据）
		</td>
    </tr>
    <tr>
    	<td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
    </tr>
    <tr>
    	<td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
    </tr>
    <tr>
    	<td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
    <tr>
    	<td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2017-10-10 11:00:00</td>
    </tr>
      <tr>
    	<td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
    </tr>
    <tr>
    	<td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
    </tr>
</table>

请求体示例

```
{

"tenantId": "1000",

"type": "3",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>
      name
    </td>
    <td>
      坐席名或ACD编号或资源组名或部门名称
    </td>
  </tr>
  <tr>
    <td>
      agent
    </td>
    <td>
      坐席号或ACD号或资源组号
    </td>
  </tr>
  <tr>
    <td>
      avgTalkTime
    </td>
    <td>
      平均通话中时长 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      calls
    </td>
    <td>
      通话总量
    </td>
  </tr>
  <tr>
    <td>
      inAnswerCalls
    </td>
    <td>
      呼入应答数
    </td>
  </tr>
  <tr>
    <td>
      inCalls
    </td>
    <td>
      呼入数
    </td>
  </tr>
  <tr>
    <td>
      outAnswerCalls
    </td>
    <td>
      呼出应答数
    </td>
  </tr>
  <tr>
    <td>
      outCalls
    </td>
    <td>
      呼出数
    </td>
  </tr>
  <tr>
    <td>
      talkTime
    </td>
    <td>
      通话中时长 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inCallCompletingRate
    </td>
    <td>
      呼入应答率
    </td>
  </tr>
  <tr>
    <td>
      outCallCompletingRate
    </td>
    <td>
      呼出应答率
    </td>
  </tr>
  <tr>
    <td>
      inTransfers
    </td>
    <td>
      呼入转接次数
    </td>
  </tr>
  <tr>
    <td>
      outTransfers
    </td>
    <td>
      呼出转接次数
    </td>
  </tr>
  <tr>
    <td>
      inMonitors
    </td>
    <td>
      呼入监听数
    </td>
  </tr>
  <tr>
    <td>
      outMonitors
    </td>
    <td>
      呼出监听数
    </td>
  </tr>
  <tr>
    <td>
      inConferences
    </td>
    <td>
      呼入三方通话次数
    </td>
  </tr>
  <tr>
    <td>
      outConferences
    </td>
    <td>
      呼出三方通话次数
    </td>
  </tr>
  <tr>
    <td>
      outAvgRingTime
    </td>
    <td>
      呼出平均振铃时长
    </td>
  </tr>
  <tr>
    <td>
      inAvgRingTime
    </td>
    <td>
      呼入平均振铃时长
    </td>
  </tr>
  <tr>
    <td>
      avgRingTime
    </td>
    <td>
      平均振铃时长
    </td>
  </tr>
  <tr>
    <td>
      inTalkTime
    </td>
    <td>
      呼入通话总时长
    </td>
  </tr>
  <tr>
    <td>
      outTalkTime
    </td>
    <td>
      呼出通话总时长
    </td>
  </tr>
  <tr>
    <td>
      avgInTalkTime
    </td>
    <td>
      呼入平均通话中时长
    </td>
  </tr>
  <tr>
    <td>
      avgOutTalkTime
    </td>
    <td>
      呼出平均通话中时长
    </td>
  </tr>
  <tr>
    <td>
      minTalkTime
    </td>
    <td>
      最短通话中时长
    </td>
  </tr>
  <tr>
    <td>
      maxTalkTime
    </td>
    <td>
      最长通话中时长
    </td>
  </tr>
  <tr>
    <td>
      inMinTalkTime
    </td>
    <td>
      呼入最短通话中时长
    </td>
  </tr>
  <tr>
    <td>
      inMaxTalkTime
    </td>
    <td>
      呼入最长通话中时长
    </td>
  </tr>
  <tr>
    <td>
      outMinTalkTime
    </td>
    <td>
      呼出最短通话中时长
    </td>
  </tr>
  <tr>
    <td>
      outMaxTalkTime
    </td>
    <td>
      呼出最长通话中时长
    </td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "10003_1000",

"talkTime": "2",

"outCallCompletingRate": "100.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 1,

"avgRingTime": "7",

"inTransfers": 0,

"inCalls": 30,

"calls": 31,

"inMonitors": 0,

"outConferences": 0,

"inConferences": 0,

"inAvgRingTime": "52",

"outAvgRingTime": "0",

"intentionAgree": 0,

"name": "10003_1000",

"outAnswerCalls": 1,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"outTransfers": 0

}

],

"message": "success!",

"tenantID": 1000,

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.33.队列分析统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| filter      | String | 是       | ACD编号，多个ACD用，分隔        |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2017-10-10 11:00:00 |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"tenantId": "10003",

"filter": "10003_8000,10003_8001",

"startTime": "2017-10-10 11:00:00",

"endTime": "2021-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>
      inAnswerTime
    </td>
    <td>
      呼入应答时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inAnswerNum
    </td>
    <td>
      呼入应答数
    </td>
  </tr>
  <tr>
    <td>
      inAvgAnswerTime
    </td>
    <td>
      呼入平均应答时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outAnswerTime
    </td>
    <td>
      呼出应答时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outAnswerNum
    </td>
    <td>
      呼出应答数
    </td>
  </tr>
  <tr>
    <td>
      outAvgAnswerTime
    </td>
    <td>
      呼出平均应答时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      answerTime
    </td>
    <td>
      应答时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      answerNum
    </td>
    <td>
      应答数
    </td>
  </tr>
  <tr>
    <td>
      avgAnswerTime
    </td>
    <td>
      平均应答时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inAgentAbandonNum
    </td>
    <td>
      呼入人工放弃数
    </td>
  </tr>
  <tr>
    <td>
      outAgentAbandonNum
    </td>
    <td>
      呼出人工放弃数
    </td>
  </tr>
  <tr>
    <td>
      agentAbandonNum
    </td>
    <td>
      人工放弃数
    </td>
  </tr>
  <tr>
    <td>
      inAgentAbandonTime
    </td>
    <td>
      呼入人工放弃时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outAgentAbandonTime
    </td>
    <td>
      呼出人工放弃时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      agentAbandonTime
    </td>
    <td>
      人工放弃时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      agentAvgAbandonTime
    </td>
    <td>
      人工放弃平均时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inQueueAbandonNum
    </td>
    <td>
      呼入队列放弃数
    </td>
  </tr>
  <tr>
    <td>
      outQueueAbandonNum
    </td>
    <td>
      呼出队列放弃数
    </td>
  </tr>
  <tr>
    <td>
      queueAbandonNum
    </td>
    <td>
      队列放弃数
    </td>
  </tr>
  <tr>
    <td>
      inQueueAbandonTime
    </td>
    <td>
      呼入队列放弃时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outQueueAbandonTime
    </td>
    <td>
      呼出队列放弃时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      queueAbandonTime
    </td>
    <td>
      队列放弃时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      queueAvgAbandonTime
    </td>
    <td>
      队列放弃平均时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      abandonNum
    </td>
    <td>
      放弃数
    </td>
  </tr>
  <tr>
    <td>
      abandonTime
    </td>
    <td>
      放弃时间
    </td>
  </tr>
  <tr>
    <td>
      avgAbandonTime
    </td>
    <td>
      放弃平均时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inAgentHoldNum
    </td>
    <td>
      呼入坐席保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inAgentHoldTime
    </td>
    <td>
      呼入坐席保持数
    </td>
  </tr>
  <tr>
    <td>
      inAgentAvgHoldTime
    </td>
    <td>
      呼入坐席平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outAgentHoldNum
    </td>
    <td>
      呼出坐席保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outAgentHoldTime
    </td>
    <td>
      呼出坐席保持数
    </td>
  </tr>
  <tr>
    <td>
      outAgentAvgHoldTime
    </td>
    <td>
      呼出坐席平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      agentHoldNum
    </td>
    <td>
      坐席保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      agentHoldTime
    </td>
    <td>
      坐席保持数
    </td>
  </tr>
  <tr>
    <td>
      agentAvgHoldTime
    </td>
    <td>
      坐席平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inQueueHoldNum
    </td>
    <td>
      呼入队列保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inQueueHoldTime
    </td>
    <td>
      呼入队列保持数
    </td>
  </tr>
  <tr>
    <td>
      inQueueAvgHoldTime
    </td>
    <td>
      呼入队列平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outQueueHoldNum
    </td>
    <td>
      呼出队列保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      outQueueHoldTime
    </td>
    <td>
      呼出队列保持数
    </td>
  </tr>
  <tr>
    <td>
      outQueueAvgHoldTime
    </td>
    <td>
      呼出队列平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      queueHoldNum
    </td>
    <td>
      队列保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      queueHoldTime
    </td>
    <td>
      队列保持数
    </td>
  </tr>
  <tr>
    <td>
      queueAvgHoldTime
    </td>
    <td>
      队列平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      holdTime
    </td>
    <td>
      保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      avgHoldTime
    </td>
    <td>
      平均保持时间 单位/秒
    </td>
  </tr>
  <tr>
    <td>
      inCallNum
    </td>
    <td>
      呼入数
    </td>
  </tr>
  <tr>
    <td>
      outCallNum
    </td>
    <td>
      呼出数
    </td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"abandonNum": 18,

"abandonTime": 882,

"agentAbandonNum": 0,

"agentAbandonTime": 0,

"agentAvgAbandonTime": "0",

"agentAvgHoldTime": "53",

"agentHoldNum": 6,

"agentHoldTime": 318,

"answerNum": 48,

"answerTime": 216,

"avgAbandonTime": "49",

"avgAnswerTime": "4",

"avgHoldTime": "72",

"holdTime": 4794,

"id": 0,

"inAgentAbandonNum": 0,

"inAgentAbandonTime": 0,

"inAgentAvgHoldTime": "0",

"inAgentHoldNum": 0,

"inAgentHoldTime": 0,

"inAnswerNum": 48,

"inAnswerTime": 216,

"inAvgAnswerTime": "4",

"inCallNum": 66,

"inQueueAbandonNum": 18,

"inQueueAbandonTime": 882,

"inQueueAvgHoldTime": "49",

"inQueueHoldNum": 18,

"inQueueHoldTime": 882,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"outAgentAbandonNum": 0,

"outAgentAbandonTime": 0,

"outAgentAvgHoldTime": "0",

"outAgentHoldNum": 0,

"outAgentHoldTime": 0,

"outAnswerNum": 0,

"outAnswerTime": 0,

"outAvgAnswerTime": "0",

"outCallNum": 0,

"outQueueAbandonNum": 0,

"outQueueAbandonTime": 0,

"outQueueAvgHoldTime": "0",

"outQueueHoldNum": 0,

"outQueueHoldTime": 0,

"queueAbandonNum": 18,

"queueAbandonTime": 882,

"queueAvgAbandonTime": "49",

"queueAvgHoldTime": "49",

"queueHoldNum": 18,

"queueHoldTime": 882,

"queueId": 0,

"queueName": "10003_8000",

"tenantId": 10003

}

],

"message": "success!",

"tenantID": 10003,

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.34.系统并发量

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryConcurrency
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryConcurrency
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 否       | 资源组号 如:10000           |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"agent": "10000_1000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
  <tr>
    <td>
      systemMaxConcurrent
    </td>
    <td>
      系统最大并发量
    </td>
  </tr>
  <tr>
    <td>
      systemOutboundChannel
    </td>
    <td>
      系统当前并发量
    </td>
  </tr>
  <tr>
    <td>
      systemCommunicate
    </td>
    <td>
      系统通话中坐席量
    </td>
  </tr>
  <tr>
    <td>
      tenantMaxConcurrent
    </td>
    <td>
      资源组最大并发量
    </td>
  </tr>
  <tr>
    <td>
      tenantOutboundChannel
    </td>
    <td>
      资源组当前并发量
    </td>
  </tr>
  <tr>
    <td>
      tenantCommunicate
    </td>
    <td>
      资源组通话中坐席量
    </td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": {

"systemMaxConcurrent": 60,

"tenantOutboundChannel": 0,

"systemCommunicate": 0,

"tenantMaxConcurrent": 30,

"systemOutboundChannel": 0,

"tenantCommunicate": 0

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.35.号码归属地

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryMobileAttribution
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryMobileAttribution
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| mobile   | String | 是       | 手机号码：如18222222222     |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"mobile": "18222222222",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，号码归属地        |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data": "湖南 长沙 湖南移动全球通卡\\n"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.36.自定义坐席状态列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentCustomState
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentCustomState
```



请求体

<table>
	<tr>
		<th>字段</th>
		<th>类型</th>
		<th>是否必须</th>
		<th>备注</th>
	</tr>
	<tr>
		<td>tenantId</td>
		<td>String</td>
		<td>是</td>
		<td>资源组编号：如10000</td>
	</tr>
	<tr>
		<td>state</td>
		<td>String</td>
		<td>否</td>
		<td>坐席状态
			<br />0:登出（坐席不再接收通信事件，且无法调用通信API）；
			<br /> 1:空闲（坐席可以接听来电）；
			<br /> 2:忙碌（坐席无法接听来电，但可以外呼）</td>
	</tr>
	<tr>
		<td>reasonCode</td>
		<td>String</td>
		<td>否</td>
		<td>state为2（忙碌）的情况下，坐席忙碌的原因。
			<br /> 0：整理（坐席结束通话后，进行文案处理）；
			<br />1：通话（坐席处于通话中）；
			<br />2：设备不可用（业务系统发送故障）；
			<br />3：忙碌（其它的情况下，需要将state设置成3）；
			<br />4：离开（坐席员离开座位）；
			<br />5：休息（坐席员进行休息，比如午休）。
			<br /> 6：拨号中(调用呼叫接口时的状态)
			<br />7：外线振铃
			<br />8：呼入振铃
			<br /> 由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长</td>
	</tr>
	<tr>
		<td>actionID</td>
		<td>String</td>
		<td>是</td>
		<td>唯一值,在响应信息中原样返回</td>
	</tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
	<tr>
		<td>
			state
		</td>
		<td>
			坐席状态
			<br />
			0:登出（坐席不再接收通信事件，且无法调用通信API）；
			<br />
			1:空闲（坐席可以接听来电）；
			<br />
			2:忙碌（坐席无法接听来电，但可以外呼）
		</td>
	</tr>
	<tr>
		<td>
			reason
		</td>
		<td>
			状态原因
		</td>
	</tr>
	<tr>
		<td>
			id
		</td>
		<td>
			主键
		</td>
	</tr>
	<tr>
		<td>
			pid
		</td>
		<td>
			上级id，为空则为一级状态
		</td>
	</tr>
</table>

reason：

<table>
  <tr>
    <th>代码</th>
    <th>含义</th>
  </tr>
  <tr>
    <td>reasonText</td>
    <td>状态码名称</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>state为2（忙碌）的情况下，坐席忙碌的原因。
      <br />0：整理（坐席结束通话后，进行文案处理）；
      <br />1：通话（坐席处于通话中）；
      <br />2：设备不可用（业务系统发送故障）；
      <br />3：忙碌（其它的情况下，需要将state设置成3）；
      <br />4：离开（坐席员离开座位）；
      <br />5：休息（坐席员进行休息，比如午休）。
      <br />6：拨号中(调用呼叫接口时的状态)
      <br />7：外线振铃
      <br />8：呼入振铃
      <br />由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 0,

"data": [

{

"state": 0

},

{

"state": 1

},

{

"reason": [

{

"reasontext": "整理",

"reasoncode": 0

},

{

"reasontext": "忙碌",

"reasoncode": 3

},

{

"reasontext": "离开",

"reasoncode": 4

},

{

"reasontext": "休息",

"reasoncode": 5

},

{

"reasontext": "通话",

"reasoncode": 1

},

{

"reasontext": "设备不可用",

"reasoncode": 2

},

{

"reasontext": "拨号中",

"reasoncode": 6

},

{

"reasontext": "外线振铃",

"reasoncode": 7

},

{

"reasontext": "呼入振铃",

"reasoncode": 8

}

],

"state": 2

}

],

"message": "success!"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.37.坐席状态颜色编码列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentStateColors
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentStateColors
```

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>state</td>
    <td>String</td>
    <td>否</td>
    <td>坐席状态
      <br/>0:登出（坐席不再接收通信事件，且无法调用通信API）；
      <br/>1:空闲（坐席可以接听来电）；
      <br/>2:忙碌（坐席无法接听来电，但可以外呼）</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>String</td>
    <td>否</td>
    <td>state为2（忙碌）的情况下，坐席忙碌的原因。
      <br/>0：整理（坐席结束通话后，进行文案处理）；
      <br/>1：通话（坐席处于通话中）；
      <br/>2：设备不可用（业务系统发送故障）；
      <br/>3：忙碌（其它的情况下，需要将state设置成3）；
      <br/>4：离开（坐席员离开座位）；
      <br/>5：休息（坐席员进行休息，比如午休）。
      <br/>6：拨号中(调用呼叫接口时的状态)
      <br/>7：外线振铃
      <br/>8：呼入振铃
      <br/>由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
  <tr>
    <td>state</td>
    <td>坐席状态
      <br/>0:登出（坐席不再接收通信事件，且无法调用通信API）；
      <br/>1:空闲（坐席可以接听来电）；
      <br/>2:忙碌（坐席无法接听来电，但可以外呼）</td>
  </tr>
  <tr>
    <td>color</td>
    <td>状态颜色编码</td>
  </tr>
  <tr>
    <td>reason</td>
    <td>状态原因</td>
  </tr>
  <tr>
    <td>id</td>
    <td>主键</td>
  </tr>
  <tr>
    <td>pid</td>
    <td>上级id，为空则为一级状态</td>
  </tr>
</table>

reason：

<table>
  <tr>
    <th>代码</th>
    <th>含义</th>
  </tr>
  <tr>
    <td>reasonText</td>
    <td>状态码名称</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>state为2（忙碌）的情况下，坐席忙碌的原因。
      <br/>0：整理（坐席结束通话后，进行文案处理）；
      <br/>1：通话（坐席处于通话中）；
      <br/>2：设备不可用（业务系统发送故障）；
      <br/>3：忙碌（其它的情况下，需要将state设置成3）；
      <br/>4：离开（坐席员离开座位）；
      <br/>5：休息（坐席员进行休息，比如午休）。
      <br/>6：拨号中(调用呼叫接口时的状态)
      <br/>7：外线振铃
      <br/>8：呼入振铃
      <br/>由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长</td>
  </tr>
  <tr>
    <td>color</td>
    <td>状态颜色编码</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 0,

"data": [

{

"reason": [],

"color": "\#f3f3f4",

"state": 0

},

{

"reason": [],

"color": "\#c5efc5",

"state": 1

},

{

"reason": [

{

"reasontext": "整理",

"color": "\#f5d4ba",

"reasoncode": "0"

},

{

"reasontext": "忙碌",

"color": "\#ecb9b7",

"reasoncode": "3"

},

{

"reasontext": "离开",

"color": "\#bbb",

"reasoncode": "4"

},

{

"reasontext": "休息",

"color": "\#eac4e3",

"reasoncode": "5"

},

{

"reasontext": "通话",

"color": "\#b7d5f7",

"reasoncode": "1"

},

{

"reasontext": "设备不可用",

"color": "\#bcb9ce",

"reasoncode": "2"

},

{

"reasontext": "拨号中",

"color": "\#f9f5ce",

"reasoncode": "6"

},

{

"reasontext": "外线振铃",

"color": "\#cef5ed",

"reasoncode": "7"

},

{

"reasontext": "呼入振铃",

"color": "\#cee0f5",

"reasoncode": "8"

}

],

"state": 2

}

],

"message": "success!"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.38.坐席状态记录列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentStateHistories
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentStateHistories
```

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>否</td>
    <td>开始时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>否</td>
    <td>结束时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>String</td>
    <td>否</td>
    <td>坐席号 如:10001_1000</td>
  </tr>
  <tr>
    <td>extension</td>
    <td>String</td>
    <td>否</td>
    <td>分机号 如:400003</td>
  </tr>
  <tr>
    <td>currentPage</td>
    <td>String</td>
    <td>否</td>
    <td>当前页</td>
  </tr>
  <tr>
    <td>pageSize</td>
    <td>String</td>
    <td>否</td>
    <td>页大小</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>String</td>
    <td>否</td>
    <td>主键id，多个逗号隔开</td>
  </tr>
  <tr>
    <td>holdTime</td>
    <td>String</td>
    <td>否</td>
    <td>排队时长(大于等于)</td>
  </tr>
  <tr>
    <td>holdTimeMin</td>
    <td>String</td>
    <td>否</td>
    <td>排队时长(小于等于)</td>
  </tr>
  <tr>
    <td>state</td>
    <td>String</td>
    <td>否</td>
    <td>坐席状态
      <br/>0:登出（坐席不再接收通信事件，且无法调用通信API）；
      <br/>1:空闲（坐席可以接听来电）；
      <br/>2:忙碌（坐席无法接听来电，但可以外呼）</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>String</td>
    <td>否</td>
    <td>state为2（忙碌）的情况下，坐席忙碌的原因。
      <br/>0：整理（坐席结束通话后，进行文案处理）；
      <br/>1：通话（坐席处于通话中）；
      <br/>2：设备不可用（业务系统发送故障）；
      <br/>3：忙碌（其它的情况下，需要将state设置成3）；
      <br/>4：离开（坐席员离开座位）；
      <br/>5：休息（坐席员进行休息，比如午休）。
      <br/>6：拨号中(调用呼叫接口时的状态)
      <br/>7：外线振铃
      <br/>8：呼入振铃
      <br/>由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长</td>
  </tr>
  <tr>
    <td>sort</td>
    <td>String</td>
    <td>否</td>
    <td>排序字段(传响应的字段)</td>
  </tr>
  <tr>
    <td>order</td>
    <td>String</td>
    <td>否</td>
    <td>排序方式 asc 或 desc</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2021-10-10 11:00:00",

"agent": "10003_1000",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
  <tr>
    <td>extension</td>
    <td>分机号</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>开始时间 时间格式 yyyy-mm-dd HH:mm:ss</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>结束时间 时间格式 yyyy-mm-dd HH:mm:ss</td>
  </tr>
  <tr>
    <td>state</td>
    <td>坐席状态
      <br/>0:登出（坐席不再接收通信事件，且无法调用通信API）；
      <br/>1:空闲（坐席可以接听来电）；
      <br/>2:忙碌（坐席无法接听来电，但可以外呼）</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>state为2（忙碌）的情况下，坐席忙碌的原因。
      <br/>0：整理（坐席结束通话后，进行文案处理）；
      <br/>1：通话（坐席处于通话中）；
      <br/>2：设备不可用（业务系统发送故障）；
      <br/>3：忙碌（其它的情况下，需要将state设置成3）；
      <br/>4：离开（坐席员离开座位）；
      <br/>5：休息（坐席员进行休息，比如午休）。
      <br/>6：拨号中(调用呼叫接口时的状态)
      <br/>7：外线振铃
      <br/>8：呼入振铃
      <br/>由于坐席状态设置成忙碌存在多种场景，所以对相关原因值进行标注，可以将这些场景进行区分；也方便后续根据标注的原因值对不同的场景进行坐席状态相关的统计，比如统计坐席因为离开而设置成忙碌的时长</td>
  </tr>
  <tr>
    <td>stateText</td>
    <td>坐席状态文本</td>
  </tr>
  <tr>
    <td>holdTime</td>
    <td>状态持续时长 单位/秒</td>
  </tr>
  <tr>
    <td>createTime</td>
    <td>创建时间</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "1",

"data": [

{

"action": 0,

"extension": "",

"agent": "10003_1000",

"endTime": "2021-08-05 10:32:14",

"id": 4323,

"extension": "",

"reasonCode": 3,

"startTime": "2021-08-05 10:32:13",

"state": 2,

"tenantId": 10003

},

{

"action": 0,

"extension": "",

"agent": "10003_1000",

"endTime": "2021-08-04 18:10:48",

"id": 4322,

"extension": "",

"reasonCode": -1,

"startTime": "2021-08-04 18:10:48",

"state": 0,

"tenantId": 10003

}

],

"message": "success!",

"totalCount": "888"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.39.随路数据

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAttachDatas
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAttachDatas
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| callID   | String | 是       | 通话标识                    |
| tenantId | String | 否       | 资源组编号：如10000         |
| type     | String | 否       | 随路数据类型                |
| key      | String | 否       | 随路数据键值                |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"callID": "2244f18763616c6c00085eca@183.129.179.6",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，随路数据键值队    |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"data": [

{

"2244f18763616c6c00085eca@183.129.179.6_digit":"1",

"2244f18763616c6c00085eca@183.129.179.6_digit_type":"4",

"2244f18763616c6c00085eca@183.129.179.6_ivr_id":"12"

}],

"message": "success!",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.40.坐席休息排队队列信息

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/callcenter/queryAgentRestQueue
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/callcenter/queryAgentRestQueue
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 否       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |
| typeCode | String | 否       | 业务编码                    |

请求体示例

```
{

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，休息队列信息      |

data:

<table>
  <tr>
    <td width="227.75">tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>restAgentQueue</td>
    <td>排队中的坐席</td>
  </tr>
  <tr>
    <td>restAgentQueueNum</td>
    <td>排队中的坐席数量</td>
  </tr>
  <tr>
    <td>restNum</td>
    <td>休息人数上限</td>
  </tr>
  <tr>
    <td>restAgent</td>
    <td>休息中坐席</td>
  </tr>
  <tr>
    <td>restAgentNum</td>
    <td>休息坐席数量</td>
  </tr>
  <tr>
    <td>typeCode</td>
    <td>业务编码</td>
  </tr>
</table>

restAgent：

| 代码          | 含义         |
|---------------|--------------|
| name          | 坐席名称     |
| agent         | 坐席号       |
| extension     | 分机号       |
| stateHoldTime | 当前休息时长 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "123456",

"code": 200,

"currentPage": "",

"data": [

{

"restAgent": [{

"name":" 坐席x",

"agent": "10005_1000",

"stateHoldTime": "10",

"extension": "5000"

}],

"restAgentQueue": "[]",

"restNum": 1,

"tenantId": 10005

}

],

"message": "success!",

"totalCount": ""

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.41.休息时间模板列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryRestTimeTemp
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryRestTimeTemp
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                |
|-------------|--------|----------|-------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                 |
| startTime   | String | 否       | 开始时段 格式:时:分:秒 如(12:00:01) |
| endTime     | String | 否       | 结束时段 格式:时:分:秒 如(12:00:01) |
| id          | String | 否       | 休息时间模板主键id                  |
| typeCode    | String | 否       | 业务编码                            |
| currentPage | String | 否       | 当前页                              |
| pageSize    | String | 否       | 页大小                              |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回         |

请求体示例

```
{

"tenantId": "10005",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>id</td>
    <td>主键id</td>
  </tr>
  <tr>
    <td>startStamp</td>
    <td>开始时段 格式:时:分:秒 如(12:00:01)</td>
  </tr>
  <tr>
    <td>endStamp</td>
    <td>结束时段 格式:时:分:秒 如(12:00:01)</td>
  </tr>
  <tr>
    <td>restNum</td>
    <td>休息人数上限</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>typeCode</td>
    <td>业务编码</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"endStamp": "23:59:59",

"id": 9,

"restNum": 1,

"startStamp": "12:00:01",

"typeCode": "12",

"tenantId": 10005

}

],

"message": "success!",

"totalCount": "1"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.42.黑名单列表

请求方式：POST

请求url:

```
http://{url}/{version}/query/queryBlacklists
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/query/queryBlacklists
```

请求频次限制：

**20次／分钟**

请求体

| 字段        | 类型   | 是否必须 | 备注                               |
|-------------|--------|----------|------------------------------------|
| tenantId    | String | 是       | 当前资源组号：如10000              |
| actionID    | String | 是       | 唯一值,原样返回,找到对应的响应信息 |
| number      | String | 否       | 联系号码：如18565485486            |
| startTime   | String | 否       | 开始时间：如2017-10-10 11:00:00    |
| endTime     | String | 否       | 结束时间：如2017-10-10 11:00:00    |
| callType    | String | 否       | 呼叫方向 1:双向 2 :呼入 3:呼出     |
| thisDN      | String | 是       | 当前登录坐席号                     |
| currentPage | String | 是       | 当前页                             |
| pageSize    | String | 是       | 页大小                             |

请求体示例

```
{

"tenantId": "10000",

"number": "18565485486",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"callType": "1",

"thisDN": "10000_1000",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                               |
|-------------|------------------------------------|
| code        | 响应码                             |
| message     | 响应信息                           |
| actionID    | 唯一值,原样返回,找到对应的响应信息 |
| data        | 返回数据，JSON格式                 |
| currentPage | 当前页                             |
| totalCount  | 记录总数                           |

data:

<table>
  <tr>
    <td>id</td>
    <td>黑名单ID</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>userId</td>
    <td>坐席ID</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>坐席名称</td>
  </tr>
  <tr>
    <td>name</td>
    <td>名称</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>电话</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>呼叫方向
      <br/>1:双向
      <br/>2 :呼入
      <br/>3:呼出</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态1：黑名单</td>
  </tr>
  <tr>
    <td>createdTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>description</td>
    <td>描述</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [{

"id":"1",

"tenantId":"10001",

"userId":"10",

"nameCn":"10001_1009",

"name":"张三",

"mobile":"18584628469",

"callType":"1",

"status":"1",

"createdTime":"2017-10-10 12:00:00",

"description":"xxx"

}]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.43.黑名单详情

请求方式：POST

请求url:

```
http://{url}/{version}/query/queryBlacklist
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/query/queryBlacklist
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| tenantId | String | 是       | 当前资源组号：如10000              |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |
| id       | String | 是       | 黑名单ID                           |

请求体示例

```
{

"tenantId": "10000",

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data:

<table>
  <tr>
    <td>id</td>
    <td>黑名单ID</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>userId</td>
    <td>坐席ID</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>坐席名称</td>
  </tr>
  <tr>
    <td>name</td>
    <td>名称</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>电话</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>呼叫方向 <br/>1:双向 <br/>2 :呼入 <br/>3:呼出</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态1：黑名单</td>
  </tr>
  <tr>
    <td>createdTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>description</td>
    <td>描述</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"userId":"10",

"nameCn":"10001_1009",

"name":"张三",

"mobile":"18584628469",

"callType":"1",

"status":"1",

"createdTime":"2017-10-10 12:00:00",

"description":"xxx"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.44.号码联络次数

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryMobileNum
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryMobileNum
```

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>String</td>
    <td>否</td>
    <td>坐席号 如:10001_1000</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>String</td>
    <td>否</td>
    <td>联系号码：如18565485486</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>否</td>
    <td>开始时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>否</td>
    <td>结束时间：如2019-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>second</td>
    <td>String</td>
    <td>否</td>
    <td>通话时间(大于等于)</td>
  </tr>
  <tr>
    <td>secondMin</td>
    <td>String</td>
    <td>否</td>
    <td>通话时间(小于等于)</td>
  </tr>
  <tr>
    <td>hangupCause</td>
    <td>String</td>
    <td>否</td>
    <td>呼叫成功 send_bye:主叫挂断;recv_bye:被叫挂断
      <br/>呼叫失败 call_failed
      <br/>被叫拒接 CALL_REJECTED
      <br/>无应答 NO_ANSWER
      <br/>被叫无响应 NO_USER_RESPONSE
      <br/>用户忙 USER_BUSY
      <br/>空号 UNALLOCATED_NUMBER
      <br/>正常释放 NORMAL_RELEASE
      <br/>双方都由运营商挂断 NORMAL_CLEARING
      <br/>呼叫线路超时 NORMAL_TEMPORARY_FAILURE
      <br/>超时（一般是SIP超时） TIMEOUT
      <br/>呼叫不可达（空号/无法路由）NO_ROUTE_DESTINATION
      <br/>未注册（网关、电话卡） USER_NOT_REGISTERED
      <br/>一般是线路不通, 可能盲区NORMAL_UNSPECIFIED
      <br/>一般是媒体超时, 异常RECOVERY_ON_TIMER_EXPIRE</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>String</td>
    <td>否</td>
    <td>呼叫方向
      <br/>1:内部呼叫
      <br/>2:呼入
      <br/>3:呼出
      <br/>4:双向（包括呼入呼出）</td>
  </tr>
  <tr>
    <td>currentPage</td>
    <td>String</td>
    <td>否</td>
    <td>当前页</td>
  </tr>
  <tr>
    <td>pageSize</td>
    <td>String</td>
    <td>否</td>
    <td>页大小</td>
  </tr>
  <tr>
    <td>ctiCallId</td>
    <td>String</td>
    <td>否</td>
    <td>通话ID</td>
  </tr>
  <tr>
    <td>campaignId</td>
    <td>String</td>
    <td>否</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>String</td>
    <td>否</td>
    <td>主键ID，多个逗号隔开</td>
  </tr>
  <tr>
    <td>isCdrInboundFail</td>
    <td>String</td>
    <td>否</td>
    <td>未接来电
      <br/>1: 转接坐席未接
      <br/>2：进入ivr未接
      <br/>3：进入ACD未接
      <br/>4: 非未接来电
      <br/>5:所有未接
      <br/>空:查询所有符合以上条件的数据</td>
  </tr>
  <tr>
    <td>isCdrOutboundFail</td>
    <td>String</td>
    <td>否</td>
    <td>未接去电
      <br/>1：未接去电
      <br/>2：非未接去电
      <br/>空:查询所有符合以上条件的数据</td>
  </tr>
  <tr>
    <td>channelAttr</td>
    <td>String</td>
    <td>否</td>
    <td>呼叫属性
      <br/>transfer 转接呼叫
      <br/>conference 三方呼叫
      <br/>monitor 监听
      <br/>makeCall 接口外呼
      <br/>holdCall 保持外呼</td>
  </tr>
  <tr>
    <td>extension</td>
    <td>String</td>
    <td>否</td>
    <td>分机号 如:400001</td>
  </tr>
  <tr>
    <td>ivrDigitType</td>
    <td>String</td>
    <td>否</td>
    <td>组件类型</td>
  </tr>
  <tr>
    <td>queue</td>
    <td>String</td>
    <td>否</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>ivrID</td>
    <td>String</td>
    <td>否</td>
    <td>ivr主键ID</td>
  </tr>
  <tr>
    <td>ivrDtmfDigit</td>
    <td>String</td>
    <td>否</td>
    <td>满意度结果</td>
  </tr>
  <tr>
    <td>repeatCallId</td>
    <td>String</td>
    <td>否</td>
    <td>是否callId去重
      <br/>空：不去重
      <br/>1：去重</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"mobile": "18565485486",

"startTime": "2017-10-10 11:00:00",

"endTime": "2019-10-10 11:00:00",

"second": "30",

"hangupCause": "NO_ANSWER",

"callType": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 联络次数                    |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": "12"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.45.资源组通话时段统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantHourDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantHourDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>资源组名称</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intHour</td>
    <td>统计时段（小时）格式:yyyy-MM-dd HH</td>
  </tr>
  <tr>
    <td>hour</td>
    <td>小时 格式: HH</td>
  </tr>
  <tr>
    <td>date</td>
    <td>日期 格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.46.ACD通话时段统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueHourDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueHourDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                      |
|-------------|--------|----------|-------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                       |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回               |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00           |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00           |
| filter      | String | 是       | 填写ACD号，例如10000_8000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                    |
| order       | String | 否       | 排序方式 asc 或 desc                      |
| currentPage | String | 否       | 当前页                                    |
| pageSize    | String | 否       | 页大小                                    |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>ACD名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intHour</td>
    <td>统计时段（小时）格式:yyyy-MM-dd HH</td>
  </tr>
  <tr>
    <td>hour</td>
    <td>小时 格式: HH</td>
  </tr>
  <tr>
    <td>date</td>
    <td>日期 格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.47.部门通话时段统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySkillGroupHourDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySkillGroupHourDateStatistics
```

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
      </tr>
      <tr>
        <td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2021-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>技能组键值对<br/> {\&quot;部门1\&quot;:
          <br/>\&quot;[10000_5000,10000_5001,10000_5002]\&quot;,
          <br/>\&quot;部门2\&quot;:
          <br/>\&quot;[10000_5003,10000_5004,10000_5005]\&quot;}；</td>
      </tr>
      <tr>
        <td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
      </tr>
      <tr>
        <td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
      </tr>
      <tr>
        <td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
      </tr>
      <tr>
        <td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>部门</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intHour</td>
    <td>统计时段（小时）格式:yyyy-MM-dd HH</td>
  </tr>
  <tr>
    <td>hour</td>
    <td>小时 格式: HH</td>
  </tr>
  <tr>
    <td>date</td>
    <td>日期 格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.48.坐席通话时段统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentHourDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentHourDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                       |
|-------------|--------|----------|--------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                        |
| filter      | String | 是       | 填写坐席号，例如10000_1000；多个值逗号隔开 |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00            |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00            |
| sort        | String | 否       | 排序字段(传响应的字段)                     |
| order       | String | 否       | 排序方式 asc 或 desc                       |
| currentPage | String | 否       | 当前页                                     |
| pageSize    | String | 否       | 页大小                                     |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回                |

请求体示例

```
{

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>坐席名称</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intHour</td>
    <td>统计时段（小时）格式:yyyy-MM-dd HH</td>
  </tr>
  <tr>
    <td>hour</td>
    <td>小时 格式: HH</td>
  </tr>
  <tr>
    <td>date</td>
    <td>日期 格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.49.资源组通话日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantDayDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>资源组名</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.50.ACD通话日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueDayDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                      |
|-------------|--------|----------|-------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                       |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回               |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00           |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00           |
| filter      | String | 是       | 填写ACD号，例如10000_8000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                    |
| order       | String | 否       | 排序方式 asc 或 desc                      |
| currentPage | String | 否       | 当前页                                    |
| pageSize    | String | 否       | 页大小                                    |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>ACD名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.51.部门通话日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySkillGroupDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySkillGroupDayDateStatistics
```

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
      </tr>
      <tr>
        <td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2021-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>技能组键值对
          <br/>{\&quot;部门1\&quot;:
          <br/>\&quot;[10000_5000,10000_5001,10000_5002]\&quot;,
          <br/>\&quot;部门2\&quot;:
          <br/>\&quot;[10000_5003,10000_5004,10000_5005]\&quot;}；</td>
      </tr>
      <tr>
        <td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
      </tr>
      <tr>
        <td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
      </tr>
      <tr>
        <td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
      </tr>
      <tr>
        <td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>部门</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.52.坐席通话日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentDayDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                       |
|-------------|--------|----------|--------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                        |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回                |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00            |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00            |
| filter      | String | 是       | 填写坐席号，例如10000_1000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                     |
| order       | String | 否       | 排序方式 asc 或 desc                       |
| currentPage | String | 否       | 当前页                                     |
| pageSize    | String | 否       | 页大小                                     |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>坐席姓名</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.53.资源组通话月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantMonthDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>资源组名</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.54.ACD通话月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueMonthDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                      |
|-------------|--------|----------|-------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                       |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回               |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00           |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00           |
| filter      | String | 是       | 填写ACD号，例如10000_8000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                    |
| order       | String | 否       | 排序方式 asc 或 desc                      |
| currentPage | String | 否       | 当前页                                    |
| pageSize    | String | 否       | 页大小                                    |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>ACD名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.55.部门通话月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySkillGroupMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySkillGroupMonthDateStatistics
```

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
      </tr>
      <tr>
        <td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2021-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>技能组键值队
          <br/>{\&quot;部门1\&quot;:
          <br/>\&quot;[10000_5000,10000_5001,10000_5002]\&quot;,
          <br/>\&quot;部门2\&quot;:
          <br/>\&quot;[10000_5003,10000_5004,10000_5005]\&quot;}；</td>
      </tr>
      <tr>
        <td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
      </tr>
      <tr>
        <td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
      </tr>
      <tr>
        <td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
      </tr>
      <tr>
        <td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>部门</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.56.坐席通话月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentMonthDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                       |
|-------------|--------|----------|--------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                        |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回                |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00            |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00            |
| filter      | String | 是       | 填写坐席号，例如10000_1000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                     |
| order       | String | 否       | 排序方式 asc 或 desc                       |
| currentPage | String | 否       | 当前页                                     |
| pageSize    | String | 否       | 页大小                                     |

请求体示例

```
{

"filter": "10005_1000",

"tenantId": "10005",

"startTime": "2021-12-15 00:00:00",

"endTime": "2021-12-15 24:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>坐席姓名</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入应答数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inCallCompletingRate</td>
    <td>呼入应答率</td>
  </tr>
  <tr>
    <td>outCallCompletingRate</td>
    <td>呼出应答率</td>
  </tr>
  <tr>
    <td>inTransfers</td>
    <td>呼入转接次数</td>
  </tr>
  <tr>
    <td>outTransfers</td>
    <td>呼出转接次数</td>
  </tr>
  <tr>
    <td>inMonitors</td>
    <td>呼入监听数</td>
  </tr>
  <tr>
    <td>outMonitors</td>
    <td>呼出监听数</td>
  </tr>
  <tr>
    <td>inConferences</td>
    <td>呼入三方通话次数</td>
  </tr>
  <tr>
    <td>outConferences</td>
    <td>呼出三方通话次数</td>
  </tr>
  <tr>
    <td>outAvgRingTime</td>
    <td>呼出平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAvgRingTime</td>
    <td>呼入平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgRingTime</td>
    <td>平均振铃时长 单位/秒</td>
  </tr>
  <tr>
    <td>minTalkTime</td>
    <td>最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>maxTalkTime</td>
    <td>最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMinTalkTime</td>
    <td>呼入最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>inMaxTalkTime</td>
    <td>呼入最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMinTalkTime</td>
    <td>呼出最短通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>outMaxTalkTime</td>
    <td>呼出最长通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>intMonth</td>
    <td>统计时段（月）格式:yyyy-MM</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"talkTime": "0",

"inMaxTalkTime": 0,

"outCallCompletingRate": "0.00%",

"inAnswerCalls": 0,

"avgTalkTime": "0",

"outCalls": 0,

"inTransfers": 0,

"outMinTalkTime": 0,

"inMonitors": 0,

"minTalkTime": 0,

"outConferences": 0,

"outAnswerCalls": 0,

"intHour": "2021-01-21 00",

"outMaxTalkTime": 0,

"intDay": null,

"maxTalkTime": 0,

"avgRingTime": "0",

"inCalls": 0,

"calls": 0,

"inConferences": 0,

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"tenantId": 10000,

"outMonitors": 0,

"inCallCompletingRate": "0.00%",

"intMonth": null,

"outTransfers": 0,

"inMinTalkTime": 0

}

],

"message": "success!",

"tenantID": 10000,

"totalCount": "24"

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 6.57.资源组状态日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantStateDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantStateDayDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>资源组</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "30",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "7",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "01:55:04",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "00:14:14",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "02:11:35",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```



## 6.58.ACD状态日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueStateDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueStateDayDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                      |
|-------------|--------|----------|-------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                       |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回               |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00           |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00           |
| filter      | String | 是       | 填写ACD号，例如10000_8000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                    |
| order       | String | 否       | 排序方式 asc 或 desc                      |
| currentPage | String | 否       | 当前页                                    |
| pageSize    | String | 否       | 页大小                                    |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000_8000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>ACD名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "26930",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "307",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "43740",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "1554",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "1414",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```



## 6.59.部门状态日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySkillGroupStateDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySkillGroupStateDayDateStatistics
```

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
      </tr>
      <tr>
        <td>startTime</td>
        <td>String</td>
        <td>是</td>
        <td>开始时间：如2017-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>endTime</td>
        <td>String</td>
        <td>是</td>
        <td>结束时间：如2021-10-10 11:00:00</td>
      </tr>
      <tr>
        <td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>技能组键值对
          <br/>{\&quot;部门1\&quot;:
          <br/>\&quot;[10000_5000,10000_5001,10000_5002]\&quot;,
          <br/>\&quot;部门2\&quot;:
          <br/>\&quot;[10000_5003,10000_5004,10000_5005]\&quot;}；</td>
      </tr>
      <tr>
        <td>sort</td>
        <td>String</td>
        <td>否</td>
        <td>排序字段(传响应的字段)</td>
      </tr>
      <tr>
        <td>order</td>
        <td>String</td>
        <td>否</td>
        <td>排序方式 asc 或 desc</td>
      </tr>
      <tr>
        <td>currentPage</td>
        <td>String</td>
        <td>否</td>
        <td>当前页</td>
      </tr>
      <tr>
        <td>pageSize</td>
        <td>String</td>
        <td>否</td>
        <td>页大小</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>部门名称</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "26430",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "37",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "01:55:04",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "1414",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```


## 6.60.坐席状态日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentStateDayDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentStateDayDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                       |
|-------------|--------|----------|--------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                        |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回                |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00            |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00            |
| filter      | String | 是       | 填写坐席号，例如10000_1000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                     |
| order       | String | 否       | 排序方式 asc 或 desc                       |
| currentPage | String | 否       | 当前页                                     |
| pageSize    | String | 否       | 页大小                                     |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>坐席或ACD编号或资源组名或部门名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席名或ACD名或资源组号</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "230",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "307",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "104",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "144",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```


## 6.61.资源组状态月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantStateMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantStateMonthDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>资源组</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intMonth</td>
    <td>统计时段（月）格式:yyyy-MM</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "230",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "307",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "104",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "144",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```



## 6.62.ACD状态月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueStateMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueStateMonthDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                      |
|-------------|--------|----------|-------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                       |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回               |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00           |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00           |
| filter      | String | 是       | 填写ACD号，例如10000_8000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                    |
| order       | String | 否       | 排序方式 asc 或 desc                      |
| currentPage | String | 否       | 当前页                                    |
| pageSize    | String | 否       | 页大小                                    |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000_8000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>ACD名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intMonth</td>
    <td>统计时段（月）格式:yyyy-MM</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "230",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "307",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "104",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "144",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```



## 6.63部门状态月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySkillGroupStateMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySkillGroupStateMonthDateStatistics
```

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>是</td>
    <td>开始时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>是</td>
    <td>结束时间：如2021-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>filter</td>
    <td>String</td>
    <td>是</td>
    <td>技能组键值队
      <br/>{\&quot;部门1\&quot;:
      <br/>\&quot;[10000_5000,10000_5001,10000_5002]\&quot;,
      <br/>\&quot;部门2\&quot;:
      <br/>\&quot;[10000_5003,10000_5004,10000_5005]\&quot;}；</td>
  </tr>
  <tr>
    <td>sort</td>
    <td>String</td>
    <td>否</td>
    <td>排序字段(传响应的字段)</td>
  </tr>
  <tr>
    <td>order</td>
    <td>String</td>
    <td>否</td>
    <td>排序方式 asc 或 desc</td>
  </tr>
  <tr>
    <td>currentPage</td>
    <td>String</td>
    <td>否</td>
    <td>当前页</td>
  </tr>
  <tr>
    <td>pageSize</td>
    <td>String</td>
    <td>否</td>
    <td>页大小</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>部门名称</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intMonth</td>
    <td>统计时段（月）格式:yyyy-MM</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "230",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "307",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "104",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "144",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```


## 6.64.坐席状态月统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentStateMonthDateStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentStateMonthDateStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                       |
|-------------|--------|----------|--------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                        |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回                |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00            |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00            |
| filter      | String | 是       | 填写坐席号，例如10000_1000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                     |
| order       | String | 否       | 排序方式 asc 或 desc                       |
| currentPage | String | 否       | 当前页                                     |
| pageSize    | String | 否       | 页大小                                     |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>坐席或ACD编号或资源组名或部门名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席名或ACD名或资源组号</td>
  </tr>
  <tr>
    <td>acwCount</td>
    <td>整理次数</td>
  </tr>
  <tr>
    <td>acwTime</td>
    <td>整理时长 单位/秒</td>
  </tr>
  <tr>
    <td>avgTalkTime</td>
    <td>平均通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>breakCount</td>
    <td>休息次数</td>
  </tr>
  <tr>
    <td>breakTime</td>
    <td>休息时长 单位/秒</td>
  </tr>
  <tr>
    <td>busyCount</td>
    <td>忙碌次数</td>
  </tr>
  <tr>
    <td>busyTime</td>
    <td>忙碌时长 单位/秒</td>
  </tr>
  <tr>
    <td>calls</td>
    <td>通话总量</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>呼入接听数</td>
  </tr>
  <tr>
    <td>inAvgTalkTime</td>
    <td>呼入平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入数</td>
  </tr>
  <tr>
    <td>inTalkTime</td>
    <td>呼入通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>intMonth</td>
    <td>统计时段（月）格式:yyyy-MM</td>
  </tr>
  <tr>
    <td>loginCount</td>
    <td>签入次数</td>
  </tr>
  <tr>
    <td>logoutCount</td>
    <td>签出次数</td>
  </tr>
  <tr>
    <td>outAnswerCalls</td>
    <td>呼出应答数</td>
  </tr>
  <tr>
    <td>outAvgTalkTime</td>
    <td>呼出平均通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>outCalls</td>
    <td>呼出数</td>
  </tr>
  <tr>
    <td>outTalkTime</td>
    <td>呼出通话时间 单位/秒</td>
  </tr>
  <tr>
    <td>readyCount</td>
    <td>空闲次数</td>
  </tr>
  <tr>
    <td>readyTime</td>
    <td>空闲时长 单位/秒</td>
  </tr>
  <tr>
    <td>talkTime</td>
    <td>通话中时长 单位/秒</td>
  </tr>
  <tr>
    <td>workTime</td>
    <td>登录时长 单位/秒</td>
  </tr>
  <tr>
    <td>leaveCount</td>
    <td>离开次数</td>
  </tr>
  <tr>
    <td>leaveTime</td>
    <td>离开时长 单位/秒</td>
  </tr>
  <tr>
    <td>operationCount_自定义状态编码</td>
    <td>坐席自定义状态操作次数</td>
  </tr>
  <tr>
    <td>operationTime_自定义状态编码</td>
    <td>坐席自定义状态操作时长</td>
  </tr>
  <tr>
    <td>operationName_自定义状态编码</td>
    <td>坐席自定义状态操作名称</td>
  </tr>
  <tr>
    <td>amountAgentReasonCodes</td>
    <td>坐席自定义状态统计</td>
  </tr>
</table>

amountAgentReasonCodes:

<table>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>operationCount</td>
    <td>操作次数</td>
  </tr>
  <tr>
    <td>operationTime</td>
    <td>操作时长 单位/秒</td>
  </tr>
  <tr>
    <td>reasonCodeId</td>
    <td>自定义状态主键ID</td>
  </tr>
  <tr>
    <td>reasonCode</td>
    <td>自定义状态编码</td>
  </tr>
  <tr>
    <td>reasonCodeName</td>
    <td>自定义状态名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席号</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": "",

"data": [

{

"agent": "test_agent_10000_5000",

"talkTime": "37",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "1",

"outCalls": 8,

"operationTime_5": "0",

"avgOutTalkTime": "4",

"operationTime_6": "0",

"readyTime": "230",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 3,

"busyTime": "307",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "516",

"inTalkTime": "0",

"logoutCount": 137,

"workTime": "4340",

"amountAgentReasonCodes": [

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "test_agent_10000_5000",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 241,

"avgRingTime": "13",

"busyCount": 25,

"inCalls": 14,

"leaveCount": 0,

"breakTime": "4",

"breakCount": 6,

"acwCount": 4,

"calls": 22,

"outTalkTime": "8",

"inAvgRingTime": "12",

"outAvgRingTime": "16",

"name": "10000_5000",

"readyCount": 390,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

},

{

"agent": "batch_5003",

"talkTime": "0",

"operationCount_7": 0,

"operationCount_8": 0,

"inAnswerCalls": 0,

"avgInTalkTime": "0",

"avgTalkTime": "0",

"outCalls": 0,

"operationTime_5": "0",

"avgOutTalkTime": "0",

"operationTime_6": "0",

"readyTime": "104",

"operationTime_3": "0",

"operationTime_4": "0",

"operationTime_7": "0",

"operationTime_8": "0",

"outAnswerCalls": 0,

"busyTime": "144",

"operationTime_1": "0",

"operationTime_2": "0",

"operationTime_0": "0",

"leaveTime": "0",

"acwTime": "0",

"inTalkTime": "0",

"logoutCount": 5,

"workTime": "235",

"amountAgentReasonCodes": [

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 0,

"reasonCodeId": 2,

"reasonCodeName": "整理",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 1,

"reasonCodeId": 3,

"reasonCodeName": "通话",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 2,

"reasonCodeId": 4,

"reasonCodeName": "设备不可用",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 3,

"reasonCodeId": 5,

"reasonCodeName": "忙碌",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 4,

"reasonCodeId": 6,

"reasonCodeName": "离开",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 5,

"reasonCodeId": 7,

"reasonCodeName": "休息",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 6,

"reasonCodeId": 8,

"reasonCodeName": "拨号中",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 7,

"reasonCodeId": 9,

"reasonCodeName": "外线振铃",

"tenantId": 10000

},

{

"agent": "batch_5003",

"extension": "",

"id": 0,

"intDay": 0,

"intHour": 0,

"intMonth": 0,

"intYear": 0,

"jobNum": "",

"name": "",

"operationCount": 0,

"operationTime": 0,

"reasonCode": 8,

"reasonCodeId": 10,

"reasonCodeName": "呼入振铃",

"tenantId": 10000

}

],

"loginCount": 6,

"avgRingTime": "0",

"busyCount": 1,

"inCalls": 0,

"leaveCount": 0,

"breakTime": "0",

"breakCount": 0,

"acwCount": 0,

"calls": 0,

"outTalkTime": "0",

"inAvgRingTime": "0",

"outAvgRingTime": "0",

"name": "10000_5003",

"readyCount": 5,

"operationCount_3": 0,

"operationCount_4": 0,

"operationCount_5": 0,

"operationCount_6": 0,

"operationCount_0": 0,

"operationCount_1": 0,

"operationCount_2": 0

}

],

"message": "success!",

"tenantID": 0,

"totalCount": "2"

}
```


## 6.65资源组队列日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryTenantDayDateQueueStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryTenantDayDateQueueStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                            |
|-------------|--------|----------|---------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000             |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回     |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00 |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00 |
| sort        | String | 否       | 排序字段(传响应的字段)          |
| order       | String | 否       | 排序方式 asc 或 desc            |
| currentPage | String | 否       | 当前页                          |
| pageSize    | String | 否       | 页大小                          |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>资源组</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>abandonTime</td>
    <td>呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>abandonAvgTime</td>
    <td>平均呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAbandonCalls</td>
    <td>呼叫放弃次数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入次数</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>人工接听数</td>
  </tr>
  <tr>
    <td>inUnAnswerCalls</td>
    <td>未接听数</td>
  </tr>
  <tr>
    <td>holdTime</td>
    <td>排队总时长 单位/秒</td>
  </tr>
  <tr>
    <td>holdAvgTime</td>
    <td>平均排队时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAnswerCallRate</td>
    <td>人工接听率</td>
  </tr>
  <tr>
    <td>inUnAnswerCallRate</td>
    <td>未接听率</td>
  </tr>
  <tr>
    <td>inAbandonCallRate</td>
    <td>呼叫放弃率</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例
```
{

"actionID": "abcd123",

"code": 200,

"currentPage": 0,

"data": [

{

"date": null,

"abandonTime": 0,

"agent": "10000",

"abandonAvgTime": 0,

"inAbandonCalls": 1,

"inAnswerCalls": 6,

"holdTime": 43,

"inCalls": 7,

"hour": null,

"inAnswerCallRate": "85.71%",

"name": "区政府服务大厅",

"tenantId": 10000,

"holdAvgTime": 6,

"inAbandonCallRate": "14.29%",

"intHour": null,

"intDay": "2021-01-14",

"intMonth": null,

"inUnAnswerCalls": 1,

"inUnAnswerCallRate": "14.29%"

}

],

"message": "success!",

"totalCount": 1

}
```


## 6.66.ACD队列日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryQueueDayDateQueueStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryQueueDayDateQueueStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                      |
|-------------|--------|----------|-------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                       |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回               |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00           |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00           |
| filter      | String | 是       | 填写ACD号，例如10000_8000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                    |
| order       | String | 否       | 排序方式 asc 或 desc                      |
| currentPage | String | 否       | 当前页                                    |
| pageSize    | String | 否       | 页大小                                    |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000_8000",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>name</td>
    <td>ACD名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>ACD号</td>
  </tr>
  <tr>
    <td>abandonTime</td>
    <td>呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>abandonAvgTime</td>
    <td>平均呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAbandonCalls</td>
    <td>呼叫放弃次数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入次数</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>人工接听数</td>
  </tr>
  <tr>
    <td>inUnAnswerCalls</td>
    <td>未接听数</td>
  </tr>
  <tr>
    <td>holdTime</td>
    <td>排队总时长 单位/秒</td>
  </tr>
  <tr>
    <td>holdAvgTime</td>
    <td>平均排队时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAnswerCallRate</td>
    <td>人工接听率</td>
  </tr>
  <tr>
    <td>inUnAnswerCallRate</td>
    <td>未接听率</td>
  </tr>
  <tr>
    <td>inAbandonCallRate</td>
    <td>呼叫放弃率</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": 0,

"data": [

{

"date": null,

"abandonTime": 0,

"agent": "10000_8000",

"abandonAvgTime": 0,

"inAbandonCalls": 0,

"inAnswerCalls": 6,

"holdTime": 43,

"inCalls": 6,

"hour": null,

"inAnswerCallRate": "100.00%",

"name": "呼叫技能组1",

"tenantId": 10000,

"holdAvgTime": 7,

"inAbandonCallRate": "0.00%",

"intHour": null,

"intDay": "2021-01-14",

"intMonth": null,

"inUnAnswerCalls": 0,

"inUnAnswerCallRate": "0.00%"

}

],

"message": "success!",

"totalCount": 1

}
```



## 6.67.部门队列日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySkillGroupDayDateQueueStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySkillGroupDayDateQueueStatistics
```

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>是</td>
    <td>开始时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>是</td>
    <td>结束时间：如2021-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>filter</td>
    <td>String</td>
    <td>是</td>
    <td>技能组键值队
      <br/>{\&quot;部门1\&quot;:
      <br/>\&quot;[10000_5000,10000_5001,10000_5002]\&quot;,
      <br/>\&quot;部门2\&quot;:
      <br/>\&quot;[10000_5003,10000_5004,10000_5005]\&quot;}；</td>
  </tr>
  <tr>
    <td>sort</td>
    <td>String</td>
    <td>否</td>
    <td>排序字段(传响应的字段)</td>
  </tr>
  <tr>
    <td>order</td>
    <td>String</td>
    <td>否</td>
    <td>排序方式 asc 或 desc</td>
  </tr>
  <tr>
    <td>currentPage</td>
    <td>String</td>
    <td>否</td>
    <td>当前页</td>
  </tr>
  <tr>
    <td>pageSize</td>
    <td>String</td>
    <td>否</td>
    <td>页大小</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>部门名称</td>
  </tr>
  <tr>
    <td>abandonTime</td>
    <td>呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>abandonAvgTime</td>
    <td>平均呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAbandonCalls</td>
    <td>呼叫放弃次数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入次数</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>人工接听数</td>
  </tr>
  <tr>
    <td>inUnAnswerCalls</td>
    <td>未接听数</td>
  </tr>
  <tr>
    <td>holdTime</td>
    <td>排队总时长 单位/秒</td>
  </tr>
  <tr>
    <td>holdAvgTime</td>
    <td>平均排队时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAnswerCallRate</td>
    <td>人工接听率</td>
  </tr>
  <tr>
    <td>inUnAnswerCallRate</td>
    <td>未接听率</td>
  </tr>
  <tr>
    <td>inAbandonCallRate</td>
    <td>呼叫放弃率</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": 0,

"data": [

{

"date": null,

"abandonTime": 0,

"agent": "",

"abandonAvgTime": 0,

"inAbandonCalls": 0,

"inAnswerCalls": 6,

"holdTime": 43,

"inCalls": 6,

"hour": null,

"inAnswerCallRate": "100.00%",

"name": "部门1",

"tenantId": 10000,

"holdAvgTime": 7,

"inAbandonCallRate": "0.00%",

"intHour": null,

"intDay": "2021-01-14",

"intMonth": null,

"inUnAnswerCalls": 0,

"inUnAnswerCallRate": "0.00%"

}

],

"message": "success!",

"totalCount": 1

}
```



## 6.68.坐席队列日统计

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryAgentDayDateQueueStatistics
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/queryAgentDayDateQueueStatistics
```

请求体

| 字段        | 类型   | 是否必须 | 备注                                       |
|-------------|--------|----------|--------------------------------------------|
| tenantId    | String | 是       | 资源组编号：如10000                        |
| actionID    | String | 是       | 唯一值,在响应信息中原样返回                |
| startTime   | String | 是       | 开始时间：如2017-10-10 11:00:00            |
| endTime     | String | 是       | 结束时间：如2021-10-10 11:00:00            |
| filter      | String | 是       | 填写坐席号，例如10000_1000；多个值逗号隔开 |
| sort        | String | 否       | 排序字段(传响应的字段)                     |
| order       | String | 否       | 排序方式 asc 或 desc                       |
| currentPage | String | 否       | 当前页                                     |
| pageSize    | String | 否       | 页大小                                     |

请求体示例

```
{

"tenantId": "10000",

"sort": "agent",

"order": "asc",

"filter": "10000,10001,10002",

"startTime": "2017-10-10 11:00:00",

"endTime": "2017-10-10 11:00:00",

"actionID": "abcd123"

}
```

返回值：

| 字段       | 含义                        |
|------------|-----------------------------|
| code       | 响应码                      |
| message    | 响应信息                    |
| actionID   | 唯一值,在响应信息中原样返回 |
| data       | 返回数据，JSON格式          |
| totalCount | 记录总数                    |

data:

<table>
  <tr>
    <td>name</td>
    <td>坐席或ACD编号或资源组名或部门名称</td>
  </tr>
  <tr>
    <td>agent</td>
    <td>坐席名或ACD名或资源组号</td>
  </tr>
  <tr>
    <td>abandonTime</td>
    <td>呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>abandonAvgTime</td>
    <td>平均呼叫放弃时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAbandonCalls</td>
    <td>呼叫放弃次数</td>
  </tr>
  <tr>
    <td>inCalls</td>
    <td>呼入次数</td>
  </tr>
  <tr>
    <td>inAnswerCalls</td>
    <td>人工接听数</td>
  </tr>
  <tr>
    <td>inUnAnswerCalls</td>
    <td>未接听数</td>
  </tr>
  <tr>
    <td>holdTime</td>
    <td>排队总时长 单位/秒</td>
  </tr>
  <tr>
    <td>holdAvgTime</td>
    <td>平均排队时长 单位/秒</td>
  </tr>
  <tr>
    <td>inAnswerCallRate</td>
    <td>人工接听率</td>
  </tr>
  <tr>
    <td>inUnAnswerCallRate</td>
    <td>未接听率</td>
  </tr>
  <tr>
    <td>inAbandonCallRate</td>
    <td>呼叫放弃率</td>
  </tr>
  <tr>
    <td>intDay</td>
    <td>统计时段（日）格式:yyyy-MM-dd</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"currentPage": 0,

"data": [

{

"date": null,

"abandonTime": 0,

"agent": "10000_5000",

"abandonAvgTime": 0,

"inAbandonCalls": 0,

"inAnswerCalls": 6,

"holdTime": 43,

"inCalls": 6,

"hour": null,

"inAnswerCallRate": "100.00%",

"name": "qzf5000",

"tenantId": 10000,

"holdAvgTime": 7,

"inAbandonCallRate": "0.00%",

"intHour": null,

"intDay": "2021-01-14",

"intMonth": null,

"inUnAnswerCalls": 0,

"inUnAnswerCallRate": "0.00%"

}

],

"message": "success!",

"totalCount": 1

}
```



## 6.69.查询系统当前时间

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/querySysDateTime
```

示例：

```
http(s)://121.196.50.152:8098/5.0.x.20210203_release/query/querySysDateTime
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                                   |
|----------|----------------------------------------|
| code     | 响应码                                 |
| message  | 响应信息                               |
| actionID | 唯一值,在响应信息中原样返回            |
| data     | 系统当前时间，格式:yyyy-MM-dd HH:mm:ss |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"actionID": "abcd123",

"code": 200,

"data": "2021-01-21 00:00:00",

"message": "success!",

"tenantID": 10000

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```





# 7.数据配置接口



## 7.1.发送短信

请求方式：POST

请求url:

```
http://{url}/{version}/sms/sendSms
```

示例：

```
http://120.27.237.19:8098/5.0.x.20210203_release/sms/sendSms
```

请求频次限制：

**20次／分钟**

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>content</td>
    <td>String</td>
    <td>是</td>
    <td>发送内容</td>
  </tr>
  <tr>
    <td>thisDN</td>
    <td>String</td>
    <td>是</td>
    <td>坐席号(发送人)</td>
  </tr>
  <tr>
    <td>number</td>
    <td>String</td>
    <td>是</td>
    <td>发送目标号码，可群发，号码以逗号隔开</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>gateway</td>
    <td>String</td>
    <td>否</td>
    <td>指定发送短信的网关</td>
  </tr>
  <tr>
    <td>port</td>
    <td>String</td>
    <td>否</td>
    <td>指定发送短信的网关端口</td>
  </tr>
  <tr>
    <td>type</td>
    <td>String</td>
    <td>否</td>
    <td>短信类型(默认值2）
      <br/>1.挂机短信
      <br/>2.手动发送
      <br/>3.手动快闪
      <br/>4.收件箱</td>
  </tr>
  <tr>
    <td>attr</td>
    <td>String</td>
    <td>否</td>
    <td>短信属性（传任意值，查询历史记录原样返回）</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,原样返回,找到对应的响应信息</td>
  </tr>
</table>

请求体示例

```
{

"content": "xxx",

"number": "182xxxxxxx,183xxxxxxx",

"tenantId": "10000",

"thisDN": "10000_1000",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.2.短信已读

请求方式：POST

请求url:

```
http://{url}/{version}/config/modifySmHistories
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/modifySmHistories
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| id       | String | 是       | 主键id多个值逗号隔开               |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.3.删除短信记录

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteSmHistories
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteSmHistories
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| id       | String | 否       | 主键id                             |
| calleeId | String | 否       | 呼叫标识                           |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.4.添加休息时间模板

请求方式：POST

请求url:

```
http://{url}/{version}/config/addRestTimeTemp
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/addRestTimeTemp
```

请求频次限制：

**20次／分钟**

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>是</td>
    <td>开始时段 格式:时:分:秒 如(12:00:01)
      <br/>同一个资源组下时段不能重叠</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>是</td>
    <td>结束时段 格式:时:分:秒 如(12:00:01)
      <br/>同一个资源组下时段不能重叠</td>
  </tr>
  <tr>
    <td>restNum</td>
    <td>String</td>
    <td>是</td>
    <td>休息人数上限</td>
  </tr>
  <tr>
    <td>typeCode</td>
    <td>String</td>
    <td>是</td>
    <td>业务类型</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,原样返回,找到对应的响应信息</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10005",

"typeCode":"12",

"startTime":"12:00:01",

"endTime":"23:59:59",

"restNum":"1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.5.修改休息时间模板

请求方式：POST

请求url:

```
http://{url}/{version}/config/modifyRestTimeTemp
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/modifyRestTimeTemp
```

请求频次限制：

**20次／分钟**

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>id</td>
    <td>String</td>
    <td>是</td>
    <td>休息时间模板主键id</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>是</td>
    <td>开始时段 格式:时:分:秒 如(12:00:01) <br/>同一个资源组下时段不能重叠</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>是</td>
    <td>结束时段 格式:时:分:秒 如(12:00:01)
      <br/>同一个资源组下时段不能重叠</td>
  </tr>
  <tr>
    <td>restNum</td>
    <td>String</td>
    <td>是</td>
    <td>休息人数上限</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>typeCode</td>
    <td>String</td>
    <td>是</td>
    <td>业务类型</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,原样返回,找到对应的响应信息</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10005",

"typeCode":"12",

"startTime":"12:00:01",

"endTime":"23:59:59",

"restNum":"1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.6.删除休息时间模板

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteRestTimeTemp
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteRestTimeTemp
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| id       | String | 是       | 主键id                             |
| tenantId | String | 是       | 资源组编号：如10000                |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |

请求体示例

```
{

"id": "1",

"tenantId": "10005",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.7.删除话务记录

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteCdrs
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteCdrs
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                                  |
|----------|--------|----------|---------------------------------------|
| id       | String | 是       | 主键id或呼叫标识callId,多个值逗号隔开 |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息    |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.8.删除录音记录

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteRecords
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteRecords
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                                  |
|----------|--------|----------|---------------------------------------|
| id       | String | 是       | 主键id或呼叫标识callId,多个值逗号隔开 |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息    |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.9.删除队列记录

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteQueueHistories
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteQueueHistories
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                                  |
|----------|--------|----------|---------------------------------------|
| id       | String | 是       | 主键id或呼叫标识callId,多个值逗号隔开 |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息    |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.10.删除IVR记录

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteIvrHistories
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteIvrHistories
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                                  |
|----------|--------|----------|---------------------------------------|
| id       | String | 是       | 主键id或呼叫标识callId,多个值逗号隔开 |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息    |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.11.添加黑名单

请求方式：POST

请求url:

```
http://{url}/{version}/config/addBlacklist
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/addBlacklist
```

请求频次限制：

**20次／分钟**

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>name</td>
        <td>String</td>
        <td>是</td>
        <td>黑名单姓名</td>
      </tr>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>当前登陆资源组号</td>
      </tr>
      <tr>
        <td>agent</td>
        <td>String</td>
        <td>是</td>
        <td>当前登陆坐席号 如:10000_1000</td>
      </tr>
      <tr>
        <td>mobile</td>
        <td>String</td>
        <td>是</td>
        <td>黑名單号码</td>
      </tr>
      <tr>
        <td>type</td>
        <td>String</td>
        <td>是</td>
        <td>呼叫方向
          <br/>1:双向
          <br/>2:呼入
          <br/>3:呼出</td>
      </tr>
      <tr>
        <td>description</td>
        <td>String</td>
        <td>否</td>
        <td>描述</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,原样返回,找到对应的响应信息</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"name": "xxx",

"tenantId": "10000",

"mobile": "185554454654",

"agent": "10000_1000",

"type": "1",

"description": "xxxx",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data:

<table>
  <tr>
    <td>id</td>
    <td>黑名单ID</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>userId</td>
    <td>坐席ID</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>坐席名称</td>
  </tr>
  <tr>
    <td>name</td>
    <td>名字</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>电话</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>呼叫方向
      <br/>1:双向<br/> 2:呼入<br/> 3:呼出</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态1：启用</td>
  </tr>
  <tr>
    <td>createdTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>description</td>
    <td>描述</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"userId":"10",

"nameCn":"10001_1009",

"name":"张三",

"mobile":"18584628469",

"callType":"1",

"status":"1",

"createdTime":"2017-10-10 12:00:00",

"description":"xxx"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.12.删除黑名单

请求方式：POST

请求url:

```
http://{url}/{version}/config/delBlacklist
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/delBlacklist
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| id       | String | 是       | 黑名单ID                           |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data:

<table>
  <tr>
    <td width="227.75">id</td>
    <td>黑名单ID</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>userId</td>
    <td>坐席ID</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>坐席名称</td>
  </tr>
  <tr>
    <td>name</td>
    <td>名字</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>电话</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>呼叫方向 <br/>1:双向 <br/>2:呼入 <br/>3:呼出</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态1：启用</td>
  </tr>
  <tr>
    <td>createdTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>description</td>
    <td>描述</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"userId":"10",

"nameCn":"10001_1009",

"name":"张三",

"mobile":"18584628469",

"callType":"1",

"status":"1",

"createdTime":"2017-10-10 12:00:00",

"description":"xxx"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.13.修改黑名单

请求方式：POST

请求url:

```
http://{url}/{version}/config/modifyBlacklist
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/modifyBlacklist
```

请求频次限制：

**20次／分钟**

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>id</td>
    <td>String</td>
    <td>是</td>
    <td>黑名单ID</td>
  </tr>
  <tr>
    <td>name</td>
    <td>String</td>
    <td>是</td>
    <td>黑名单姓名</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>String</td>
    <td>是</td>
    <td>黑名單号码</td>
  </tr>
  <tr>
    <td>type</td>
    <td>String</td>
    <td>是</td>
    <td>呼叫方向
      <br/>1:双向
      <br/>2:呼入
      <br/>3:呼出</td>
  </tr>
  <tr>
    <td>description</td>
    <td>String</td>
    <td>否</td>
    <td>描述</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,原样返回,找到对应的响应信息</td>
  </tr>
</table>

请求体示例

```
{

"id": "1",

"name": "xxx",

"mobile": "185554454654",

"type": "1",

"description": "xxxx",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data:

<table>
  <tr>
    <td>id</td>
    <td>黑名单ID</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>所属资源组号</td>
  </tr>
  <tr>
    <td>userId</td>
    <td>坐席ID</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>坐席名称</td>
  </tr>
  <tr>
    <td>name</td>
    <td>名字</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>电话</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>呼叫方向
      <br/>1:双向
      <br/>2:呼入
      <br/>3:呼出</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态1：启用</td>
  </tr>
  <tr>
    <td>createdTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>description</td>
    <td>描述</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"tenantId":"10001",

"userId":"10",

"nameCn":"10001_1009",

"name":"张三",

"mobile":"18584628469",

"callType":"1",

"status":"1",

"createdTime":"2017-10-10 12:00:00",

"description":"xxx"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 7.14.删除坐席状态记录

请求方式：POST

请求url:

```
http://{url}/{version}/config/deleteAgentStateHistories
```

示例：

```
http://121.196.50.152:8098/5.0.x.20210203_release/config/deleteAgentStateHistories
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| id       | String | 是       | 主键id,多个值逗号隔开              |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```





# 8.群呼接口



## 8.1.添加群呼项目

请求方式：POST

请求url:

```
http://{url}/{version}/config/addOutboundInstance
```

示例：

```
http://120.27.237.19:8098/5.0.x.20210203_release/config/addOutboundInstance
```

请求频次限制：

**20次／分钟**

请求体
<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>name</td>
        <td>String</td>
        <td>是</td>
        <td>项目名称</td>
      </tr>
      <tr>
        <td>agent</td>
        <td>String</td>
        <td>是</td>
        <td>坐席号 如:10001_1000</td>
      </tr>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组号</td>
      </tr>
      <tr>
        <td>queueId</td>
        <td>String</td>
        <td>否</td>
        <td>执行ACD主键ID <br/>isVgc等于0时必填</td>
      </tr>
      <tr>
        <td>callType</td>
        <td>String</td>
        <td>否</td>
        <td>呼叫类型
          <br/>1预测型
          <br/>2预览型
          <br/>isVgc等于0时必填</td>
      </tr>
      <tr>
        <td>ratio</td>
        <td>String</td>
        <td>否</td>
        <td>外呼速率 <br/>isVgc等于0时必填</td>
      </tr>
      <tr>
        <td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>号码字符串，以逗号区隔
          <br/>例如：“182xxxxxxxx,183xxxxxxxx”
          <br/>如果语音外呼，并需要指定每个号码的语音流程则数据格式为: “182xxxxxxxx:ivrId,183xxxxxxxx:ivrId”</td>
      </tr>
      <tr>
        <td>contactNum</td>
        <td>String</td>
        <td>否</td>
        <td>号码数量 <br/>号码来源等于2时必填</td>
      </tr>
      <tr>
        <td>removeRepetition</td>
        <td>String</td>
        <td>否</td>
        <td>是否去重
          <br/>0是
          <br/>1否
          <br/>默认为0</td>
      </tr>
      <tr>
        <td>ivrId</td>
        <td>String</td>
        <td>否</td>
        <td>IVR流程ID <br/>isVgc等于1时必填</td>
      </tr>
      <tr>
        <td>isVgc</td>
        <td>String</td>
        <td>否</td>
        <td>是否启用语音群呼
          <br/>0否
          <br/>1启动
          <br/>默认为0</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,原样返回,找到对应的响应信息</td>
      </tr>
      <tr>
        <td>numberBatch</td>
        <td>String</td>
        <td>否</td>
        <td>号码池策略ID</td>
      </tr>
      <tr>
        <td>maxRingTime</td>
        <td>String</td>
        <td>否</td>
        <td>最大振铃时长 单位/秒（默认60）</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"name": "张三",

"tenantId": "10000",

"agent": "10000_1000",

"queueId": "1",

"callType": "1",

"ratio": "xxx",

"dataFrom": "1",

"filter": "182xxxxxxxx,15487854654,13678754165",

"removeRepetition": "0",

"isVgc": "0",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data：

<figure>
  <table>
    <tr>
      <td>id</td>
      <td>项目ID</td>
    </tr>
    <tr>
      <td>name</td>
      <td>项目名称</td>
    </tr>
    <tr>
      <td>nameCn</td>
      <td>创建人</td>
    </tr>
    <tr>
      <td>callType</td>
      <td>外呼类型
        <br/>1:预测型;
        <br/>2:预览型</td>
    </tr>
    <tr>
      <td>ratio</td>
      <td>速率</td>
    </tr>
    <tr>
      <td>status</td>
      <td>状态
        <br/>2：可执行
        <br/>3：执行中
        <br/>4：暂停中
        <br/>5：已结束</td>
    </tr>
    <tr>
      <td>contactNumber</td>
      <td>名单数</td>
    </tr>
    <tr>
      <td>callNum</td>
      <td>执行数</td>
    </tr>
    <tr>
      <td>touchNum</td>
      <td>应答数</td>
    </tr>
    <tr>
      <td>queueDn</td>
      <td>参与ACD</td>
    </tr>
  </table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"name":"xx",

"nameCn":"张三",

"callType":"1",

"ratio":"3",

"status":"3",

"contactNumber":"30",

"callNum":"20",

"touchNum":"10",

"queueDn":"10001_8000"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.2.群呼项目追加号码

请求方式：POST

请求url:

```
http://{url}/{version}/config/appendOutboundInstance
```

示例：

```
http://120.27.237.19:8098/5.0.x.20210203_release/config/appendOutboundInstance
```

请求频次限制：

**20次／分钟**

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>outboundId</td>
        <td>String</td>
        <td>是</td>
        <td>项目主键ID</td>
      </tr>
      <tr>
        <td>filter</td>
        <td>String</td>
        <td>是</td>
        <td>号码字符串，以逗号区隔
          <br/>例如：“182xxxxxxxx,183xxxxxxxx”
          <br/>如果语音外呼，并需要指定每个号码的语音流程则数据格式为: “182xxxxxxxx:ivrId,183xxxxxxxx:ivrId”</td>
      </tr>
      <tr>
        <td>removeRepetition</td>
        <td>String</td>
        <td>否</td>
        <td>是否去重
          <br/>0是
          <br/>1否
          <br/>默认为0</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,原样返回,找到对应的响应信息</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"name": "张三",

"tenantId": "10000",

"agent": "10000_1000",

"queueId": "1",

"callType": "1",

"ratio": "xxx",

"dataFrom": "1",

"filter": "182xxxxxxxx,15487854654,13678754165",

"removeRepetition": "0",

"isVgc": "0",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data：

<table>
  <tr>
    <td width="227.75">id</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>name</td>
    <td>项目名称</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>创建人</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>外呼类型
      <br/>1:预测型;
      <br/>2:预览型</td>
  </tr>
  <tr>
    <td>ratio</td>
    <td>速率</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态
      <br/>2：可执行
      <br/>3：执行中
      <br/>4：暂停中
      <br/>5：已结束</td>
  </tr>
  <tr>
    <td>contactNumber</td>
    <td>名单数</td>
  </tr>
  <tr>
    <td>callNum</td>
    <td>执行数</td>
  </tr>
  <tr>
    <td>touchNum</td>
    <td>应答数</td>
  </tr>
  <tr>
    <td>queueDn</td>
    <td>参与ACD</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"name":"xx",

"nameCn":"张三",

"callType":"1",

"ratio":"3",

"status":"3",

"contactNumber":"30",

"callNum":"20",

"touchNum":"10",

"queueDn":"10001_8000"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.3.删除语音群呼项目

请求方式：POST

请求url:

```
http://{url}/{version}/config/delVoiceOutboundInstance
```

示例：

```
http://120.27.237.19:8098/5.0.x.20210203_release/config/delVoiceOutboundInstance
```

请求频次限制：

**20次／分钟**

请求体

| 字段     | 类型   | 是否必须 | 备注                               |
|----------|--------|----------|------------------------------------|
| id       | String | 是       | 群呼项目ID                         |
| actionID | String | 是       | 唯一值,原样返回,找到对应的响应信息 |

请求体示例

```
{

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data：

<table>
  <tr>
    <td width="227.75">id</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>name</td>
    <td>项目名称</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>创建人</td>
  </tr>
  <tr>
    <td>isVgc</td>
    <td>外呼类型 1:语音群呼</td>
  </tr>
  <tr>
    <td>ratio</td>
    <td>速率</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态
      <br/>2：可执行
      <br/>3：执行中
      <br/>4：暂停中
      <br/>5：已结束</td>
  </tr>
  <tr>
    <td>contactNumber</td>
    <td>名单数</td>
  </tr>
  <tr>
    <td>callNum</td>
    <td>执行数</td>
  </tr>
  <tr>
    <td>touchNum</td>
    <td>应答数</td>
  </tr>
  <tr>
    <td>queueDn</td>
    <td>参与ACD</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"name":"xx",

"nameCn":"张三",

"callType":"1",

"ratio":"3",

"status":"3",

"contactNumber":"30",

"callNum":"20",

"touchNum":"10",

"queueDn":"10001_8000"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.4.启动群呼项目

请求方式：POST

请求url:

```
http://{url}/config/StartOutbound
```

示例：

```
http://120.27.237.19:8099/config/StartOutbound
```

请求频次限制：

**20次／分钟**

请求体

| 字段       | 类型   | 是否必须 | 备注                     |
| ---------- | ------ | -------- | ------------------------ |
| outboundId | String | 是       | 项目ID                   |
| tenantId   | String | 是       | 所属资源组号             |
| dialMode   | String | 是       | 拨号模式:1预测式;2预览式 |

请求体示例

```
{

"tenantId": "10000",

"outboundId": "46",

"dialMode": "1"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.5.暂停群呼项目

请求方式：POST

请求url:

```
http://{url}/config/PauseOutbound
```

示例：

```
http://120.27.237.19:8099/config/PauseOutbound
```

请求频次限制：

**20次／分钟**

请求体

| 字段       | 类型   | 是否必须 | 备注                      |
| ---------- | ------ | -------- | ------------------------- |
| outboundId | String | 是       | 项目ID                    |
| tenantId   | String | 是       | 所属资源组号              |
| dialMode   | String | 是       | 拨号模式:1预测式 ;2预览式 |

请求体示例

```
{

"tenantId": "10000",

"outboundId": "46",

"dialMode": "1"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

}
```

返回201示例：

```
{

"code": 201,

"message": "Please check your parameters"

}
```



## 8.6.停止群呼项目

请求方式：POST

请求url:

```
http://{url}/config/StopOutbound
```

示例：

```
http://120.27.237.19:8099/config/StopOutbound
```

请求频次限制：

**20次／分钟**

请求体

| 字段       | 类型   | 是否必须 | 备注                      |
| ---------- | ------ | -------- | ------------------------- |
| outboundId | String | 是       | 项目ID                    |
| tenantId   | String | 是       | 所属资源组号              |
| dialMode   | String | 是       | 拨号模式:1预测式 ;2预览式 |

请求体示例

```
{

"tenantId": "10000",

"outboundId": "46",

"dialMode": "1"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

}
```

返回201示例：

```
{

"code": 201,

"message": "Please check your parameters"

}
```



## 8.7.群呼项目重置

请求方式：POST

请求url:

```
http://{url}/{version}/config/outboundInstanceReset
```

示例：

```
http://120.27.237.19:8098/5.0.x.20210203_release/config/outboundInstanceReset
```

请求频次限制：

**20次／分钟**

请求体

| 字段      | 类型   | 是否必须 | 备注                                |
|-----------|--------|----------|-------------------------------------|
| id        | String | 是       | 项目ID                              |
| resetType | String | 是       | 重置类型: 复位呼叫失败 复位所有号码 |
| actionID  | String | 是       | 唯一值,原样返回,找到对应的响应信息  |

请求体示例

```
{

"id": "10" ,

"resetType": "1" ,

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                               |
|----------|------------------------------------|
| code     | 响应码                             |
| message  | 响应信息                           |
| actionID | 唯一值,原样返回,找到对应的响应信息 |
| data     | 返回数据，JSON格式                 |

data：

<table>
  <tr>
    <td>id</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>name</td>
    <td>项目名称</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>创建人</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>外呼类型 1:预测式;2:预览式</td>
  </tr>
  <tr>
    <td>ratio</td>
    <td>速率</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态
      <br/>2：可执行
      <br/>3：执行中
      <br/>4：暂停中
      <br/>5：已结束</td>
  </tr>
  <tr>
    <td>contactNumber</td>
    <td>名单数</td>
  </tr>
  <tr>
    <td>callNum</td>
    <td>执行数</td>
  </tr>
  <tr>
    <td>touchNum</td>
    <td>应答数</td>
  </tr>
  <tr>
    <td>queueDn</td>
    <td>参与ACD</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"name":"xx",

"nameCn":"张三",

"callType":"1",

"ratio":"3",

"status":"3",

"contactNumber":"30",

"callNum":"20",

"touchNum":"10",

"queueDn":"10001_8000"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.8.群呼项目列表

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryOutboundInstances
```

示例：

```
http(s)://120.27.237.19:8098/5.0.x.20210203_release/query/queryOutboundInstances
```

请求体

<figure>
  <table>
    <thead>
      <tr>
        <th>字段</th>
        <th>类型</th>
        <th>是否必须</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>tenantId</td>
        <td>String</td>
        <td>是</td>
        <td>资源组编号：如10000</td>
      </tr>
      <tr>
        <td>name</td>
        <td>String</td>
        <td>否</td>
        <td>项目名称</td>
      </tr>
      <tr>
        <td>status</td>
        <td>String</td>
        <td>否</td>
        <td>项目状态
          <br/>2：可执行
          <br/>3：执行中
          <br/>4：暂停中
          <br/>5：已结束</td>
      </tr>
      <tr>
        <td>actionID</td>
        <td>String</td>
        <td>是</td>
        <td>唯一值,在响应信息中原样返回</td>
      </tr>
      <tr>
        <td>currentPage</td>
        <td>String</td>
        <td>是</td>
        <td>当前页</td>
      </tr>
      <tr>
        <td>pageSize</td>
        <td>String</td>
        <td>是</td>
        <td>页大小</td>
      </tr>
    </tbody>
  </table>
</figure>

请求体示例

```
{

"tenantId": "10000",

"name": "18565485486",

"status": "",

"currentPage": "1",

"pageSize": "10",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
  <tr>
    <td>id</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>name</td>
    <td>项目名称</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>创建人</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>外呼类型 1:预测式;2:预览式</td>
  </tr>
  <tr>
    <td>ratio</td>
    <td>速率</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态
      <br/>2：可执行
      <br/>3：执行中
      <br/>4：暂停中
      <br/>5：已结束</td>
  </tr>
  <tr>
    <td>contactNum</td>
    <td>名单数</td>
  </tr>
  <tr>
    <td>callNum</td>
    <td>执行数</td>
  </tr>
  <tr>
    <td>touchNum</td>
    <td>应答数</td>
  </tr>
  <tr>
    <td>queueDn</td>
    <td>参与ACD</td>
  </tr>
  <tr>
    <td>createTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>开始时间</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>结束时间</td>
  </tr>
  <tr>
    <td>idleTime</td>
    <td>二次呼叫间隔</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [

{

"id":"1",

"name":"xx",

"nameCn":"张三",

"callType":"1",

"ratio":"3",

"status":"3",

"contactNumber":"30",

"callNum":"20",

"touchNum":"10",

"queueDn":"10001_8000"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.9.群呼项目详情

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryOutboundInstance
```

示例：

```
http(s)://120.27.237.19:8098/5.0.x.20210203_release/query/queryOutboundInstance
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |
| id       | String | 是       | 项目ID                      |

请求体示例

```
{

"tenantId": "10000",

"id": "1",

"actionID": "abcd123"

}
```

返回值：

| 字段     | 含义                        |
|----------|-----------------------------|
| code     | 响应码                      |
| message  | 响应信息                    |
| actionID | 唯一值,在响应信息中原样返回 |
| data     | 返回数据，JSON格式          |

data:

<table>
  <tr>
    <td>id</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>name</td>
    <td>项目名称</td>
  </tr>
  <tr>
    <td>nameCn</td>
    <td>创建人</td>
  </tr>
  <tr>
    <td>callType</td>
    <td>外呼类型 1:预测式;2:预览式</td>
  </tr>
  <tr>
    <td>ratio</td>
    <td>速率</td>
  </tr>
  <tr>
    <td>status</td>
    <td>状态
      <br/>2：可执行
      <br/>3：执行中
      <br/>4：暂停中
      <br/>5：已结束</td>
  </tr>
  <tr>
    <td>contactNumber</td>
    <td>名单数</td>
  </tr>
  <tr>
    <td>callNum</td>
    <td>执行数</td>
  </tr>
  <tr>
    <td>touchNum</td>
    <td>应答数</td>
  </tr>
  <tr>
    <td>queueDn</td>
    <td>参与ACD</td>
  </tr>
  <tr>
    <td>createTime</td>
    <td>创建时间</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>开始时间</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>结束时间</td>
  </tr>
  <tr>
    <td>idleTime</td>
    <td>二次呼叫间隔</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"data":

{

"id":"1",

"name":"xx",

"nameCn":"张三",

"callType":"1",

"ratio":"3",

"status":"3",

"contactNumber":"30",

"callNum":"20",

"touchNum":"10",

"queueDn":"10001_8000"

}

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.10.群呼项目通话记录

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryOutboundContacts
```

示例：

```
http(s)://120.27.237.19:8098/5.0.x.20210203_release/query/queryOutboundContacts
```

请求体

<table>
  <tr>
    <th>字段</th>
    <th>类型</th>
    <th>是否必须</th>
    <th>备注</th>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>String</td>
    <td>是</td>
    <td>资源组编号：如10000</td>
  </tr>
  <tr>
    <td>outboundId</td>
    <td>String</td>
    <td>否</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>callState</td>
    <td>String</td>
    <td>否</td>
    <td>状态
      <br/>0:查看所有
      <br/>1:联系成功
      <br/>2:联系失败
      <br/>4:联系中
      <br/>5:坐席忙
      <br/>7:未联系</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>String</td>
    <td>否</td>
    <td>联络号码</td>
  </tr>
  <tr>
    <td>startTime</td>
    <td>String</td>
    <td>否</td>
    <td>开始时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>endTime</td>
    <td>String</td>
    <td>否</td>
    <td>结束时间：如2017-10-10 11:00:00</td>
  </tr>
  <tr>
    <td>actionID</td>
    <td>String</td>
    <td>是</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
  <tr>
    <td>currentPage</td>
    <td>String</td>
    <td>是</td>
    <td>当前页</td>
  </tr>
  <tr>
    <td>pageSize</td>
    <td>String</td>
    <td>是</td>
    <td>页大小</td>
  </tr>
  <tr>
    <td>extends</td>
    <td>String</td>
    <td>否</td>
    <td>扩展查询(格式:&quot;field1,字段值|field2,字段值|...&quot;)</td>
  </tr>
</table>

请求体示例

```
{

"tenantId": "10000",

"outboundId": "7",

"callState": "",

"currentPage": "1",

"pageSize": "10",

"extends":"field1,字段值\|field2,字段值\|..."

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
  <tr>
    <td>id</td>
    <td>明细ID</td>
  </tr>
  <tr>
    <td>tenantId</td>
    <td>资源组Id</td>
  </tr>
  <tr>
    <td>outboundId</td>
    <td>项目ID</td>
  </tr>
  <tr>
    <td>mobile</td>
    <td>联络号码</td>
  </tr>
  <tr>
    <td>exten</td>
    <td>坐席号</td>
  </tr>
  <tr>
    <td>queueDn</td>
    <td>ACD编号</td>
  </tr>
  <tr>
    <td>callState</td>
    <td>状态
      <br/>0:根据hangupCause判断;
      <br/>1:联系成功;
      <br/>5，7，8:坐席忙;
      <br/>9:未联系;</td>
  </tr>
  <tr>
    <td>hangupCause</td>
    <td>状态
      <br/>空：联系中
      <br/>其它：联系失败</td>
  </tr>
  <tr>
    <td>callId</td>
    <td>唯一值,在响应信息中原样返回</td>
  </tr>
  <tr>
    <td>callTime</td>
    <td>联络时间</td>
  </tr>
  <tr>
    <td>outboundInstanceName</td>
    <td>项目名称</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [

{

"id":"1",

"tenantId":"10001",

"outboundId":"1",

"mobile":"123456789",

"hangupCause":"41",

"exten":"10001_1001",

"queueDn":"10001_8000",

"callState":"1",

"callId":"sadxc4sdqwe1a54sd54a4d1",

"callTime":"2017-11-26 13:46:42",

"outboundInstanceName":"xxx"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.11.获取外拨设置参数

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryOutboundConfig
```

示例：

```
http(s)://120.27.237.19:8098/5.0.x.20210203_release/query/queryOutboundConfig
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>ratio</td>
    <td>默认速率</td>
  </tr>
  <tr>
    <td>maxRatio</td>
    <td>最大呼叫速率</td>
  </tr>
  <tr>
    <td>idleTime</td>
    <td>呼叫间隔 单位：毫秒</td>
  </tr>
  <tr>
    <td>hasVgc</td>
    <td>语音群呼权限 0无 1有</td>
  </tr>
  <tr>
    <td>ivrIdleTime</td>
    <td>语音呼叫间隔 单位：毫秒</td>
  </tr>
  <tr>
    <td>ivrRatio</td>
    <td>语音群呼速率 单位：毫秒</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [

{

"tenantId":"10001",

"ratio":"1",

"maxRatio":"3",

"idleTime":"16000",

"hasVgc":"0",

"ivrIdleTime":"15000",

"ivrRatio":"5"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```



## 8.12.查询号码批次

请求方式：POST

请求url:

```
http(s)://{url}/5.0.x.20210203_release/query/queryNumberBatch
```

示例：

```
http(s)://120.27.237.19:8098/5.0.x.20210203_release/query/queryNumberBatch
```

请求体

| 字段     | 类型   | 是否必须 | 备注                        |
|----------|--------|----------|-----------------------------|
| tenantId | String | 是       | 资源组编号：如10000         |
| actionID | String | 是       | 唯一值,在响应信息中原样返回 |

请求体示例

```
{

"tenantId": "10000",

"actionID": "abcd123"

}
```

返回值：

| 字段        | 含义                        |
|-------------|-----------------------------|
| code        | 响应码                      |
| message     | 响应信息                    |
| actionID    | 唯一值,在响应信息中原样返回 |
| data        | 返回数据，JSON格式          |
| currentPage | 当前页                      |
| totalCount  | 记录总数                    |

data:

<table>
  <tr>
    <td>tenantId</td>
    <td>资源组号</td>
  </tr>
  <tr>
    <td>id</td>
    <td>批次主键id</td>
  </tr>
  <tr>
    <td>numbers</td>
    <td>号码池</td>
  </tr>
  <tr>
    <td>strategy</td>
    <td>策略 1.顺序，2.轮转，3.使用频次</td>
  </tr>
  <tr>
    <td>batchName</td>
    <td>批次名称</td>
  </tr>
  <tr>
    <td>frequency</td>
    <td>使用频次：5,10,30,50</td>
  </tr>
</table>

code：

| 代码 | 含义           |
|------|----------------|
| 200  | 请求成功       |
| 201  | 请求体参数错误 |

返回200示例

```
{

"code": 200,

"message": "success!",

"actionID": "abcd123",

"currentPage": "abcd123",

"totalCount": "abcd123",

"data": [

{

"tenantId":"10001",

"ratio":"1",

"maxRatio":"3",

"idleTime":"16000",

"hasVgc":"0",

"ivrIdleTime":"15000",

"ivrRatio":"5"

}

]

}
```

返回201示例：

```
{

"code": 201,

"actionID": "abcd123",

"message": "Please check your parameters"

}
```


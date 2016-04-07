## 日志的相关操作

### 查看日志详情
URL: http://172.16.8.124:8089/JCenterHome/space.jsp?do=blog&id=45
> 参数: 
id: blogid
```json
{
    "id": 45,
    "hash": "e9f340285c56e485655abb39674c935e",
    "idtype": "blogid",
    "multi": "",
    "list": [   // 评论的List,当前显示为全部。前台处理显示5条，点击更多的时候显示全部。
        {
            "message": "guozi", //  评论内容
            "id": 45,           //  日志id
            "uid": 3,
            "magicflicker": 0,
            "author": "guozi",  // 评论者
            "idtype": "blogid", // id类型
            "authorid": 2,      // 评论者的id
            "dateline": 1459390817,  // 时间戳
            // 头像
            "avatar": "<img src=\"data/avatar/000/00/00/02_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "cid": 102,  // 评论的ID
            "ip": "127.0.0.1"
        }...
    ],
    "manageBlog": false,
    "blog": { // 日志详情
        "uid": 3,  //  用户ID
        "topicid": 0,
        "picflag": 0,
        "subject": "TST",  // 标题
        "dateline": 1459388511,  // 时间戳
        "password": "",
        "username": "dudy",    // 用户名
        "replynum": 3,         // 回复数
        "click_5": 0,
        "click_4": 0,
        "click_3": 0,
        "click_2": 0,
        "click_1": 0,
        "magicpaper": 0,
        "top": 1,            // 是否置顶: 2. 置顶，1. 取消置顶
        "classid": 3,        // 分类的ID
        "noreply": 0,        // 是否允许回复
        "magiccolor": 0,
        "viewnum": 1,        // 查看数
        "magiccall": 0,
        "blogid": 45,        // 
        "pic": "",
        "hotuser": "2",
        "message": "DDDDDDDTEST<div><br></div><div><br></div><div><br></div>", // 日志详情。
        "relatedtime": 1459388511,
        "hot": 1,
        "postip": "127.0.0.1",
        "target_ids": "",
        "friend": 1     // 
    },
    "cid": 0
}
```

### 日志发表
URL: http://172.16.8.124:8089/JCenterHome/cp.jsp?ac=blog&blogid=

参数:
```xml
	classid:0             // 分类ID
	subject:规定是否更多发  //  标题
	message:撒旦法是大法官撒旦法 // 内容
	friend:0                    //  权限： 0.  全部用户可见  1. 仅好友可见  3. 仅自己可见
	makefeed:1                 // 是否产生动态
	blogsubmit:true            // 提交验证
	//tag:多发 更多 定是 是否 规定  // 标签
	//password:                   
	//selectgroup:
	//target_names:
	//topicid:
	//  formhash:c110d5fd
	日志的权限和动态相对应的。
```
结果: 
```json
{
    "detailUrl": "space.jsp?uid=3&do=blog&id=53",  // 日志详情的连接请求
    "msg": "操作成功"                               // 信息。
}
```


### 日志删除
URL:　　http://172.16.8.124:8089/JCenterHome01/cp.jsp?ac=blog&blogid=44&op=delete
>参数:
blogid: 日志ID

>结果:  
msg:"1", 说明操作成功。 出错为具体的信息: "删除操作失败"

### 日志编辑
URL: http://172.16.8.124:8089/JCenterHome01/cp.jsp?ac=blog&blogid=53&op=edit 

参数:  blogid  日志的ID，其他默认。
```json
{
    "classarr": {  // 日志分类属性,改成Map形式，方便回显
    	"0": "默认分类",
        "3": "java",
        "5": "test"
    },
    "blogprivacy": true,
    "selectgroupstyle": "display:none",
    "allowhtml": 1,
    "blogid": 53,      //  日志ID
    "blog": { // 具体属性见上边内容
        "target_names": "",
        "uid": 3,
        "topicid": 0,
        "picflag": 0,
        "subject": "TESTButton",  // 
        "tag": "",
        "dateline": 1459412872,
        "password": "",
        "related": "",
        "username": "dudy",
        "replynum": 0,
        "click_5": 0,
        "click_4": 0,
        "click_3": 0,
        "click_2": 0,
        "click_1": 0,
        "magicpaper": 0,
        "top": 1,
        "classid": 0,
        "noreply": 0,
        "magiccolor": 0,
        "viewnum": 0,
        "magiccall": 0,
        "blogid": 53,
        "pic": "",
        "hotuser": "",
        "message": "TESTContent",
        "relatedtime": 0,
        "hot": 0,
        "postip": "127.0.0.1",
        "target_ids": "",
        "friend": 0
    },
    "friend": 0  // 参看上边内容。
}
```

### 日志置顶
URL: http://172.16.8.124:8089/JCenterHome/cp.jsp?ac=blog&blogid=53&op=edittop&top=2

参数:

	blogid: 日志的ID           
	top:    1. 取消置顶  2. 置顶  

结果: 
   
	msg:"1",  表示操作成功。 成功后再获取日志列表。  

### 日志搜索:

URL: http://172.16.8.124:8089/JCenterHome/space.jsp

参数：

	searchkey: TEST    搜索的内容   
	do:blog                         
	view:me            me: 我的  we: 好友的     
结果和 获取列表相同。   

### 好友中的日期搜索

URL: http://172.16.8.124:8089/JCenterHome/space.jsp?uid=3&do=blog&view=we&callback=fn    <br>
参数: 和 查询好友日志列表一样,只是添加 year 和 month 参数 , 分页相同

	year: 2016  当前年份
	month: 3    当前月份

结果: [参考好友日志列表](./blog.md.html)。

### 批量删除:
URL: http://172.16.8.124:8089/JCenterHome/cp.jsp?ac=blog&op=fetchDel    <br>
参数: 

	"blogIds":blogIds   blogIds为 字符串类型，表示要删除的IDS，中间用","隔开，例如: "31,32"

结果: 

	msg:"1",  表示操作成功。 成功后再获取日志列表。  
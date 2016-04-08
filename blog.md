## 日志：
### 日志列表:

#### 我的日志:  

返回全部的日志，前台分页。

URL:space.jsp?do=blog&view=me

```json
{
	// 分类信息，可以直接根据ID获取名字。
	 "classList": [   //  更新:   分类List    2016-4-8 16:03:33  
        {
            "uid": 3,
            "dateline": 1454483433,
            "count": 1,
            "classid": 5,
            "classname": "test"
        },
        {
            "uid": 3,
            "dateline": 1454483433,
            "count": 9,
            "classid": 3,
            "classname": "java"
        },
        {
            "uid": 3,
            "count": 11,
            "classname": "默认分类",
            "classid": 0
        }
    ],
    "actives": {
        "me": " class=\"active\""
    },
    "theurl": "space.jsp?uid=2&do=blog&view=me",
    "count": 3, // 总数
    "list": [
        {
            "noreply": 0,
            "uid": 2,
            "magiccolor": 0,
            "topicid": 0,
            "viewnum": 0,
            "picflag": 0,
            "subject": "测试1", // 标题
            "blogid": 43, // 日志ID
            "pic": "",
            "dateline": 1459305373, // 时间戳/1000
            "password": "",
            "message": "时间测试", // 日志内容
            "username": "guozi",   //  作者
            "replynum": 1,         //  回复数
            "click_5": 0,
            "hot": 1,
            "click_4": 0,
            "click_3": 0,
            "click_2": 0,
            "target_ids": "",
            "click_1": 0,
            "friend": 0,
            "top": 1,             //top 是否置顶,1 取消置顶，2 置顶
            "classid": 0      // 分类的ID 
        }
    ],
    "pricount": 0,
    "searchkey": ""
}
```
#### 好友日志
默认只显示10条记录,加载更多的时候在查询第二页的。

URL:space.jsp?do=blog&view=we&page=2

参数: page表示当前第几页。
```json
{
    "userlist": [   //好友列表
        {
            "uid": 2,
            "fusername": "dudy",
            "num": 12,
            "status": 1,
            "gid": 0,
            "dateline": 1458283102,
            "fuid": 3,
            "note": ""
        },
        {
            "uid": 2,
            "fusername": "admin",
            "num": 6,
            "status": 1,
            "gid": 0,
            "dateline": 1454569534,
            "fuid": 1,
            "note": "您好"
        }
    ],
    "actives": {
        "we": " class=\"active\""
    },
    "theurl": "space.jsp?uid=2&do=blog&view=we",
    "count": 16, // 总数,当前没用。
    "list": [
        {
            "noreply": 0,
            "uid": 3,
            "magiccolor": 0,
            "topicid": 0,
            "viewnum": 0,
            "picflag": 0,
            "subject": "123423",
            "blogid": 21,
            "pic": "",
            "dateline": 2018365485,
            "password": "",
            "message": "12342134234 --------------- test",
            "username": "dudy",
            "replynum": 0,
            "click_5": 0,
            "hot": 0,
            "click_4": 0,
            "click_3": 0,
            "click_2": 0,
            "target_ids": "",
            "click_1": 0,
            "friend": 0,
            "top": 1,
            "classid": 0
        }...
        
    ],
    "pricount": 0, 
    "searchkey": ""
}
```
### 日志分类:
#### 分类列表: 
都有一个默认分类: classid = 0

URL: cp.jsp?ac=class
```json
{
	"dafaultCount":0, //    class0: 默认分类下日志的数量          2016-3-31 16:02:39 更新，新增默认分类的数量
    "list": [
        {
            "uid": 3, //用户的ID 
            "dateline": 1454483433, // 时间
            "count": 0,    // 当前分类下日志的数量
            "classid": 5, // 分类的ID
            "classname": "test" // 分类的名字
        }...
    ]
}
```
#### 分类操作:
全局:
返回结果: msg:"1", 如果msg等于"1"，说明操作成功。错误，msg为具体的出错信息。

* 修改：
> URL: cp.jsp?ac=class&op=edit&classid=6&classname=edit"
参数:
	ac=class   固定              <br>
	op=edit    固定              <br>
	classid    分类的ID         <br>
	classname  分类的名字      <br>
结果:     <br>
	①msg："当前名字已存在。  

* 删除:
> URL: cp.jsp?ac=class&op=delete&classid=6            <br>
参数: classid                                       <br>
结果: 														 <br>
	①msg："当前分类下含有日志，不能删除"。 <br>

* 新增:
> URL: cp.jsp?ac=class&op=add&classname=TEST <br>
参数: classname  							 <br>
结果:           						     <br>
	①msg："当前名字已存在"。                 <br>
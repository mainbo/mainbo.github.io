## 通讯录

### 好友列表
URL: http://172.16.8.124:8089/JCenterHome/space.jsp?do=friend
```json
{
    "viewnum": 25,
    "fgroups": [ // 好友分组
        {
            "uid": 3, // 用户id
            "gname": "TEST", // 分组名
            "gid": 1       // 分组id
        }
    ],
    "list": [  // 好友列表
        {
            "uid": 2,  // 好友id
            "sex": 0,  // 性别 
            "gname": "TEST",  //分组名 
            "avatar": "<img src=\"data/avatar/000/00/00/02_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "isfriend": true,
            "username": "guozi",  // 登录名
            "num": 25,
            "name": "",  // 用户名
            "gid": 1, // 分组id
            "credit": 252, // 积分
        }...
        
    ],
    "todayviewnum": 0  //  今日浏览数
}
```

## 好友分组操作

### 新增分组
	URL:cp.jsp?ac=friendgroup&op=add&gname=TEST1
	参数: 
		gname :  分组名  

### 修改分组
	URL: cp.jsp?ac=friendgroup&op=update&gname=UPDATE&gid=4
	参数: 
		gname: 修改的分组名
		gid: 分组ID

### 删除分组
如果当前分组下有好友，就将好友移动到默认分组（我的好友） 中

	URL:  cp.jsp?ac=friendgroup&op=delete&gid=1
	参数: 
		gid: 分组的ID

### 更改好友到分组
	URL: cp.jsp?ac=friendgroup&op=move&gid=4&fuid=2
	参数: 
		gid: 目标分组ID
		fuid: 好友ID

## 好友操作 
### 好友申请列表：

URL: cp.jsp?ac=friend&op=request  必须使用 post请求
```json
{
    "uid": 0,
    "op": "request",
    "count": 1, // 好友申请的数量 
    "list": [ // list 列表
        {
            "cfriend": "",
            "uid": 14, // 用户的ID
            "eventinvitenum": 0,
            "updatetime": 1459394229,
            "doingnum": 0,
            "advgiftcount": 0,
            "addfriendnum": 0,
            "dateline": 1459927300,
            "attachsize": 0,
            "giftnum": 0,
            "username": "TEST09", // 用户名
            "regip": "127.0.0.1",
            "todayviewnum": 0,
            // 头像
            "avatar": "<img src=\"data/avatar/000/00/00/14_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "lastsend": 0,
            "myinvitenum": 0,
            "ip": 127000000,
            "flag": 0,
            "newpm": 0,
            "fuid": 3,
            "threadnum": 0,
            "friend": "",
            "notenum": 0
        }
    ]
}
```	
### 好友申请:
	URL: cp.jsp?ac=friend&op=add&uid=5
	参数:
		addsubmit:true
		uid: 对方的ID
		gid:0
	结果: 
		msg:"1" ,请求已发送，正在等待对方验证中 
	注: 没同意的情况下再次发送申请，消息一致。
### 同意: 
    URL: cp.jsp?ac=friend&op=add&uid=5
    参数:
    	uid:5  对方的ID
    	gid:0   
		add2submit:true
	结果: 
		msg:"1", 表示添加成功。

### 忽略:
	URL: cp.jsp?ac=friend&op=ignore&uid=3 
	参数: 
		uid: 对方的ID
	结果: 
		msg:"1", 表示操作成功。
### 忽略消息删除：
	URL: cp.jsp?ac=friend&op=delete&uid=2&confirm=1
	参数：
		friendsubmit:true
		uid: 对方的ID
	结果: 
		msg:"1", 表示操作成功。
### 搜索: 
#### 在好友中搜索, 目前还没有班级
	URL: space.jsp?do=friend&searchkey=ddy&searchsubmit=%E6%89%BE%E5%A5%BD%E5%8F%8B&searchmode=1
	参数: 
		searchkey:  搜索的关键字 比如: ddy, 支持模糊搜索
		searchsubmit: 找好友
		searchmode:  1
结果: 
```json
{
    "viewnum": 26,
    "fgroups": [
        {
            "uid": 3,
            "gname": "UPDATE",
            "gid": 4
        }
    ],
    "list": [ // 好友列表list
        {
            "uid": 4,
            "num": 1,
            "username": "ddy",
            "sex": 1,
            "name": "",
            "gname": "我的好友",
            "gid": 0,
            "avatar": "<img src=\"data/avatar/000/00/00/04_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "credit": 142
        }
    ],
    "todayviewnum": 0
}
```
#### 搜索好友:
	URL: cp.jsp?searchsubmit=查找&ac=friend&op=search&type=all
	     cp.jsp?searchsubmit=查找&ac=friend&op=search&type=all&name=d
	参数: 
		searchkey=             名字  支持模糊查询
		sex=1                  男女: 1. 男  2. 女
		resideprovince=        省
		residecity=            市
		endAge= 16             年龄
结果：
```json
{
    "uid": 0,
    "op": "search",
    "list": [ // 结果列表
        {
            "uid": 4,
            "username": "ddy",
            "name": "",
            "namestatus": 1,
            "avatar": "<img src=\"data/avatar/000/00/00/04_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "credit": 142,
            "isfriend": true
        },
        {
            "uid": 5,
            "username": "ddy01",
            "name": "",
            "namestatus": 0,
            "avatar": "<img src=\"data/avatar/000/00/00/05_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "credit": 135,
            "isfriend": true
        }
    ]
}
```
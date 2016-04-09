## 个人资料

### 登录信息
URL: space.jsp?do=userinfo
```json
{
    "avatar": "<img src=\"http://img4.tiboo.cn/1005/363663_127503877648.jpg\" alt=\"\">",
    "space": {
        "uid": 3,
        "eventinvitenum": 0,
        "resideprovince": "重庆",
        "updatetime": 1460088111,
        "advgiftcount": 0,
        "addfriendnum": 0,
        "dateline": 1456211975,
        "spacenote": "asdf<img src=\"image/face/1.gif\" class=\"face\">",
        "attachsize": 158798,
        "menunum": 0,
        "timeoffset": "",
        "username": "dudy",
        "friends": [
            "5",
            "4",
            "2",
            "14",
            "10"
        ],
        "albumnum": 2,
        "videostatus": 0,
        "birthprovince": "重庆",
        "namestatus": 1,
        "groupid": 1,
        "addsize": 0,
        "credit": 21969,
        "msnrobot": "",
        "marry": 1,
        "sendmail": "",
        "lastsearch": 0,
        "mtaginvitenum": 0,
        "msn": "1234567890",
        "pollnum": 0,
        "msncstatus": 0,
        "mood": 1,
        "lastlogin": 1460167099,
        "lastpost": 1460088111,
        "privacy": {
            "feed": {
                "invite": 1,
                "post": 1,
                "task": 1,
                "click": 1,
                "show": 1,
                "join": 1,
                "blog": 1,
                "upload": 1,
                "share": 1,
                "poll": 1,
                "event": 1,
                "thread": 1,
                "mtag": 1,
                "doing": 1,
                "joinpoll": 1,
                "credit": 1,
                "comment": 1,
                "friend": 1,
                "profile": 1
            },
            "view": {
                "gift": 0,
                "share": 0,
                "index": 0,
                "poll": 0,
                "event": 0,
                "album": 0,
                "mtag": 0,
                "doing": 0,
                "feed": 0,
                "blog": 0,
                "wall": 0,
                "friend": 0
            }
        },
        "newemail": "",
        "friendnum": 5,
        "todayviewnum": 0,
        "blood": "A",
        "avatar": 0,
        "lastsend": 0,
        "flag": 0,
        "authstr": "1457403558\t1\t3pq7rB",
        "magicstar": 0,
        "email": "1796244932@qq.com",
        "newpm": 0,
        "friend": "5,4,2,14,10",
        "css": "",
        "notenum": 2,
        "mobile": "1234567890",
        "allnotenum": 2,
        "nocss": 0,
        "birthday": 1,
        "birthmonth": 1,
        "residecity": "大渡口",
        "sex": 1,
        "doingnum": 6,
        "birthcity": "涪陵",
        "magicexpire": 0,
        "self": true,
        "emailcheck": 0,
        "giftnum": 0,
        "regip": "unknown",
        "feedfriend": "5,4,2,14,10",
        "eventnum": 1,
        "name": "dudy",
        "domain": "",
        "experience": 1709,
        "sharenum": 0,
        "note": "asdf<img src=\"image/face/1.gif\" class=\"face\">",
        "qq": "1234567890",
        "viewnum": 26,
        "blognum": 21,
        "theme": "t13",
        "pokenum": 0,
        "showgiftlink": 0,
        "addfriend": 0,
        "myinvitenum": 0,
        "ip": 127000000,
        "birthyear": 1992,
        "videopic": "",
        "threadnum": 1
    }
}
```

### 个人资料
获取基本信息: 
URL： cp.jsp?ac=profile 
```json
{   // 教育工作信息
    "workEdu": [
        {
            "uid": 3,
            "infoid": 19,
            "title": "清华",
            "startyear": 2016,
            "subtype": "",
            "endyear": 0,
            "subtitle": "文学院",
            "startmonth": 0,
            "endmonth": 0,
            "type": "edu",  //  type: edu 教育 ,  work : 工作 
            "friend": 0
        },
        {
            "uid": 3,
            "infoid": 20,
            "title": "mainbo",
            "startyear": 2016,
            "subtype": "",
            "endyear": 0,
            "subtitle": "平台应用",
            "startmonth": 1,
            "endmonth": 0,
            "type": "work",
            "friend": 0
        }
    ],
    "info": {
        "birthyear": 1992,
        "uid": 3,
        "resideprovince": "重庆",
        "birthday": 1,
        "birthmonth": 1,
        "residecity": "大渡口",
        "sex": 1,
        "username": "dudy",
        "email": "1796244932@qq.com",
        "name": "dudy",
        "blood": "A",
        "qq": "1234567890",
        "mobile": "1234567890"
    }
}
```

### 修改基本信息
URL:cp.jsp?ac=profile&op=save
参数: 
```json
var params = {  "uid": 13,
		        "resideprovince": "重庆",
		        "birthday": 1,
		        "birthmonth": 1,
		        "residecity": "大渡口",
		        "sex": 1,
		        "eEndmonth": 0,
		        "department": "平台应用",
		        "username": "dudy",
		        "name": "dudy",
		        "qq": "1234567890",
		        "classes": "文学院",
		        "wEndmonth": 0,
		        "blood": "A",
		        "birthyear": 1992,
		        "eEndyear": 0,
		        "school": "清华",
		        "email": "1796244932@qq.com",
		        "company": "mainbo",
		        "mobile": "1234567890",
		        "wEndyear": 0};
```

### 密码修改

URL: cp.jsp
参数:

	ac:password
	op:
	username:dudy     用户名
	password:123456   原密码  
	newpasswd1:123456 新密码
	newpasswd2:123456 确认密码
	pwdsubmit:true
结果: 

	msg:  1    // 修改成功
	      两次输入的密码不一致
	      密码空或包含非法字符，请重新填写
	      您没有输入旧密码或旧密码错误，请返回重新填写。
	      异常信息
### 修改头像
URL: cp.jsp?ac=avatar



确定： 
URL: avatar.jsp?a=rectavatar&appid=0&uid=3&hash=fbe0c3a2aa04e1b791632ec7b45a8d73&agent=df5efccb8f31c951989ef6315666dc29&avatartype=virtual&randomnumber=7029


预览:
URL : avatar.jsp?a=uploadavatar&appid=0&uid=3&hash=fbe0c3a2aa04e1b791632ec7b45a8d73&agent=df5efccb8f31c951989ef6315666dc29&avatartype=virtual
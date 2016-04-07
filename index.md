---
title: 首页数据
---

## 首页:

动态信息 URL: http://172.16.8.129:8089/JCenterHome/space.jsp?do=feed&view=we&callback=fn&start=0

图书    URL: http://172.16.8.129:8089/JCenterHome/space.jsp?uid=3&do=library&callback=fn


应用  URL:  http://172.16.8.129:8089/JCenterHome/space.jsp?do=appCenter

注释: 
好友动态中将请求地址改下就可以。
我的动态: 将 view=we 改为 view=me
全部动态: 将 view=we 去掉或者改为 all

动态一次性加载 perNum = 10条, start 为 0 + perNum ，0为第一页，下一页的话就是 start = 10

```JAVA
{
    "hiddenfeed_list": { }, 
    "filter_list": [ ], 
    "count": 3, 
    "hiddenfeed_num": { }, 
    "list": { // 动态列表
        "today": [
            {
                "uid": 3, 
                "icon_image": "image/icon/blog.gif", 
                //动态id类型 blogid: 日志
                "idtype": "blogid", 
                "image_3": "", 
                "appid": 0, 
                "image_2": "", 
                "image_1": "http://172.16.8.129:8089/BJCenterHome/ueditor/jsp/upload/image/20160315/1458018129357061040.png", 
                "dateline": 2024552495, 
                "image_1_link": "space.jsp?uid=3&do=blog&id=32", 
                "id": 32, // 日志的id
                "showmanage": 1, 
                // 用户名
                "username": "dudy", 
                "image_2_link": "", 
                "style": "", 
                "image_4": "", 
                "body_template": "<b><a target=\"_blank\"   href=\"space.jsp?uid=3&do=blog&id=32\" >qewrwerqwer</a></b><br>1.1 JVM  1.1.1. Java内存模型，Java内存管理，Java堆和栈，垃圾回收    http://www.jcp.org/en/jsr/detail?id=133    http://ifeve.com/jmm-faq/    1.1.2. 了", 
				// 标题
                "title_template": "<a target=\"_blank\"   href=\"space.jsp?uid=3\" >dudy</a> 发表了新日志", 
                "hash_template": "2c24ba00fafd81b79f331389e04a26cb", 
                "icon": "blog", 
                "image_3_link": "", 
                "thisapp": 1, 
                "image_4_link": "", 
                 // 当前动态用户的头像
                "avatar": "<img src=\"data/avatar/000/00/00/03_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
                "feedid": 79, // 动态ID
                "body_general": "", 
                "target": " target=\"_blank\"", 
                "hash_data": "4215d72e0eed8050f077bfd6c7ccd704", 
                "hot": 1, 
                "body_data": {
                    "summary": "1.1 JVM  1.1.1. Java内存模型，Java内存管理，Java堆和栈，垃圾回收    http://www.jcp.org/en/jsr/detail?id=133    http://ifeve.com/jmm-faq/    1.1.2. 了", 
                    "subject": "<a href=\"space.jsp?uid=3&do=blog&id=32\">qewrwerqwer</a>"
                }, 
                // 当前动态下的评论，数据形式
                "comment": [
                    {
	                    //内容
                        "message": "<div class=\"quote\"><span class=\"q\"><b>guozi</b>: 水电费</span></div>回复？？？",
                        "id": 32, // 日志id, 
                        "uid": 3, // 用户id
                        "magicflicker": 0,
                        "author": "dudy", // 作者（谁回复的）
                        "idtype": "blogid", // id类型（目前只有blogid:日志）
                        "authorid": 3,  //回复的id 
                        "dateline": 1459129428, // 时间
                        "cid": 70, // 评论id
                        "ip": "127.0.0.1"
                    },
                    {
                        "message": "<div class=\"quote\"><span class=\"q\"><b>dudy</b>: <img src=\"image/face/1.gif\" class=\"face\"></span></div>我去》》》》》",
                        "id": 32,
                        "uid": 3,
                        "magicflicker": 0,
                        "author": "guozi",
                        "idtype": "blogid",
                        "authorid": 2,
                        "dateline": 1459146753,
                        "cid": 72,
                        "ip": "127.0.0.1"
                    },
                    {
                        "message": "ddddd",
                        "id": 32,
                        "uid": 3,
                        "magicflicker": 0,
                        "author": "dudy",
                        "idtype": "blogid",
                        "authorid": 3,
                        "dateline": 1459156360,
                        "cid": 73,
                        "ip": "127.0.0.1"
                    },
                    {
                        "message": "<div class=\"quote\"><span class=\"q\"><b>guozi</b>: 我去》》》》》</span></div>qqqqqqqqqqqqqqqq",
                        "id": 32,
                        "uid": 3,
                        "magicflicker": 0,
                        "author": "dudy",
                        "idtype": "blogid",
                        "authorid": 3,
                        "dateline": 1459156511,
                        "cid": 74,
                        "ip": "127.0.0.1"
                    },
                    {
                        "message": "评论TEST",
                        "id": 32,
                        "uid": 3,
                        "magicflicker": 0,
                        "author": "dudy",
                        "idtype": "blogid",
                        "authorid": 3,
                        "dateline": 1459159592,
                        "cid": 76,
                        "ip": "127.0.0.1"
                    },
                    {
                        "message": "的点点滴滴",
                        "id": 32,
                        "uid": 3,
                        "magicflicker": 0,
                        "author": "dudy",
                        "idtype": "blogid",
                        "authorid": 3,
                        "dateline": 1459217870,
                        "cid": 81,
                        "ip": "127.0.0.1"
                    },
                    {
                        "message": "<div class=\"quote\"><span class=\"q\"><b>dudy</b>: 的点点滴滴</span></div>去去去去去去去去去去去去去去去去",
                        "id": 32,
                        "uid": 3,
                        "magicflicker": 0,
                        "author": "guozi",
                        "idtype": "blogid",
                        "authorid": 2,
                        "dateline": 1459222875,
                        "cid": 83,
                        "ip": "127.0.0.1"
                    }
                ]，
                "target_ids": "", 
                "friend": 0, 
                "magic_class": ""
            }, 
            {
                "uid": 3, 
                "icon_image": "image/icon/doing.gif", 
                "idtype": "doid", 
                "image_3": "", 
                "appid": 0, 
                "image_2": "", 
                "image_1": "", 
                "dateline": 1458898241, 
                "image_1_link": "", 
                "id": 15, 
                "username": "dudy", 
                "image_2_link": "", 
                "style": "", 
                "image_4": "", 
                "body_template": "", 
                "title_template": "<a target=\"_blank\"   href=\"space.jsp?uid=3\" >dudy</a>：asdf<img src=\"image/face/1.gif\" class=\"face\">", 
                "hash_template": "7405fddb51d86fcb3dce6bfa66d591b3", 
                "icon": "doing", 
                "image_3_link": "", 
                "thisapp": 1, 
                "title_data": {
                    "message": "asdf<img src=\"image/face/1.gif\" class=\"face\">"
                }, 
                "image_4_link": "", 
                "avatar": "<img src=\"data/avatar/000/00/00/03_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">", 
                "feedid": 93, 
                "body_general": "", 
                "target": " target=\"_blank\"", 
                "hash_data": "109f2f087444c1e74efff174aae9f2b6", 
                "hot": 0, 
                "body_data": { }, 
                "target_ids": "", 
                "friend": 0, 
                "magic_class": ""
            }, 
            {
                "uid": 3, 
                "icon_image": "image/icon/doing.gif", 
                "idtype": "doid", 
                "image_3": "", 
                "appid": 0, 
                "image_2": "", 
                "image_1": "", 
                "dateline": 1458898238, 
                "image_1_link": "", 
                "id": 14, 
                "username": "dudy", 
                "image_2_link": "", 
                "style": "", 
                "image_4": "", 
                "body_template": "", 
                "title_template": "<a target=\"_blank\"   href=\"space.jsp?uid=3\" >dudy</a>：<img src=\"image/face/1.gif\" class=\"face\">", 
                "hash_template": "7405fddb51d86fcb3dce6bfa66d591b3", 
                "icon": "doing", 
                "image_3_link": "", 
                "thisapp": 1, 
                "title_data": {
                    "message": "<img src=\"image/face/1.gif\" class=\"face\">"
                }, 
                "image_4_link": "", 
                "avatar": "<img src=\"data/avatar/000/00/00/03_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">", 
                "feedid": 92, 
                "body_general": "", 
                "target": " target=\"_blank\"", 
                "hash_data": "9ffc316766c87d4685ad188e2b217190", 
                "hot": 0, 
                "body_data": { }, 
                "target_ids": "", 
                "friend": 0, 
                "magic_class": ""
            }
        ]
    }, 
    // 个人中心信息
    "space": {
        "uid": 3, //用户ID
        "eventinvitenum": 0, 
        "resideprovince": "重庆", // 居住地
        "updatetime": 1458898241, 
        "advgiftcount": 0, 
        "addfriendnum": 0, 
        "dateline": 1456211975, 
        "spacenote": "asdf<img src=\"image/face/1.gif\" class=\"face\">", 
        "attachsize": 158798, 
        "menunum": 0, 
        "timeoffset": "", 
        "username": "dudy", // 用户名
        "friends": [ // 
            "5", 
            "2", 
            "4"
        ], 
        "albumnum": 2, // 相册数
        "videostatus": 0, 
        "birthprovince": "重庆", // 出生地
        "namestatus": 1, 
        "groupid": 1, 
        "addsize": 0, 
        "credit": 21770, 
        "msnrobot": "", 
        "marry": 1, 
        "sendmail": "", 
        "lastsearch": 0, 
        "mtaginvitenum": 0, 
        "msn": "1234567890", 
        "pollnum": 0, 
        "msncstatus": 0, 
        "mood": 1, 
        "lastlogin": 1458898169, 
        "lastpost": 1458898241, 
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
        // 
        "friendnum": 3, //好友数
        "todayviewnum": 0, // 今日浏览数
        "blood": "A", 
        "avatar": 1, 
        "lastsend": 0, 
        "filter_icon": [ ], 
        "flag": 0, 
        "authstr": "1457403558	1	3pq7rB", 
        "magicstar": 0, 
        "email": "1796244932@qq.com", 
        "newpm": 0, 
        "friend": "5,2,4", 
        "css": "", 
        "notenum": 0, 
        "mobile": "1234567890", 
        "allnotenum": 0, 
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
        "feedfriend": "5,2,4", 
        "eventnum": 1, 
        "name": "dudy", 
        "domain": "", 
        "experience": 1514, 
        "sharenum": 0, 
        "note": "asdf<img src=\"image/face/1.gif\" class=\"face\">", 
        "qq": "1234567890", 
        "viewnum": 23, // 访客数
        "blognum": 11, // 日志数
        "theme": "t13", 
        "pokenum": 0, 
        "showgiftlink": 0, 
        "addfriend": 0, 
        "myinvitenum": 0, 
        "ip": 172016008, 
        "birthyear": 2016, 
        "videopic": "", 
        "threadnum": 1
    }, 
    // 头像地址
    "avatar": "<img src=\"data/avatar/000/00/00/03_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">", 
    "perpage": 10, 
    "navtitle": "", 
    "actives": {
        "all": " class=\"active\""
    }, 
    "start": 0, 
    "feedIcon_actives": {
        "all": " class=\"current\""
    }, 
    "TPL": { }, 
    "isnewer": true, 
    "filtercount": 0
}
```


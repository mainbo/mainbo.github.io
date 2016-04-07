---
title: 动态页面
---

可能敢兴趣的人:

查找的是当前好友的好友。

URL: cp.jsp?ac=friend&op=find
```json
{
    "uid": 0,
    "op": "find",
    "onLineList": [],
    "friendList": [// 可能认识的人列表
        {	// 头像
            "avatar": "<img src=\"data/avatar/000/00/00/01_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "uid": 1, // 用户ID
            "username": "admin" // 用户名
        }
    ]
}
```
最近访客:

URL: space.jsp?do=friend&view=visitor&callback=fn
```java
{
	// 总的访问量
    "viewnum": 23,
    "count": 3,
    "actives": {
        "me": " class=\"active\""
    },
    "multi": "",
    "list": [
        {
	        // 用户ID
            "uid": 2,
            "resideprovince": "",
            "sex": 0,
            "residecity": "",
            "c": "",
            "dateline": 1458790435,
            "spacenote": "<img src=\"image/face/1.gif\" class=\"face\">",
            // 头像
            "avatar": "<img src=\"data/avatar/000/00/00/02_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "isfriend": true,
            "username": "guozi",// 用户名
            "p": "",
            "gColor": "",
            "note": "",
            "gIcon": ""
        },
        {
            "uid": 5,
            "resideprovince": "",
            "sex": 0,
            "residecity": "",
            "c": "",
            "dateline": 1457575393,
            "spacenote": "ddy01",
            "avatar": "<img src=\"data/avatar/000/00/00/05_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "isfriend": true,
            "username": "ddy01",
            "p": "",
            "gColor": "",
            "note": "ddy01",
            "gIcon": ""
        },
        {
            "uid": 4,
            "resideprovince": "",
            "sex": 1,
            "residecity": "",
            "c": "",
            "dateline": 1457575329,
            "spacenote": "1",
            "avatar": "<img src=\"data/avatar/000/00/00/04_avatar_middle.jpg\" onerror=\"this.onerror=null;this.src='data/avatar/noavatar_middle.gif'\">",
            "isfriend": true,
            "username": "ddy",
            "p": "",
            "gColor": "",
            "note": "1",
            "gIcon": ""
        }
    ],
    "a_actives": {
        "visitor": " class=\"current\""
    },
    // 今日访客
    "todayviewnum": 0
}
```
动态信息和首页的请求一样。

评论的操作列表如下:

<table>
	<tr>
		<th>操作</th>
		<th>URL</th>
		<th>参数</th>
	</tr>
	<tr>
		<td>动态评论：</td>
		<td>cp.jsp?ac=feed&feedid=? </td>
		<td> 
		feedid:              当前的动态的ID <br>
		message:             评论的信息     <br>
		commentsubmit:true   验证: 大于2个字符       <br>
		<br> 
		</td>
	</tr>
	<tr>
		<td>回复:</td>
		<td>cp.jsp?ac=comment</td>
		<td> 
		message: 评论的内容(后台拼串)，前台传递也行。    <br> 
		id:32             日志的id                  <br>
		idtype:blogid     id类型                    <br>
		cid:72            评论的id                  <br>
		commentsubmit:true   评论提交验证通过        <br>
		</td>
	</tr>
	
	<tr>
		<td>删除:</td>
		<td>cp.jsp?ac=comment&op=delete&cid=77&inajax=1  </td>
		<td>cid  当前评论的id。</td>
	</tr>

	
</table>



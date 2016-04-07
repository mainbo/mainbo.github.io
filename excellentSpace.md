## 优秀空间推荐

站点:http://172.16.8.129:8089/JCenterHome/ 中心平台配置。

URL: space.jsp?do=excellentSpace

```json
{
    "defalut": "data/avatar/noavatar_middle.gif", // 默认头像
    // 家长
    "parents": [
        {
            "center": "/center.jsp?uid=1",
            "uid": 1,
            "username": "admin",
            "school": "中心小学",
            "avatar": "/data/avatar/000/00/00/01_real_avatar_middle.jpg"
        }...
    ],
    // 学生
    "students": [
       {
            "center": "/center.jsp?uid=1", //  个人中心连接
            "uid": 1,                      // 用户id
            "username": "admin",           // 用户名
            "school": "中心小学",           // 学校
            "avatar": "/data/avatar/000/00/00/01_real_avatar_middle.jpg"  // 头像
        }...
    ],
    // 老师
    "teachers": [
        {
            "center": "/center.jsp?uid=1",
            "uid": 1,
            "username": "admin",
            "school": "中心小学",
            "avatar": "/data/avatar/000/00/00/01_real_avatar_middle.jpg"
        }...
    ]
}
```
## 注意：
头像链接：
```html
<img src="/data/avatar/000/00/00/01_real_avatar_middle.jpg" onerror="this.onerror=null;this.src='data/avatar/noavatar_big.gif'" style="width: 183px;">
```
需要自己拼接以上字符串。(目前不知道正确不正确)
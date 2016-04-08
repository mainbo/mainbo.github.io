## 个人资料

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
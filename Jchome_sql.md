## 用户这块的数据表
数据库: jchome
统一前缀: jchome
### member : 用户
添加如下字段:
```sql
`guid` varchar(32) DEFAULT NULL COMMENT '用来存储从平台同步过来唯一身份标示',
`user_type` mediumint(8) unsigned NOT NULL DEFAULT '3' COMMENT '用户类型',
`user_type_name` varchar(32) NOT NULL COMMENT '用户类型名',
```
300          学校管理员    ；
200          教育局管理员  ；
0            教育局职工    ；
2            老师（班主任）；
3            学生          ；
1            学校职工      ；
4            校长          ；
(?)			 家长          ；

### appclass: 班级
```sql
CREATE TABLE `jchome_appclass` (
  `id` int(10) NOT NULL AUTO_INCREMENT COMMENT '班级内部ID',
  `class_id` varchar(32) NOT NULL COMMENT '班级 外部ID',
  `class_name` varchar(64) NOT NULL COMMENT '班级名称',
  `class_memo` text COMMENT '班级简介',
  `s_state` tinyint(3) unsigned NOT NULL DEFAULT '0' COMMENT '班级状态',
  `s_creator_id` bigint(20) unsigned NOT NULL COMMENT '创建者ID',
  `create_time` datetime DEFAULT NULL COMMENT '创建时间',
  `s_creator` varchar(30) DEFAULT NULL COMMENT '创建者姓名',
  `class_org` mediumint(9) NOT NULL COMMENT '班级所在机构',
  `class_org_name` varchar(64) NOT NULL COMMENT '班级所在机构名称',
  `class_members` smallint(6) NOT NULL COMMENT '成员数',
  `available_capacity` bigint(20) DEFAULT NULL COMMENT '班级空间可用容量（字节）',
  `capacity` bigint(20) DEFAULT NULL COMMENT '班级空间总容量（字节）',
  `pic_url` varchar(255) DEFAULT NULL COMMENT '班级头像',
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=333 DEFAULT CHARSET=utf8 COMMENT='班级';
```
### appclass_member  用户班级关联表
```
CREATE TABLE `jchome_appclass_member` (
  `class_id` mediumint(8) NOT NULL COMMENT '班级主键',
  `class_name` varchar(64) NOT NULL COMMENT '班级名称',
  `user_id` int(11) NOT NULL,
  `user_name` varchar(64) NOT NULL,
  `user_type` tinyint(4) NOT NULL,
  `user_type_name` varchar(64) NOT NULL,
  `class_admin` tinyint(1) NOT NULL,
  KEY `classIndex` (`class_id`,`user_type`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='班级成员关联表';
```
### 机构表  organization
```
CREATE TABLE `jchome_organization` (
  `org_id` mediumint(8) unsigned NOT NULL AUTO_INCREMENT COMMENT '主键',
  `org_code` varchar(10) DEFAULT NULL COMMENT '机构码',
  `parent_id` mediumint(8) unsigned NOT NULL COMMENT '父节点',
  `org_name` varchar(64) NOT NULL COMMENT '机构名称',
  `area_ids` varchar(128) DEFAULT NULL COMMENT '区域ID（1_2_2）',
  `area_names` varchar(256) DEFAULT NULL,
  `org_address` varchar(64) DEFAULT NULL COMMENT '地址',
  `contact_person` varchar(64) DEFAULT NULL COMMENT '联系人',
  `phone_number` varchar(64) DEFAULT NULL COMMENT '联系电话',
  `org_level` tinyint(3) unsigned NOT NULL COMMENT '机构级别',
  `org_level_name` varchar(128) DEFAULT NULL COMMENT '机构级别名称',
  `org_order` smallint(5) unsigned NOT NULL COMMENT '排序',
  `class_capacity` bigint(20) NOT NULL COMMENT '班级容量',
  `upload_max` bigint(20) NOT NULL COMMENT '单个文件上传最大size',
  `tree_level` tinyint(3) unsigned NOT NULL COMMENT '机构树的层级（从1开始）',
  `pic_url` varchar(255) DEFAULT NULL COMMENT '图片路径',
  PRIMARY KEY (`org_id`)
) ENGINE=InnoDB AUTO_INCREMENT=26227 DEFAULT CHARSET=utf8 COMMENT='机构';
```
### 机构和用户关联表 organization_member
参考班级和用户关联表
### sys_area 系统区域表  用户同步可能需要，一期当前业务用不到。
### space_appclass 班级空间表: 存放班级的一些信息。
```sql
CREATE TABLE `jchome_space_appclass` (
  `cid` mediumint(8) unsigned NOT NULL DEFAULT '0' COMMENT '班级ID',
  `classname` char(15) NOT NULL DEFAULT '' COMMENT '班级名称',
  `viewnum` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '总访客数',
  `todayviewnum` int(10) NOT NULL DEFAULT '0' COMMENT '今日访客',
  `albumnum` smallint(6) unsigned NOT NULL DEFAULT '0',
  `sharenum` smallint(6) unsigned NOT NULL DEFAULT '0' COMMENT '共享数',
  `dateline` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '时间',
  PRIMARY KEY (`cid`),
  KEY `username` (`classname`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='班级空间';
```
### space_org  机构空间表
参考班级空间表
### 班级访客表: visitor_appclass
```sql
CREATE TABLE `jchome_visitor_appclass` (
  `cid` mediumint(8) unsigned NOT NULL DEFAULT '0' COMMENT '班级ID',
  `vuid` mediumint(8) unsigned NOT NULL DEFAULT '0' COMMENT '访客用户ID',
  `vusername` char(15) NOT NULL DEFAULT '' COMMENT '访客用户名',
  `dateline` int(10) unsigned NOT NULL DEFAULT '0' COMMENT '时间',
  PRIMARY KEY (`cid`,`vuid`),
  KEY `dateline` (`cid`,`dateline`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COMMENT='班级访客';
```
### 群组动态表
```
CREATE TABLE `jchome_group_dynamic` (
  `dynamic_id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT '动态Id',
  `type` smallint(1) DEFAULT '0' COMMENT '0 班级 1 机构',
  `dynamic_type` bigint(3) DEFAULT NULL COMMENT '动态类型  0 日志 , 1相册 , 2 文件共享 , 3 发布公告',
  `dynamic_title` varchar(255) DEFAULT NULL,
  `dynamic_content` text COMMENT '公告内容',
  `group_id` mediumint(8) DEFAULT NULL COMMENT '班级/机构Id',
  `group_name` varchar(64) DEFAULT NULL COMMENT '班级/机构名称',
  `s_creator` bigint(20) DEFAULT NULL COMMENT '创建者ID',
  `s_creator_name` varchar(32) DEFAULT NULL COMMENT '创建者名称',
  `s_create_time` datetime DEFAULT NULL COMMENT '创建时间',
  `dynamic_type_id` mediumint(8) DEFAULT NULL COMMENT '相应的id: 如果是blog, 则是当前日志的ID',
  PRIMARY KEY (`dynamic_id`)
) ENGINE=InnoDB AUTO_INCREMENT=3766 DEFAULT CHARSET=utf8;
```

#### 龙哥可能要注意的地方: 
用户表: member  对应的space空间表。                      <br>
班级表: appclass  对应的 space_appclass 表。              <br>
机构表: organization  对应的 space_org 表。               <br>
以及对应的  appclass_member  和  organization_member 表。 <br>
space_info（工作和教育经历） 和 space_field (出生日期，血型，出生地等) 不知道和平台那边数据库类型是否匹配，

不维护的话可以用户自己设置。













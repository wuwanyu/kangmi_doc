medicalManage后台接口文档
---------------------------


测试：http://120.25.124.68:5001/medicalManage/api/xxx （using）
开发：http://120.25.124.68:5000/medicalManage/api/xxx
*  [0. 通用接口](#1)
	* [0.1 message：获取短信验证码](#01)
	* [0.2 province：获取省列表](#02)
	* [0.3 city：根据省id，获取市列表](#03)
	* [0.4 region：根据市id，获取区列表](#04)

*  [01. 环信接口](#01)
	* [01.1 创建一个讨论组](#011)
	* [01.2 修改一个讨论组](#012)
	* [01.38 删除一个讨论组](#013)
	* [01.4 添加讨论组成员[单个] ](#014)
	* [01.4_1 添加讨论组成员[批量] ](#014_1)
	* [01.5 移除讨论组成员[单个]](#015)
	* [01.5_1 移除讨论组成员[批量]](#015_1)
	* [01.6 获取用户参与的所有讨论组](#016)
	* [01.7 获取讨论组所有成员](#017)
	* [01.8 发消息或群发消息](#018)
    * [01.9 getAgreedImGroupAndFriendList：获取群组及好友列表](#019)
    * [01.10 getNoneAgreedImFriendList：获取申请好友列表](#0110)
    * [01.11 getFriendListByImGroupId：根据群组id，获取好友列表](#019)
 	* [01.12 创建一个群组：2.1 addType：增加类别](#011)
	* [01.13 修改一个群组：2.2 updateType：修改类别](#012)
	* [01.14 删除一个群组：2.3 deleteType：删除类别](#014)
	* [01.15 修改用户所在群组：4.5 updateRelation：修改好友所在群组/审核好友申请](#015)
	* [01.16 获取好友申请列表：](#016)
	* [01.17 群发消息](#017)

*  [1. news：新闻](#1)
	* [1.1 addNews :创建新闻](#11)
	* [1.2 updateNews：修改新闻 ](#12)
	* [1.3 deleteNews：删除新闻](#13)
	* [1.4 getListByTypeId ：根据类型ID，获取新闻列表](#14)
	* [1.5 getInfoByNewsId ：根绝newsid，获取新闻详情](#15)
	* [1.6 getInfoAndCommentList：根据newsid，获取新闻详情及评论列表](#16)


*  [2. type：类别](#2)
	* [2.1 addType：增加类别](#21)
	* [2.2 updateType：修改类别](#22)
	* [2.3 deleteType：删除类别](#23)
	* [ 2.4 getListByType：根据类型获取标签/分类列表](#24)
    * [ 2.5 getmedicItem23List：获取医疗美容项目类型2和3](#25)
    * [ 2.6 deleteTypes：批量删除类别](#26)


*  [3. commnity：社区](#3)
	* [3.1 addCommunity：创建社区](#31)
	* [3.2 updateCommunity：修改社区](#32)
	*  [3.3 deleteCommunity：删除社区](#33)
	* [3.4 getListByTypeId ：根据社区类型ID，获取社区列表](#34)
	* [3.5 getInfoAndPostList：根据communityid，获取社区详情及帖子列表](#35)
	* [3.6 getHotCommunityList：获取社区列表（首页使用）](#36)
	* [3.7 getMyFocusCommunity：获取我关注的社区](#37)
	* [ 3.8 getHotCommunityBesideMyFocus：获取热门社区，不包括我关注的社区](#38)
	* [3.9 getPostFromMyFocusCommunity：获取我关注的社区的发帖](#38)


*   [4. relation：关系](#4)
	* [4.1 addRelation：新增关系](#41)
	* [4.2 deleteRelation：删除关系](#42)
	* [4.3 getCollectionByUserId：根据userid，获取收藏的xxx](#43)
	* [4.4 getFocusByUserId：根据userid，获取关注的xxx](#44)
	* [4.5 getImFriendApplyList：获取好友申请列表](#45)
    * [4.6 updateRelationAboutImFriend：审核好友申请](#46)
	* [4.7 updateRelationAboutGroup：修改好友所在的群组[批量]](#47)



*   [5. post：帖子和日记(new)](#5)
	* [5.1 add：创建帖子/日记](#51)
	* [5.2 update：修改帖子/日记](#52)
    * [5.3 delete：删除帖子/日记](#53)
	* [5.4 getPostListByCommunityId：根据社区id,获取帖子列表](#54)
	* [5.6 getListByTypeId：根据分类ID，获取列表](#56)
    * [5.7 getInfo：获取详情](#57)
	* [5.8 getInfoAndCommentList：获取详情及评论列表](#58)
	* [5.9 getPostListByCommunityId：根据communityid，获取帖子列表](#59)
	* [5.11 getGoodPostListByCommunityId：根据communityid，获取精选帖](#55)  -todo
	* [5.12 getTopPostListByCommunityId：根据communityid，获取置顶帖](#56)  -todo
	*  [5.13 getHotPostListByCommunityId：根据communityid，获取热门帖](#57) -todo
	*  [5.14 getListByXXX：根据条件，获取帖子或日记列表](#514) 
	*  [5.15 getNoteFromMyFocusUser：根据userid，获取我关注的用户的日记](#515) 
	*  [5.15_1 getNoteFromFocusMeUser：根据userid，获取关注我的用户的日记](#515_1) 
   *  [5.16 getPostFromMyFocusUser：根据userid，获取我关注的用户的帖子](#516) 
	*  [5.17 getHotLabelListOfPost：获取热门日记标签](#517) 
	*  [5.18 getHotLabelListOfPost：获取热门帖子标签](#518) 
   *  [5.19_1 getMyPraiseList：根据userid，获取我点赞的列表](#519_1) 
   *  [5.19_2 getMyPraisedList：根据userid，获取点赞我的列表](#519_2) 
   *  [5.20_1 getMyCommentList：根据userid，获取我评论的列表](#520_1) 
   *  [5.20_2 getMyCommentedList：根据userid，获取评论我的列表](#520_2) 
   *  [5.21 getNoteAndPostFromMyFocusUser：根据userid，获取我关注的用户的帖子和日记](#521) 
   *  [5.22 getNoteAndPostFromFocusMeUser：根据userid，获取我关注的用户的帖子和日记](#522) 


*   [6. comment：评论](#6)
	* [6.1 addComment：创建评论](#61)
	* [6.2 deleteComment：删除评论](#62)
	* [6.3 getListByParentId：根据parentid获取评论列表](#63)
	* [6.4 getListByObjId：根据对象Id获取评论列表](#64)

*  [7. user：用户](#7)
	* [7.1 register：用户注册](#71)
	* [7.2 updateUser：修改用户](#72)
	* [7.2_1 forget：忘记密码](#72_1)
	* [7.3 deleteUser：删除用户](#73)
	* [7.4 login：登录](#74)
    * [7.50 adminReg：管理员注册](#750)
	* [7.5 adminLogin：管理员登录](#75)
	* [7.6 adminLogout：管理员退出](#76) -no
	* [7.7 getPersonHomePage：根据friendId，获取用户主页](#77)
	* [7.7_1 根据账号，获取用户信息列表](#7.7_1)
	* [7.7_2  根据昵称/手机号查询用户](#7.7_2)
	* [7.8 list：获取用户列表](#78)
	* [7.9 getCommentListByUserId：根据userid，获取帖子和日记评论列表](#79)  todo
   * [7.10 getPraiseListByUserId：根据userid，获取帖子和日记点赞列表](#710)  todo
	* [7.11 getNoteListByUserId：根据userid，获取用户日记列表](#711)  -todo
	* [7.12 getPostListByUserId：根据userid，获取用户发帖列表](#712)  -todo
   * [7.13 getFocusedUserListByUserId：根据userid，获取关注我的用户列表](#713)  -todo
   * [7.14 getDocListByXXX：获取医生列表](#714)  
   * [7.15 getDocByDocId：获取医生信息](#715)  
   * [7.16 getDocInfo：获取医生详细](#716)  


*  [8. note：日记（old） ](#8)
	* [8.1 addNote :创建日记](#81)
	* [8.2 updateNote：修改日记 ](#82)
	* [8.3 deleteNote：删除日记](#83)
	* [8.4 getListByTypeId ：根据类型ID，获取日记列表](#84)
	* [8.5 getInfoByNoteId ：根据ID，获取日记详情](#85)
	* [8.6 getInfoAndCommentList：根据postid，获取日记详情及评论列表](#86)

*  [9. notebook：日记本](#9)
	* [9.1 addNotebook:创建日记](#91)
	* [9.2 updateNotebook：修改日记 ](#92)
	* [9.3 deleteNotebook：删除日记](#93)
	* [9.4 getListByUserId ：根据userid，获取日记本列表](#94)
	* [9.5 getOne：根据notebookId，获取日记本基础信息](#95)
	* [9.6 getInfoByNotebookId：根据notebookId，获取日记详情](#96)
	* [9.7 getInfoAndNoteList：根据notebookid，获取日记本详情及日记列表](#97)


*  [10. hospital：医院](#10)
	* [10.1 addHospital:创建医院](#101)
	* [10.2 updateHospital：修改医院 ](#102)
	* [10.3 findListByXXX：获取医院列表](#103)
	* [10.4 getHosById：获取医院信息](#104)
	* [10.5 getHosInfo：获取医院详细信息，含医生、项目列表等](#105)
	* [10.6 deleteHospital：删除医院](#106)

*  [12. project：医疗项目](#12)
	* [12.1 addProject:创建项目](#121)
	* [12.2 updateProject：修改项目 ](#122)
	* [12.3 findListByXXX：获取项目列表](#123)
	* [12.4 getInfoById：获取项目信息](#124)
	* [12.5 getProInfo：获取项目详细信息，含医院、医生等](#125)
	* [12.6 deleteProject：删除项目](#126)


*  [13. immsg：群发消息](#13)
	* [13.1 add：新增一条群发消息记录](#131)
	* [13.2 getListByAccount：获取群发消息记录](#132)


*  [14. medicItem：医疗项目详情描述](#14)
	* [14.1 add：新增项目描述](#141)
	* [14.2 getOne：根据medicItemId，获取描述](#142)
	* [14.3 delete：删除](#143)


<a name="0"></a>
### 0. 通用接口
<a name="01"></a>
#### 0.1 message：获取短信验证码
- 接口地址：/medicalManage/system/message
方法：post
参数：
mobile:
action:  forget/register
platform:resident/doctor

逻辑说明:
action = register时，通过 mobile +platform 查找用户，若用户不存在，则发送短信，否则提示错误信息；
action = forget时，通过 mobile +platform 查找用户，若用户存在，则发送短信，否则提示错误信息；


| 序号       |platform | action|   说明|
| -----  |:----:       	  	   |  ----:| 
| 1      | resident| register | 居民端注册 |
| 2       | resident| forget	| 居民端忘记密码  | 
| 3       | doctor| register | 医生端注册 | 
| 4       | doctor|  forget | 医生端忘记密码| 

```
mobile:13721264201
{
  "code": "400",
  "msg": "缺少必要参数！"
}


mobile:13721264202
action:forget
platform:resident

{
  "code": "400",
  "msg": "该账号尚未注册应用，请先注册！"
}

mobile:13721264201
action:register
platform:resident

{
  "code": "400",
  "msg": "该账号已注册该应用，不能重复注册！"
}


{
  "code": "200",
  "msg": "验证码发送成功",
  "sms": "715703",  //验证码
  "sms_result": {  //短信中心返回值
    "reason": "操作成功",
    "result": {
      "sid": "201612051337531858853614",
      "fee": 1,
      "count": 1
    },
    "error_code": 0
  }
}
```


<a name="02"></a>
#### 0.2 province：根据省id，获取市列表
- 接口地址：/medicalManage/system/province
方法：post
参数：
keyword:

```
keyword:河

{
 code:"200",
 msg:"获取列表成功！",
 result:
 [
  {
    "ProID": 3,
    "name": "河北省",
    "ProSort": 5,
    "ProRemark": "省份"
  },
  {
    "ProID": 16,
    "name": "河南省",
    "ProSort": 17,
    "ProRemark": "省份"
  }
]
}
```

<a name="03"></a>
#### 0.3 city：根据市id，获取区列表
- 接口地址：/medicalManage/system/city
方法：post
参数：
ProID: 所属省id
keyword:市名关键字

```
ProID:12
keyword:州
{
 code:"200",
 msg:"获取列表成功！",
 result:
 [
  {
    "CityID": 96,
    "name": "滁州市",
    "ProID": 12,
    "CitySort": 96
  },
  {
    "CityID": 98,
    "name": "宿州市",
    "ProID": 12,
    "CitySort": 98
  },
  {
    "CityID": 101,
    "name": "亳州市",
    "ProID": 12,
    "CitySort": 101
  },
  {
    "CityID": 102,
    "name": "池州市",
    "ProID": 12,
    "CitySort": 102
  }
]
}
```


<a name="04"></a>
#### 0.4 region：获取区列表
- 接口地址：/medicalManage/system/region
方法：post
参数：
CityID:所属市id
keyword:区名关键字

```
CityID:98
keyword:
{
 code:"200",
 msg:"获取列表成功！",
 result:
[
  {
    "Id": 936,
    "DisName": "埇桥区",
    "CityID": 98,
    "DisSort": null
  },
  {
    "Id": 937,
    "DisName": "砀山县",
    "CityID": 98,
    "DisSort": null
  },
  {
    "Id": 938,
    "DisName": "萧县",
    "CityID": 98,
    "DisSort": null
  },
  {
    "Id": 939,
    "DisName": "灵璧县",
    "CityID": 98,
    "DisSort": null
  },
  {
    "Id": 940,
    "DisName": "泗县 ",
    "CityID": 98,
    "DisSort": null
  }
]
}
```




<a name="01"></a>
### 01. 环信接口


<a name="011"></a>
#### 01.1 创建一个讨论组
- 接口地址：/medicalManage/system/im_group_add
方法：post
参数：
groupname:群名称
desc:群描述
owner:管理员账号
members:["wuwanyu","14911111111"]

地址：
http://localhost:5001/medicalManage/system/im_group_add

返回值：
```
{
  "status": 200,
  "result": {
    "action": "post",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi",
    "entities": [],
    "data": {
      "groupid": "279179151439561228"
    },
    "timestamp": 1482566261524,
    "duration": 32,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}
```

```
失败返回：
{
  "status": 400,
  "result": {
    "error": "illegal_argument",
    "timestamp": 1478003787699,
    "duration": 0,
    "exception": "java.lang.IllegalArgumentException",
    "error_description": "the owner doesn't exist"
  }
}
```

<a name="012"></a>
#### 01.2 修改一个讨论组
- 接口地址：/medicalManage/system/im_group_edit
方法：post
参数：
group_id:群组id，必填
groupname:群名
desc:描述

地址：
http://localhost:5001/medicalManage/system/im_group_edit

返回值：
```
{
  "status": 200,
  "result": {
    "action": "put",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi",
    "entities": [],
    "data": {
      "groupname": true
    },
    "timestamp": 1482566527304,
    "duration": 138,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}

```


<a name="013"></a>
#### 01.3 删除一个讨论组
- 接口地址：/medicalManage/system/im_group_delete
方法：post
参数：
group_id:群组id，必填

地址：
http://localhost:5001/medicalManage/system/im_group_delete

返回值：
```
{
  "status": 200,
  "result": {
    "action": "delete",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi",
    "entities": [],
    "data": {
      "success": true,
      "groupid": "279180692338770444"
    },
    "timestamp": 1482566664810,
    "duration": 10,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}
```


<a name="014"></a>
#### 01.4 添加讨论组成员[单个]
- 接口地址：/medicalManage/system/im_group_addUser
方法：post
参数：
参数：
group_id:群组id，必填
username:

地址：
http://localhost:5001/medicalManage/system/im_group_addUser


```
成功返回：
{
  "status": 200,
  "result": {
    "action": "post",
    "application": "9b674910-9a99-11e6-84b4-8f32a891bcf8",
    "uri": "https://a1.easemob.com/1154161025115110/medic",
    "entities": [],
    "data": {
      "result": true,
      "action": "add_member",
      "user": "15511111111",
      "groupid": "259569979702116780"
    },
    "timestamp": 1478004521924,
    "duration": 65,
    "organization": "1154161025115110",
    "applicationName": "kangmi"
  }
}
```

```
失败返回（群不存在）：
{
  "status": 404,
  "result": {
    "error": "service_resource_not_found",
    "timestamp": 1478004250544,
    "duration": 0,
    "exception": "org.apache.usergrid.services.exceptions.ServiceResourceNotFoundException",
    "error_description": "Service resource not found"
  }
}
失败返回（用户不存在）：
{
  "status": 400,
  "result": {
    "error": "illegal_argument",
    "timestamp": 1478004383519,
    "duration": 0,
    "exception": "java.lang.IllegalArgumentException",
    "error_description": "user 18233561200 doesn't exist"
  }
}
```


<a name="014_1"></a>
#### 01.4_1 添加讨论组成员[批量]
- 接口地址：/medicalManage/system/im_group_addUsers
方法：post
参数：
group_id:群组id，必填
accountStr:一个或多个账号，逗号分隔

```
accountStr:15084868481,13721264100
group_id:279177095341408796

{
  "status": 200,
  "result": {
    "action": "post",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi",
    "entities": [],
    "data": {
      "newmembers": [
        "15084868481",
        "13721264100"
      ],
      "action": "add_member",
      "groupid": "279177095341408796"
    },
    "timestamp": 1482569654512,
    "duration": 78,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}

```


<a name="015"></a>
#### 01.5 移除讨论组成员[单个]
- 接口地址：/medicalManage/system/im_group_deleteUser
方法：post
参数：
参数：
group_id:群组id，必填
username:

地址：
http://localhost:5001/medicalManage/system/im_group_deleteUser


```
成功返回：
{
  "status": 200,
  "result": {
    "action": "delete",
    "application": "9b674910-9a99-11e6-84b4-8f32a891bcf8",
    "uri": "https://a1.easemob.com/1154161025115110/medic",
    "entities": [],
    "data": {
      "result": true,
      "action": "remove_member",
      "user": "15511111111",
      "groupid": "259569979702116780"
    },
    "timestamp": 1478004566892,
    "duration": 27,
    "organization": "1154161025115110",
    "applicationName": "kangmi"
  }
}
```



<a name="01.5_1"></a>
#### 01.5_1 移除讨论组成员[批量]
- 接口地址：/medicalManage/system/im_group_deleteUsers
方法：post
参数：
group_id:群组id，必填
accountStr:一个或多个账号，逗号分隔

```
accountStr:15084868481,13721264100
group_id:279177095341408796


{
  "status": 200,
  "result": {
    "action": "delete",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi",
    "entities": [],
    "data": [
      {
        "result": true,
        "action": "remove_member",
        "user": "15084868481",
        "groupid": "279177095341408796"
      },
      {
        "result": true,
        "action": "remove_member",
        "user": "13721264100",
        "groupid": "279177095341408796"
      }
    ],
    "timestamp": 1482569999779,
    "duration": 50,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}
```


<a name="016"></a>
#### 01.6 获取用户参与的所有讨论组
- 接口地址：/medicalManage/system/im_group_getGroupListByUser
方法：post
参数：
username:账号

地址：
http://localhost:5001/medicalManage/system/im_group_getGroupListByUser


```
username:18233561909
成功返回：
{
  "status": 200,
  "result": {
    "action": "get",
    "uri": "http://a1.easemob.com/1117161219115882/kangmi/chatgroups/279177095341408796,279179090831868436,279179117142737436,279179151439561228",
    "entities": [],
    "data": [
      {
        "membersonly": true,
        "allowinvites": false,
        "public": true,
        "name": "特别关注",
        "description": "",
        "affiliations": [
          {
            "member": "18233561908"
          },
          {
            "owner": "18233561909"
          },
          {
            "member": "18867365368"
          }
        ],
        "id": "279177095341408796",
        "maxusers": 300,
        "affiliations_count": 3
      },
      ...
    ],
    "timestamp": 1482567247837,
    "duration": 25,
    "count": 4
  }
}
```




<a name="017"></a>
#### 01.7 获取讨论组所有成员
- 接口地址：/medicalManage/system/im_group_getUserListByGroupId
方法：post
参数：
group_id:群组id，必填

地址：
http://localhost:5001/medicalManage/system/im_group_getUserListByGroupId


```
group_id:279177095341408796

{
  "status": 200,
  "result": {
    "action": "get",
    "uri": "http://a1.easemob.com/1117161219115882/kangmi/chatgroups/279177095341408796/users",
    "entities": [],
    "data": [
      {
        "member": "18233561908"
      },
      {
        "owner": "18233561909"
      },
      {
        "member": "18867365368"
      }
    ],
    "timestamp": 1482567467646,
    "duration": 9,
    "count": 3
  }
}
```



<a name="018"></a>
#### 01.8 发消息或群发消息
- 接口地址：/medicalManage/system/im_message
方法：post
参数：
accountStr:	收消息账号，多个账号之间用,分割
msg:消息内容
from:发消息人的账号

```
accountStr:18233561908,18867365368
msg:盆友们，10月20号我在做手术，谁来看我呢
from:18233561909

{
  "status": 200,
  "result": {
    "action": "post",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "path": "/messages",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi/messages",
    "data": {
      "'18867365368'": "success",
      "'18233561908'": "success"
    },
    "timestamp": 1482570723990,
    "duration": 0,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}
```

<a name="019"></a>
####01.9 getAgreedImGroupAndFriendList：获取群组及好友列表
- 接口地址：/medicalManage/api/relation/getAgreedImGroupAndFriendList
方法：post
参数：
objType:imFriend
userId:当前登录用户的id

```
objType:imFriend
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取列表成功！",
  "imGroupList": [
    {
      "id": 28,
      "typeId": "78a36e70-cc2d-11e6-abe4-03e68f3955ea",
      "icon": null,
      "name": "特别关注",
      "type": "imGroup",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1482840635095",
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "createdAt": "2016-12-27T12:10:35.000Z",
      "updatedAt": "2016-12-27T12:10:35.000Z",
      "friendList": [
        {
          "groupName": "特别关注",
          "groupId": "78a36e70-cc2d-11e6-abe4-03e68f3955ea",
          "objId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
          "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
          "parentId": "78a36e70-cc2d-11e6-abe4-03e68f3955ea",
          "ifagree": null,
          "createdAt": "2016-12-27T14:10:52.000Z",
          "updatedAt": "2016-12-27T14:10:52.000Z",
          "friendName": "减肥超人S",
          "friendAccount": "18867365368",
          "friendIcon": null,
          "friendDesc": ""
        }
      ]
    },
     {
      "name": "未分组",
      "type": "imGroup",
      "friendList": [
        {
          "groupName": null,
          "groupId": null,
          "objId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
          "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
          "parentId": null,
          "ifagree": "yes",
          "createdAt": "2016-12-27T14:07:53.000Z",
          "updatedAt": "2016-12-27T14:07:53.000Z",
          "friendName": "小路",
          "friendAccount": "18233561908",
          "friendIcon": "image/DSC_0005.JPG",
          "friendDesc": "好男儿志在四方"
        }
      ]
    }
   ...
  ]
}
```



<a name="0110"></a>
####01.10 getNoneAgreedImFriendList：获取申请好友列表
- 接口地址：/medicalManage/api/relation/getNoneAgreedImFriendList
方法：post
参数：
userId:当前登录用户的id

```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "groupName": "特别关注",
      "groupId": "78a36e70-cc2d-11e6-abe4-03e68f3955ea",
      "objId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "parentId": "78a36e70-cc2d-11e6-abe4-03e68f3955ea",
      "ifagree": "none",
      "createdAt": "2016-12-27T14:10:52.000Z",
      "updatedAt": "2016-12-27T14:10:52.000Z",
      "friendName": "减肥超人S",
      "friendAccount": "18867365368",
      "friendIcon": null,
      "friendDesc": ""
    }
  ]
}

```

<a name="0111"></a>
####01.11 getFriendListByImGroupId：根据群组id，获取好友列表
- 接口地址：/medicalManage/api/relation/getFriendListByImGroupId
方法：post
参数：
userId:当前登录用户的id
imGroupId:群组id

```
parentId:82b2f660-cc2d-11e6-abe4-03e68f3955ea
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
{
  "code": "200",
  "msg": "获取列表成功！",
  "imFriendList": [
    {
      "groupName": "我的好友",
      "groupId": "82b2f660-cc2d-11e6-abe4-03e68f3955ea",
      "objId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
      "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
      "parentId": "82b2f660-cc2d-11e6-abe4-03e68f3955ea",
      "ifagree": "yes",
      "createdAt": "2016-12-27T14:07:53.000Z",
      "updatedAt": "2016-12-27T14:07:53.000Z",
      "friendName": "小路",
      "friendAccount": "18233561908",
      "friendIcon": "image/DSC_0005.JPG",
      "friendDesc": "好男儿志在四方"
    }
  ]
}

```

<a name="0117"></a>
####01.17 群发消息
- 接口地址：/medicalManage/api/relation/getFriendListByImGroupId
方法：post
参数：
userId:当前登录用户的id
imGroupId:群组id

```

```

<a name="0118"></a>
####01.18 获取群发消息列表
- 接口地址：/medicalManage/api/imMsgHistory/getListByAccount
方法：post
参数：
account:当前登录用户的id

```

```

<a name="1"></a>
### 1. news
<a name="11"></a>
#### 1.1 addNews :创建新闻
- 接口地址：/medicalManage/api/news/addNews
方法：post(form-data)
参数：
typeId:		新闻类型id
typeName:		新闻类型名称
title:		新闻名称
content:	新闻内容
from:		新闻来源
icon:		新闻图标
level:		新闻等级


地址：
http://120.25.124.68:5001/medicalManage/api/news/addNews

返回值：
```

typeId:3
typeName:热点
title:奥迪二手车广告引争议：婆婆捏儿媳口鼻查验惹来众怒
content:博鳌•21世纪房地产论坛第17届年会于7月21日-24日在海南三亚隆重举行。论坛由南方财经全媒体集团旗下《21世纪经济报道》于2001年主办发起，全联房地产商会联合主办，是中国目前规格最高，影响最大的房地产专业论坛之一。本届年会主题为“强监管与去杠杆：地产结构性变革的窗口期”。　↵↵　　【观点速览】任志强：今年房地产销售面积、销售额都会创历史新高↵↵　　当前房地产各种指标中，一个要看土地另一个要看新开工数据。从目前的情况看，今年房地产从销售面积到销售金额都会创历史新高，哪怕只有1%的增长。有谁认为我们的黄金时代已经过去了？但为什么我们的数据仍在增长呢？
from: 21世纪经济报道
level:

{
    "code": "200",
    "msg": "创建成功！",
    "item": {
        "typeId": "3",
        "typeName": "热点",
        "title": "奥迪二手车广告引争议：婆婆捏儿媳口鼻查验惹来众怒",
        "content": "博鳌•21世纪房地产论坛第17届年会于7月21日-24日在海南三亚隆重举行。论坛由南方财经全媒体集团旗下《21世纪经济报道》于2001年主办发起，全联房地产商会联合主办，是中国目前规格最高，影响最大的房地产专业论坛之一。本届年会主题为“强监管与去杠杆：地产结构性变革的窗口期”。　\n\n　　【观点速览】任志强：今年房地产销售面积、销售额都会创历史新高\n\n　　当前房地产各种指标中，一个要看土地另一个要看新开工数据。从目前的情况看，今年房地产从销售面积到销售金额都会创历史新高，哪怕只有1%的增长。有谁认为我们的黄金时代已经过去了？但为什么我们的数据仍在增长呢？",
        "from": " 21世纪经济报道",
        "level": "",
        "icon": "http://120.25.124.68:5001/upload/image/in37F0PVpIC1tUKZ0TdV2SEJ.jpg",
        "createdAt": "2017-07-23T08:51:59.634Z",
        "updatedAt": "2017-07-23T08:51:59.634Z",
        "newsId": 14
    }
}
```
<a name="12"></a>
#### 1.2 updateNews：修改新闻
- 接口地址：/medicalManage/api/news/updateNews
方法：post(form-data)
参数：
typeId:		新闻类型id
typeName:		新闻类型名称
title:		新闻名称
content:	新闻内容
from:		新闻来源
newsId:		新闻id
icon:		新闻图标
level:		新闻等级

地址：
http://120.25.124.68:5001/medicalManage/api/news/updateNews

```
title:任志强：今年房地产销售面积销售额都会创历史新高
newsId:14

{
    "code": "200",
    "msg": "修改成功！",
    "item": {
        "newsId": 14,
        "level": "",
        "typeId": "3",
        "typeName": "热点",
        "title": "任志强：今年房地产销售面积销售额都会创历史新高",
        "icon": "http://120.25.124.68:5001/upload/image/in37F0PVpIC1tUKZ0TdV2SEJ.jpg",
        "content": "博鳌•21世纪房地产论坛第17届年会于7月21日-24日在海南三亚隆重举行。论坛由南方财经全媒体集团旗下《21世纪经济报道》于2001年主办发起，全联房地产商会联合主办，是中国目前规格最高，影响最大的房地产专业论坛之一。本届年会主题为“强监管与去杠杆：地产结构性变革的窗口期”。　\n\n　　【观点速览】任志强：今年房地产销售面积、销售额都会创历史新高\n\n　　当前房地产各种指标中，一个要看土地另一个要看新开工数据。从目前的情况看，今年房地产从销售面积到销售金额都会创历史新高，哪怕只有1%的增长。有谁认为我们的黄金时代已经过去了？但为什么我们的数据仍在增长呢？",
        "from": " 21世纪经济报道",
        "createdAt": "2017-07-23T08:51:59.000Z",
        "updatedAt": "2017-07-23T08:51:59.000Z"
    }
}
```
<a name="13"></a>
#### 1.3 deleteNews：删除新闻
- 接口地址：/medicalManage/api/news/deleteNews
方法：post
参数：
newsId:新闻id

地址：
http://120.25.124.68:5001/medicalManage/api/news/deleteNews

```
{
  "code": "200",
  "msg": "删除成功！",
  "item": {
      "id": 3,
      "newsId": "ee3696b0-b62c-11e6-8649-6b1b6518e324",
      "level": "0",
      "typeId": "ae198ba0-b5fa-11e6-bbb2-0fcd9912076d",
      "typeName": "热点",
      "title": "上汽奥迪渠道之争能否借鉴特斯拉？",
      "icon": null,
      "content": "“现在经销商空前团结，几乎所有的一汽奥迪经销商都加入了流通协会的奥迪经销商联会，现在来看，12月1日不提车是大概率事件。”11月27日，一位参与佛山会议的奥迪经销商在接受21世纪经济报道记者采访时表示。",
      "from": "经济参考报",
      "datems": "1480421477276",
      "createdAt": "2016-11-29T12:11:17.000Z",
      "updatedAt": "2016-11-29T12:11:17.000Z"
    }
}

```


<a name="14"></a>
#### 1.4 getListByTypeId ：根据类型ID，获取新闻列表
- 接口地址：/medicalManage/api/news/getListByTypeId
方法：post
参数：
typeId:		类型id

说明：按发布时间倒叙排列

地址：
http://120.25.124.68:5001/medicalManage/api/news/getListByTypeId

```
typeId:1

{
    "code": "200",
    "msg": "获取列表成功",
    "count": 4,
    "list": [
        {
            "newsId": 13,
            "level": "0",
            "typeId": "1",
            "typeName": "推荐",
            "title": "标题",
            "icon": "http://120.25.124.68:5001/upload/image/rpIV24wm6djC3JZZFWM9gk7B.jpg",
            "content": "<p>我是一只可爱的猫咪，喵喵喵</p>",
            "from": "自媒体",
            "createdAt": "2017-05-21T02:41:18.000Z",
            "updatedAt": "2017-05-21T02:41:18.000Z",
            "collect_count": null,
            "praise_count": null,
            "comment_count": null
        },
        {
            "newsId": 12,
            "level": "0",
            "typeId": "1",
            "typeName": "推荐",
            "title": "我是一颗，小小的石头...",
            "icon": "http://120.25.124.68:5001/upload/image/AXYzl193yNgpuRnhnxo7PuMa.jpg",
            "content": "深深埋在，泥土之中。你的影子，我看不见...",
            "from": "腾讯网",
            "createdAt": "2017-03-21T07:15:51.000Z",
            "updatedAt": "2017-03-21T07:15:51.000Z",
            "collect_count": null,
            "praise_count": null,
            "comment_count": null
        },
        {
            "newsId": 2,
            "level": "0",
            "typeId": "1",
            "typeName": "推荐",
            "title": "上汽奥迪渠道之争能否借鉴特斯拉？",
            "icon": "",
            "content": "“现在经销商空前团结，几乎所有的一汽奥迪经销商都加入了流通协会的奥迪经销商联会，现在来看，12月1日不提车是大概率事件。”11月27日，一位参与佛山会议的奥迪经销商在接受21世纪经济报道记者采访时表示。",
            "from": "经济参考报",
            "createdAt": "2016-11-29T12:11:14.000Z",
            "updatedAt": "2016-11-29T12:11:14.000Z",
            "collect_count": null,
            "praise_count": null,
            "comment_count": 6
        },
        {
            "newsId": 1,
            "level": "0",
            "typeId": "1",
            "typeName": "推荐",
            "title": "上海天津限购后房贷出现新一轮收紧",
            "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
            "content": "28日，天津、上海同时发布收紧房贷政策。这意味着，继新一轮限购收紧后，新一轮限贷拉开帷幕。",
            "from": "经济参考报",
            "createdAt": "2016-11-29T11:56:01.000Z",
            "updatedAt": "2016-11-29T11:56:01.000Z",
            "collect_count": null,
            "praise_count": null,
            "comment_count": 32
        }
    ]
}

```
<a name="15"></a>
#### 1.5 getInfoByNewsId ：根绝newsid，获取新闻详情
- 接口地址：/medicalManage/api/news/getInfoByNewsId
方法：post
参数：
newsId:	新闻id
userId:用户id

地址：
http://120.25.124.68:5001/medicalManage/api/news/getInfoByNewsId

```
newsId:1
userId:13

{
    "code": "200",
    "msg": "获取详情成功",
    "ifPraise": "yes",
    "item": {
        "newsId": 1,
        "level": "0",
        "typeId": "1",
        "typeName": "推荐",
        "title": "上海天津限购后房贷出现新一轮收紧",
        "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
        "content": "28日，天津、上海同时发布收紧房贷政策。这意味着，继新一轮限购收紧后，新一轮限贷拉开帷幕。",
        "from": "经济参考报",
        "createdAt": "2016-11-29T11:56:01.000Z",
        "updatedAt": "2016-11-29T11:56:01.000Z",
        "collect_count": 1,
        "praise_count": 2,
        "comment_count": 32,
        "if_praise": 1,
        "if_collect": 1,
        "if_subscribe": null,
        "shared_page_url": "http://120.25.124.68:5001/medicalManage/mobile/news?newsId=1"
    }
}

```

<a name="16"></a>
#### 1.6 getInfoAndCommentList：根据newsid，获取新闻详情及评论列表
- 接口地址：/medicalManage/api/news/getInfoAndCommentList
方法：post
参数：
newsId:	新闻id

地址：
http://120.25.124.68:5001/medicalManage/api/news/getInfoAndCommentList

```
newsId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f

{
  "code": "200",
  "msg": "获取详情成功",
  "ifPraise": "yes",
 "item": {
        "newsId": 1,
        "level": "0",
        "typeId": "1",
        "typeName": "推荐",
        "title": "上海天津限购后房贷出现新一轮收紧",
        "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
        "content": "28日，天津、上海同时发布收紧房贷政策。这意味着，继新一轮限购收紧后，新一轮限贷拉开帷幕。",
        "from": "经济参考报",
        "createdAt": "2016-11-29T11:56:01.000Z",
        "updatedAt": "2016-11-29T11:56:01.000Z",
        "collect_count": 1,
        "praise_count": 2,
        "comment_count": 32,
        "if_praise": 1,
        "if_collect": 1,
        "if_subscribe": null,
        "shared_page_url": "http://120.25.124.68:5001/medicalManage/mobile/news?newsId=1"
    },
  "commentlist": [
    {
            "commentId": 124,
            "parentId": "74",
            "star": 5,
            "objId": "1",
            "objType": "note",
            "userId": "13",
            "content": "咋地啦八点",
            "createdAt": "2017-04-25T07:46:50.000Z",
            "updatedAt": "2017-04-25T07:46:50.000Z",
            "comment_userId": 13,
            "comment_userName": "奈何一笑",
            "comment_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
            "commented_userId": 13,
            "commented_userName": "奈何一笑",
            "commented_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
            "praise_count": null,
            "if_praise": null
        }, ... ]
}
```
<a name="2"></a>
### 2. type

<a name="21"></a>
#### 2.1 addType：增加类别
- 接口地址：/medicalManage/api/type/addType
方法：post(form-date)
参数：
icon:
name:
type:
userId:
parentId:
parentName:
order:


| 序号       |type|   说明| 其他|
| -----  |:----:       	  	   |  ----:| 
| 1      | newsType|  新闻类别 |  |
| 2       | communityType|  社区类别		|   |
| 3       | postLabel|  发帖标签| userId为创建用户的userId|
| 4       | noteLabel|  日记标签| userId为创建用户的userId|
| 5       | noteType|  日记类别| |
| 6       | imGroup|  用户分组|userId必填 |
| 7       | roomType1| 一级科室类别| |
| 8       | roomType2| 二级科室类别| |
| 9       | medicItem1|  医疗美容项目一级类别| |
| 10       | medicItem2|  医疗美容项目二级类别| parentId必填|
| 11       | medicItem3|  医疗美容项目三级类别| parentId必填|
| 12       | dossierGroup|  病历夹分组| userId为创建用户的userId|
| 13      | medicKnowledgeType1|  教患分类一级| |
| 14     | medicKnowledgeType2|  教患分类二级| parentId必填|


地址：
http://120.25.124.68:5001/medicalManage/api/type/addType

例1：newsType 获取新闻类别列表
```
name:上海
type:newsType

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "娱乐",  //类型名称
    "type": "newsType",  //类型类别
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG", //类型图标
    "typeId": "e95322d0-b5fa-11e6-bbb2-0fcd9912076d", //类型id
    "order": "1",  //排序
    "datems": "1480399994237",
    "createdAt": "2016-11-29T06:13:14.239Z",
    "updatedAt": "2016-11-29T06:13:14.239Z",
    "id": 4
  }
}
```
例2：communityType 获取社区类别列表
```

name:同城
type:communityType

返回值：
{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "同城",
    "type": "communityType",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
    "order": "1",
    "datems": "1480400068505",
    "createdAt": "2016-11-29T06:14:28.506Z",
    "updatedAt": "2016-11-29T06:14:28.506Z",
    "id": 5
  }
}
```
例3：noteType  获取日记类型列表
```
name:账单
type:noteLabel
userId:4e3512f0-b60d-11e6-9ed3-9184a13c35d7

返回值：
{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "账单",
    "type": "noteLabel",
    "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
    "order": "1",
    "datems": "1480410317303",
    "createdAt": "2016-11-29T09:05:17.308Z",
    "updatedAt": "2016-11-29T09:05:17.308Z",
    "id": 7
  }
}
```
例3：postType  获取帖子类型列表
```

name:整形日记
type:postLabel
userId:4e3512f0-b60d-11e6-9ed3-9184a13c35d7

返回值：
{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "整形日记",
    "type": "postLabel",
    "typeId": "2d7d7790-b613-11e6-b7e2-f9d10cb604b7",
    "order": "1",
    "datems": "1480410416521",
    "createdAt": "2016-11-29T09:06:56.523Z",
    "updatedAt": "2016-11-29T09:06:56.523Z",
    "id": 8
  }
}
```
添加好友分组
```
name:家人
type:imGroup
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "家人",
    "type": "userGroup",
    "typeId": "86a4ca00-cc2d-11e6-abe4-03e68f3955ea",
    "order": "1",
    "datems": "1482840658592",
    "createdAt": "2016-12-27T12:10:58.593Z",
    "updatedAt": "2016-12-27T12:10:58.593Z",
    "id": 31
  }
}
```

| 8       | roomType1| 一级科室类别| |
```
name:产科
type:roomType1
order:6
{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "产科",
    "type": "roomType1",
    "order": "6",
    "typeId": "d75e2a10-d563-11e6-9973-4d5838778506",
    "datems": "1483853547313",
    "createdAt": "2017-01-08T05:32:27.314Z",
    "updatedAt": "2017-01-08T05:32:27.314Z",
    "id": 37
  }
}
```
| 8       | roomType2| 二级科室类别| |

```
name:新生儿科
type:roomType2
order:1
parentId:bd7cf360-d563-11e6-9973-4d5838778506
parentName:儿科

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "新生儿科",
    "type": "roomType2",
    "order": "1",
    "parentId": "bd7cf360-d563-11e6-9973-4d5838778506",
    "parentName": "儿科",
    "typeId": "3fd5f050-d564-11e6-9973-4d5838778506",
    "datems": "1483853722581",
    "createdAt": "2017-01-08T05:35:22.582Z",
    "updatedAt": "2017-01-08T05:35:22.582Z",
    "id": 39
  }
}
```

| 7       | medicItem1|  医疗美容项目一级类别| |
```
name:皮肤
type:medicItem1
order:8

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "皮肤",
    "type": "medicItem1",
    "order": "8",
    "typeId": "dca8ec10-d565-11e6-b3ac-f5350455130e",
    "datems": "1483854415185",
    "createdAt": "2017-01-08T05:46:55.185Z",
    "updatedAt": "2017-01-08T05:46:55.185Z",
    "id": 47
  }
}
```
| 7       | medicItem2|  医疗美容项目二级类别| |
```
name:双眼皮
type:medicItem2
order:1
parentId:b25fe120-d565-11e6-b3ac-f5350455130e
parentName:眼部

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "双眼皮",
    "type": "medicItem2",
    "order": "1",
    "parentId": "b25fe120-d565-11e6-b3ac-f5350455130e",
    "parentName": "眼部",
    "typeId": "3fd5f050-d564-11e6-9973-4d5838778506",
    "datems": "1483853722581",
    "createdAt": "2017-01-08T05:35:22.582Z",
    "updatedAt": "2017-01-08T05:35:22.582Z",
    "id": 39
  }
}
```
| 7       | medicItem3|  医疗美容项目三级类别| |
```
name:埋线双眼皮
type:medicItem3
order:1
parentId:3aac7520-d566-11e6-b3ac-f5350455130e
parentName:双眼皮

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "name": "埋线双眼皮",
    "type": "medicItem3",
    "order": "1",
    "parentId": "3aac7520-d566-11e6-b3ac-f5350455130e",
    "parentName": "双眼皮",
    "typeId": "ef558ac0-d566-11e6-b3ac-f5350455130e",
    "datems": "1483854876012",
    "createdAt": "2017-01-08T05:54:36.014Z",
    "updatedAt": "2017-01-08T05:54:36.014Z",
    "id": 59
  }
}
```

| 12       | dossierGroup|  病历夹分组| userId为创建用户的userId|
```
name:107房病人
type:dossierGroup
userId:3dd4e6a0-d558-11e6-ac80-35e73a3a9d09
order:1

{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "icon": "",
    "name": "107房病人",
    "type": "dossierGroup",
    "userId": "3dd4e6a0-d558-11e6-ac80-35e73a3a9d09",
    "parentId": "",
    "parentName": "",
    "order": "1",
    "typeId": "ce0dd020-ef51-11e6-bf39-b3266d9fc4cc",
    "createdAt": "2017-02-10T05:28:50.987Z",
    "updatedAt": "2017-02-10T05:28:50.987Z",
    "id": 81
  }
}
```

| 13      | medicKnowledgeType1|  教患分类一级| |

```
{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "icon": "",
    "name": "内科",
    "type": "medicKnowledgeType1",
    "userId": "",
    "parentId": "",
    "parentName": "",
    "order": "1",
    "typeId": "a6779e40-ef53-11e6-a4a8-5be012b27e99",
    "createdAt": "2017-02-10T05:42:03.556Z",
    "updatedAt": "2017-02-10T05:42:03.556Z",
    "id": 92
  }
}
```

| 14     | medicKnowledgeType2|  教患分类二级| parentId必填|


```
{
  "code": "200",
  "msg": "新增成功",
  "item": {
    "icon": "",
    "name": "辅食喂养",
    "type": "medicKnowledgeType2",
    "userId": "",
    "parentId": "eff49880-ef52-11e6-a4a8-5be012b27e99",
    "parentName": "妇产科",
    "order": "1",
    "typeId": "84209270-ef53-11e6-a4a8-5be012b27e99",
    "createdAt": "2017-02-10T05:41:05.944Z",
    "updatedAt": "2017-02-10T05:41:05.944Z",
    "id": 91
  }
}
```

<a name="22"></a>
#### 2.2 updateType：修改类别
- 接口地址：/medicalManage/api/type/updateType
方法：post(form-date)
参数：
typeId:		类型id
icon:		类型图标
name:		类型名称
order:		类型排序

地址：
http://120.25.124.68:5001/medicalManage/api/type/updateType

```
{
  "code": "200",
  "msg": "修改成功",
  "item": {
    "id": 8,
    "typeId": "2d7d7790-b613-11e6-b7e2-f9d10cb604b7",
    "icon": null,
    "name": "整形日记",
    "type": "postType",
    "parentId": null,
    "parentName": null,
    "order": "1",
    "datems": "1480410416521",
    "user_id": null,
    "createdAt": "2016-11-29T09:06:56.000Z",
    "updatedAt": "2016-11-29T09:06:56.000Z"
  }
}
```

<a name="23"></a>
#### 2.3 deleteType：删除类别
- 接口地址：/medicalManage/api/type/deleteType
方法：post
参数：
typeId:		类型id

地址：
http://120.25.124.68:5001/medicalManage/api/type/deleteType

```
{
  "code": "200",
  "msg": "删除成功！",
  "item": [
    {
      "id": 2,
      "typeId": "e1ea02c0-b5fa-11e6-bbb2-0fcd9912076d",
      "icon": "image/DSC_0005.JPG",
      "name": "军事",
      "type": "newsType",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1480399981804",
      "user_id": null,
      "createdAt": "2016-11-29T06:13:01.000Z",
      "updatedAt": "2016-11-29T06:13:01.000Z"
    }
  ]
}
```

<a name="24"></a>
#### 2.4 getListByType：根据类型获取标签/分类列表
- 接口地址：/medicalManage/api/type/getListByType
方法：post
参数：
type:
userId:

| 序号       |type|   说明| 其他|
| -----  |:----:       	  	   |  ----:| 
| 1      | newsType|  新闻类别 |  |
| 2       | communityType|  社区类别		|   |
| 3       | postLabel|  发帖标签| userId为创建用户的userId|
| 4       | noteLabel|  日记标签| userId为创建用户的userId|
| 5      | noteType|  日记类别 |  |
| 6       | imGroup|  用户分组|userId必填 |
| 7       | roomType1| 一级科室类别| |
| 8       | roomType2| 二级科室类别| |
| 9       | medicItem1|  医疗项目一级类别| |
| 10       | medicItem2|  医疗项目二级类别| |
| 11       | medicItem3|  医疗项目三级类别| |
| 12       | dossierGroup|  病历夹分组| userId为创建用户的userId|
| 13      | medicKnowledgeType1|  教患分类一级| |
| 14     | medicKnowledgeType2|  教患分类二级| parentId必填|


说明：按照order字段正序排列

地址：
http://120.25.124.68:5001/medicalManage/api/type/getListByType

```

{
  "code": "200",
  "msg": "获取列表成功",
  "list": [
    {
      "id": 1,
      "typeId": "ae198ba0-b5fa-11e6-bbb2-0fcd9912076d",
      "icon": "image/DSC_0005.JPG",
      "name": "热点",
      "type": "newsType",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1480399894875",
      "user_id": null,
      "createdAt": "2016-11-29T06:11:34.000Z",
      "updatedAt": "2016-11-29T06:11:34.000Z",
      "child_count":3 
    },
    ...
  ]
}
```

```
type:communityType

{
  "code": "200",
  "msg": "获取列表成功",
  "list": [
    {
      "id": 6,
      "typeId": "2f7b3040-b5fb-11e6-bbb2-0fcd9912076d",
      "icon": null,
      "name": "推荐",
      "type": "communityType",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1480400111940",
      "user_id": null,
      "createdAt": "2016-11-29T06:15:11.000Z",
      "updatedAt": "2016-11-29T06:15:11.000Z"
    },
    ...
  ]
}
```

```
type:imGroup
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取列表成功",
  "list": [
    {
      "id": 31,
      "typeId": "86a4ca00-cc2d-11e6-abe4-03e68f3955ea",
      "icon": null,
      "name": "家人",
      "type": "userGroup",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1482840658592",
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "createdAt": "2016-12-27T12:10:58.000Z",
      "updatedAt": "2016-12-27T12:10:58.000Z"
    },
   ...
  ]
}

```

| 7       | roomType1| 一级科室类别| |
```
type:roomType1

{
  "code": "200",
  "msg": "获取成功",
  "list": [
    {
      "id": 32,
      "typeId": "91f41570-d563-11e6-b20c-8d2d5ed54d0c",
      "icon": null,
      "name": "妇科",
      "type": "roomType1",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1483853430855",
      "userId": null,
      "createdAt": "2017-01-08T05:30:30.000Z",
      "updatedAt": "2017-01-08T05:30:30.000Z"
    },
   ...
  ],
  "count": 6
}
```
| 8       | roomType2| 二级科室类别| |
```
type:roomType2
parentId:bd7cf360-d563-11e6-9973-4d5838778506

{
  "code": "200",
  "msg": "修改成功",
  "list": [
    {
      "id": 38,
      "typeId": "3b8bea90-d564-11e6-9973-4d5838778506",
      "icon": null,
      "name": "小儿科",
      "type": "roomType2",
      "parentId": "bd7cf360-d563-11e6-9973-4d5838778506",
      "parentName": "儿科",
      "order": "1",
      "datems": "1483853715385",
      "userId": null,
      "createdAt": "2017-01-08T05:35:15.000Z",
      "updatedAt": "2017-01-08T05:35:15.000Z"
    },
    {
      "id": 39,
      "typeId": "3fd5f050-d564-11e6-9973-4d5838778506",
      "icon": null,
      "name": "新生儿科",
      "type": "roomType2",
      "parentId": "bd7cf360-d563-11e6-9973-4d5838778506",
      "parentName": "儿科",
      "order": "1",
      "datems": "1483853722581",
      "userId": null,
      "createdAt": "2017-01-08T05:35:22.000Z",
      "updatedAt": "2017-01-08T05:35:22.000Z"
    }
  ],
  "count": 2
}

```

| 9       | medicItem1|  医疗项目一级类别| |
```
type:medicItem1

{
  "code": "200",
  "msg": "修改成功",
  "list": [
    {
      "id": 40,
      "typeId": "b25fe120-d565-11e6-b3ac-f5350455130e",
      "icon": null,
      "name": "眼部",
      "type": "medicItem1",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1483854344242",
      "userId": null,
      "createdAt": "2017-01-08T05:45:44.000Z",
      "updatedAt": "2017-01-08T05:45:44.000Z"
    },
    ...
  ],
  "count": 8
}
```

| 10       | medicItem2|  医疗项目二级类别| |
```
type:medicItem2
parentId:b25fe120-d565-11e6-b3ac-f5350455130e

{
  "code": "200",
  "msg": "修改成功",
  "list": [
    {
      "id": 48,
      "typeId": "2b0b7350-d566-11e6-b3ac-f5350455130e",
      "icon": null,
      "name": "开眼角",
      "type": "medicItem2",
      "parentId": "b25fe120-d565-11e6-b3ac-f5350455130e",
      "parentName": "眼部",
      "order": "1",
      "datems": "1483854546693",
      "userId": null,
      "createdAt": "2017-01-08T05:49:06.000Z",
      "updatedAt": "2017-01-08T05:49:06.000Z"
    },
  ...
  ],
  "count": 4
}
```
| 11       | medicItem3|  医疗项目三级类别| |
```
type:medicItem3
parentId:2b0b7350-d566-11e6-b3ac-f5350455130e

{
  "code": "200",
  "msg": "修改成功",
  "list": [
    {
      "id": 52,
      "typeId": "6be7e980-d566-11e6-b3ac-f5350455130e",
      "icon": null,
      "name": "开内眼角",
      "type": "medicItem3",
      "parentId": "2b0b7350-d566-11e6-b3ac-f5350455130e",
      "parentName": "开眼角",
      "order": "1",
      "datems": "1483854655512",
      "userId": null,
      "createdAt": "2017-01-08T05:50:55.000Z",
      "updatedAt": "2017-01-08T05:50:55.000Z"
    },
   ...
  ],
  "count": 2
}
```
| 12       | dossierGroup|  病历夹分组| userId为创建用户的userId|

```
type:dossierGroup
userId:3dd4e6a0-d558-11e6-ac80-35e73a3a9d09

{
  "code": "200",
  "msg": "获取成功！",
  "list": [
    {
      "id": 81,
      "typeId": "ce0dd020-ef51-11e6-bf39-b3266d9fc4cc",
      "icon": "",
      "name": "107房病人",
      "type": "dossierGroup",
      "parentId": "",
      "parentName": "",
      "order": "1",
      "userId": "3dd4e6a0-d558-11e6-ac80-35e73a3a9d09",
      "createdAt": "2017-02-10T05:28:50.000Z",
      "updatedAt": "2017-02-10T05:28:50.000Z"
    }
  ],
  "count": 1
}
```

| 13      | medicKnowledgeType1|  教患分类一级| |
```
type:medicKnowledgeType1

{
  "code": "200",
  "msg": "获取成功！",
  "list": [
    {
      "id": 82,
      "typeId": "d3406bb0-ef52-11e6-a4a8-5be012b27e99",
      "icon": "",
      "name": "内科",
      "type": "medicKnowledgeType1",
      "parentId": "",
      "parentName": "",
      "order": "1",
      "userId": null,
      "createdAt": "2017-02-10T05:36:09.000Z",
      "updatedAt": "2017-02-10T05:36:09.000Z"
    },
   ...
  ],
  "count": 3
}
```
| 14     | medicKnowledgeType2|  教患分类二级| parentId必填|
```
type:medicKnowledgeType2
parentId:eff49880-ef52-11e6-a4a8-5be012b27e99

{
  "code": "200",
  "msg": "获取成功！",
  "list": [
    {
      "id": 86,
      "typeId": "48f441b0-ef53-11e6-a4a8-5be012b27e99",
      "icon": "",
      "name": "宝宝发育",
      "type": "medicKnowledgeType2",
      "parentId": "eff49880-ef52-11e6-a4a8-5be012b27e99",
      "parentName": "妇产科",
      "order": "1",
      "userId": "",
      "createdAt": "2017-02-10T05:39:26.000Z",
      "updatedAt": "2017-02-10T05:39:26.000Z"
    },
   ...
  ],
  "count": 6
}
```



<a name="25"></a>
#### 2.5 getMedicItem23List：获取医疗项目类型2级和3级
- 接口地址：/medicalManage/api/type/getmedicItem23List
方法：post
参数：
parentId:医疗美容项目一级类别id

地址：
http://120.25.124.68:5001/medicalManage/api/type/getmedicItem23List

```
parentId:b25fe120-d565-11e6-b3ac-f5350455130e

{
  "code": "200",
  "msg": "获取医疗项目类别2级3级列表成功！",
  "list": [
    {
      "id": 48,
      "typeId": "2b0b7350-d566-11e6-b3ac-f5350455130e",
      "icon": null,
      "name": "开眼角",
      "type": "medicItem2",
      "parentId": "b25fe120-d565-11e6-b3ac-f5350455130e",
      "parentName": "眼部",
      "order": "1",
      "datems": "1483854546693",
      "userId": null,
      "createdAt": "2017-01-08T05:49:06.000Z",
      "updatedAt": "2017-01-08T05:49:06.000Z",
      "childList": [
        {
          "id": 52,
          "typeId": "6be7e980-d566-11e6-b3ac-f5350455130e",
          "icon": null,
          "name": "开内眼角",
          "type": "medicItem3",
          "parentId": "2b0b7350-d566-11e6-b3ac-f5350455130e",
          "parentName": "开眼角",
          "order": "1",
          "datems": "1483854655512",
          "userId": null,
          "createdAt": "2017-01-08T05:50:55.000Z",
          "updatedAt": "2017-01-08T05:50:55.000Z"
        },
       ...
      ]
    },
   ...
      ]
    }
  ]
}
```

<a name="26"></a>
#### 2.6 deleteTypes：批量删除类别
- 接口地址：/medicalManage/api/type/deleteTypes
方法：post
参数：
typeIdStr:		一个或多个类型id，逗号分隔

地址：
http://120.25.124.68:5001/medicalManage/api/type/deleteType

```
typeIdStr:1221122,1322322

{
  "code": "200",
  "msg": "删除成功！",
  "item": {
    "fieldCount": 0,
    "affectedRows": 2,
    "insertId": 0,
    "serverStatus": 34,
    "warningCount": 0,
    "message": "",
    "protocol41": true,
    "changedRows": 0
  }
}
```

<a name="3"></a>
### 3. community

<a name="31"></a>
#### 3.1 addCommunity：创建社区
- 接口地址：/medicalManage/api/community/addCommunity
方法：post(form-data)
参数：
typeId:  所属类别id
typeName:	类别名称
name:	社区名称
title:		社区标题
icon:		社区图标

地址：
http://120.25.124.68:5001/medicalManage/api/community/addCommunity

```
{
  "code": "200",
  "msg": "创建成功！",
  "community": {
    "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
    "typeName": "同城",
    "name": "同城玩耍",
    "title": "男生女生约起来",
    "icon": "http://120.25.124.68:5000/upload/image/DSC_0005.JPG",
    "communityId": "8aa3e1a0-b935-11e6-b0ee-23915c83f0c3",
    "createdAt": "2016-12-03T08:50:29.180Z",
    "updatedAt": "2016-12-03T08:50:29.180Z",
    "id": 1
  }
}
```
<a name="32"></a>
#### 3.2 updateCommunity：修改社区
- 接口地址：/medicalManage/api/community/updateCommunity
方法：post(form-data)
参数：
typeId: 		社区类别id
typeName:		社区类别名称
name:		社区名称
title:		社区标题
communityId:		社区id
icon:		社区图标

地址：
http://120.25.124.68:5001/medicalManage/api/community/updateCommunity

```
{
  "code": "200",
  "msg": "修改成功！",
  "item": {
    "id": 4,
    "communityId": "dd1f7390-b935-11e6-b0ee-23915c83f0c3",
    "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
    "typeName": "同城",
    "name": "华晨宇歌友会",
    "title": "一起来听：滑板鞋~~",
    "icon": "http://120.25.124.68:5000/upload/image/DSC_0005.JPG",
    "order": null,
    "datems": null,
    "createdAt": "2016-12-03T08:52:47.000Z",
    "updatedAt": "2016-12-03T08:52:47.000Z"
  }
}
```

<a name="33"></a>
#### 3.3 deleteCommunity：删除社区
- 接口地址：/medicalManage/api/community/deleteCommunity
方法：post
参数：
communityId:

地址：
http://120.25.124.68:5001/medicalManage/api/community/deleteCommunity

```
{
  "code": "200",
  "msg": "操作成功！！",
  "community":{
      "id": 3,
      "communityId": "dc20c840-b935-11e6-b0ee-23915c83f0c3",
      "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
      "typeName": "同城",
      "name": "华晨宇歌友会",
      "title": "一起来听：滑板鞋",
      "icon": "image/DSC_0005.JPG",
      "order": null,
      "datems": null,
      "createdAt": "2016-12-03T08:52:45.000Z",
      "updatedAt": "2016-12-03T08:52:45.000Z"
    }
}
```
<a name="34"></a>
#### 3.4 getListByTypeId ：根据社区类型ID，获取社区列表
- 接口地址：/medicalManage/api/community/getListByTypeId
方法：post
参数：
typeId:		类别id
userId:		当前登录用户id

地址：
http://120.25.124.68:5001/medicalManage/api/community/getListByTypeId

```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
typeId:15978890-b5fb-11e6-bbb2-0fcd9912076d

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 5,
  "list": [
    {
      "id": 6,
      "communityId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
      "typeName": "同城",
      "name": "瘦身减肥",
      "title": "单身减肥社区",
      "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "order": null,
      "datems": null,
      "createdAt": "2016-12-20T01:49:41.000Z",
      "updatedAt": "2016-12-20T01:49:41.000Z",
      "focus_count": 1,
      "post_count": 3,
      "if_focus": null  //null:未关注,1:关注
    },
    ...
  ]
}
```
<a name="35"></a>
#### 3.5 getInfoAndPostList：根据communityid，获取社区详情及帖子列表
- 接口地址：/medicalManage/api/community/getInfoAndPostList
方法：post
参数：
communityId:社区id
userId:当前登录用户Id
地址：
http://120.25.124.68:5001/medicalManage/api/community/getInfoAndPostList

```
communityId:9325bd70-c656-11e6-8ca5-37b03af6926d
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取信息成功！",
  "ifFocused": "yes",//是否关注，yes/no
  "community": {
    "id": 6,
    "communityId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
    "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
    "typeName": "同城",
    "name": "瘦身减肥",
    "title": "单身减肥社区",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "order": null,
    "platform": "resident",
    "createdAt": "2016-12-20T01:49:41.000Z",
    "updatedAt": "2016-12-20T01:49:41.000Z",
    "focus_count": 2,  //关注量
    "post_count": 3 //发帖量
  },
  "postlist": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "id": 6,
      "postId": "ede140f0-cf29-11e6-929e-4fce1bb7475f",
      "labelId": "9325bd70-c656-11e6-8ca5-37b03af6926d\u0001499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "labelName": "开外眼角\u0001埋线双眼皮",
      "typeId": "2d7d7790-b613-11e6-b7e2-f9d10cb604b7\u00014de86cf0-e2d8-11e6-9768-577de73e03e3",
      "typeName": null,
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": "减肥3个月啦",
      "content": "减肥三个月了，看这效果明显吧，哈哈哈，以前那个肉呼呼的胖妹纸不见了...现在下巴秀气而高挺了吧~~哈哈，现在照镜子总忍不住臭美一番~~~需要传授经验吗",
      "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg",
      "level": null,
      "type": "post",
      "createdAt": "2016-12-31T07:22:47.000Z",
      "updatedAt": "2016-12-31T07:22:47.000Z",
      "share_count": null,
      "praise_count": 1,
      "comment_count": null,
      "if_praise": 1,  //是否点赞，1：是，0：否
      "if_focus": 1, //是否关注，1：是，0：否
      "shared_page_url": "http://120.25.124.68:5001/medicalManage/mobile/post?post_id=ede140f0-cf29-11e6-929e-4fce1bb7475f"
    }
  ]
}

```


<a name="36"></a>
#### 3.6 getHotCommunityList：获取社区列表（首页使用）
- 接口地址：/medicalManage/api/community/getHotCommunityList
方法：post
参数：
limit:返回个数，默认6个
说明：返回社区列表根据发帖量，关注量倒序排序
```
{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
   {
      "id": 2,
      "communityId": "ba6fc070-b935-11e6-b0ee-23915c83f0c3",
      "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
      "typeName": "同城",
      "name": "程序猿生活",
      "title": "我的滑板鞋~~~",
      "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "order": null,
      "datems": null,
      "createdAt": "2016-12-03T08:51:49.000Z",
      "updatedAt": "2016-12-03T08:51:49.000Z",
      "focus_count": null,
      "post_count": 3
    },
    ...
  ]
}
```


<a name="37"></a>
#### 3.7 getMyFocusCommunity：获取我关注的社区
- 接口地址：/medicalManage/api/community/getMyFocusCommunity
方法：post
参数：
userId：当前登录用户

```
{
  "code": "200",
  "msg": "获取我关注的社区列表成功！",
  "result": [
    {
      "id": 6,
      "communityId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
      "typeName": "同城",
      "name": "瘦身减肥",
      "title": "单身减肥社区",
      "icon": "image/DSC_0005.JPG",
      "order": null,
      "platform": "resident",
      "createdAt": "2016-12-20T01:49:41.000Z",
      "updatedAt": "2016-12-20T01:49:41.000Z",
      "focus_count": 2,
      "post_count": 5
    }
  ]
}
```


<a name="38"></a>
#### 3.8 getHotCommunityBesideMyFocus：获取热门社区，不包括我关注的社区
- 接口地址：/medicalManage/api/community/getHotCommunityBesideMyFocus
方法：post
参数：
userId：当前登录用户

```
{
  "code": "200",
  "msg": "获取热门社区列表成功！",
  "result": [
    {
      "id": 6,
      "communityId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
      "typeName": "同城",
      "name": "瘦身减肥",
      "title": "单身减肥社区",
      "icon": "image/DSC_0005.JPG",
      "order": null,
      "platform": "resident",
      "createdAt": "2016-12-20T01:49:41.000Z",
      "updatedAt": "2016-12-20T01:49:41.000Z",
      "focus_count": 2,
      "post_count": 5
    }
  ]
}
```

<a name="39"></a>
#### 3.9 getPostFromMyFocusCommunity：获取我关注的社区的发帖
- 接口地址：/medicalManage/api/post/getPostFromMyFocusCommunity
方法：post
参数：
userId：当前登录用户

```
{
  "code": "200",
  "msg": "获取热门社区列表成功！",
  "result": [
    {
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "user_name": "奈何一笑",
      "user_account": "18867365368",
      "user_icon": "other/tq1m8mkv3ZafBFj6yr233iXT.png",
      "id": 11,
      "postId": "5999bf80-edc4-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "typeId": "52354ee0-c5fa-11e6-9c21-9ff2d56ab9f3\u0001f259d960-b612-11e6-b7e2-f9d10cb04b78",
      "typeName": "喇叭花",
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": "切开双眼皮\u0001长沙亚韩整形记录",
      "content": "就弄Monmouth",
      "images": "image/IMG_20170206_181944.jpg\u0001image/IMG_20170205_210933.jpg",
      "level": null,
      "type": "post",
      "createdAt": "2017-02-08T06:03:45.000Z",
      "updatedAt": "2017-02-08T06:03:45.000Z",
      "share_count": null,
      "praise_count": null,
      "comment_count": null,
      "if_praise": null,  //是否点赞，1：是，0：否
      "if_focus": null  //是否关注，1：是，0：否
    }  ]
}
```






<a name="4"></a>
### 4. relation：关系表

<a name="41"></a>
#### 4.1 addRelation：新增关系
- 接口地址：/medicalManage/api/relation/addRelation
方法：post
参数：

objId:	对象id，例如新闻id，社区id等
objType:	对象类别
parentId:	对象父类id(删除at2017.2.28)
userId:		用户id
operation:	操作类型


|序号|operation|	objType|	说明|
| ----- |:----:   |:----:     |  ----:| 
|1|	focus  	|user	|关注用户，同步IM好友关系|
|2|	focus		|community	|关注社区|
|3|	focus		|newsType	|关注新闻类别|
|3|	focus		|imFriend	|添加im好友|
|3|	focus		|hospital |关注医院|
|4|	collect 	|news	|收藏新闻|
|5|	collect		|note	|收藏日记|
|6|	collect		|post	|收藏帖子|
|7|	praise	    |news	|点赞新闻|
|8|	praise		|note	|点赞日记|
|9|	praise		|post	|点赞帖子|
|10|praise	    |	comment	|点赞评论|
|10|praise	    |	notebook	|点赞笔记本|
|11|	share	    |news	|点赞新闻|
|12|	share       |note	|点赞日记|
|13|	share      |post	|点赞帖子|


地址：
http://120.25.124.68:5001/medicalManage/api/relation/addRelation

```
|1|	focus  	|user	|关注用户|

http://120.25.124.68:5000/medicalManage/api/relation/add

objId:e86fad20-b91a-11e6-945f-71d86d0db9d0
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
objType:user
operation:focus

{
  "code": "200",
  "msg": "操作成功！",
  "friend": {  //好友信息
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "name": "小美",
    "password": "123456",
    "account": "18233561909",
    "hospital": null,
    "room": null,
    "position": null,
    "city": "上海",
    "address": "上海市浦东新区",
    "type": "user",
    "icon": "image/DSC_0005.JPG",
    "sex": "女",
    "age": "18",
    "desc": "在最好的年纪遇到你",
    "datems": "1480743590131",
    "points": "10",
    "platform": "resident",
    "createdAt": "2016-12-03T05:39:50.000Z",
    "updatedAt": "2016-12-03T05:39:50.000Z",
    "id": 15
  },
  "im_code": 200,  //im添加好友
  "im_result": {
    "action": "post",
    "application": "276f3750-b639-11e6-928e-db3fd954d021",
    "path": "/users/c62dfe10-b91a-11e6-b848-8f510a1e901a/contacts",
    "uri": "https://a1.easemob.com/1154161025115110/kangmi/users/c62dfe10-b91a-11e6-b848-8f510a1e901a/contacts",
    "entities": [
      {
        "uuid": "e721a950-b91a-11e6-b471-83f88d0e7798",
        "type": "user",
        "created": 1480743587941,
        "modified": 1480743587941,
        "username": "18233561909",
        "activated": true,
        "nickname": "小美"
      }
    ],
    "timestamp": 1480743628363,
    "duration": 103,
    "organization": "1154161025115110",
    "applicationName": "kangmi"
  },
  "im_message_code": 200,  //发送消息通知好友
  "im_message_result": {
    "action": "post",
    "application": "276f3750-b639-11e6-928e-db3fd954d021",
    "path": "/messages",
    "uri": "https://a1.easemob.com/1154161025115110/kangmi/messages",
    "data": {
      "18233561909": "success"
    },
    "timestamp": 1480743628721,
    "duration": 0,
    "organization": "1154161025115110",
    "applicationName": "kangmi"
  },
  "item": {
    "objId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
    "objType": "user",
    "operation": "focus",
    "datems": "1480743630397",
    "createdAt": "2016-12-03T05:40:30.399Z",
    "updatedAt": "2016-12-03T05:40:30.400Z",
    "id": 11
  }
}
```

```
|2|	focus		|community	|关注社区|

objId:dd1f7390-b935-11e6-b0ee-23915c83f0c3
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:community
operation:focus

{
  "code": "200",
  "msg": "操作成功！",
  "results": {
    "objId": "dd1f7390-b935-11e6-b0ee-23915c83f0c3",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "community",
    "operation": "focus",
    "datems": "1480763670022",
    "createdAt": "2016-12-03T11:14:30.039Z",
    "updatedAt": "2016-12-03T11:14:30.039Z",
    "id": 17
  }
}

```

|3|	focus		|imFriend	|im好友|

im添加好友


```
objId:c77264f0-b91a-11e6-945f-71d86d0db9d0
objType:imFriend
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
operation:focus

{
  "code": "400",
  "msg": "已经是好友关系，不能重复添加！"
}

```

```
objId:db8ebf20-baae-11e6-b180-872a6e363290
objType:imFriend
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
operation:focus

{
  "code": "200",
  "msg": "操作成功！",
  "item": {
    "objId": "db8ebf20-baae-11e6-b180-872a6e363290",
    "objType": "imFriend",
    "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
    "operation": "focus",
    "ifagree": "none",
    "createdAt": "2017-02-28T06:05:56.638Z",
    "updatedAt": "2017-02-28T06:05:56.638Z",
    "id": 41
  }
}

```

```
|3|	focus		|newsType	|关注新闻类别|
objId:e6e2e620-b5fa-11e6-bbb2-0fcd9912076d
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
objType:newsType
operation:focus
{
  "code": "200",
  "msg": "操作成功！",
  "result":{
	 objId: 'e6e2e620-b5fa-11e6-bbb2-0fcd9912076d',
     userId: 'c77264f0-b91a-11e6-945f-71d86d0db9d0',
     objType: 'newsType',
     operation: 'focus',
     datems: '1480744388861',
     createdAt: '2016-12-03T05:53:08.867Z',
     updatedAt: '2016-12-03T05:53:08.867Z',
     id: 12 
     }
}
```

```
|4|	collect 	|news	|收藏新闻|
objId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
objType:news
operation:collect
{
  "code": "200",
  "msg": "操作成功！"，
  "result": {
	 objId: 'cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f',
     userId: 'c77264f0-b91a-11e6-945f-71d86d0db9d0',
     objType: 'news',
     operation: 'collect',
     datems: '1480744388861',
     createdAt: '2016-12-03T05:53:08.867Z',
     updatedAt: '2016-12-03T05:53:08.867Z',
     id: 13 
     }
}
```
```
|5|	collect		|note	|收藏日记|
objId:e9da97b0-b92e-11e6-a9ef-f36a4004c390
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:note
operation:collect

{
  "code": "200",
  "msg": "操作成功！",
  "results": {
    "objId": "e9da97b0-b92e-11e6-a9ef-f36a4004c390",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "note",
    "operation": "collect",
    "datems": "1480763738504",
    "createdAt": "2016-12-03T11:15:38.511Z",
    "updatedAt": "2016-12-03T11:15:38.511Z",
    "id": 18
  }
}
```

```
|6|	collect		|post	|收藏帖子|

objId:13cbc0d0-b93e-11e6-8fa1-9f820747b10a
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:post
operation:collect

{
  "code": "200",
  "msg": "操作成功！",
  "results": {
    "objId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "post",
    "operation": "collect",
    "datems": "1480763794605",
    "createdAt": "2016-12-03T11:16:34.610Z",
    "updatedAt": "2016-12-03T11:16:34.610Z",
    "id": 19
  }
}
```
```
|7|	praise	    |news	|点赞新闻|
objId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
objType:news
operation:praise
{
  "code": "200",
  "msg": "操作成功！",
  "results": {
    "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
    "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
    "objType": "news",
    "operation": "praise",
    "datems": "1480744703612",
    "createdAt": "2016-12-03T05:58:23.623Z",
    "updatedAt": "2016-12-03T05:58:23.623Z",
    "id": 14
  }
}
```
```
|8|	praise		|note	|点赞日记|

objId:e9da97b0-b92e-11e6-a9ef-f36a4004c390
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:note
operation:praise

{
  "code": "200",
  "msg": "操作成功！",
  "results": {
    "objId": "e9da97b0-b92e-11e6-a9ef-f36a4004c390",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "note",
    "operation": "praise",
    "datems": "1480765147385",
    "createdAt": "2016-12-03T11:39:07.392Z",
    "updatedAt": "2016-12-03T11:39:07.392Z",
    "id": 25
  }
}
```
```
|9|	praise		|post	|点赞帖子|

objId:13cbc0d0-b93e-11e6-8fa1-9f820747b10a
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:post
operation:praise

{
  "code": "200",
  "msg": "操作成功！",
  "im_message_code": 200,
  "im_message_result": {
    "action": "post",
    "application": "276f3750-b639-11e6-928e-db3fd954d021",
    "path": "/messages",
    "uri": "https://a1.easemob.com/1154161025115110/kangmi/messages",
    "data": {
      "18233561909": "success"
    },
    "timestamp": 1480765067757,
    "duration": 0,
    "organization": "1154161025115110",
    "applicationName": "kangmi"
  }
}

```
```
|10|praise	    |	comment	|点赞评论|

objId:98bafc70-b632-11e6-a1f1-2f9175fb66f5
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
objType:comment
operation:praise

{
  "code": "200",
  "msg": "操作成功！",
  "results": {
    "objId": "98bafc70-b632-11e6-a1f1-2f9175fb66f5",
    "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
    "objType": "comment",
    "operation": "praise",
    "datems": "1480744763319",
    "createdAt": "2016-12-03T05:59:23.334Z",
    "updatedAt": "2016-12-03T05:59:23.334Z",
    "id": 16
  }
}
```


```
|11|	share	    |news	|点赞新闻|

objId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:news
operation:share

{
  "code": "200",
  "msg": "创建成功！",
  "item": {
    "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "news",
    "operation": "share",
    "datems": "1480766473486",
    "createdAt": "2016-12-03T12:01:13.489Z",
    "updatedAt": "2016-12-03T12:01:13.489Z",
    "id": 28
  }
}
```

```
|12|	share       |note	|点赞日记|

objId:e9da97b0-b92e-11e6-a9ef-f36a4004c390
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:note
operation:share

{
  "code": "200",
  "msg": "创建成功！",
  "item": {
    "objId": "e9da97b0-b92e-11e6-a9ef-f36a4004c390",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "note",
    "operation": "share",
    "datems": "1480766366438",
    "createdAt": "2016-12-03T11:59:26.450Z",
    "updatedAt": "2016-12-03T11:59:26.450Z",
    "id": 26
  }
}
```

```
|13|	share      |post	|点赞帖子|

objId:13cbc0d0-b93e-11e6-8fa1-9f820747b10a
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
objType:post
operation:share

{
  "code": "200",
  "msg": "创建成功！",
  "item": {
    "objId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "objType": "post",
    "operation": "share",
    "datems": "1480766400967",
    "createdAt": "2016-12-03T12:00:00.968Z",
    "updatedAt": "2016-12-03T12:00:00.968Z",
    "id": 27
  }
}
```

<a name="42"></a>
#### 4.2 deleteRelation：删除关系
- 接口地址：/medicalManage/api/relation/deleteRelation
方法：post
参数：
parent_id:
obj_id:
user_id:
operation:
type:


| 序号    |operation   |type|   说明| 其他|
| ----- |:----:   |:----:     |  ----:| 
| 1     | g | news_type |  关注新闻标签 |  |
| 2     | g | community |  关注社区		|   |
| 2     | g | user|  关注用户		|   |
| 2     | s | news|  新闻		|   |

地址：
http://120.25.124.68:5001/medicalManage/api/relation/deleteRelation


```
{
  "code": "200",
  "msg": "操作成功！！",
  "item": [
    {
      "id": 4,
      "relation_id": "98220720-9aaf-11e6-9a21-63aabdd3102d",
      "parent_id": "",
      "obj_id": "5811dda0-b2ec-11e5-a306-33448f6b146a",
      "user_id": "2fc48bd0-a62c-11e5-9a32-a31e4e4cd6a5",
      "operation": "g",
      "type": "news_type",
      "fcount": 0,
      "datems": "1477398964370",
      "createdAt": "2016-10-25T12:36:04.000Z",
      "updatedAt": "2016-10-25T12:36:04.000Z"
    }
  ]
}
```


<a name="43"></a>
#### 4.3 getCollectionByUserId：根据userid，获取收藏的xxx
- 接口地址：/medicalManage/api/relation/getCollectionByUserId
方法：post
参数：
userId:
operation:s
type:

| 序号    |operation   |type|   说明| 其他|
| ----- |:----:   |:----:     |  ----:| 
| 2     | collect | note|  新闻		|   |
| 2     | collect | news|  新闻		|   |
| 2     | collect | post|  新闻		|   |

地址：
http://120.25.124.68:5001/medicalManage/api/relation/getCollectionByUserId


```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
operation:collect
objType:note

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "id": 2,
      "noteId": "e9da97b0-b92e-11e6-a9ef-f36a4004c390",
      "level": "0",
      "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
      "typeName": "账单",
      "title": "9月份账单",
      "icon": "image/DSC_0005.JPG",
      "content": "吃饭：1000，住宿:1800",
      "from": "康咪",
      "datems": "1480752182443",
      "createdAt": "2016-12-03T08:03:02.000Z",
      "updatedAt": "2016-12-03T08:03:02.000Z"
    }
  ]
}

```


```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
operation:collect
objType:news

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "id": 1,
      "newsId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "level": "0",
      "typeId": "ae198ba0-b5fa-11e6-bbb2-0fcd9912076d",
      "typeName": "热点",
      "title": "上海天津限购后房贷出现新一轮收紧",
      "icon": "image/DSC_0005.JPG",
      "content": "28日，天津、上海同时发布收紧房贷政策。这意味着，继新一轮限购收紧后，新一轮限贷拉开帷幕。",
      "from": "经济参考报",
      "datems": "1480420561174",
      "createdAt": "2016-11-29T11:56:01.000Z",
      "updatedAt": "2016-11-29T11:56:01.000Z"
    }
  ]
}

```

```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
operation:collect
objType:post

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "id": 4,
      "postId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
      "typeId": null,
      "typeName": null,
      "parentId": "dc20c840-b935-11e6-b0ee-23915c83f0c3",
      "parentName": "华晨宇歌友会",
      "title": "华晨宇12月20日南京演唱会有人同行吗？",
      "content": "自从听了“天籁之音”从此对花花路转粉了...",
      "images": "image/2f54fc091600dce8c811533b50707002_b.jpg",
      "level": null,
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "datems": "1480758695261",
      "createdAt": "2016-12-03T09:51:35.000Z",
      "updatedAt": "2016-12-03T09:51:35.000Z"
    }
  ]
}

```

<a name="44"></a>
#### 4.4 getFocusByUserId：根据userid，获取关注的xxx
- 接口地址：/medicalManage/api/relation/getFocusByUserId
方法：post
参数：
userId:
operation:
objType:

| 序号    |operation   |type|   说明| 其他|
| ----- |:----:   |:----:     |  ----:| 
| 1     | focus | newsType |  关注新闻标签 |  |
| 2     | focus | community |  关注社区		|   |
| 3     | focus | user|  获取我关注的用户		|   |
| 4     | focus | imFriend|  获取我的im好友		|   |

地址：
http://120.25.124.68:5001/medicalManage/api/relation/getFocusByUserId


```
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
operation:focus
objType:newsType

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "id": 3,
      "typeId": "e6e2e620-b5fa-11e6-bbb2-0fcd9912076d",
      "icon": "image/DSC_0005.JPG",
      "name": "体育",
      "type": "newsType",
      "parentId": null,
      "parentName": null,
      "order": "1",
      "datems": "1480399990146",
      "user_id": null,
      "createdAt": "2016-11-29T06:13:10.000Z",
      "updatedAt": "2016-11-29T06:13:10.000Z"
    }
  ]
}
```
```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
operation:focus
objType:community

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "id": 4,
      "communityId": "dd1f7390-b935-11e6-b0ee-23915c83f0c3",
      "typeId": "15978890-b5fb-11e6-bbb2-0fcd9912076d",
      "typeName": "同城",
      "name": "华晨宇歌友会",
      "title": "一起来听：滑板鞋~~",
      "icon": "image/DSC_0005.JPG",
      "order": null,
      "datems": null,
      "createdAt": "2016-12-03T08:52:47.000Z",
      "updatedAt": "2016-12-03T08:52:47.000Z"
    }
  ]
}
```

```
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0
operation:focus
objType:user

{
  "code": "200",
  "msg": "获取列表成功！",
  "list": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "name": "小美",
      "password": "123456",
      "account": "18233561909",
      "hospital": null,
      "room": null,
      "position": null,
      "city": "上海",
      "address": "上海市浦东新区",
      "type": "user",
      "icon": "image/DSC_0005.JPG",
      "sex": "女",
      "age": "18",
      "desc": "在最好的年纪遇到你",
      "datems": "1480743590131",
      "points": "25",
      "platform": "resident",
      "createdAt": "2016-12-03T05:39:50.000Z",
      "updatedAt": "2016-12-03T05:39:50.000Z",
      "ID": 15
    }
  ]
}
```


<a name="45"></a>
#### 4.5 getImFriendApplyList：获取好友申请列表
- 接口地址：/medicalManage/api/relation/getImFriendApplyList
方法：post(form-data)
参数：
userId:  //发帖人
objType:imFriend

地址：
http://120.25.124.68:5001/medicalManage/api/relation/getImFriendApplyList

```
objType:imFriend
userId:db8ebf20-baae-11e6-b180-872a6e363290

{
  "code": "200",
  "msg": "获取好友申请列表成功！",
  "list": [
    {
      "id": 41,
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "userName": "奈何一笑",
      "userAccount": "18867365368",
      "userIcon": "other/tq1m8mkv3ZafBFj6yr233iXT.png",
      "createdAt": "2017-02-28T06:05:56.000Z",
      "ifagree": "none"
    }
  ]
}

```

<a name="46"></a>
#### 4.6 updateRelationAboutImFriend：审核好友申请
- 接口地址：/medicalManage/api/relation/updateRelationAboutImFriend
方法：post
参数：

userId:自己userid（必填）
objId:对方userid（必填）
objType:imFriend（必填）
ifagree:是否同意，yes:同意，no:不同意

地址：
http://120.25.124.68:5001/medicalManage/api/relation/updateRelation

修改用户所在群组
```
拒绝：
objId:db8ebf20-baae-11e6-b180-872a6e363290
objType:imFriend
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
ifagree:no


{
  "code": "200",
  "msg": "更新成功！",
  "result": [
    {
      "id": 42,
      "objId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "ifagree": "no"
    },
    {
      "id": 41,
      "objId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "ifagree": "none"
    }
  ]
}


同意：
objId:db8ebf20-baae-11e6-b180-872a6e363290
objType:imFriend
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
ifagree:yes


{
  "code": "200",
  "msg": "更新成功！"
}

重复操作：
{
  "code": "400",
  "msg": "已经存在好友关系！"
}
```

<a name="47"></a>
#### 4.7 updateRelationAboutGroup：修改好友所在的群组[批量]
- 接口地址：/medicalManage/api/relation/updateRelationAboutGroup
方法：post
参数：
userId:自己userid（必填）
objIdStr:对方userid，多个用英文逗号分隔（必填）
typeId :修改好友所在的群组
typeName:修改好友所在的群组名称


地址：
http://120.25.124.68:5001/medicalManage/api/relation/updateRelationAboutGroup

修改用户所在群组
```
objType:imFriend
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
objIdStr:c77264f0-b91a-11e6-945f-71d86d0db9d0,e86fad20-b91a-11e6-945f-71d86d0db9d0,db8ebf20-baae-11e6-b180-872a6e363290
typeId:5c6b42c0-eff8-11e6-8885-b357dc60476e
typeName:我的同事

{
  "code": "200",
  "msg": "操作成功！"
}

```





<a name="5"></a>
### 5. post：帖子和日记

<a name="51"></a>
#### 5.1 add：创建帖子/日记
- 接口地址：/medicalManage/api/post/add
方法：post(form-data)
参数：
userId:  //发帖人
title:  //标题
content:  //内容
images: //图片，可接受多个
itemId:  //项目id，多个之间用0x01分隔
itemName:  //项目名称，多个之间用0x01分隔
labelId:  //标签id，多个之间用0x01分隔
labelName:  //标签名称，多个之间用0x01分隔
parentId:  //社区id/日记本id，多个之间用0x01分隔
parentName:   //type=post：parentId是社区id、type=note：parentId是日记本id。多个之间用0x01分隔
type:帖子：post，日记：note。不传默认是post,


地址：
http://120.25.124.68:5001/medicalManage/api/post/add

添加笔记
```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
title:鼻综合整形记录
content:术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~
typeId:e86fad20-b91a-11e6-945f-71d86d0db9d0
typeName:精选
type:note
parentId: 
parentName: 

{
  "code": "200",
  "msg": "创建成功！",
  "post": {
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "title": "鼻综合整形记录",
    "content": "术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
    "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "typeName": "精选",
    "type": "note",
    "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "postId": "7fd91130-cd87-11e6-afb5-870770b90a75",
    "datems": "1482989253059",
    "createdAt": "2016-12-29T05:27:33.064Z",
    "updatedAt": "2016-12-29T05:27:33.064Z",
    "id": 11
  }
}
```

<a name="52"></a>
#### 5.2 update：修改帖子/日记
- 接口地址：/medicalManage/api/post/update
方法：post(form-data)
参数：
postId:帖子id
itemId:  //项目id，多个之间用0x01分隔
itemName:  //项目名称，多个之间用0x01分隔
labelId:  //标签id，多个之间用0x01分隔
labelName:  //标签名称，多个之间用0x01分隔
parentId:  //type=post：parentId是社区id、type=note：parentId是日记本id。多个之间用0x01分隔
parentName:  //社区名称，多个之间用0x01分隔

地址：
http://120.25.124.68:5001/medicalManage/api/post/update

修改
```

```

<a name="53"></a>
#### 5.3 delete：删除帖子/日记
- 接口地址：/medicalManage/api/post/delete
方法：post
参数：
postId:笔记/帖子id


地址：
http://120.25.124.68:5001/medicalManage/api/post/delete

删除
```

```




<a name="514"></a>
#### 5.14 getListByXXX：根据条件，获取帖子或日记列表
- 接口地址：/medicalManage/api/post/getListByXXX
方法：post
参数：
parentId:社区id
userId:发帖人id
itemId:项目id
keyword:关键字
type:post/note
myId:当前登录用户id

地址：
http://120.25.124.68:5001/medicalManage/api/post/getListByXXX

```
{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 2,
  "list": [
    {
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "user_name": "减肥超人S",
      "user_account": "18867365368",
      "user_icon": null,
      "id": 8,
      "postId": "20d9b360-c99f-11e6-af22-4558735d9a46",
      "itemId": null,
      "itemName": null,
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥社区",
      "title": "减肥2个月啦~~",
      "content": "减肥2个月了，看着效果明显吧！哈哈，以前那个胖乎乎的妹纸不见了吧~~现在的下巴够秀气够挺拔吧~~现在照镜子都会忍不住臭美一番，哈哈~~需要传授经验吗？",
      "images": null,
      "level": null,
      "datems": "1482559596950",
      "type": "post",
      "createdAt": "2016-12-24T06:06:36.000Z",
      "updatedAt": "2016-12-24T06:06:36.000Z",
      "share_count": null,
      "praise_count": null,
      "comment_count": null,
      "if_praise": null,
      "shared_page_url": "http://120.25.124.68:5001/medicalManage/mobile/post?post_id=20d9b360-c99f-11e6-af22-4558735d9a46"
    },
  ...
  ]
}
```

<a name="55"></a>
#### 5.5 getNoteListByNotebookId：根据笔记本ID，获取笔记列表
- 接口地址：/medicalManage/api/post/getNoteListByNotebookId
方法：post
参数：
notebookId:笔记本id

地址：
http://120.25.124.68:5001/medicalManage/api/post/getNoteListByNotebookId


```
notebookId:1 

{ 
“code”: “200”, 
“msg”: “获取列表成功！”, 
“count”: 3, 
“list”: [ 
{ 
“userId”: “e86fad20-b91a-11e6-945f-71d86d0db9d0”, 
“user_name”: “冷心真心傻傻”, 
“user_account”: “18233561909”, 
“user_icon”: “image/DSC_0005.JPG”, 
“id”: 11, 
“postId”: “7fd91130-cd87-11e6-afb5-870770b90a75”, 
“typeId”: “e86fad20-b91a-11e6-945f-71d86d0db9d0”, 
“typeName”: “精选”, 
“parentId”: “1”, 
“parentName”: “整容日记”, 
“title”: “鼻综合整形记录”, 
“content”: “术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~”, 
“images”: “image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg”,
“level”: null, 
“datems”: “1482989253059”, 
“type”: “note”, 
“createdAt”: “2016-12-29T05:27:33.000Z”, 
“updatedAt”: “2016-12-29T05:27:33.000Z”, 
“share_count”: null, 
“praise_count”: null, 
“comment_count”: null, 
“if_praise”: null, 
“shared_page_url”: “http://120.25.124.68:5001/medicalManage/mobile/post?post_id=7fd91130-cd87-11e6-afb5-870770b90a75” 
}, 
… 
] 
}

```



<a name="57"></a>
#### 5.7 getInfo：获取详情
- 接口地址：/medicalManage/api/post/getInfo
方法：post
参数：
postId:帖子或笔记id
userId:当前登录用户的userId
type:post/note，帖子/日记
地址：
http://120.25.124.68:5001/medicalManage/api/post/getInfo

```
postId:5999bf80-edc4-11e6-89e4-0fabf77c2771
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取信息成功！",
  "post": {
    "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
    "name": "奈何一笑",
    "account": "18867365368",
     "icon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
    "sex": "男",
    "age": "23",
    "proName": null,
    "cityName": null,
    "disName": null,
    "id": 11,
    "postId": "5999bf80-edc4-11e6-89e4-0fabf77c2771",
    "labelId": null,
    "labelName": null,
    "typeId": "52354ee0-c5fa-11e6-9c21-9ff2d56ab9f3\u0001f259d960-b612-11e6-b7e2-f9d10cb04b78",
    "typeName": "喇叭花",
    "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
    "parentName": "瘦身减肥",
    "title": "切开双眼皮\u0001长沙亚韩整形记录",
    "content": "就弄Monmouth",
    "images": "http://120.25.124.68:5001/upload/image/IMG_20170206_181944.jpg\u0001http://120.25.124.68:5001/upload/image/IMG_20170205_210933.jpg",
    "level": null,
    "type": "post",
    "createdAt": "2017-02-08T06:03:45.000Z",
    "updatedAt": "2017-02-08T06:03:45.000Z",
    "share_count": 0,
    "collect_count": 1,
    "praise_count": 1,
    "comment_count": 17,
   "if_focus_user": null,
    "if_praise_post": 1,
    "if_collect_post": 1,
    "shared_page_url": "http://120.25.124.68:5001/medicalManage/mobile/post?postId=5999bf80-edc4-11e6-89e4-0fabf77c2771"
  }
}
```

<a name="58"></a>
#### 5.8 getInfoAndCommentList：获取详情及评论列表
- 接口地址：/medicalManage/api/post/getInfoAndCommentList
方法：post
参数：
postId:帖子或笔记id


地址：
http://120.25.124.68:5001/medicalManage/api/post/getInfoAndCommentList


```
postId:7fd91130-cd87-11e6-afb5-870770b90a75

{
  "code": "200",
  "msg": "获取信息成功！",
  "ifDz": "null",
  "post": {
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "name": "冷心真心傻傻",
    "account": "18233561909",
    "icon": "image/DSC_0005.JPG",
    "id": 11,
    "postId": "7fd91130-cd87-11e6-afb5-870770b90a75",
    "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "typeName": "精选",
    "parentId": "1",
    "parentName": "整容日记",
    "title": "鼻综合整形记录",
    "content": "术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
    "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "level": null,
    "datems": "1482989253059",
    "type": "note",
    "createdAt": "2016-12-29T05:27:33.000Z",
    "updatedAt": "2016-12-29T05:27:33.000Z",
    "share_count": 0,
    "collect_count": 0,
    "praise_count": 0,
    "comment_count": 1,
    "shared_page_url": "http://120.25.124.68:5001/medicalManage/mobile/post?post_id=7fd91130-cd87-11e6-afb5-870770b90a75"
  },
  "commentlist": [
    {
      "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "小路",
      "user_account": "18233561908",
      "user_icon": "image/DSC_0005.JPG",
      "id": 3,
      "commentId": "e2f96f80-b932-11e6-b682-c5e2e93c9a53",
      "objId": "7fd91130-cd87-11e6-afb5-870770b90a75",
      "objType": "note",
      "content": "这个月花费挺少的嘛",
      "datems": "1480753888889",
      "createdAt": "2016-12-03T08:31:28.000Z",
      "updatedAt": "2016-12-03T08:31:28.000Z",
      "praise_count": 0,
      "comment_count": 0
    }
  ]
}


```

<a name="515"></a>
####5.15 getNoteFromMyFocusUser：根据userid，获取我关注的用户的日记
- 接口地址：/medicalManage/api/post/getNoteFromMyFocusUser
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/post/getNoteFromMyFocusUser

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取我关注的用户的日记！",
  "result": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "image/DSC_0005.JPG",
      "id": 1,
      "postId": "3d953950-cf28-11e6-8cdb-d360ff27a8f8",
      "labelId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
      "labelName": "开内眼角",
      "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "typeName": "精选",
      "parentId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
      "parentName": "整形日记",
      "title": "鼻综合整形记录",
      "content": "术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg",
      "level": null,
      "type": "note",
      "createdAt": "2016-12-31T07:10:42.000Z",
      "updatedAt": "2016-12-31T07:10:42.000Z",
      "share_count": null,
      "praise_count": 2,
      "comment_count": null,
      "if_praise": 2,
      "if_focus": 25
    }
  ]
}
```


<a name="515_1"></a>
#### 5.15_1 getNoteFromFocusMeUser：根据userid，获取关注我的用户的日记
- 接口地址：/medicalManage/api/post/getNoteFromFocusMeUser
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/user/getNoteFromFocusMeUser

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取关注我的用户的日记！",
  "result": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "id": 3,
      "postId": "4a647d80-cf28-11e6-8cdb-d360ff27a8f8",
      "labelId": "52354ee0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "labelName": null,
      "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "typeName": "精选",
      "parentId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
      "parentName": "整形日记",
      "title": "鼻综合整形记录",
      "content": "术后60天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg",
      "level": null,
      "type": "note",
      "createdAt": "2016-12-31T07:11:03.000Z",
      "updatedAt": "2016-12-31T07:11:03.000Z",
      "share_count": null,
      "praise_count": 1,
      "comment_count": null,
      "if_praise": 1,
      "if_focus": 1
    },
  ...
  ]
}
```


<a name="516"></a>
####5.16 getPostFromMyFocusUser：根据userid，获取我关注的用户的帖子
- 接口地址：/medicalManage/api/post/getPostFromMyFocusUser
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/user/getPostFromMyFocusUser

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
{
  "code": "200",
  "msg": "获取我关注的用户的帖子！",
  "result": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "image/DSC_0005.JPG",
      "id": 4,
      "postId": "e684a400-cf29-11e6-929e-4fce1bb7475f",
      "labelId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "labelName": "开外眼角",
      "typeId": "2d7d7790-b613-11e6-b7e2-f9d10cb604b7",
      "typeName": null,
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": "减肥1个月啦",
      "content": "减肥一个月了，看这效果明显吧，哈哈哈，以前那个肉呼呼的胖妹纸不见了...现在下巴秀气而高挺了吧~~哈哈，现在照镜子总忍不住臭美一番~~~需要传授经验吗",
      "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg",
      "level": null,
      "type": "post",
      "createdAt": "2016-12-31T07:22:34.000Z",
      "updatedAt": "2016-12-31T07:22:34.000Z",
      "share_count": null,
      "praise_count": 1,
      "comment_count": null,
      "if_praise": null,
      "if_focus": 2
    }
  ]
}
```


<a name="517"></a>
####5.17 getHotLabelListOfPost：获取热门日记标签
- 接口地址：/medicalManage/api/post/getHotLabelListOfPost
方法：post
参数：
type:note

地址：
http://localhost:5001/medicalManage/api/post/getHotLabelListOfPost

```
type:note

{
  "code": "200",
  "msg": "获取成功！",
  "list": [
    "9325bd70-c656-11e6-8ca5-37b03af6926d",
    "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3"
  ]
}

```


<a name="518"></a>
####5.18 getHotLabelListOfPost：获取热门帖子标签
- 接口地址：/medicalManage/api/post/getHotLabelListOfPost
方法：post
参数：
type:note

地址：
http://localhost:5001/medicalManage/api/post/getHotLabelListOfPost


```
type:note

{
  "code": "200",
  "msg": "获取成功！",
  "list": [
    "f259d960-b612-11e6-b7e2-f9d10cb604b7",
    "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3"
  ]
}
```




<a name="519_1"></a>
####5.19_1 getMyPraiseList：根据userid，获取我点赞的列表
- 接口地址：/medicalManage/api/post/getMyPraiseList
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/post/getMyPraiseList

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
{
  "code": "200",
  "msg": "获取我点赞的列表成功！",
  "result": [
    {
      "praise_createdAt": "2017-04-23T01:56:24.000Z",  //点赞时间
      //点赞人信息
      "praise_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "praise_userName": "奈何一笑",
      "praise_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      //被点赞人信息
      "praised_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "praised_userName": "奈何一笑",
      "praised_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      //点赞帖子/日记信息
      "id": 11,
      "postId": "5999bf80-edc4-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "itemId": "52354ee0-c5fa-11e6-9c21-9ff2d56ab9f3\u0001f259d960-b612-11e6-b7e2-f9d10cb04b78",
      "itemName": null,
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": "切开双眼皮\u0001长沙亚韩整形记录",
      "content": "就弄Monmouth",
      "images": "http://120.25.124.68:5001/upload/image/IMG_20170206_181944.jpg\u0001http://120.25.124.68:5001/upload/image/IMG_20170205_210933.jpg",
      "level": null,
      "type": "post",
      "createdAt": "2017-02-08T06:03:45.000Z",
      "updatedAt": "2017-02-08T06:03:45.000Z"
    },
   ...
  ]
}
```


<a name="519_2"></a>
#### 5.19_2 getMyPraisedList：根据userid，获取点赞我的列表
- 接口地址：/medicalManage/api/post/getMyPraisedList
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/post/getMyPraisedList

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取点赞我的列表成功！",
  "result": [
    {
      "praise_createdAt": "2017-04-23T01:56:24.000Z",//点赞时间
      //点赞人信息
      "praise_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "praise_userName": "奈何一笑",
      "praise_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      //被点赞人信息
      "praised_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "praised_userName": "奈何一笑",
      "praised_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
        //点赞帖子/日记信息
      "id": 11,
      "postId": "5999bf80-edc4-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "itemId": "52354ee0-c5fa-11e6-9c21-9ff2d56ab9f3\u0001f259d960-b612-11e6-b7e2-f9d10cb04b78",
      "itemName": null,
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": "切开双眼皮\u0001长沙亚韩整形记录",
      "content": "就弄Monmouth",
      "images": "http://120.25.124.68:5001/upload/image/IMG_20170206_181944.jpg\u0001http://120.25.124.68:5001/upload/image/IMG_20170205_210933.jpg",
      "level": null,
      "type": "post",
      "createdAt": "2017-02-08T06:03:45.000Z",
      "updatedAt": "2017-02-08T06:03:45.000Z"
    }
  ]
}
```


 
<a name="520_1"></a>
#### 5.20_1 getMyCommentList：根据userid，获取我评论的列表
- 接口地址：/medicalManage/api/post/getMyCommentList
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/post/getMyCommentList

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取我评论的列表成功！",
  "result": [
    {
    //评论信息
      "comment_createdAt": "2017-04-13T02:06:28.000Z",
      "content": "图兔兔",
      //评论人
      "comment_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "comment_userName": "奈何一笑",
      "comment_userIcon": "http://120.25.124.68:5001/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      //被评论人
      "commented_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "commented_userName": "奈何一笑",
      "commented_userIcon": "http://120.25.124.68:5001/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      //评论对象
      "id": 10,
      "postId": "c1b17b80-edb0-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "itemId": "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "itemName": "埋线双眼皮",
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": null,
      "images": "http://120.25.124.68:5001/upload/image/IMG_20170205_210933.jpg",
      "level": null,
      "type": "note",
      "createdAt": "2017-02-08T03:43:30.000Z",
      "updatedAt": "2017-02-08T03:43:30.000Z"
    }
  ]
}
```

<a name="520_2"></a>
#### 5.20_2 getMyCommentedList：根据userid，获取评论我的列表
- 接口地址：/medicalManage/api/post/getMyCommentedList
方法：post
参数：
userId:用户id
page:页码，默认1
limit:条数，默认10

地址：
http://localhost:5001/medicalManage/api/post/getMyCommentedList

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b
{
  "code": "200",
  "msg": "获取点赞我的列表成功！",
  "result": [
    {
     //评论信息
      "comment_createdAt": "2017-04-13T02:06:28.000Z",
      "content": "图兔兔",
       //评论人
      "comment_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "comment_userName": "奈何一笑",
      "comment_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
        //被评论人
        "commented_userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "commented_userName": "奈何一笑",
      "commented_userIcon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      //评论对象
      "id": 10,
      "postId": "c1b17b80-edb0-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "itemId": "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "itemName": "埋线双眼皮",
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": null,
      "images": "http://120.25.124.68:5001/upload/image/IMG_20170205_210933.jpg",
      "level": null,
      "type": "note",
      "createdAt": "2017-02-08T03:43:30.000Z",
      "updatedAt": "2017-02-08T03:43:30.000Z"
    },
...
  ]
}
```




<a name="521"></a>
#### 5.21 getNoteAndPostFromMyFocusUser：根据userid，获取我关注的用户的帖子和日记
- 接口地址：/medicalManage/api/post/getNoteAndPostFromMyFocusUser
方法：post
参数：
userId:用户id

地址：
http://localhost:5001/medicalManage/api/post/getNoteAndPostFromMyFocusUser

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取我关注的用户的日记！",
  "result": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "id": 2,
      "postId": "48722360-cf28-11e6-8cdb-d360ff27a8f8",
      "labelId": "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "labelName": "埋线双眼皮",
      "itemId": null,
      "itemName": null,
      "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "typeName": "精选",
      "parentId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
      "parentName": "整形日记",
      "title": "鼻综合整形记录",
      "content": "术后30天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg",
      "level": null,
      "type": "note",
      "createdAt": "2016-12-31T07:11:00.000Z",
      "updatedAt": "2016-12-31T07:11:00.000Z",
      "share_count": null,
      "praise_count": null,
      "comment_count": null,
      "if_praise": null,
      "if_focus": 1
    }
  ]
}
```


<a name="522"></a>
#### 5.22 getNoteAndPostFromFocusMeUser：根据userid，获取我关注的用户的帖子和日记
- 接口地址：/medicalManage/api/post/getNoteAndPostFromFocusMeUser
方法：post
参数：
userId:用户id

地址：
http://localhost:5001/medicalManage/api/post/getNoteAndPostFromFocusMeUser

```
userId:4b213800-c35a-11e6-a2cd-e377470ab12b

{
  "code": "200",
  "msg": "获取关注我的用户的日记！",
  "result": [
    {
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "user_name": "奈何一笑",
      "user_account": "18867365368",
      "user_icon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      "id": 14,
      "postId": "db3ed5b0-52a1-11e7-a18d-f5ce3e885c34",
      "labelId": null,
      "labelName": null,
      "itemId": null,
      "itemName": null,
      "typeId": "dd55e0c0-529f-11e7-89e9-bde29f2de843",
      "typeName": null,
      "parentId": null,
      "parentName": null,
      "title": "心情好",
      "content": "好心情",
      "images": "http://120.25.124.68:5001/upload/other/vv7VHg9FOHaxJAKjE5jptCo8.jpg\u0001http://120.25.124.68:5001/upload/other/sYf90-xPcl8_eszX0mD2mxqh.jpg",
      "level": null,
      "type": "note",
      "createdAt": "2017-06-16T14:41:17.000Z",
      "updatedAt": "2017-06-16T14:41:17.000Z",
      "share_count": null,
      "praise_count": null,
      "comment_count": null,
      "if_praise": null,
      "if_focus": null
    }
  ]
}
```
<a name="6"></a>
### 6. comment：评论

<a name="61"></a>
#### 6.1 addComment：创建评论
- 接口地址：/medicalManage/api/comment/addComment
方法：post
参数：
objId:评论对象的Id（必填）
objType:评论对象的类型，参考下表（必填）
userId:当前用户id(必填)
content:(必填)
parentId:父评论的id（不是uuid,是id,uuid查询速度慢），默认是0（一级评论）


| 序号       |parent_type|   说明| 其他|
| -----  |:----:       	  	   |  ----:| 
| 1      | news |  新闻 |  |
| 2       | post|  帖子	|   |
| 3       | note|  日记	|   |
| 4       | notebook|  日记本	|   |

地址：
http://120.25.124.68:5001/medicalManage/api/comment/addComment

```
objId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f
objType:news
userId:4e3512f0-b60d-11e6-9ed3-9184a13c35d7
content:为什么大家都说不关自己事呢【捂脸】
parentId:2

{
  "code": "200",
  "msg": "评论成功！",
  "item": {
    "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
    "objType": "news",
    "userId": "4e3512f0-b60d-11e6-9ed3-9184a13c35d7",
    "content": "为什么大家都说不关自己事呢【捂脸】",
    "parentId": 2,
    "commentId": "1fe9af90-18e7-11e7-981b-37c411c319a0",
    "createdAt": "2017-04-04T03:31:01.019Z",
    "updatedAt": "2017-04-04T03:31:01.019Z",
    "id": 23
  },
  "count": 3,
  "list": [  //新的评论列表
    {
      "id": 1,
      "commentId": "98bafc70-b632-11e6-a1f1-2f9175fb66f5",
      "parentId": 0,
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "objType": "news",
      "userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "content": "又限购？可是又管我什么事呢",
      "createdAt": "2016-11-29T12:51:50.000Z",
      "updatedAt": "2016-11-29T12:51:50.000Z",
      "comment_userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "comment_userName": "小蔡",
      "comment_userIcon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "commented_userId": null,
      "commented_userName": null,
      "commented_userIcon": null,
      "praise_count": 1,
      "if_praise": null
    },
    ...
  ]
}
```


<a name="62"></a>
#### 6.2 deleteComment：删除评论
- 接口地址：/medicalManage/api/comment/deleteComment
方法：post
参数：
comment_id:

地址：
http://120.25.124.68:5001/medicalManage/api/comment/deleteComment

```
{
  "code": "200",
  "msg": "操作成功！！",
  "item": [
    {
      "id": 3,
      "commentId": "e30d0f10-b633-11e6-b3e4-33ad28475035",
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "objType": "news",
      "userId": "4e3512f0-b60d-11e6-9ed3-9184a13c35d7",
      "content": "又限购？",
      "datems": "1480424465025",
      "createdAt": "2016-11-29T13:01:05.000Z",
      "updatedAt": "2016-11-29T13:01:05.000Z"
    }
  ]
}
```

<a name="63"></a>
#### 6.3 getListByParentId：根据parentid获取评论列表(删除)
- 接口地址：/medicalManage/api/comment/getListByParentId
方法：post
参数：
objId:

地址：
http://120.25.124.68:5001/medicalManage/api/comment/getListByParentId

```
{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 2,
  "list": [
    {
      "userId": "4e3512f0-b60d-11e6-9ed3-9184a13c35d7",
      "user_name": "小璐",
      "user_account": "18233561908",
      "user_icon": "image/DSC_0005.JPG",
      "id": 1,
      "commentId": "98bafc70-b632-11e6-a1f1-2f9175fb66f5",
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "objType": "news",
      "content": "又限购？可是又管我什么事呢",
      "datems": "1480423910840",
      "createdAt": "2016-11-29T12:51:50.000Z",
      "updatedAt": "2016-11-29T12:51:50.000Z"
    },
    {
      "userId": "4e3512f0-b60d-11e6-9ed3-9184a13c35d7",
      "user_name": "小璐",
      "user_account": "18233561908",
      "user_icon": "image/DSC_0005.JPG",
      "id": 2,
      "commentId": "ad731800-b632-11e6-a1f1-2f9175fb66f5",
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "objType": "news",
      "content": "呵呵，也不关我事",
      "datems": "1480423945601",
      "createdAt": "2016-11-29T12:52:25.000Z",
      "updatedAt": "2016-11-29T12:52:25.000Z"
    }
  ]
}
```


<a name="64"></a>
#### 6.4 getListByObjId：根据对象Id获取评论列表
- 接口地址：/medicalManage/api/comment/getListByObjId
方法：post
参数：
objId:对象id(uuid)，如newsId(必填)
rootId:父评论的id，默认为0。若需要获取某个评论的子评论列表，root为该评论的id
depth:评论层级深度，默认获取所有层级评论。depth=1时，只获取层级为1的评论
userId:当前登录用户的id

地址：
http://localhost:5001/medicalManage/api/comment/getListByObjId
```
获取newsId=cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f层级为1的所有评论列表

objId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f
rootId:0
depth:1
userId：c77264f0-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 1,
  "list": [
    {
      "id": 1,
      "commentId": "98bafc70-b632-11e6-a1f1-2f9175fb66f5",
      "parentId": 0, //parentId=0，层级为1
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",  //newsId
      "objType": "news",
      "userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "content": "又限购？可是又管我什么事呢",
      "createdAt": "2016-11-29T12:51:50.000Z",
      "updatedAt": "2016-11-29T12:51:50.000Z",
      "comment_userId": "db8ebf20-baae-11e6-b180-872a6e363290",  //评论用户
      "comment_userName": "小蔡",
      "commented_userId": null,  //被评论用户
      "commented_userName": null
    }
  ]
}
```

```
获取评论id=1的评论及其子评论

objId:cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f
rootId:1
userId:c77264f0-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 2,
  "list": [
    {
      "id": 1,
      "commentId": "98bafc70-b632-11e6-a1f1-2f9175fb66f5",
      "parentId": 0,
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "objType": "news",
      "userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "content": "又限购？可是又管我什么事呢",
      "createdAt": "2016-11-29T12:51:50.000Z",
      "updatedAt": "2016-11-29T12:51:50.000Z",
      "comment_userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "comment_userName": "小蔡",
      "comment_userIcon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "commented_userId": null,
      "commented_userName": null,
      "commented_userIcon": null,
      "praise_count": 1,
      "if_praise": 1
    },
    {
      "id": 2,
      "commentId": "ad731800-b632-11e6-a1f1-2f9175fb66f5",
      "parentId": 1,
      "objId": "cc2c5d40-b62a-11e6-b4a2-b5f0bfcaa19f",
      "objType": "news",
      "userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "content": "呵呵，也不关我事",
      "createdAt": "2016-11-29T12:52:25.000Z",
      "updatedAt": "2016-11-29T12:52:25.000Z",
      "comment_userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "comment_userName": "小蔡",
      "comment_userIcon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "commented_userId": "db8ebf20-baae-11e6-b180-872a6e363290",
      "commented_userName": "小蔡",
      "commented_userIcon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "praise_count": null,
      "if_praise": null
    }
  ]
}
```

<a name="7"></a>
### 7. user：用户
<a name="71"></a>
#### 7.1 register：用户注册
- 接口地址：/medicalManage/api/user/register
方法：post(form-data)

居民段参数：
account:
password:
platform: resident
name:
icon:
sex:
age:
desc:
proName://省
proId
cityName://市
cityId
disName://区
disId
address://详细地址
type:user/manager 不填，默认user

医生端参数：
account:
password:
platform: doctor
name:
icon:
sex:
age:
desc:
docTitle: //医生头衔
docPhone://医生电话
docGoodAt://医生擅长
idCardNum://身份证号
proName://省
proId
cityName://市
cityId
disName://区
disId
address://详细地址
hosName: //医院
hosId: 
roomName: //科室
roomId: 
type:user/manager 不填，默认user

地址：
http://120.25.124.68:5001/medicalManage/api/user/register

```
{
  "code": "200",
  "msg": "注册成功！",
  "item": {
    "account": "18233561909",
    "password": "123456",
    "platform": "resident",
    "name": "小希",
    "sex": "女",
    "age": "16",
    "desc": "小女子年方28",
    "city": "上海",
    "address": "上海市浦东新区",
    "icon": "http://120.25.124.68:5000/upload/image/DSC_0005.JPG",
    "userId": "b4709e30-b915-11e6-b039-7de1a10ca0f6",
    "points": "10",
    "datems": "1480741355413",
    "type": "user",
    "createdAt": "2016-12-03T05:02:35.429Z",
    "updatedAt": "2016-12-03T05:02:35.429Z",
    "id": 10
  }
},
 "im_code": 200,
  "im_result": {
    "action": "post",
    "application": "276f3750-b639-11e6-928e-db3fd954d021",
    "path": "/users",
    "uri": "https://a1.easemob.com/1154161025115110/kangmi/users",
    "entities": [
      {
        "uuid": "b3314060-b915-11e6-b4e9-412558f1876e",
        "type": "user",
        "created": 1480741353318,
        "modified": 1480741353318,
        "username": "18233561909",
        "activated": true
      }
    ],
    "timestamp": 1480741353326,
    "duration": 0,
    "organization": "1154161025115110",
    "applicationName": "kangmi"
  },
```
```
医生注册参数：
account:13721264200
password:123
platform:doctor
name:丁医生
sex:男
age:43
desc:从事医疗美容10多年，经验丰富，好评如潮
docTitle:副主任
docPhone:021-20610091
docGoodAt:丰胸丰臀
idCardNum:34220119670901
proName:湖南省
proId:18
cityName:长沙市
cityId:177
disName:岳麓区
disId:1558
address: 咸嘉湖路8002

{
  "code": "200",
  "msg": "注册成功！",
  "item": {
    "account": "13721264200",
    "password": "123",
    "platform": "doctor",
    "name": "丁医生",
    "sex": "男",
    "age": "43",
    "desc": "从事医疗美容10多年，经验丰富，好评如潮",
    "docTitle": "副主任",
    "docPhone": "021-20610091",
    "docGoodAt": "丰胸丰臀",
    "idCardNum": "34220119670901",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "address": " 咸嘉湖路8002",
    "icon": "http://120.25.124.68:5001/upload/image/u=3557557066,2008108873&fm=85&s=F112519C6822AC9AC38C9CAB0300B091.jpg",
    "userId": "3dd4e6a0-d558-11e6-ac80-35e73a3a9d09",
    "points": "10",
    "datems": "1483848565258",
    "type": "user",
    "createdAt": "2017-01-08T04:09:25.266Z",
    "updatedAt": "2017-01-08T04:09:25.266Z",
    "id": 54
  },
  "im_code": 200,
  "im_result": {
    "action": "post",
    "application": "240c5d60-c5c8-11e6-bafb-c7cf17151b24",
    "path": "/users",
    "uri": "https://a1.easemob.com/1117161219115882/kangmi/users",
    "entities": [
      {
        "uuid": "3d35c070-d558-11e6-b6b2-03c2b13f7709",
        "type": "user",
        "created": 1483848564215,
        "modified": 1483848564215,
        "username": "13721264200",
        "activated": true,
        "nickname": "丁医生"
      }
    ],
    "timestamp": 1483848564222,
    "duration": 0,
    "organization": "1117161219115882",
    "applicationName": "kangmi"
  }
}
```
```
账号在数据库不存在，im存在
{
  "code": "200",
  "msg": "注册成功！",
  "item": {
    "account": "18867365368",
    "password": "123",
    "platform": "resident",
    "name": "测试用户",
    "sex": "女",
    "age": "23",
    "desc": "",
    "city": "上海",
    "address": "浦东新区",
    "userId": "e7533570-c332-11e6-8e58-bd9d8d35de39",
    "points": "10",
    "datems": "1481853407816",
    "type": "user",
    "createdAt": "2016-12-16T01:56:47.834Z",
    "updatedAt": "2016-12-16T01:56:47.834Z",
    "id": 34
  },
  "im_code": 201  //im已经存在用户
}
```
```
账号在数据库中已经存在
{
  "code": "400",
  "msg": "该账号已注册该应用！"
}
```
<a name="72"></a>
#### 7.2 updateUser：修改用户
- 接口地址：/medicalManage/api/user/updateUser
方法：post(form-data)
参数：
居民段参数：
userId:
password://新密码
name://昵称
icon://头像
sex://性别
age://年龄
desc://个性签名
proName://省
proId
cityName://市
cityId
disName://区
disId
address://详细地址
hosName: //医院
hosId: 
roomName: //科室
roomId: 


医生端参数：
userId:
password://新密码
name://姓名
icon://头像
sex://性别
age://年龄
desc://简介
docTitle: //医生头衔
docPhone://医生电话
docGoodAt://医生擅长
idCardNum://身份证号
proName://省
proId
cityName://市
cityId
disName://区
disId
address://详细地址


地址：
http://120.25.124.68:5001/medicalManage/api/user/updateUser

```
成功注册：
{
  "code": "200",
  "msg": "修改成功",
  "item": {
    "userId": "84c62720-b601-11e6-a771-9d5e4b5b83fe",
    "name": "小武",
    "password": "123456",
    "account": "18233561907",
    "hospital": "上海红房子医院",
    "room": "妇科",
    "position": "实习生",
    "city": "上海",
    "address": "上海市闵行区",
    "type": "user",
    "icon": "http://120.25.124.68:5000/upload/image/DSC_0005.JPG",
    "sex": "女",
    "age": "23",
    "desc": "美女",
    "datems": "1480402832019",
    "points": "10",
    "platform": "doctor",
    "createdAt": "2016-11-29T07:00:32.000Z",
    "updatedAt": "2016-11-29T07:00:32.000Z",
    "ID": 1,
    "focused_count": null,
    "focus_count": null,
    "post_count": null
  }
}
注册失败：
{
  "code": "400",
  "msg": "该账号已注册该应用！"
}
```



<a name="72_1"></a>
#### 7.2_1 forget：忘记密码
- 接口地址：/medicalManage/api/user/forget
方法：post
参数：
account: 
password:
platform:resident/doctor

```
account:13721264201
password:123
platform:

{
  "code": "400",
  "msg": "缺少必要参数！"
}


account:13721264201
password:123
platform:doctor

{
  "code": "400",
  "msg": "你要修改的用户是居民端用户，请登录居民端进行修改！"
}

account:13721264202
password:123
platform:resident

{
  "code": "400",
  "msg": "你要修改的用户不存在！"
}


account:18233561909
password:123
platform:resident

{
  "code": "200",
  "msg": "修改成功",
  "item": {
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "name": "小美",
    "password": "123",
    "account": "18233561909",
    "hospital": null,
    "room": null,
    "position": null,
    "city": "上海",
    "address": "上海市浦东新区",
    "type": "user",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "sex": "女",
    "age": "18",
    "desc": "在最好的年纪遇到你",
    "datems": "1480743590131",
    "points": "25",
    "platform": "resident",
    "createdAt": "2016-12-03T05:39:50.000Z",
    "updatedAt": "2016-12-03T05:39:50.000Z",
    "ID": 15,
    "focused_count": 1,  //被关注量/粉丝量
    "focus_count": 9,  //关注量
    "post_count": 4    //发帖量
  }
}
```


<a name="73"></a>
#### 7.3 deleteUser：删除用户
- 接口地址：/medicalManage/api/user/deleteUser
方法：post
参数：
userId:

地址：
http://120.25.124.68:5001/medicalManage/api/user/deleteUser

```
 {
  "code": "200",
  "msg": "操作成功！！",
  "result": [
    {
      "ID": 2,
      "userId": "dd4b64a0-b60b-11e6-9cff-e9bdefe92e69",
      "name": "wuwanyu",
      "password": "123456",
      "account": "18233561907",
      "hospital": "上海红房子医院",
      "room": "妇科",
      "position": "实习生",
      "city": "上海",
      "address": "上海市浦东新区",
      "type": "user",
      "icon": null,
      "sex": "女",
      "age": "23",
      "desc": "美女",
      "datems": "1480407275499",
      "points": "10",
      "platform": "doctor",
      "createdAt": "2016-11-29T08:14:35.000Z",
      "updatedAt": "2016-11-29T08:14:35.000Z"
    }
  ]
}
```

<a name="74"></a>
#### 7.4 login：登录
- 接口地址：/medicalManage/api/user/login
方法：post
参数：
password:
account:
platform:


| 序号   | platform       | 说明                           | 
| ---- | ---------- | ------------------------------- | 
| 1      | resident |居民端用户  | 
| 2      |doctor |医生端用户  |


地址：
http://120.25.124.68:5001/medicalManage/api/user/login

```
password:123456
account:18233561908
platform:resident

{
  "code": "200",
  "msg": "登录成功！",
  "item": {
    "userId": "4e3512f0-b60d-11e6-9ed3-9184a13c35d7",
    "name": "小璐",
    "password": "123456",
    "account": "18233561908",
    "hospital": null,
    "room": null,
    "position": null,
    "city": "上海",
    "address": "上海市浦东新区",
    "type": "user",
    "icon": "image/DSC_0005.JPG",
    "sex": "女",
    "age": "23",
    "desc": "美女",
    "datems": "1480407894432",
    "points": "10",
    "platform": "resident",
    "createdAt": "2016-11-29T08:24:54.000Z",
    "updatedAt": "2016-11-29T08:24:54.000Z",
    "ID": 3,
    "focused_count": null,
    "focus_count": null,
    "post_count": null
  }
}

password:12345
account:18233561908
platform:resident

{
  "code": "201",
  "msg": "密码输入错误！"
}


password:123456
account:18233561908
platform:doctor

{
  "code": "202",
  "msg": "账号不存在"
}

```



<a name="750"></a>
#### 7.50 adminReg：管理员注册
- 接口地址：/medicalManage/api/user/adminReg
方法：post
参数：
password:
account:
name:
platform:resident/doctor
type:manager

地址：
http://120.25.124.68:5001/medicalManage/api/user/adminReg
```

```

<a name="75"></a>
#### 7.5 adminLogin：管理员登录
- 接口地址：/medicalManage/api/user/adminLogin
方法：post
参数：
password:
account:
vnum:验证码
platform:
type:manager

地址：
http://120.25.124.68:5001/medicalManage/api/user/adminLogin
```
{
  "code": "200",
  "msg": "登录成功！",
  "user":{
      "userId": "1010",
      "name": "居民端管理员",
      "password": "123",
      "account": "1010",
      "hospital": null,
      "room": null,
      "position": null,
      "city": null,
      "address": null,
      "type": "manager",
      "icon": null,
      "sex": null,
      "age": null,
      "desc": null,
      "datems": "1480407894432",
      "points": null,
      "platform": "resident",
      "createdAt": "2016-11-29T08:24:54.000Z",
      "updatedAt": "2016-11-29T08:24:54.000Z",
      "ID": 4,
      "focused_count": null,
      "focus_count": null,
      "post_count": null
    }
}

```


<a name="76"></a>
#### 7.6 adminLogout：管理员退出登陆
- 接口地址：/medicalManage/api/user/adminLogout
方法：post
参数：
userId:

地址：
http://120.25.124.68:5001/medicalManage/api/user/adminLogout
```


```


<a name="77"></a>
#### 7.7 getPersonHomePage：根据friendId，获取用户主页
- 接口地址：/medicalManage/api/user/getPersonHomePage
方法：post
参数：
friendId:对方id
userId:登陆用户的id

地址：
http://120.25.124.68:5001/medicalManage/api/user/getPersonHomePage

```
friendId:13
userId:8

{
  "code": "200",
  "msg": "获取列表成功！",
   "isFocused": "yes",
  "userInfo": {
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "name": "冷心真心傻傻",
    "password": "123",
    "account": "18233561909",
    "hospital": null,
    "room": null,
    "position": null,
    "city": "长沙",
    "address": "长沙市XX区XX路XX号",
    "type": "user",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "sex": "女",
    "age": "18",
    "desc": "爱美之心人皆有之",
    "datems": "1480743590131",
    "points": "34",
    "platform": "resident",
    "createdAt": "2016-12-03T05:39:50.000Z",
    "updatedAt": "2016-12-03T05:39:50.000Z",
    "ID": 15,
    "focused_count": 1,
    "focus_count": 11,
    "praise_count": 2
  },
  "postList": [ //帖子列表
    {
      "id": 4,
      "postId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
      "typeId": null,
      "typeName": null,
      "parentId": "dc20c840-b935-11e6-b0ee-23915c83f0c3",
      "parentName": "华晨宇歌友会",
      "title": "华晨宇12月20日南京演唱会有人同行吗？",
      "content": "自从听了“天籁之音”从此对花花路转粉了...",
      "images": "http://120.25.124.68:5001/upload/image/2f54fc091600dce8c811533b50707002_b.jpg",
      "level": null,
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "datems": "1480758695261",
      "type": "post",
      "createdAt": "2016-12-03T09:51:35.000Z",
      "updatedAt": "2016-12-03T09:51:35.000Z",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "user_desc": "爱美之心人皆有之",
      "praise_count": 1,
      "share_count": 1,
      "comment_count": 1
    },
    ...
  ],
  "noteList": [  //日记列表
    {
      "id": 11,
      "postId": "7fd91130-cd87-11e6-afb5-870770b90a75",
      "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "typeName": "精选",
      "parentId": "1",
      "parentName": "整容日记",
      "title": "鼻综合整形记录",
      "content": "术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
      "level": null,
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "datems": "1482989253059",
      "type": "note",
      "createdAt": "2016-12-29T05:27:33.000Z",
      "updatedAt": "2016-12-29T05:27:33.000Z",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "user_desc": "爱美之心人皆有之",
      "praise_count": 0,
      "share_count": 0,
      "comment_count": 1
    },
    ...
  ],
  "postAndNoteList": [  //日记和帖子列表
    {
      "id": 11,
      "postId": "7fd91130-cd87-11e6-afb5-870770b90a75",
      "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "typeName": "精选",
      "parentId": "1",
      "parentName": "整容日记",
      "title": "鼻综合整形记录",
      "content": "术后100天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
      "level": null,
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "datems": "1482989253059",
      "type": "note",  //类别，标识是日记还是帖子
      "createdAt": "2016-12-29T05:27:33.000Z",
      "updatedAt": "2016-12-29T05:27:33.000Z",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "user_desc": "爱美之心人皆有之",
      "praise_count": 0,
      "share_count": 0,
      "comment_count": 1
    },
    ...
  ]
}

{
  "code": "200",
  "msg": "获取列表成功！",
  "isFocused": "null",
  "userInfo": {
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "name": "冷心真心傻傻",
    "password": "123",
    "account": "18233561909",
    "hospital": null,
    "room": null,
    "position": null,
    "city": "长沙",
    "address": "长沙市XX区XX路XX号",
    "type": "user",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "sex": "女",
    "age": "18",
    "desc": "爱美之心人皆有之",
    "datems": "1480743590131",
    "points": "25",
    "platform": "resident",
    "createdAt": "2016-12-03T05:39:50.000Z",
    "updatedAt": "2016-12-03T05:39:50.000Z",
    "ID": 15,
    "focused_count": 1,
    "focus_count": 9,
    "praise_count": 2
  },
  "postList": [
    {
      "id": 4,
      "postId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
      "typeId": null,
      "typeName": null,
      "parentId": "dc20c840-b935-11e6-b0ee-23915c83f0c3",
      "parentName": "华晨宇歌友会",
      "title": "华晨宇12月20日南京演唱会有人同行吗？",
      "content": "自从听了“天籁之音”从此对花花路转粉了...",
      "images": "http://120.25.124.68:5001/upload/image/2f54fc091600dce8c811533b50707002_b.jpg",
      "level": null,
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "datems": "1480758695261",
      "createdAt": "2016-12-03T09:51:35.000Z",
      "updatedAt": "2016-12-03T09:51:35.000Z",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "user_desc": "爱美之心人皆有之",
      "praise_count": 1,
      "share_count": 1,
      "comment_count": 1
    },
    ...
  ],
  "noteList": [
    {
      "id": 6,
      "noteId": "9a777620-c991-11e6-af22-4558735d9a46",
      "level": "0",
      "typeId": "7afc7da0-c990-11e6-af22-4558735d9a46",
      "typeName": "精选",
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "title": "鼻综合整形记录2",
      "icon": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg",
      "content": "术后34天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "from": "",
      "datems": "1482553788034",
      "createdAt": "2016-12-24T04:29:48.000Z",
      "updatedAt": "2016-12-24T04:29:48.000Z",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "collect_count": 0,
      "praise_count": 0,
      "comment_count": 0
    },
   ...
  ]
}
```


<a name="7.7_1"></a>
#### 7.7_1 根据账号，获取用户信息列表
- 接口地址：/medicalManage/api/user/getUserListByAccount
方法：post
参数：
userId:当前用户id
accountStr:账号列表，英文逗号分隔
mobiNameStr:手机名称列表，英文逗号分隔

地址：
http://120.25.124.68:5001/medicalManage/api/user/getUserListByAccount

```
accountStr:18233561908,18233561909
mobiNameStr:小吴,小妹
userId:13

{
  "code": "200",
  "msg": "获取信息成功！",
  "result": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "name": "冷心真心傻傻",
      "password": "123",
      "account": "18233561909",
      "hospital": null,
      "room": null,
      "position": null,
      "city": "长沙",
      "address": "长沙市XX区XX路XX号",
      "type": "user",
      "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "sex": "女",
      "age": "18",
      "desc": "爱美之心人皆有之",
      "datems": "1480743590131",
      "points": "25",
      "platform": "resident",
      "createdAt": "2016-12-03T05:39:50.000Z",
      "updatedAt": "2016-12-03T05:39:50.000Z",
      "ID": 15,
      accountStr:18233561908,18233561909,
      "if_focus": 1,  //是否关注
	  "mobiName": "小妹"  //手机备注
    },
    ...
  ]
}
```

<a name="7.7_2"></a>
#### 7.7_2  根据昵称/手机号查询用户
- 接口地址：/medicalManage/api/user/queryUserByKeyword
方法：post
参数：
keyword:昵称/手机号
platform:平台 doctor/resident，不输入默认包括两个平台的用户
地址：
http://120.25.124.68:5001/medicalManage/api/user/queryUserByKeyword
说明：查询用户包括医生端+居民端
```
keyword:冷心真心
{
  "code": "200",
  "msg": "获取信息成功！",
  "result": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "name": "冷心真心傻傻",
      "password": "123456",
      "account": "18233561909",
      "hosName": null,
      "hosId": null,
      "roomName": null,
      "roomId": null,
      "docTitle": null,
      "docPhone": null,
      "docGoodAt": null,
      "idCardNum": null,
      "proName": null,
      "proId": null,
      "cityName": null,
      "cityId": null,
      "disName": null,
      "disId": null,
      "address": "长沙市XX区XX路XX号",
      "type": "user",
      "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "sex": "女",
      "age": "18",
      "desc": "爱美之心人皆有之",
      "points": "52",
      "platform": "resident",
      "ifAuthed": null,
      "createdAt": "2016-12-03T05:39:50.000Z",
      "updatedAt": "2016-12-03T05:39:50.000Z",
      "ID": 15,
      "post_count": 3,
      "note_count": 3
    }
  ]
}
```

<a name="78"></a>
#### 7.8 list：获取用户列表
- 接口地址：/medicalManage/api/user/list
方法：post
参数：
platform:所属平台，doctor/resident
type:用户类型，user/manager
keyword:关键字
page:页码，默认0
limit:每页条数，默认10

地址：
http://120.25.124.68:5001/medicalManage/api/user/list

```
platform:resident
type:user

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 13,
  "list": [
    {
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "name": "冷心真心傻傻",
      "password": "123",
      "account": "18233561909",
      "hosName": null,
      "hosId": null,
      "roomName": null,
      "roomId": null,
      "docTitle": null,
      "docPhone": null,
      "docGoodAt": null,
      "idCardNum": null,
      "proName": null,
      "proId": null,
      "cityName": null,
      "cityId": null,
      "disName": null,
      "disId": null,
      "address": "长沙市XX区XX路XX号",
      "type": "user",
      "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "sex": "女",
      "age": "18",
      "desc": "爱美之心人皆有之",
      "datems": "1480743590131",
      "points": "52",
      "platform": "resident",
      "ifAuthed": null,
      "createdAt": "2016-12-03T05:39:50.000Z",
      "updatedAt": "2016-12-03T05:39:50.000Z",
      "ID": 15,
      "post_count": 3,
      "note_count": 3
    },
   ...
  ]
}
```


<a name="79"></a>
#### 7.9 getCommentListByUserId：根据userid，获取帖子和日记评论列表
- 接口地址：/medicalManage/api/user/getCommentListByUserId
方法：post
参数：
userId:用户id
page:页数，首页为1，默认为1
limit:每页条数，默认10

地址：
http://localhost:5001/medicalManage/api/user/getCommentListByUserId


```
userId:13

{
  "code": "200",
  "msg": "获取成功",
  "count": 1,
  "commentList": [
    {
      "commentId": "2cb6e240-b93f-11e6-8fa1-9f820747b10a",
      "p_content": "我也想去，可惜门票买不起",
      "p_datems": "1480759166565",
      "p_createdAt": "2016-12-03T09:59:26.000Z",
      "p_updatedAt": "2016-12-03T09:59:26.000Z",
      "p_userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
      "p_userName": "小路",
      "p_user_account": "18233561908",
      "p_user_icon": "image/DSC_0005.JPG",
      "postId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
      "title": "华晨宇12月20日南京演唱会有人同行吗？",
      "content": "自从听了“天籁之音”从此对花花路转粉了...",
      "images": "http://120.25.124.68:5001/upload/image/2f54fc091600dce8c811533b50707002_b.jpg",
      "datems": "1480758695261"
    }
  ]
}
```

<a name="710"></a>
#### 7.10 getPraiseListByUserId：根据userid，获取帖子和日记点赞列表
- 接口地址：/medicalManage/api/user/getPostPraiseListByUserId
方法：post
参数：
userId:用户id
page:页数，首页为1，默认为1
limit:每页条数，默认10

地址：
http://localhost:5001/medicalManage/api/user/getPraiseListByUserId


```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取成功",
  "count": 1,
  "praiseList": [
    {
      "operation": "praise",
      "d_datems": "1480765069806",
      "d_userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "d_user_name": "小美",
      "d_user_account": "18233561909",
      "d_user_icon": "image/DSC_0005.JPG",
      "postId": "13cbc0d0-b93e-11e6-8fa1-9f820747b10a",
      "title": "华晨宇12月20日南京演唱会有人同行吗？",
      "content": "自从听了“天籁之音”从此对花花路转粉了...",
      "images": "http://120.25.124.68:5001/upload/image/2f54fc091600dce8c811533b50707002_b.jpg",
      "datems": "1480758695261"
    }
  ]
}
```



<a name="714"></a>
#### 7.14 getDocListByXXX：获取医生列表
- 接口地址：/medicalManage/api/user/getDocListByXXX
方法：post
参数：
roomId://科室id
hosId://医院id
keyword://关键字
地址：
http://localhost:5001/medicalManage/api/user/getDocListByXXX

```
hosId:f60014d0-d4ad-11e6-9487-b543495b4bae

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 1,
  "list": [
    {
      "userId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
      "name": "李某某",
      "password": "wang123456789",
      "account": "18867365367",
      "hosName": "长沙亚韩医学美容医院",
      "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
      "roomName": null,
      "roomId": null,
      "docTitle": null,
      "docPhone": null,
      "docGoodAt": null,
      "idCardNum": null,
      "proName": null,
      "proId": null,
      "cityName": null,
      "cityId": null,
      "disName": null,
      "disId": null,
      "address": null,
      "type": "user",
      "icon": null,
      "sex": null,
      "age": null,
      "desc": null,
      "datems": "1481359477597",
      "points": "10",
      "platform": "doctor",
      "ifAuthed": null,
      "createdAt": "2016-12-10T08:44:37.000Z",
      "updatedAt": "2016-12-10T08:44:37.000Z",
      "ID": 21
    }
  ]
}
```

<a name="715"></a>
#### 7.15 getDocById：获取医生信息
- 接口地址：/medicalManage/api/user/getDocById
方法：post
参数：
userId:用户id

地址：
http://localhost:5001/medicalManage/api/user/getDocById

```
userId:e1f920d0-beb4-11e6-98b8-69381c15d525

{
  "code": "200",
  "msg": "获取信息成功！",
  "doctor": {
    "userId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "name": "李某某",
    "password": "wang123456789",
    "account": "18867365367",
    "hosName": "长沙亚韩医学美容医院",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "roomName": null,
    "roomId": null,
    "docTitle": null,
    "docPhone": null,
    "docGoodAt": null,
    "idCardNum": null,
    "proName": null,
    "proId": null,
    "cityName": null,
    "cityId": null,
    "disName": null,
    "disId": null,
    "address": null,
    "type": "user",
    "icon": null,
    "sex": null,
    "age": null,
    "desc": null,
    "datems": "1481359477597",
    "points": "10",
    "platform": "doctor",
    "ifAuthed": null,
    "createdAt": "2016-12-10T08:44:37.000Z",
    "updatedAt": "2016-12-10T08:44:37.000Z",
    "id": 21
  }
}
```



<a name="716"></a>
#### 7.16 getDocInfo：获取医生详细
- 接口地址：/medicalManage/api/user/getDocInfo
方法：post
参数：
userId:用户id

地址：
http://localhost:5001/medicalManage/api/user/getDocInfo

```
userId:e1f920d0-beb4-11e6-98b8-69381c15d525

{
  "code": "200",
  "msg": "获取信息成功！",
  "doctor": {
    "userId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "name": "李某某",
    "password": "wang123456789",
    "account": "18867365367",
    "hosName": "长沙亚韩医学美容医院",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "roomName": null,
    "roomId": null,
    "docTitle": null,
    "docPhone": null,
    "docGoodAt": null,
    "idCardNum": null,
    "proName": null,
    "proId": null,
    "cityName": null,
    "cityId": null,
    "disName": null,
    "disId": null,
    "address": null,
    "type": "user",
    "icon": null,
    "sex": null,
    "age": null,
    "desc": null,
    "datems": "1481359477597",
    "points": "10",
    "platform": "doctor",
    "ifAuthed": null,
    "createdAt": "2016-12-10T08:44:37.000Z",
    "updatedAt": "2016-12-10T08:44:37.000Z",
    "id": 21
  },
  "hospital": {
    "id": 1,
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "hosType": "专科\u0001整形美容",
    "hosTypeId": "1\u00011",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级甲等",
    "hosIcon": "other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosNature": "民营医疗美容诊所",
    "hosGoodAt": "医疗美容&微整形",
    "hosMap": null,
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T07:50:30.000Z",
    "updatedAt": "2017-01-07T07:50:30.000Z"
  },
  "proList": [
    {
      "id": 1,
      "proId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
      "proName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
      "proPrice": "1999",
      "proPrePrice": "2000",
      "proImages": "http://120.25.124.68:5001/upload/other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=4259816641,3670994149&fm=73.jpg",
      "proDes": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
      "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
      "proWarning": "购买须知购买须知购买须知购买须知",
      "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
      "hosName": "长沙亚韩医学美容医院",
      "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
      "docName": "李某某",
      "createdAt": "2017-01-08T02:11:10.000Z",
      "updatedAt": "2017-01-08T02:11:10.000Z"
    },
   ...
  ]
}
```



<a name="8"></a>
### 8. note
<a name="81"></a>
#### 8.1 addNote :创建日记
- 接口地址：/medicalManage/api/post/addNote
方法：post(form-data)
参数：
userId:
typeId:
typeName:
title:
content:
from:
icon:

地址：
http://120.25.124.68:5001/medicalManage/api/note/addNote

返回值：
```
{
  "code": "200",
  "msg": "操作成功！！",
  "note": {
    "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
    "typeName": "账单",
    "title": "10月份账单",
    "content": "吃饭：1000，住宿2000",
    "from": "康咪",
    "icon": "http://120.25.124.68:5000/upload/image/DSC_0005.JPG",
    "noteId": "a00adf00-b92e-11e6-a9ef-f36a4004c390",
    "level": "0",
    "datems": "1480752058608",
    "createdAt": "2016-12-03T08:00:58.622Z",
    "updatedAt": "2016-12-03T08:00:58.622Z",
    "id": 1
  }
}
```


<a name="82"></a>
#### 8.2 updateNote：修改日记
- 接口地址：/medicalManage/api/note/updateNote
方法：post(form-data)
参数：
noteId
typeId:
typeName:
title:
content:
from:
icon:
level:

地址：
http://120.25.124.68:5001/medicalManage/api/note/updateNote

返回值：
```
{
  "code": "200",
  "msg": "修改成功！",
  "item": {
    "id": 2,
    "noteId": "e9da97b0-b92e-11e6-a9ef-f36a4004c390",
    "level": "0",
    "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
    "typeName": "账单",
    "title": "9月份账单",
    "icon": "http://120.25.124.68:5000/upload/image/DSC_0005.JPG",
    "content": "吃饭：1000，住宿:1800",
    "from": "康咪",
    "datems": "1480752182443",
    "createdAt": "2016-12-03T08:03:02.000Z",
    "updatedAt": "2016-12-03T08:03:02.000Z",
    "collect_count": 0,
    "praise_count": 0,
    "comment_count": 0
  }
}
```

<a name="83"></a>
#### 8.3 deleteNote：删除日记
- 接口地址：/medicalManage/api/note/deleteNote
方法：post
参数：
noteId

地址：
http://120.25.124.68:5001/medicalManage/api/note/deleteNote

返回值：
```
{
  "code": "200",
  "msg": "删除成功！！",
  "item": {
      "id": 3,
      "noteId": "ff5b16e0-b92f-11e6-9605-9585ec0f61b3",
      "level": "0",
      "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
      "typeName": "账单",
      "title": "9月份账单",
      "icon": "image/DSC_0005.JPG",
      "content": "吃饭：1000，住宿2000",
      "from": "康咪",
      "datems": "1480752648015",
      "createdAt": "2016-12-03T08:10:48.000Z",
      "updatedAt": "2016-12-03T08:10:48.000Z"
    }
}
```


<a name="84"></a>
#### 8.4 getListByTypeId ：根据类型ID，获取日记列表
- 接口地址：/medicalManage/api/note/getListByTypeId
方法：post
参数：
typeId

地址：
http://120.25.124.68:5001/medicalManage/api/note/getListByTypeId

返回值：
```
{
  "code": "200",
  "msg": "获取列表成功",
  "count": 2,
  "list": [
    {
      "id": 2,
      "noteId": "e9da97b0-b92e-11e6-a9ef-f36a4004c390",
      "level": "0",
      "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
      "typeName": "账单",
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",//发帖人id
      "title": "9月份账单",
      "icon": "image/DSC_0005.JPG",
      "content": "吃饭：1000，住宿:1800",
      "from": "康咪",
      "datems": "1480752182443",
      "createdAt": "2016-12-03T08:03:02.000Z",
      "updatedAt": "2016-12-03T08:03:02.000Z",
      "user_name": "冷心真心傻傻", //发帖人姓名
      "user_account": "18233561909", //发帖人账户
      "user_icon": "image/DSC_0005.JPG",//发帖人头像
      "collect_count": 1,
      "praise_count": 1,
      "comment_count": null
    },
    ...
  ]
}
```

<a name="85"></a>
#### 8.5 getInfoByNoteId ：根据ID，获取日记详情
- 接口地址：/medicalManage/api/note/getInfoByNoteId
方法：post
参数：
noteId:

地址：
http://120.25.124.68:5001/medicalManage/api/note/getInfoByNoteId


返回值：
```
{
  "code": "200",
  "msg": "获取信息成功！",
  "ifDz": "null",
  "item": {
    "id": 1,
    "noteId": "a00adf00-b92e-11e6-a9ef-f36a4004c390",
    "level": "0",
    "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
    "typeName": "账单",
    "title": "10月份账单",
    "icon": "image/DSC_0005.JPG",
    "content": "吃饭：1000，住宿2000",
    "from": "康咪",
    "datems": "1480752058608",
    "createdAt": "2016-12-03T08:00:58.000Z",
    "updatedAt": "2016-12-03T08:00:58.000Z",
    "collect_count": 0,
    "praise_count": 0,
    "comment_count": 0,
    "shared_page_url": "http://120.25.124.68:5001/studentManage/mobile/note?note_id=a00adf00-b92e-11e6-a9ef-f36a4004c390"
  }
}
```



<a name="86"></a>
#### 8.6 getInfoAndCommentList：根据postid，获取日记详情及评论列表
- 接口地址：/medicalManage/api/note/getInfoAndCommentList
方法：post
参数：
noteId:

地址：
http://120.25.124.68:5001/medicalManage/api/note/getInfoAndCommentList

返回值：
```
{
  "code": "200",
  "msg": "获取信息成功！",
  "ifDz": "null",
  "item": {
    "id": 1,
    "noteId": "a00adf00-b92e-11e6-a9ef-f36a4004c390",
    "level": "0",
    "typeId": "f259d960-b612-11e6-b7e2-f9d10cb604b7",
    "typeName": "账单",
    "title": "10月份账单",
    "icon": "image/DSC_0005.JPG",
    "content": "吃饭：1000，住宿2000",
    "from": "康咪",
    "datems": "1480752058608",
    "createdAt": "2016-12-03T08:00:58.000Z",
    "updatedAt": "2016-12-03T08:00:58.000Z",
    "collect_count": 0,
    "praise_count": 0,
    "comment_count": 1,
    "shared_page_url": "http://120.25.124.68:5001/studentManage/mobile/note?note_id=a00adf00-b92e-11e6-a9ef-f36a4004c390"
  },
  "commentlist": [
    {
      "userId": "c77264f0-b91a-11e6-945f-71d86d0db9d0",
      "user_name": "小路",
      "user_account": "18233561908",
      "user_icon": "image/DSC_0005.JPG",
      "id": 3,
      "commentId": "e2f96f80-b932-11e6-b682-c5e2e93c9a53",
      "objId": "a00adf00-b92e-11e6-a9ef-f36a4004c390",
      "objType": "note",
      "content": "这个月花费挺少的嘛",
      "datems": "1480753888889",
      "createdAt": "2016-12-03T08:31:28.000Z",
      "updatedAt": "2016-12-03T08:31:28.000Z",
      "praise_count": null,
      "comment_count": null
    }
  ]
}
```
<a name="9"></a>
### 9. notebook 日记本

<a name="91"></a>
#### 9.1 addNotebook:创建日记
- 接口地址：/medicalManage/api/notebook/addNotebook
方法：post(form-data)
参数：
projectId:
userId:
orderId:
hospitalId:
hospitalName:
doctorId:
doctorName:
icon:
title:
images:术前照片
satisDegree:
desc:



地址：
http://120.25.124.68:5001/medicalManage/api/notebook/addNotebook

返回值：
```
projectId:1
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0
orderId:1
hospitalId:1
hospitalName:
doctorId:1
doctorName:
title:整形日记
satisDegree:
desc:整形日记简介

{
  "code": "200",
  "msg": "操作成功！！",
  "notebook": {
    "projectId": "1",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "hospitalId": "1",
    "hospitalName": "",
    "doctorId": "1",
    "doctorName": "",
    "title": "整形日记",
    "desc": "整形日记简介",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "notebookId": "f4059e40-cf24-11e6-a488-af6813411b76",
    "satisLevel": "0",
    "datems": "1483166830132",
    "createdAt": "2016-12-31T06:47:10.152Z",
    "updatedAt": "2016-12-31T06:47:10.152Z",
    "id": 1
  }
}
```

<a name="92"></a>
#### 9.2 updateNotebook：修改日记
- 接口地址：/medicalManage/api/notebook/updateNotebook
方法：post(form-data)
参数：
notebookId:
userId:
hospitalId:
hospitalName:
doctorId:
doctorName:
icon:
title:
images:
satisDegree:
desc:


地址：
http://120.25.124.68:5001/medicalManage/api/notebook/updateNotebook

返回值：
```
{
  "code": "200",
  "msg": "修改成功！",
  "item": {
    "id": 1,
    "notebookId": "f4059e40-cf24-11e6-a488-af6813411b76",
    "projectId": "1",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "hospitalId": "1",
    "hospitalName": "",
    "doctorId": "1",
    "doctorName": "",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "title": "我的整形日记",
    "desc": "我的整形日记简介",
    "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "satisLevel": "0",
    "datems": "1483166830132",
    "createdAt": "2016-12-31T06:47:10.000Z",
    "updatedAt": "2016-12-31T06:47:10.000Z",
    "collect_count": 0,
    "praise_count": 0,
    "comment_count": 0
  }
}
```

<a name="93"></a>
#### 9.3 deleteNotebook：删除日记
- 接口地址：/medicalManage/api/notebook/deleteNotebook
方法：post
参数：
notebookId:


地址：
http://120.25.124.68:5001/medicalManage/api/notebook/deleteNotebook

返回值：
```
{
  "code": "200",
  "msg": "删除成功！！",
  "item": {
    "id": 2,
    "notebookId": "06df6770-cf26-11e6-8235-9bf874300566",
    "projectId": "1",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "hospitalId": "1",
    "hospitalName": "",
    "doctorId": "1",
    "doctorName": "",
    "icon": "image/DSC_0005.JPG",
    "title": "整形日记",
    "desc": "整形日记简介",
    "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "satisLevel": "0",
    "datems": "1483167291240",
    "createdAt": "2016-12-31T06:54:51.000Z",
    "updatedAt": "2016-12-31T06:54:51.000Z"
  }
}
```

<a name="94"></a>
#### 9.4 getListByUserId ：根据userid，获取日记本列表
- 接口地址：/medicalManage/api/notebook/getListByUserId 
方法：post
参数：
userId:

地址：
http://120.25.124.68:5001/medicalManage/api/notebook/getListByUserId

返回值：
```
userId:e86fad20-b91a-11e6-945f-71d86d0db9d0

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 2,
  "list": [
    {
      "id": 3,
      "notebookId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
      "projectId": "1",
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "user_account": "13721260000",
      "hospitalId": "1",
      "hospitalName": "",
      "doctorId": "1",
      "doctorName": "",
      "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "title": "整形日记",
      "desc": "整形日记简介",
      "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
      "satisLevel": "5",
      "datems": "1483167378653",
      "createdAt": "2016-12-31T06:56:18.000Z",
      "updatedAt": "2016-12-31T06:56:18.000Z",
      "note_count": 3
    },
    ...
  ]
}
```


<a name="95"></a>
#### 9.5 getOne：根据notebookId，获取日记本基础信息
- 接口地址：/medicalManage/api/notebook/getOne
方法：post
参数：
notebookId:

地址：
http://120.25.124.68:5001/medicalManage/api/notebook/getOne

返回值：
```
{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "notebookId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
    "projectId": "1",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "hospitalId": "1",
    "hospitalName": "",
    "doctorId": "1",
    "doctorName": "",
    "icon": "image/DSC_0005.JPG",
    "title": "整形日记",
    "desc": "整形日记简介",
    "images": "image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "satisLevel": "5",
    "datems": "1483167378653",
    "createdAt": "2016-12-31T06:56:18.000Z",
    "updatedAt": "2016-12-31T06:56:18.000Z"
  }
}
```


<a name="96"></a>
#### 9.6 getInfoByNotebookId：根据notebookId，获取日记详情
- 接口地址：/medicalManage/api/notebook/getInfoByNotebookId
方法：post
参数：
notebookId:

地址：
http://120.25.124.68:5001/medicalManage/api/notebook/getInfoByNotebookId

返回值：
```
notebookId:3af96ab0-cf26-11e6-8cdb-d360ff27a8f8

{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "notebookId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
    "projectId": "1",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "hospitalId": "1",
    "hospitalName": "",
    "doctorId": "1",
    "doctorName": "",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "title": "整形日记",
    "desc": "整形日记简介",
    "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "satisLevel": "5",
    "datems": "1483167378653",
    "createdAt": "2016-12-31T06:56:18.000Z",
    "updatedAt": "2016-12-31T06:56:18.000Z",
    "note_count": 3
  }
}
```


<a name="97"></a>
#### 9.7 getInfoAndNoteList：根据notebookid，获取日记本详情及日记列表
- 接口地址：/medicalManage/api/notebook/getInfoAndNoteList
方法：post
参数：
userId:当前登录用户id
notebookId:

地址：
http://120.25.124.68:5001/medicalManage/api/notebook/getInfoAndNoteList

返回值：
```
notebookId:3af96ab0-cf26-11e6-8cdb-d360ff27a8f8

{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "notebookId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
    "projectId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
    "projectName": "注射玻尿酸",
    "medicItem": null,
    "medmedicItem: null,
    "orderId": null,
    "userId": null,
    "hospitalId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hospitalName": "长沙亚韩医学美容医院",
    "doctorId": "3dd4e6a0-d558-11e6-ac80-35e73a3a9d09",
    "doctorName": "丁医生",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "title": "整形日记",
    "desc": null,
    "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "satisLevel": "5", 
    "createdAt": "2016-12-31T06:56:18.000Z",
    "updatedAt": "2016-12-31T06:56:18.000Z",
    "note_count": 7,  //笔记总量
    "notebook_praise_count": 0,  //笔记本点赞量
    "if_praise_notebook": null,  //是否点赞笔记本
    "userName": "冷心真心傻傻",
    "userAccount": "18233561909",
    "userIcon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "userAge": "18",
    "userProName": null,
    "userCityName": null,
    "userDisName": null,
    "if_focus_user": null, //是否关注用户
    "docName": null,
    "docAccount": null,
    "docIcon": null,
    "docTitle": null,
    "docHosName": null,
    "docRoomName": null,
    "docGoodAt": null,  //医生擅长
    "docDesc": null,  //医生简介
    "objId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "docStar": null,  //医生等级
    "if_focus_doc": null,  //是否关注医生
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "hosType": "专科\u0001整形美容",
    "hosNature": "民营医疗美容诊所", //运营方式
    "hosIcon": "other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosGoodAt": "医疗美容&微整形",
    "hosStar": 4.5,  //医院等级
    "if_focus_hos": null  //是否关注医院
  },
  "notelist": [
    {
      "id": 10,
      "postId": "c1b17b80-edb0-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "typeId": "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "typeName": "埋线双眼皮",
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": null,
      "content": "图兔兔",
      "images": "http://120.25 .124.68:5001/upload/image/IMG_20170205_210933.jpg",
      "level": null,
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "type": "note",
      "createdAt": "2017-02-08T03:43:30.000Z",
      "updatedAt": "2017-02-08T03:43:30.000Z",
      "user_name": "奈何一笑",
      "user_account": "18867365368",
      "user_icon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      "user_desc": "奈何一笑而过",
      "praise_count": 0, //点赞数量
      "share_count": 0, //分享数量
      "comment_count": 1, //评论数量
      "if_praise": null  //是否点赞
    }
  ]
}

{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "notebookId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
    "projectId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
    "projectName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "userId": "3dd4e6a0-d558-11e6-ac80-35e73a3a9d09",
    "hospitalId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hospitalName": "长沙亚韩医学美容医院",
    "doctorId": "3dd4e6a0-d558-11e6-ac80-35e73a3a9d09",
    "doctorName": "丁医生",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "title": "整形日记",
    "desc": "整形日记简介",
    "images":    "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",  //术前照片
    "satisLevel": "5",
    "createdAt": "2016-12-31T06:56:18.000Z",
    "updatedAt": "2016-12-31T06:56:18.000Z",
    "note_count": 7,
    "userName": "冷心真心傻傻",  //用户信息
    "userAccount": "18233561909",
    "userIcon": "image/DSC_0005.JPG",
    "userAge": "18",
    "userProName": null,
    "userCityName": null,
    "userDisName": null,
    "docName": "丁医生",    //医生信息
    "docAccount": "13721264200",
    "docIcon": "image/u=3557557066,2008108873&fm=85&s=F112519C6822AC9AC38C9CAB0300B091.jpg",
    "docTitle": "副主任",
    "docHosName": "长沙亚韩医学美容医院",
    "docRoomName": "美容科室",
    "objId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "docStar": 3,  //医生评价
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",  //医院信息
    "hosName": "长沙亚韩医学美容医院",
    "hosType": "专科\u0001整形美容",
    "hosIcon": "other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosGoodAt": "医疗美容&微整形",
    "hosStar": 4.5   //医院评价
  },
  "notelist": [
    {
      "id": 10,
      "postId": "c1b17b80-edb0-11e6-89e4-0fabf77c2771",
      "labelId": null,
      "labelName": null,
      "typeId": "499ab3b0-c5fa-11e6-9c21-9ff2d56ab9f3",
      "typeName": "埋线双眼皮",
      "parentId": "9325bd70-c656-11e6-8ca5-37b03af6926d",
      "parentName": "瘦身减肥",
      "title": null,
      "content": "图兔兔",
      "images": "http://120.25.124.68:5001/upload/image/IMG_20170205_210933.jpg",
      "level": null,
      "userId": "4b213800-c35a-11e6-a2cd-e377470ab12b",
      "type": "note",
      "createdAt": "2017-02-08T03:43:30.000Z",
      "updatedAt": "2017-02-08T03:43:30.000Z",
      "user_name": "奈何一笑",
      "user_account": "18867365368",
      "user_icon": "http://120.25.124.68:5001/upload/other/tq1m8mkv3ZafBFj6yr233iXT.png",
      "user_desc": "奈何一笑而过",
      "praise_count": 13,
      "share_count": 0,
      "comment_count": 0
    },
   ...
  ]
}


{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "notebookId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
    "projectId": "1",
    "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
    "hospitalId": "1",
    "hospitalName": "",
    "doctorId": "1",
    "doctorName": "",
    "icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
    "title": "整形日记",
    "desc": "整形日记简介",
    "images": "http://120.25.124.68:5001/upload/image/a75_b19169e2_1423_a6e7_854f_b3a0521135e3_1.jpg\u0001http://120.25.124.68:5001/upload/image/a75_ba768839_334f_34ca_d2a3_c2829e582979_1.jpg",
    "satisLevel": "5",
    "datems": "1483167378653",
    "createdAt": "2016-12-31T06:56:18.000Z",
    "updatedAt": "2016-12-31T06:56:18.000Z",
    "note_count": 3
  },
  "notelist": [
    {
      "id": 3,
      "postId": "4a647d80-cf28-11e6-8cdb-d360ff27a8f8",
      "typeId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "typeName": "精选",
      "parentId": "3af96ab0-cf26-11e6-8cdb-d360ff27a8f8",
      "parentName": "整形日记",
      "title": "鼻综合整形记录",
      "content": "术后60天啦，这几天在武汉天气特别冷，刚刚吃了热乎乎的武汉热干面，压压惊，哈哈~~",
      "images": null,
      "level": null,
      "userId": "e86fad20-b91a-11e6-945f-71d86d0db9d0",
      "datems": "1483168263512",
      "type": "note",
      "createdAt": "2016-12-31T07:11:03.000Z",
      "updatedAt": "2016-12-31T07:11:03.000Z",
      "user_name": "冷心真心傻傻",
      "user_account": "18233561909",
      "user_icon": "http://120.25.124.68:5001/upload/image/DSC_0005.JPG",
      "user_desc": "爱美之心人皆有之",
      "praise_count": 0,
      "share_count": 0,
      "comment_count": 0
    },
    ...
  ]
}
```


<a name="10"></a>
### 10. hospital：医院

<a name="101"></a>
#### 10.1 addHospital:创建医院
- 接口地址：/medicalManage/api/hospital/addHospital
方法：post(form-data)
参数：
hosName: 医院名称
hosType:医院类型（儿科，妇科...）
hosTypeId:类型id
proName:省
proId:
cityName:市
cityId:
disName:区
disId:
hosAddress:医院地址
hosPhone:医院电话
hosLevel:医院等级
hosIcon:医院图标
hosImages:医院图片
hosNature:医院性质（私立...）
hosGoodAt:擅长
hosMap:经纬度（暂时不用）
hosDes:医院描述
ifAuthed:是否认证（yes/no），默认no

地址：
http://120.25.124.68:5001/medicalManage/api/hospital/addHospital

返回值：
```
hosName:长沙艾尔医疗整形医院
hosType:专科| 整形美容
hosTypeId:1|1
proName:湖南省
proId:18
cityName:长沙市
cityId:177
disName:岳麓区
disId:1558
hosAddress: 咸嘉湖路1076 
hosPhone:(0731)88940736
hosLevel:三级乙等
hosNature:民营医疗美容门诊
hosGoodAt:医疗美容，微整形
hosDes:长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖

{
  "code": "200",
  "msg": "创建成功！",
  "item": {
    "hosName": "长沙艾尔医疗整形医院",
    "hosType": "专科| 整形美容",
    "hosTypeId": "1|1",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级乙等",
    "hosNature": "民营医疗美容门诊",
    "hosGoodAt": "医疗美容，微整形",
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "hosIcon": "other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T07:50:30.309Z",
    "updatedAt": "2017-01-07T07:50:30.309Z",
    "id": 1
  }
}
```

<a name="102"></a>
#### 10.2 updateHospital：修改医院
- 接口地址：/medicalManage/api/hospital/updateHospital
方法：post(form-data)
参数：
hosId:医院id
hosName: 医院名称
hosType:医院类型（儿科，妇科...）
hosTypeId:类型id
proName:省
proId:
cityName:市
cityId:
disName:区
disId:
hosAddress:医院地址
hosPhone:医院电话
hosLevel:医院等级
hosIcon:医院图标
hosImages:医院图片
hosNature:医院性质（私立...）
hosGoodAt:擅长
hosMap:经纬度（暂时不用）
hosDes:医院描述
ifAuthed:是否认证（yes/no），默认no



地址：
http://120.25.124.68:5001/medicalManage/api/hospital/updateHospital

返回值：
```
hosLevel:三级甲等
hosNature:民营医疗美容诊所
hosGoodAt:医疗美容&微整形
hosDes:长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖
hosId:f60014d0-d4ad-11e6-9487-b543495b4bae

{
  "code": "200",
  "msg": "�޸ĳɹ���",
  "item": {
    "id": 1,
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙艾尔医疗整形医院",
    "hosType": "专科| 整形美容",
    "hosTypeId": "1|1",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级甲等",
    "hosIcon": "http://120.25.124.68:5001/upload/other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "http://120.25.124.68:5001/upload/other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001http://120.25.124.68:5001/upload/other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosNature": "民营医疗美容诊所",
    "hosGoodAt": "医疗美容&微整形",
    "hosMap": null,
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T07:50:30.000Z",
    "updatedAt": "2017-01-07T07:50:30.000Z"
  }
}
```

<a name="103"></a>
#### 10.3 findListByXXX：获取医院列表
- 接口地址：/medicalManage/api/hospital/findListByXXX
方法：post
参数：
hosTypeId:医院类型id
proId:省id
cityId:市id
disId:区id
keyword:关键字

地址：
http://120.25.124.68:5001/medicalManage/api/hospital/findListByXXX

返回值：
```
proId:18

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 2,
  "list": [
    {
      "id": 3,
      "hosId": "527b0ca0-d4af-11e6-9904-298acaa79d24",
      "hosName": "长沙艾尔医疗整形医院二院",
      "hosType": "专科| 整形美容",
      "hosTypeId": "1\u00011",
      "proName": "湖南省",
      "proId": "18",
      "cityName": "长沙市",
      "cityId": "177",
      "disName": "岳麓区",
      "disId": "1558",
      "hosAddress": " 咸嘉湖路1076 ",
      "hosPhone": "(0731)88940736",
      "hosLevel": "三级乙等",
      "hosIcon": "http://120.25.124.68:5001/upload/other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
      "hosImages": "http://120.25.124.68:5001/upload/other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001http://120.25.124.68:5001/upload/other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=2398874369,3614038171&fm=23&gp=0.jpg",
      "hosNature": "民营医疗美容门诊",
      "hosGoodAt": "医疗美容，微整形",
      "hosMap": null,
      "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
      "ifAuthed": "no",
      "createdAt": "2017-01-07T08:00:14.000Z",
      "updatedAt": "2017-01-07T08:00:14.000Z"
    },
 ...
  ]
}
```

<a name="104"></a>
#### 10.4 getHosById：获取医院信息
- 接口地址：/medicalManage/api/hospital/getHosById
方法：post
参数：
hosId:医院id

地址：
http://120.25.124.68:5001/medicalManage/api/hospital/getHosById

返回值：
```
{
  "code": "200",
  "msg": "获取信息成功！",
  "hospital": {
    "id": 3,
    "hosId": "527b0ca0-d4af-11e6-9904-298acaa79d24",
    "hosName": "长沙艾尔医疗整形医院二院",
    "hosType": "专科| 整形美容",
    "hosTypeId": "1\u00011",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级乙等",
    "hosIcon": "http://120.25.124.68:5001/upload/other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "http://120.25.124.68:5001/upload/other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001http://120.25.124.68:5001/upload/other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosNature": "民营医疗美容门诊",
    "hosGoodAt": "医疗美容，微整形",
    "hosMap": null,
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T08:00:14.000Z",
    "updatedAt": "2017-01-07T08:00:14.000Z"
  }
}
```


<a name="105"></a>
#### 10.5 getHosInfo：获取医院详细信息，含医生、项目列表等
- 接口地址：/medicalManage/api/hospital/getHosInfo
方法：post
参数：
hosId:医院id

地址：
http://120.25.124.68:5001/medicalManage/api/hospital/getHosInfo

返回值：
```
hosId:f60014d0-d4ad-11e6-9487-b543495b4bae

{
  "code": "200",
  "msg": "获取信息成功！",
  "hospital": {
    "id": 1,
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "hosType": "专科\u0001整形美容",
    "hosTypeId": "1\u00011",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级甲等",
    "hosIcon": "http://120.25.124.68:5001/upload/other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "http://120.25.124.68:5001/upload/other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001http://120.25.124.68:5001/upload/other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosNature": "民营医疗美容诊所",
    "hosGoodAt": "医疗美容&微整形",
    "hosMap": null,
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T07:50:30.000Z",
    "updatedAt": "2017-01-07T07:50:30.000Z"
  },
  "docList": [
    {
      "userId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
      "name": "李某某",
      "password": "wang123456789",
      "account": "18867365367",
      "hosName": "长沙亚韩医学美容医院",
      "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
      "roomName": null,
      "roomId": null,
      "docTitle": null,
      "docPhone": null,
      "docGoodAt": null,
      "idCardNum": null,
      "proName": null,
      "proId": null,
      "cityName": null,
      "cityId": null,
      "disName": null,
      "disId": null,
      "address": null,
      "type": "user",
      "icon": null,
      "sex": null,
      "age": null,
      "desc": null,
      "datems": "1481359477597",
      "points": "10",
      "platform": "doctor",
      "ifAuthed": null,
      "createdAt": "2016-12-10T08:44:37.000Z",
      "updatedAt": "2016-12-10T08:44:37.000Z",
      "ID": 21
    },
 ...
  ]
}
```

<a name="106"></a>
#### 10.6 deleteHospital：删除医院
- 接口地址：/medicalManage/api/hospital/deleteHospital
方法：post
参数：
hosId:医院id

地址：
http://120.25.124.68:5001/medicalManage/api/hospital/deleteHospital

返回值：
```
hosId:065b5e90-d4b1-11e6-afd2-f344366bff28

{
  "code": "200",
  "msg": "删除成功！！",
  "item": {
    "id": 4,
    "hosId": "065b5e90-d4b1-11e6-afd2-f344366bff28",
    "hosName": "长沙艾尔医疗整形医院二院",
    "hosType": "专科| 整形美容",
    "hosTypeId": "1|1",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级乙等",
    "hosIcon": "other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosNature": "民营医疗美容门诊",
    "hosGoodAt": "医疗美容，微整形",
    "hosMap": null,
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T08:12:26.000Z",
    "updatedAt": "2017-01-07T08:12:26.000Z"
  }
}
```



<a name="12"></a>
### 12. project：医疗项目

<a name="121"></a>
#### 12.1 addProject:创建项目
- 接口地址：/medicalManage/api/project/addProject
方法：post(form-data)
参数：
proName:项目名称
proDes:项目描述
proPrePrice:原价
proPrice:价格
proImages:图片
proDetail:图文介绍 
proWarning:购买须知
hosId:所属医院
hosName:
docId:所属医生
docName:


地址：
http://120.25.124.68:5001/medicalManage/api/project/addProject

返回值：
```
proName:海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形
proDes:海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形
proPrePrice:2000
proPrice:1888
proDetail:图文介绍图文介绍图文介绍图文介绍图文介绍
proWarning:购买须知购买须知购买须知购买须知
hosId:f60014d0-d4ad-11e6-9487-b543495b4bae
hosName:长沙亚韩医学美容医院
docId:e1f920d0-beb4-11e6-98b8-69381c15d525
docName:李某某

{
  "code": "200",
  "msg": "创建成功！",
  "item": {
    "proName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proDes": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proPrePrice": "2000",
    "proPrice": "1888",
    "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
    "proWarning": "购买须知购买须知购买须知购买须知",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "docName": "李某某",
    "proImages": "other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001other/u=4259816641,3670994149&fm=73.jpg",
    "proId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
    "createdAt": "2017-01-08T02:11:10.237Z",
    "updatedAt": "2017-01-08T02:11:10.237Z",
    "id": 1
  }
}
```

<a name="122"></a>
#### 12.2 updateProject：修改项目
- 接口地址：/medicalManage/api/project/updateProject
方法：post(form-data)
参数：


地址：
http://120.25.124.68:5001/medicalManage/api/project/updateProject

返回值：
```
proId:b8dc52e0-d547-11e6-8ac7-cf1704c30020
proPrice:1999

{
  "code": "200",
  "msg": "修改成功！",
  "item": {
    "id": 1,
    "proId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
    "proName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proPrice": "1999",
    "proPrePrice": "2000",
    "proImages": "http://120.25.124.68:5001/upload/other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=4259816641,3670994149&fm=73.jpg",
    "proDes": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
    "proWarning": "购买须知购买须知购买须知购买须知",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "docName": "李某某",
    "createdAt": "2017-01-08T02:11:10.000Z",
    "updatedAt": "2017-01-08T02:11:10.000Z"
  }
}
```

<a name="123"></a>
#### 12.3 findListByXXX：获取项目列表
- 接口地址：/medicalManage/api/project/findListByXXX
方法：post
参数：
hosId
docId
keyword

地址：
http://120.25.124.68:5001/medicalManage/api/project/findListByXXX

返回值：
```
hosId:f60014d0-d4ad-11e6-9487-b543495b4bae
docId:
keyword:

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 3,
  "list": [
    {
      "id": 1,
      "proId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
      "proName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
      "proPrice": "1999",
      "proPrePrice": "2000",
      "proImages": "http://120.25.124.68:5001/upload/other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=4259816641,3670994149&fm=73.jpg",
      "proDes": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
      "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
      "proWarning": "购买须知购买须知购买须知购买须知",
      "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
      "hosName": "长沙亚韩医学美容医院",
      "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
      "docName": "李某某",
      "createdAt": "2017-01-08T02:11:10.000Z",
      "updatedAt": "2017-01-08T02:11:10.000Z"
    },
  ...
  ]
}
```

<a name="124"></a>
#### 12.4 getInfoById：获取项目信息
- 接口地址：/medicalManage/api/project/getInfoById
方法：post
参数：
proId

地址：
http://120.25.124.68:5001/medicalManage/api/project/getInfoById

返回值：
```
{
  "code": "200",
  "msg": "获取信息成功！",
  "project": {
    "id": 1,
    "proId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
    "proName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proPrice": "1999",
    "proPrePrice": "2000",
    "proImages": "http://120.25.124.68:5001/upload/other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=4259816641,3670994149&fm=73.jpg",
    "proDes": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
    "proWarning": "购买须知购买须知购买须知购买须知",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "docName": "李某某",
    "createdAt": "2017-01-08T02:11:10.000Z",
    "updatedAt": "2017-01-08T02:11:10.000Z"
  }
}
```


<a name="125"></a>
#### 12.5 getProInfo：获取项目详细信息，含医院、医生等
- 接口地址：/medicalManage/api/project/getProInfo
方法：post
参数：
proId

地址：
http://120.25.124.68:5001/medicalManage/api/project/getProInfo

返回值：
```
{
  "code": "200",
  "msg": "获取信息成功！",
  "project": {  //项目
    "id": 1,
    "proId": "b8dc52e0-d547-11e6-8ac7-cf1704c30020",
    "proName": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proPrice": "1999",
    "proPrePrice": "2000",
    "proImages": "http://120.25.124.68:5001/upload/other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001http://120.25.124.68:5001/upload/other/u=4259816641,3670994149&fm=73.jpg",
    "proDes": "海威玻尿酸注射隆鼻丰下巴保湿补水填充塑体微整形",
    "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
    "proWarning": "购买须知购买须知购买须知购买须知",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "docName": "李某某",
    "createdAt": "2017-01-08T02:11:10.000Z",
    "updatedAt": "2017-01-08T02:11:10.000Z"
  },
  "hospital": {   //医院
    "id": 1,
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "hosType": "专科\u0001整形美容",
    "hosTypeId": "1\u00011",
    "proName": "湖南省",
    "proId": "18",
    "cityName": "长沙市",
    "cityId": "177",
    "disName": "岳麓区",
    "disId": "1558",
    "hosAddress": " 咸嘉湖路1076 ",
    "hosPhone": "(0731)88940736",
    "hosLevel": "三级甲等",
    "hosIcon": "other/u=3515680927,3069006402&fm=58&s=9C0E7C329AF5588041C0DBFF03007024.jpg",
    "hosImages": "other/55e736d12f2eb9387d72d2f7d5628535e5dd6f9c.jpg\u0001other/u=175707136,2835784752&fm=23&gp=0.jpg\u0001other/u=2398874369,3614038171&fm=23&gp=0.jpg",
    "hosNature": "民营医疗美容诊所",
    "hosGoodAt": "医疗美容&微整形",
    "hosMap": null,
    "hosDes": "长沙艾尔医疗整形医院多年专注医疗美容事业，经验丰富，值得信赖",
    "ifAuthed": "no",
    "createdAt": "2017-01-07T07:50:30.000Z",
    "updatedAt": "2017-01-07T07:50:30.000Z"
  },
  "doctor": {  //医生
    "userId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "name": "李某某",
    "password": "wang123456789",
    "account": "18867365367",
    "hospital": null,
    "room": null,
    "position": null,
    "city": null,
    "address": null,
    "type": "user",
    "icon": null,
    "sex": null,
    "age": null,
    "desc": null,
    "datems": "1481359477597",
    "points": "10",
    "platform": "doctor",
    "createdAt": "2016-12-10T08:44:37.000Z",
    "updatedAt": "2016-12-10T08:44:37.000Z",
    "id": 21
  }
}
```

<a name="126"></a>
#### 12.6 deleteProject：删除项目
- 接口地址：/medicalManage/api/project/deleteProject
方法：post
参数：
proId

地址：
http://120.25.124.68:5001/medicalManage/api/project/deleteProject

返回值：
```
proId:d4cdcbf0-d547-11e6-8ac7-cf1704c30020
{
  "code": "200",
  "msg": "删除成功！！",
  "hospital": {
    "id": 3,
    "proId": "d4cdcbf0-d547-11e6-8ac7-cf1704c30020",
    "proName": "海威丰下巴保湿补水填充塑体微整形",
    "proPrice": "1888",
    "proPrePrice": "2000",
    "proImages": "other/u=4034780701,2315121927&fm=23&gp=0.jpg\u0001other/u=4259816641,3670994149&fm=73.jpg",
    "proDes": "海威丰下巴保湿补水填充塑体微整形",
    "proDetail": "图文介绍图文介绍图文介绍图文介绍图文介绍",
    "proWarning": "购买须知购买须知购买须知购买须知",
    "hosId": "f60014d0-d4ad-11e6-9487-b543495b4bae",
    "hosName": "长沙亚韩医学美容医院",
    "docId": "e1f920d0-beb4-11e6-98b8-69381c15d525",
    "docName": "李某某",
    "createdAt": "2017-01-08T02:11:57.000Z",
    "updatedAt": "2017-01-08T02:11:57.000Z"
  }
}
```

<a name="13"></a>
### 13. immsg：消息

<a name="131"></a>
#### 13.1 add：新增一条群发消息记录
- 接口地址：/medicalManage/api/immsg/add
方法：post
参数：

msgFrom:
msgTarget::多个之间0x01分割
msgTargetName:多个账号0x01分割
msgContent:

地址：
http://120.25.124.68:5001/medicalManage/api/immsg/add

返回值：
```
msgFrom:18867365368
msgTarget:1823356190818233561909
msgTargetName:小路冷心真心傻傻
msgContent:我生病了，谁来看看我

{
  "code": "200",
  "msg": "创建成功！",
  "item": {
    "msgFrom": "18867365368",
    "msgTarget": "18233561908\u000118233561909",
    "msgTargetName": "小路\u0001冷心真心傻傻",
    "msgContent": "我生病了，谁来看看我",
    "createdAt": "2017-02-28T09:49:21.858Z",
    "updatedAt": "2017-02-28T09:49:21.858Z",
    "id": 6
  }
}
```

<a name="132"></a>
#### 13.2 getListByAccount：获取群发消息记录
- 接口地址：/medicalManage/api/immsg/getListByAccount
方法：post
参数：

msgFrom:


地址：
http://120.25.124.68:5001/medicalManage/api/immsg/add

返回值：
```
msgFrom:18867365368

{
  "code": "200",
  "msg": "获取列表成功！",
  "count": 2,
  "list": [
    {
      "id": 1,
      "msgContent": "hello world",
      "msgFrom": "18867365368",
      "msgTarget": "18233561908\u000118233561909",
      "msgTargetName": "小路\u0001冷心真心傻傻",
      "createdAt": "2017-02-28T09:23:24.000Z",
      "updatedAt": "2017-02-28T09:23:24.000Z"
    },
    {
      "id": 2,
      "msgContent": "我生病了，谁来看看我",
      "msgFrom": "18867365368",
      "msgTarget": "18233561908\u000118233561909",
      "msgTargetName": "小路\u0001冷心真心傻傻",
      "createdAt": "2017-02-28T09:49:21.000Z",
      "updatedAt": "2017-02-28T09:49:21.000Z"
    }
  ]
}
```




<a name="13"></a>
### 14. medicItem：医疗项目详情描述

<a name="141"></a>
#### 14.1 add：新增项目描述
说明：先在type表创建一个医疗项目，然后在这里添加描述
- 接口地址：/medicalManage/api/medicItem/add
方法：post（form-data）
参数：
medicItemId：项目id
medicItemName:
item_description:简介
treatment_painLevel:疼痛感
treatment_effect_duration:持续时间
treatment_days:治疗时间
treatment_price:参考价格
anaesthetic_type:麻醉方式
if_inHospital:是否住院
remove_suture_days:拆线时间
treatment_before_img:效果对比_术前图
treatment_after_img:效果对比_术后图
treatment_result:效果比对_描述
attention_suitable:适应人群
attention_advantage:优缺点
attention_prepare:术前术后准备
instruction_process:恢复过程
instruction_care:术后护理
instruction_riskControl:风险管控
item_warm_prompt:温馨提示



地址：
http://120.25.124.68:5001/medicalManage/api/immsg/add

返回值：
```
medicItemId:6be7e980-d566-11e6-b3ac-f5350455130e
medicItemName:开内眼角
item_description:切除内眼角多余皮肤，放大眼睛
treatment_painLevel:3
treatment_effect_duration:永久
treatment_days:20-30分钟
treatment_price:5000-18000元
anaesthetic_type:局麻
if_inHospital:否
remove_suture_days:5-7天
treatment_before_img:
treatment_after_img:
treatment_result:这是术后五天，看这效果明显吧，哈哈，眼睛大了很多
attention_suitable:{"适应人群"：["1.眼睛间距远的人","2.眼睛间距远的，眉形淡的","3.眼睛间距远的人"],"紧急人群":["1.眼睛间距近的人","1.眼睛间距近的人,眉形重的"]}
attention_advantage:{"优点"：["1.眼睛可以变大","2.脸型可以变美"],"缺点":["1.手术有风险","2.可能会有后遗症"]}
attention_prepare:{"术前准备"：["1.术前1周不要熬夜","2.每日睡前滴眼药水"],	"术后准备":["1.术前1周不要熬夜","2.每日睡前滴眼药水"]}
instruction_process:这是术后五天，看这效果明显吧，哈哈，眼睛大了很多
instruction_care:每日按摩10-15分钟，用热毛巾敷脸
instruction_riskControl:建议为手术买一份保险
item_warm_prompt:这是术后五天，看这效果明显吧，哈哈，眼睛大了很多

{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "medicItemId": "d641b630-d566-11e6-b3ac-f5350455130e",
    "medicItemName": "埋线双眼皮",
    "item_description": "切除内眼角多余皮肤，放大眼睛",
    "treatment_painLevel": "3",
    "treatment_effect_duration": "永久",
    "treatment_days": "20-30分钟",
    "treatment_price": "5000-18000元",
    "anaesthetic_type": "局麻",
    "if_inHospital": "否",
    "remove_suture_days": "5-7天",
    "treatment_img_before": null,
    "treatment_img_after": null,
    "treatment_result": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
    "attention_suitable": {
      "适应人群": [
        "1.眼睛间距远的人",
        "2.眼睛间距远的，眉形淡的",
        "3.眼睛间距远的人"
      ],
      "紧急人群": [
        "1.眼睛间距近的人",
        "1.眼睛间距近的人,眉形重的"
      ]
    },
    "attention_advantage": {
      "优点": [
        "1.眼睛可以变大",
        "2.脸型可以变美"
      ],
      "缺点": [
        "1.手术有风险",
        "2.可能会有后遗症"
      ]
    },
    "attention_prepare": {
      "术前准备": [
        "1.术前1周不要熬夜",
        "2.每日睡前滴眼药水"
      ],
      "术后准备": [
        "1.术前1周不要熬夜",
        "2.每日睡前滴眼药水"
      ]
    },
    "instruction_process": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
    "instruction_care": "每日按摩10-15分钟，用热毛巾敷脸",
    "instruction_riskControl": "建议为手术买一份保险",
    "item_warm_prompt": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
    "createdAt": "2017-04-23T08:08:44.000Z",
    "updatedAt": "2017-04-23T08:08:44.000Z"
  }
}
```


<a name="142"></a>
#### 14.2 getOne：新增项目描述
说明：先在type表创建一个医疗项目，然后在这里添加描述
- 接口地址：/medicalManage/api/medicItem/getOne
方法：post
参数：
medicItemId：项目id

地址：
http://120.25.124.68:5001/medicalManage/api/medicItem/getOne

返回值：
```
medicItemId:d641b630-d566-11e6-b3ac-f5350455130e
{
  "code": "200",
  "msg": "获取信息成功！",
  "item": {
    "id": 3,
    "medicItemId": "d641b630-d566-11e6-b3ac-f5350455130e",
    "medicItemName": "埋线双眼皮",
    "item_description": "切除内眼角多余皮肤，放大眼睛",
    "treatment_painLevel": "3",
    "treatment_effect_duration": "永久",
    "treatment_days": "20-30分钟",
    "treatment_price": "5000-18000元",
    "anaesthetic_type": "局麻",
    "if_inHospital": "否",
    "remove_suture_days": "5-7天",
    "treatment_img_before": null,
    "treatment_img_after": null,
    "treatment_result": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
    "attention_suitable": "{\"适应人群\"：[\"1.眼睛间距远的人\",\"2.眼睛间距远的，眉形淡的\",\"3.眼睛间距远的人\"],\"紧急人群\":[\"1.眼睛间距近的人\",\"1.眼睛间距近的人,眉形重的\"]}",
    "attention_advantage": "{\"优点\"：[\"1.眼睛可以变大\",\"2.脸型可以变美\"],\"缺点\":[\"1.手术有风险\",\"2.可能会有后遗症\"]}",
    "attention_prepare": "{\"术前准备\"：[\"1.术前1周不要熬夜\",\"2.每日睡前滴眼药水\"],\t\"术后准备\":[\"1.术前1周不要熬夜\",\"2.每日睡前滴眼药水\"]}",
    "instruction_process": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
    "instruction_care": "每日按摩10-15分钟，用热毛巾敷脸",
    "instruction_riskControl": "建议为手术买一份保险",
    "item_warm_prompt": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
    "createdAt": "2017-04-23T08:08:44.000Z",
    "updatedAt": "2017-04-23T08:08:44.000Z"
  }
}

```


<a name="143"></a>
#### 14.3 delete：删除

- 接口地址：/medicalManage/api/medicItem/delete
方法：post
参数：
medicItemId：项目id

地址：
http://120.25.124.68:5001/medicalManage/api/medicItem/delete

返回值：
```
{
  "code": "200",
  "msg": "操作成功！！",
  "item": [
    {
      "id": 4,
      "medicItemId": "d641b630-d566-11e6-b3ac-f5350455130e1",
      "medicItemName": "埋线双眼皮1",
      "item_description": "切除内眼角多余皮肤，放大眼睛",
      "treatment_painLevel": "3",
      "treatment_effect_duration": "永久",
      "treatment_days": "20-30分钟",
      "treatment_price": "5000-18000元",
      "anaesthetic_type": "局麻",
      "if_inHospital": "否",
      "remove_suture_days": "5-7天",
      "treatment_img_before": null,
      "treatment_img_after": null,
      "treatment_result": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
      "attention_suitable": "{\"适应人群\"：[\"1.眼睛间距远的人\",\"2.眼睛间距远的，眉形淡的\",\"3.眼睛间距远的人\"],\"紧急人群\":[\"1.眼睛间距近的人\",\"1.眼睛间距近的人,眉形重的\"]}",
      "attention_advantage": "{\"优点\"：[\"1.眼睛可以变大\",\"2.脸型可以变美\"],\"缺点\":[\"1.手术有风险\",\"2.可能会有后遗症\"]}",
      "attention_prepare": "{\"术前准备\"：[\"1.术前1周不要熬夜\",\"2.每日睡前滴眼药水\"],\t\"术后准备\":[\"1.术前1周不要熬夜\",\"2.每日睡前滴眼药水\"]}",
      "instruction_process": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
      "instruction_care": "每日按摩10-15分钟，用热毛巾敷脸",
      "instruction_riskControl": "建议为手术买一份保险",
      "item_warm_prompt": "这是术后五天，看这效果明显吧，哈哈，眼睛大了很多",
      "createdAt": "2017-04-23T08:09:17.000Z",
      "updatedAt": "2017-04-23T08:09:17.000Z"
    }
  ]
}

```

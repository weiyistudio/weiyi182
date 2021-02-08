# weiyi182
基于SSM框架的酒店管理系统的设计与实现

# 基于SSM框架的酒店管理系统的设计与实现


#### 介绍
在当今社会里，游玩、出行等各种各样的游乐设施及项目吸引众多游客眼球，而不管人们身在何处，衣食住行是不可或缺的，特别是宾馆酒店是所有人在外地的首选。部分宾馆提供早餐项目，而酒店更提供高档的商谈场地，宾馆酒店是结合各种项目的消费场所。酒店部门相对较多、业务复杂，而宾馆是提供客户入住的简单场所，人数也同样不少。
每天需要统计的各种信息数量庞大，要想提要劳动生产率，降低劳动率，降低相应成本，并且提高服务质量和部门管理等级，进而促进经济的高效发展，那么需要借助计算机来进行统一的现代化的信息管理。而宾馆和酒店规模不一、项目不一，所以本系统是融合了宾馆和酒店的部分需要，使得酒店能够用本系统，同时宾馆也可以使用。基于SSM框架的酒店管理系统的设计与实现就是围绕本需求而设计的。在目标上，本系统争取达到性价比最优，同时满足宾馆酒店需求。酒店客流量很多，能清楚的看到客房使用率、客户的入住情况是必要的系统功能，针对这个需求，本系统采用图表形式将数据的变化以折线图、散点图或者柱状图呈现出来。由于酒店客流量很多，历史入住详情也是必不可少的系统功能，本系统提供了历史入住查询以及打印excel表单。酒店管理系统已经越来越受到酒店行业的喜爱，本系统也是抓住了这个机遇而进行开发。
设计上，本系统应用于互联网平台设计基于SSM的酒店管理系统，采用B/S架构，更方便用户使用及维护，通过系统默认一个超级管理员管理该平台去创建平台操作员，同过操作员统一管理每天的房客，房间，库存等信息，查看数据报表的分析，实现房客入住的方便快捷，技术上采用Vue.js、Ajax进行前后端交互，让该系统完成更加简便，数据库采用MySQL，开发工具为Eclipse，测试服务器Tomcat。








#### 项目说明
开房和订房都需要经过房态图，已入住显示入住信息，空闲即可办理入住和预定，该系统有5中房态，空闲、入住、钟点、预定、停用。
入住管理模块管理在住客户的退房、续费、换房功能（也可批量处理）。
类型管理模块管理该宾馆酒店所需要的类型，根据用户自己定义，可以增删改查。
房间管理模块管理该宾馆酒店所要的房间，根据自定义的类型，设置相对应得房间。
可以增删改查。
早餐管理模块管理一个星期内的早餐情况，可以增删改查。
订单管理模块管理所有人的入住信息，包括是否离店不可修改。
报表分析模块通过ECharts.js管理近几个月的信息。
部门管理模块主要应用于大型酒店，实现人员化管理，小型宾馆酒店可以不用该功能可以增删改查。
人员管理模块主要在有部门的情况下对人员的增删改查。

![输入图片说明](https://images.gitee.com/uploads/images/2021/0209/015033_d5bf0f76_8650135.png "屏幕截图.png")

![输入图片说明](https://images.gitee.com/uploads/images/2021/0209/015044_57431aa9_8650135.png "屏幕截图.png")

（1）客户（id、顾客姓名、顾客身份证类型、身份证号、电话号、房间编号、入住日期、离开日期、消费金额、押金、住房状态、入住时长、消费项目、支付方式）
（2）身份证类型（id、身份证名称）
（3）房间（id、房间号、类型id、房间面积、窗、价格、状态、卫浴、电视）
（4）房间类型（id、类型名称、类型面积、类型价格、类型url）
（5）用户（id、账号、密码、名字、身份、创建时间、最后登录时间、登录次数、ip）
（6）职位（id、职位名称）
（7）用户职位（id、用户id、职位id）
（8）早餐（id、早餐名称、日期、状态）

表4.1 客户表（cus_customer）
列名	描述	类型	非空
id	id	int(60)	Primary key
cu_name	顾客姓名	varchar(60)	Null
cu_cardtype	顾客身份证类型	varchar(60)	Null
cu_idcard	身份证号	varchar(60)	Null
cu_phone	电话号	varchar(60)	Null
cu_rrid	房间编号	varchar(60)	Null
cu_startdate	入住日期	varchar(60)	Null
cu_enddate	离开日期	varchar(60)	Null
cu_price	消费金额	varchar(60)	Null
cu_deposit	押金	varchar(60)	Null
cu_struts	住房状态	varchar(60)	Null
cu_timelong	入住时长	varchar(60)	Null
cu_project	消费项目	varchar(60)	Null
cu_payway	支付方式	varchar(60)	Null
说明：本表是客户表，记录客户的入住信息和历史信息。


表4.2 身份类型表（idcardtype）
列名	描述	类型	非空
id	id	int(60)	Primary key
ci_typename	类型名称	varchar(60)	Null
说明：本表是身份证类型表，身份类型例如身份证，护照。
表4.3 房间表（sys_room）
列名	描述	类型	非空
id	id	int(60)	Primary key
rr_id	房间号	varchar(60)	Null
rr_tyid	类型id	varchar(60)	Null
rr_area	房间面积	varchar(60)	Null
rr_window	窗	varchar(60)	Null
rr_price	价格	varchar(60)	Null
rr_struts	状态	varchar(60)	Null
rr_livenum	床位数	varchar(60)	Null
rr_bathroom	卫浴	varchar(60)	Null
rr_tv	电视	varchar(60)	Null
说明：本表是房间表，用于对房间的增删改查。
表4.4 房间类型表（sys_roomtype）
列名	描述	类型	非空
id	id	int(60)	Primary key
rt_typename	类型名字	varchar(60)	Null
rt_avgarea	类型面积	varchar(60)	Null
rt_pricer	类型价格	varchar(60)	Null
rt_url	类型url	varchar(60)	Null
说明：本表是房间类型表，用于对房间类型的增删改查。
表4.5 用户表（sys_user）
列名	描述	类型	非空
id	id	int(60)	Primary key
user_account	账号	varchar(60)	Null
user_pass	密码	varchar(60)	Null
user_name	名字	varchar(60)	Null
user_ident	身份	varchar(60)	Null
user_creatdate	创建时间	varchar(60)	Null

续表4.5 职位表（sys_user）
列名	描述	类型	非空
user_lastlogin	最后登录时间	varchar(60)	Null
user_loginnum	登录次数	varchar(60)	Null
user_ip	ip	varchar(60)	Null
说明：本表是用户表，用于对系统的访问和对员工的增删改查。
表4.6 职位表（sys_apart）
列名	描述	类型	非空
id	id	int(60)	Primary key
apart_name	职位名称	varchar(60)	Null
说明：本表是职位表，用于对职位的增删改查。
表4.7 用户职位表（sys_userapart）
列名	描述	类型	非空
id	id	int(60)	Primary key
user_id	用户id	int(60)	Null
apart_id	身份id	int(60)	Null
说明：本表是用户职位表，用于对用户和职位的多连。
表4.8 早餐表（sys_food）
列名	描述	类型	非空
id	id	int(60)	Primary key
food_name	早餐名称	varchar(60)	Null
food_date	早餐时间	datetime	Null
food_status	早餐状态	varchar(60)	Null






#### 项目截图
![输入图片说明](https://images.gitee.com/uploads/images/2021/0209/015124_cd886964_8650135.png "屏幕截图.png")

![输入图片说明](https://images.gitee.com/uploads/images/2021/0209/015132_95c6350c_8650135.png "屏幕截图.png")

![输入图片说明](https://images.gitee.com/uploads/images/2021/0209/015311_7085eed9_8650135.png "屏幕截图.png")

#### 求助热线




代码有任何问题可联系
联系Q：2762501186

                            
![输入图片说明](https://images.gitee.com/uploads/images/2020/1119/003728_cd598bb9_4865385.jpeg "微信.jpg")           

感谢Gitee！！  
觉得项目不错的给个Star谢谢大佬！！！
提供无偿review服务


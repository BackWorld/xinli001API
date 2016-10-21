#心理FM接口
##1-启动封面图
[http://yiapi.xinli001.com/fm/initial-cover.json?key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/initial-cover.json?key=046b6a2a43dc6ff6e770255f57328f89)
#####`Response`:
![image](cover.png)
___

##2-首页
[http://yiapi.xinli001.com/fm/home-list.json?key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/home-list.json?key=046b6a2a43dc6ff6e770255f57328f89)
#####`Response`:
![image](home.png)
___

###2-首页-tuijian-列表
[http://bapi.xinli001.com/fm2/broadcast_list.json/?offset=0&speaker_id=0&tag=%E6%8A%91%E9%83%81%E7%97%87%E6%98%AF%E6%9D%A1%E9%BB%91%E7%8B%97&rows=10&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/broadcast_list.json/?offset=0&speaker_id=0&tag=%E6%8A%91%E9%83%81%E7%97%87%E6%98%AF%E6%9D%A1%E9%BB%91%E7%8B%97&rows=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
speaker_id	0
tag	抑郁症是条黑狗
rows	10
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](home-tuijian-detail.png)
___

###2-首页-category-详情
[http://yiapi.xinli001.com/fm/category-jiemu-list.json?category_id=1&offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/category-jiemu-list.json?category_id=1&offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
GET
```
category_id	1 //分类id - 情绪管理等
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](home-category-detail.png)
___

###3-FM播放
[http://yiapi.xinli001.com/fm/broadcast-detail.json?id=99389004&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/broadcast-detail.json?id=99389004&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
id	99389004
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](fm_play.png)
___

###3-FM播放-点赞 - POST
`http://bapi.xinli001.com/fm2/toggle_fav.json/`
#####`Request`:
```
fmid	99389004
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"code": 1
}
```
___

###3-FM播放-取消点赞 - POST
`http://bapi.xinli001.com/fm2/toggle_fav.json/`
#####`Request`:
```
fmid	99389004
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"code": 2
}
```
___

###3-FM播放-阅读原文
[http://bapi.xinli001.com/fm2/article.json/?pk=99389004&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/article.json/?pk=99389004&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
pk	99389004
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
```
{
	"data": "HTML文本",
	"code": 0
}
```
___


###3-FM播放-评论列表
[http://yiapi.xinli001.com/fm/comment-latest-list.json?offset=0&broadcast_id=99389004&limit=10&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/comment-latest-list.json?offset=0&broadcast_id=99389004&limit=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
broadcast_id	99389004
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](fm-play-comlist.png)
___

###3-FM播放-评论列表-评论FM - POST
`http://yiapi.xinli001.com/fm/post-comment.json`
#####`Request`:
```
broadcast_id	99389004
reply_object_id	0
key	046b6a2a43dc6ff6e770255f57328f89
content	哈喽？
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "3028874",
        "user_id": "1004261911",
        "content": "哈喽？",
        "created": "刚刚",
        "created_str": "2016-07-17 14:10:14",
        "zannum": 0,
        "replynum": 0,
        "role": 0,
        "role_id": 0,
        "user": {
            "id": "1004261911",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "replyuser": null,
        "replyobject": null,
        "is_comment": 1,
        "is_host_speaker": 0,
        "reply_user": null
    },
    "message": "发表成功，成功获得10金币",
    "num": "10"
}
```
___

###3-FM播放-评论列表-点赞某人评论 - POST
同`与主播详情-评论列表-点赞某人评论`
___

###3-FM播放-评论列表-回复某人 - POST
`http://yiapi.xinli001.com/fm/post-comment.json
#####`Request`:
```
broadcast_id	99389004
reply_object_id	3028874
key	046b6a2a43dc6ff6e770255f57328f89
content	哈喽
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "3028876",
        "user_id": "1004261911",
        "content": "哈喽",
        "created": "刚刚",
        "created_str": "2016-07-17 14:13:17",
        "zannum": 0,
        "replynum": 0,
        "role": 0,
        "role_id": 0,
        "user": {
            "id": "1004261911",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "replyuser": null,
        "replyobject": {
            "id": "3028874",
            "user_id": "1004261911",
            "content": "哈喽？",
            "created": "3分钟前",
            "created_str": "2016-07-17 14:10:14",
            "zannum": 0,
            "replynum": 0,
            "role": 0,
            "role_id": 0,
            "user": {
                "id": "1004261911",
                "username": "18810706793",
                "nickname": "菲拉兔",
                "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
            },
            "replyuser": null,
            "replyobject": null,
            "is_comment": 1,
            "is_host_speaker": 0
        },
        "is_comment": 1,
        "is_host_speaker": 0,
        "reply_user": null
    },
    "message": "发表成功，成功获得10金币",
    "num": "10"
}
```
___


###3-FM播放-主播详情
[http://yiapi.xinli001.com/fm/diantai-detai.json?id=921&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/diantai-detai.json?id=921&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
id	921
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](fm-play-diantai-detail.png)
___

###3-FM播放-主播详情-是否关注
[http://yiapi.xinli001.com/fm/diantai-check-guanzhu.json?diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://yiapi.xinli001.com/fm/diantai-check-guanzhu.json?diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd60689)
#####`Request`:
```
diantai_id	921
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"code": 0,
	"data": false
}
```
___

###3-FM播放-主播详情-加关注
[http://yiapi.xinli001.com/fm/diantai-toggle-guanzhu.json?diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://yiapi.xinli001.com/fm/diantai-toggle-guanzhu.json?diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
diantai_id	921
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"code": 0,
	"data": true,
	"message": "关注成功"/"取消关注"
}
```
___

###3-FM播放-主播详情-节目列表
[http://yiapi.xinli001.com/fm/diantai-jiemu-list.json?offset=0&limit=10&diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/diantai-jiemu-list.json?offset=0&limit=10&diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
limit	10
diantai_id	921
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](fm_play_diantai_detail_jiemulist.png)
___

###3-FM播放-主播详情-私信
[http://yiapi.xinli001.com/fm/diantai-jiemu-list.json?offset=0&limit=10&diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/diantai-jiemu-list.json?offset=0&limit=10&diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
other_id	775853
rows	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"count": 0,
	"data": [],
	"code": 0
}
```
___


###3-FM播放-主播详情-留言列表
[http://yiapi.xinli001.com/fm/diantai-comment-list.json?offset=0&limit=10&diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/diantai-comment-list.json?offset=0&limit=10&diantai_id=921&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
limit	10
diantai_id	921
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](fm-play-diantai-detail-comlist.png)
___

###3-FM播放-主播详情-评论电台 - POST
`http://yiapi.xinli001.com/fm/diantai-comment.json`
#####`Request`:
```
diantai_id	921
reply_object_id	0
key	046b6a2a43dc6ff6e770255f57328f89
content	哈喽？
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "3028867",
        "user_id": "1004261911",
        "content": "哈喽？",
        "created": "刚刚",
        "created_str": "2016-07-17 13:56:21",
        "zannum": 0,
        "replynum": 0,
        "role": 0,
        "role_id": 0,
        "user": {
            "id": "1004261911",
            "username": "18810706793",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "replyuser": null,
        "replyobject": null,
        "is_comment": 1,
        "is_host_speaker": 0
    },
    "message": "发表成功"
}
```
___

###3-FM播放-主播详情-点赞某人评论 - POST
`http://yiapi.xinli001.com/fm/post-comment-like.json`
#####`Request`:
```
comment_id	3009990
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": null,
    "message": "点赞成功"
}
```
___

###3-FM播放-主播详情-回复某人评论 - POST
`http://yiapi.xinli001.com/fm/diantai-comment.json`
#####`Request`:
```
diantai_id	921
reply_object_id	3009990
key	046b6a2a43dc6ff6e770255f57328f89
content	好
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "3028871",
        "user_id": "1004261911",
        "content": "好",
        "created": "刚刚",
        "created_str": "2016-07-17 14:02:29",
        "zannum": 0,
        "replynum": 0,
        "role": 0,
        "role_id": 0,
        "user": {
            "id": "1004261911",
            "username": "18810706793",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "replyuser": null,
        "replyobject": {
            "id": "3009990",
            "user_id": "1000632085",
            "content": "喜欢😍",
            "created": "4周前",
            "created_str": "2016-06-17 17:51:08",
            "zannum": 0,
            "replynum": 0,
            "role": 0,
            "role_id": 0,
            "user": {
                "id": "1000632085",
                "username": "xinli_14453245065348",
                "nickname": "暮雪晨星",
                "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
            },
            "replyuser": null,
            "replyobject": null,
            "is_comment": 1,
            "is_host_speaker": 0
        },
        "is_comment": 1,
        "is_host_speaker": 0
    },
    "message": "发表成功"
}
```
___


##4社区-发起讨论 - POST
`http://yiapi.xinli001.com/fm/post-forum-thread.json`
#####`Request`:
```
flag	0
title	"hello"
key	046b6a2a43dc6ff6e770255f57328f89
content	"hello"
token	b845588abcf58804c99d289584cd6068
images[] application/octet-stream
images[] application/octet-stream
images[] application/octet-stream //最多6张
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "27740",
        "user_id": "1004261911",
        "title": "有人吗",
        "content": "嗯",
        "created": "刚刚",
        "updated": "刚刚",
        "jin": "0",
        "commentnum": "0",
        "user": {
            "id": "1004261911",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "absolute_url": "http://yiapi.xinli001.com/fm/forum-share-page/27740",
        "images": [
            "http://ossimg.xinli001.com/20160717/82daa9a7e41de3b77e9118eae3ef3f01.jpg",
            "http://ossimg.xinli001.com/20160717/04d27cd71f02f1694e0193d9d866a7b1.jpg",
            "http://ossimg.xinli001.com/20160717/31fc4d7c6c555cc08adefb717b6169bf.jpg",
            "http://ossimg.xinli001.com/20160717/8062a899e40f382d89ee05ab139d6ea5.jpg",
            "http://ossimg.xinli001.com/20160717/238565837f61122aadb71332a206a91c.jpg",
            "http://ossimg.xinli001.com/20160717/cf5a1a523219bb262c4e5a3d36a92f3b.jpg"
        ]
    },
    "message": "发布成功"
}
```
___

##4社区列表-精华/最新
[http://yiapi.xinli001.com/fm/forum-thread-list.json?flag=0&offset=0&limit=10&type=1&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/forum-thread-list.json?flag=0&offset=0&limit=10&type=1&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
flag	0-精华 1-热门
offset	10
limit	10
type	1
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](forumlist.png)
___

##4社区列表-详情-评论列表
[http://yiapi.xinli001.com/fm/forum-comment-list.json?post_id=697&offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89](http://yiapi.xinli001.com/fm/forum-comment-list.json?post_id=697&offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
post_id	697
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](forum-detail-comlist.png)
___


##4社区列表-详情-发布评论 - POST
`http://yiapi.xinli001.com/fm/post-forum-comment.json`
#####`Request`:
```
flag	0
post_id	697
reply_user_id	0
key	046b6a2a43dc6ff6e770255f57328f89
content	不错
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "3028883",
        "user_id": "1004261911",
        "content": "不错",
        "created": "刚刚",
        "created_str": "2016-07-17 14:31:50",
        "zannum": "0",
        "replynum": "0",
        "role": "0",
        "role_id": "0",
        "user": {
            "id": "1004261911",
            "username": "18810706793",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "replyuser": null,
        "reply": [],
        "floor": 281
    },
    "message": "评论成功"
}
```
___

##4社区列表-详情-回复别人评论 - POST
`http://yiapi.xinli001.com/fm/post-forum-comment.json`
#####`Request`:
```
flag	0
post_id	697
reply_user_id	不为0
key	046b6a2a43dc6ff6e770255f57328f89
content	不错
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "code": 0,
    "data": {
        "id": "3028885",
        "user_id": "1004261911",
        "content": "真的",
        "created": "刚刚",
        "created_str": "2016-07-17 14:35:25",
        "zannum": "0",
        "replynum": "0",
        "role": "0",
        "role_id": "0",
        "user": {
            "id": "1004261911",
            "username": "18810706793",
            "nickname": "菲拉兔",
            "avatar": "http://ossimg.xinli001.com/20160329/9fe4842afb2c58c2200a1b9ae7a68ca9.png!80"
        },
        "replyuser": null,
        "reply": [],
        "floor": 282
    },
    "message": "评论成功"
}
```
___
##5发现-幻灯
[http://bapi.xinli001.com/fm2/hot_tag_list.json/?flag=4&offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/hot_tag_list.json/?flag=4&offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
flag	4
offset	0
rows	10
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](find-top5-slide.png)
___

##5发现-Alarmtext
[http://bapi.xinli001.com/fm2/alarmtext_list.json/?key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/alarmtext_list.json/?key=046b6a2a43dc6ff6e770255f57328f89)

#####`Response`:
![image](find-alarmtext.png)
___

##5发现-tag-搜索
[http://bapi.xinli001.com/fm2/broadcast_list.json/?offset=0&speaker_id=0&tag=%E5%BF%AB%E4%B9%90&rows=10&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/broadcast_list.json/?offset=0&speaker_id=0&tag=%E5%BF%AB%E4%B9%90&rows=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
speaker_id	0
tag	快乐/悲伤...无聊等18个
rows	10
key	046b6a2a43dc6ff6e770255f57328f89
```

#####`Response`:
![image](find-tag-searchlist.png)
___

##5发现-搜索-热门搜索tags
[http://bapi.xinli001.com/fm2/hot_tag_list.json/?flag=1&offset=0&rows=100&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/hot_tag_list.json/?flag=1&offset=0&rows=100&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
flag	1
offset	0
rows	100
key	046b6a2a43dc6ff6e770255f57328f89
```

#####`Response`:
![image](find-hot-search-taglist.png)
___

##5发现-搜索-关键词搜索
[http://bapi.xinli001.com/fm2/broadcast_list.json/?q=%E5%A4%B1%E6%81%8B&is_teacher=&offset=0&speaker_id=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/broadcast_list.json/?q=%E5%A4%B1%E6%81%8B&is_teacher=&offset=0&speaker_id=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
q	音乐/tag.name
is_teacher	
offset	0
speaker_id	0
rows	10
key	046b6a2a43dc6ff6e770255f57328f89
```

#####`Response`:
![image](find-search-resultlist.png)
___


##5发现-主播
[http://bapi.xinli001.com/fm2/hot_tag_list.json/?flag=4&offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/hot_tag_list.json/?flag=4&offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
limit	6
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](find-diantailist-6.png)
___

##6我的-签到
[http://bapi.xinli001.com/fm2/qiandao.json/?key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://bapi.xinli001.com/fm2/qiandao.json/?key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
key	046b6a2a43dc6ff6e770255f57328f89
token b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "num": "50",
    "code": 0,
    "msg": "恭喜你获得50个金币"
}
```
___

##6我的-关注电台
[http://yiapi.xinli001.com/fm/diantai-myguanzhu-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://yiapi.xinli001.com/fm/diantai-myguanzhu-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"code": 0,
	"data": []
}
// 没有数据的话 展示推荐关注列表
```
![image](mine-guanzhudiantai-list.png)
___

##6我的-关注电台-推荐关注
[http://yiapi.xinli001.com/fm/diantai-myguanzhu-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://yiapi.xinli001.com/fm/diantai-myguanzhu-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
![image](mine-guanzhudiantai-list.png)
___

##6我的-赞过的电台
[http://bapi.xinli001.com/fm2/favorite_list.json/?offset=0&user_id=1004261911&rows=10&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/fm2/favorite_list.json/?offset=0&user_id=1004261911&rows=10&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
offset	0
user_id	1004261911
rows	10
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
![image](mine-favdiantail-list.png)
___

##6我的-我的话题-发表的
[hhttp://yiapi.xinli001.com/fm/user-forum-thread-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://yiapi.xinli001.com/fm/user-forum-thread-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
![image](mine-forum-sendlist.png)
___

##6我的-我的话题-回复的
[http://yiapi.xinli001.com/fm/user-forum-comment-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://yiapi.xinli001.com/fm/user-forum-comment-list.json?offset=0&limit=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
![image](mine-forum-replylist.png)
___

##6我的-通知
[http://bapi.xinli001.com/fm2/notice_list.json/?offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://bapi.xinli001.com/fm2/notice_list.json/?offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
	"data": [],
	"code": 0
}
```
___

##6我的-私信
[http://bapi.xinli001.com/users/messages.json/?offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://bapi.xinli001.com/users/messages.json/?offset=0&rows=10&key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
offset	0
limit	10
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
![image](mine-messages.png)
___

##6我的-私信-详情
`同发送私信接口`
___


##7手机号注册-验证码
[http://bapi.xinli001.com/users/register_validcode.json/?phone=18810706793&key=046b6a2a43dc6ff6e770255f57328f89](http://bapi.xinli001.com/users/register_validcode.json/?phone=18810706794&key=046b6a2a43dc6ff6e770255f57328f89)
#####`Request`:
```
phone	18810706793
key	046b6a2a43dc6ff6e770255f57328f89
```
#####`Response`:
```
{
    "data": "发送成功",
    "code": 0
}
```
___

##7手机号注册-确认注册 - POST
`http://bapi.xinli001.com/users/register2.json/`
#####`Request`:
```
validcode	123456
nickname	哈哈
password2	132465
password1	132465
key	046b6a2a43dc6ff6e770255f57328f89
username	18810706794
```
#####`Response`:
```
{
    {
    "errors": {
        "validcode": [
            "注册验证码不正确"
        ]
    },
    "data": [
        "validcode:注册验证码不正确"
    ],
    "code": -1,
    "msg": "注册验证码不正确"
}
```
___


##8忘记密码-验证码
[http://bapi.xinli001.com/users/find_pwd.json/?key=046b6a2a43dc6ff6e770255f57328f89&username=18810706793](http://bapi.xinli001.com/users/find_pwd.json/?key=046b6a2a43dc6ff6e770255f57328f89&username=18810706793)
#####`Request`:
```
key	046b6a2a43dc6ff6e770255f57328f89
username	18810706794
```
#####`Response`:
```
{
    "data": "该手机号码没有注册",
    "code": -5
}
OR
{
    "data": "发送成功",
    "code": 0
}
```
___

##8忘记密码-重置 - POST
`http://bapi.xinli001.com/users/reset_pwd.json/`
#####`Request`:
```
password	123456
validcode	271662
key	046b6a2a43dc6ff6e770255f57328f89
username	18810706793
```
#####`Response`:
```
{
    "data": "密码修改成功",
    "code": 0
}
```
___

##9登录 - POST
`http://bapi.xinli001.com/users/get_token.json/`
#####`Request`:
```
password	gggg
key	046b6a2a43dc6ff6e770255f57328f89
username	18810706793
```
#####`Response`:
```
{
    "data": "username or password error",
    "post": {
        "password": "gggg",
        "key": "046b6a2a43dc6ff6e770255f57328f89",
        "username": "18810706793"
    },
    "code": -1,
    "msg": "邮箱或密码不正确"
}
OR
{
    "data": {
        "qq_openid": "",
        "introduce": "?哈哈?",
        "id": 1004261911,
        "renren_openid": "",
        "nickname": "菲拉兔",
        "avatar": "http://image.xinli001.com/images/avatar.jpg",
        "sina_openid": ""
    },
    "token": "b845588abcf58804c99d289584cd6068",
    "code": 0,
    "expire": "1471280139"
}
```
___
#####`myuserinfo`:
[http://bapi.xinli001.com/fm2/myuserinfo.json/?key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068](http://bapi.xinli001.com/fm2/myuserinfo.json/?key=046b6a2a43dc6ff6e770255f57328f89&token=b845588abcf58804c99d289584cd6068)
#####`Request`:
```
key	046b6a2a43dc6ff6e770255f57328f89
token	b845588abcf58804c99d289584cd6068
```
#####`Response`:
```
{
    "data": {
        "msgnum": 0,
        "qiandao": true,
        "noticenum": 0,
        "introduce": "?哈哈?",
        "id": 1004261911,
        "nickname": "菲拉兔",
        "avatar": "http://image.xinli001.com/images/avatar.jpg",
        "bitcoin": 70
    },
    "code": 0
}
```
#END

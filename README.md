# 91Porn-crawler
91porn爬虫在线api 及 在线web预览

**最新地址**：[https://eyey.pw](https://eyey.pw)

今日口令（每日21:00更新 ）**a5dcd**,时效:1天,总次数:1000

# API版接口 

接口baseUrl: https://91povideo.com/api/ (已被GFW屏蔽)  
备用1： https://ayay.pw/api/  
备用2： https://byby.pw/api/ 
备用3： https://eyey.pw/api/ 

## 接口：获取视频列表
| 描述     | 内容               |
| -------- | ------------------ |
| 接口功能 | 请求91porn视频列表 |
| 请求协议 | HTTPS              |
| 请求方法 | GET                |
| 请求url  | list_info          |
| 响应格式 | json               |

### 请求参数

| 参数     | 描述                                             | 必填 | 类型   |
| -------- | ------------------------------------------------ | ---- | ------ |
| category | 列表种类 ：rf-精华 tf-本月最热 空字符串-所有视频 | 否   | String |
| page     | 页码                                             | 是   | int    |

### 响应参数

| 参数        | 描述                     | 必有 | 类型          |
| ----------- | ------------------------ | ---- | ------------- |
| totalPage   | 总页数                   | 是   | String        |
| currentPage | 当前页                   | 是   | String        |
| category    | 回显列表种类字段         | 是   | String        |
| list        | 视频列表，object格式见下 | 是   | Array[Object] |

list object结构,如下：

| 参数       | 描述        | 必有 | 类型   |
| ---------- | ----------- | ---- | ------ |
| viewkey    | 视频viewkey | 是   | String |
| title      | 视频标题    | 是   | String |
| pic        | 封面图片URL | 是   | String |
| duration   | 视频时长    | 是   | String |
| loadtime   | 上传日期    | 否   | String |
| authorName | 作者名字    | 是   | String |

### 请求示例

```
https://91povideo.com/api/list_info?category=&page=1
```

### 响应示例


```
{
	"success": 1,
	"data": {
		"key": "1rf",
		"list": [{
			"viewkey": "c8cf551c39e0421239a2",
			"title": "标题示例1",
			"pic": "http://img.t6k.co/thumb/1_357370.jpg",
			"duration": "21:52",
			"loadtime": "9小时前",
			"authorName": "作者名字1"
		}, {
			"viewkey": "406e4a6c648a881a81d0",
			"title": "标题示例2",
			"pic": "http://img.t6k.co/thumb/1_357369.jpg",
			"duration": "11:23",
			"loadtime": "11小时前",
			"authorName": "作者名字2"
		}],
		"totalPage": "146",
		"currentPage": "1",
		"category": "rf"
	}
}
```

## 接口：获取视频详情

| 描述     | 内容               |
| -------- | ------------------ |
| 接口功能 | 请求91porn视频详情 |
| 请求协议 | HTTPS              |
| 请求方法 | GET                |
| 请求url  | video_info         |
| 响应格式 | json               |

### 请求参数

| 参数            | 描述                                            | 必填 | 类型   |
| --------------- | ----------------------------------------------- | ---- | ------ |
| viewkey         | 视频viewkey，列表接口中获取                     | 是   | String |
| userKey (K大写) | 口令（[购买口令](https://91povideo.com/#/buy)） | 是   | String |

### 响应参数

| 参数       | 描述                     | 必有 | 类型   |
| ---------- | ------------------------ | ---- | ------ |
| filename   | 视频编号                 | 是   | String |
| viewkey    | 总页数                   | 是   | String |
| title      | 当前页                   | 是   | String |
| duration   | 回显列表种类字段         | 是   | String |
| posterUrl  | 视频列表，object格式见下 | 是   | String |
| videoSrc   | 视频文件URL              | 是   | String |
| authorInfo | 作者信息（格式见下）     | 是   | Object |

authorInfo格式：

| 参数     | 描述       | 必有 |        |
| -------- | ---------- | ---- | ------ |
| name     | 作者用户名 | 是   | String |
| UID      | 作者UID    | 是   | String |
| videoNum | 作者视频数 | 是   | String |

### 请求示例

```
https://91povideo.com/api/video_info?viewkey=b61b439af0d4ae20b0dd&userKey=abcde
```

### 响应示例

```json
{
	"success": 1,
	"data": {
		"filename": "357411",
		"viewkey": "b61b439af0d4ae20b0dd",
		"title": "视频标题",
		"duration": "00:15",
		"posterUrl": "http://img2.t6k.co/thumb/357411.jpg",
		"authorInfo": {
			"name": "pangweihe",
			"UID": "23b4LzN97E18ASeQKLzukCCzL8GsHiZe1UmrKSKT7MDNb5tu",
			"videoNum": 1
		},
		"videoSrc": "视频文件地址"
	}
}
```



# 购买口令

[购买口令](https://eyey.pw/#/buy)

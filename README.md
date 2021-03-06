# Python3 爬虫合集![python version](https://img.shields.io/badge/python-3.5-brightgreen.svg)
> 人生苦短, 我用Python!

## Contents
<table>
	<tr>
		<td><a href="#bilibili">Bilibili</a></td>
		<td><a href="#豆瓣">豆瓣</a></td>
		<td><a href="#优酷">优酷</a></td>
		<td><a href="#pixiv">Pixiv</a></td>
	</tr>
	<tr>
		<td><a href="#网易云">网易云</a></td>
		<td><a href="#微博">微博</a></td>
		<td><a href="#知乎">知乎</a></td>
		<td><a href="#百度">百度</a></td>
	</tr>
	<tr>
		<td><a href="#微软">微软</a></td>
		<td><a href="#其他">其他</a></td>
	</tr>
</table>

## Bilibili
### [爬取弹幕并保存到txt中](bilibili/danmu.py)
- [Usage]: `python danmu.py $url`
- [Example]: `python danmu.py https://www.bilibili.com/video/av9933492/`

### [番剧索引](bilibili/bangumi_index.py)
#### 还在进行中...
需要传递的参数及说明如下所示, 由于 `tag_id` 的可选项太多, 暂时没有考虑
```
data  = {
	'page':1,			# 第几页
	'page_size':20,		# 每页的数量
	'version':0, 		# 类型： 全部 正片 剧场版 其他 [0 - 4]
	'is_finish':0,		# 状态： 全部 完结 连载 [0 2 1]
	'start_year':0, 	# 时间： 全部 某一年 [0 xxxx]
	'tag_id':'',		# 风格
	'index_type':1,		# 排序方式: 更新时间 追番人数 开播时间 [0 - 2]
	'index_sort':0,		# 排序类型: 递减 递增 [0 - 1]
	'area':0,			# 地区: 全部 日本 美国 其他 [0 2 3 4]
	'quarter':0   		# 季度： 全部 1月 4月 7月 10月 [0 - 4]
}
```
- [Usage]: `python bangumi_index.py [-t <type> | -a <area> | -e <state> | -m <time> | -s <season> |--tag <style> | --index_type <index_type> | --index_sort <index_sort>]`
- 返回的 `Json` 文件
<div align="center">
	<img src="bilibili/bangumi-1.png" alt="bangumi-1" width="600">
</div>

- `list` 中一项
<div align="center">
	<img src="bilibili/bangumi-2.png" alt="bangumi-2" width="600">
</div>

## 豆瓣
### [爬取豆瓣电影top250并存到Excel中](douban/MovieTop250.py)
<div align="center">
	<img src="douban/movieTop250.png" alt="douban" width="500">
</div>

## 优酷
### [爬取优酷视频弹幕](youku/danmu.py)
- 使用前记得修改 `data` 和 `headers` 中的 `Referer` 数据，我填入的是[火影第一集](http://v.youku.com/v_show/id_XNTQwMTgxMTE2.html)的弹幕请求数据
- [视频介绍](https://www.bilibili.com/video/av13784309/)

### [爬取优酷首页轮换图](youku/screen_pics.py)
<div align="center">
	<img src="https://i.loli.net/2017/11/07/5a0155cebc280.png" alt="youku" width="500">
</div>

## Pixiv
### [爬取首页的轮换图片](pixiv/cover.py)
<div align="center">
	<img src="pixiv/pixiv.png" alt="pixiv首页轮换图" width="500">
</div>

## 网易云
### [下载网易云歌曲](netease/download_music.py)
- 网易云获取歌曲 `API` 为 `http://music.163.com/song/media/outer/url?id={song_id}.mp3`
- 只需要传入对应歌曲的 `song_id` 即可

## 微博
### [爬取微博亚洲新歌榜top50并存到Excel中](weibo/NewSongTop50.py)
<div align="center">
	<img src="weibo/weibo.png" alt="微博亚洲新歌榜" width="450">
</div>

## 知乎
### [爬取知乎回答图片](zhihu/image.py)
- 使用前需要更新问题 `id`, 填入 `Cookie`, `include` 应该不需要更新

### [爬取知乎异步加载页面数据(第二页及之后)](zhihu/ajax_page.py)
- 返回未验证方式是因为没有给headers传递 `X-API-VERSION`, `X-UDID`, `authorization` 等参数
- 问题来自知乎一位朋友问我, 因此做的比较粗糙, 没有详细提取数据, 仅将答主提取出来
- 得到的一些答主 [数据](zhihu/ajax_page.txt)

## 百度
### [爬取贴吧图片并保存到对应pid文件夹下](baidu/getTiebaPics.py)
- [Usage]: `python danmu.py $pid`
- [Example]: `python getTiebaPics.py 2271504759`

### [爬取百度图片](baidu/getBaiduPics.py)
- [Usage]: `python3 getBaiduPics.py [Word] [pages = 1]`
- [Example]: `python3 getBaiduPics.py 猫 30`
- 注: 图片将保存在关键词的同名目录下。

## 微软
### [爬取bing主页背景图](bing/cover.py)
<div align="center">
	<img src="bing/Piraputanga_ZH-CN13303102627_1920x1080.jpg" alt="bing" width="600">
</div>
<div align="center">
	<img src="bing/QQ截图20171130191346.jpg" alt="screenshot" width="600">
</div>

## 其他
### [爬取「ONE · 一个」的插图](one/image.py)
- [「ONE · 一个」](http://www.wufazhuce.com/)

### 爬取[煎蛋网](http://jandan.net/ooxx/)妹子图
- [问题](http://bbs.fishc.com/thread-98098-1-1.html)来自[鱼C互助区](http://bbs.fishc.com/bestanswer.php?mod=huzhu)
- [代码](fishC/jandan.py)
    - 此代码并没有加下载图片的函数。因为我之前试过爬微博图片，与其自己写下载函数，倒不如把链接保存下来，全部扔到迅雷来下载，那样速度快多了
- 有时间改成多线程


### [爬取堆糖图片](duitang/picture.py)
- 有时间将爬取专辑的函数加上
<div align="center">
	<img src="https://i.loli.net/2017/11/13/5a09631192f59.png" alt="堆糖·古风" width="600">
</div>

### [爬取慕课网课程](imooc/README.md)
<div align="center">
	<img src="imooc/images/img-7.png" alt="慕课网课程" width="600">
</div>
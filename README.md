# WeiboSpider
利用`selenium`实现后台自动爬取**指定关键词下**发布的所有微博及其相关数据
## 注意事项
1. 由于selenium对浏览器有要求, 在运行之前请确保计算机已经安装了***Firefox浏览器***或***Chrome浏览器***  
2. 运行程序前, 需要根据自己使用的浏览器下载对应的浏览器驱动, 并将驱动与python.exe放置在同一文件夹中, 这里给出了两种浏览器驱动的压缩文件, 也可以自行上网下载

浏览器名称 | 驱动名
---- | ----
Firefox | geckodriver.exe
Chrome | chromedriver.exe

## 爬取内容

 内容 | 变量名 | 数据类型
 ---- | ---- | ----
  用户名 | ID | str
  用户主页 | Href | str
  微博博文 | Blog | str
  发布时间 | PubTime | str
   点赞数  | Like | int
   评论数 | Comment | int
   转发数 | Transfer | int

## 例子
先爬取关键词**微博**下的前20页微博信息, 接着每隔半小时(1800s)更新一次数据
```
csv_file = 'C:/test.csv'
my_username = 'abcdefg'
my_password = '11111111'
keyword = '微博'

Standby(keyword, csv_file, my_username, my_password, maxpage=20, sleeptime=1800)

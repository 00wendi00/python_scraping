# scraping
Basic knowledge of Scraping


根据<用python写网络爬虫>一书,  网络爬虫.
环境:win10 , python3.5.2


目录 :
## base
## cache
## captcha
## dynamic
## form_ui
## mongo
## mongo_queue
## multi_thread


以下为文件说明 :

## base

crawling1           网络爬虫 -- robots.txt, 网站地图, 网站大小, 使用技术, 所有者; 下载网页,网站地图爬虫.ID遍历爬虫,链接爬虫. 寻找网站所有者

crawling2           数据抓取 . Soup , 补全prettify , 定位find

ScrapeCall          回调类 -- 扩展 : 重写了__init__和__call__方法 --> 将scrape的数据写入csv文件中

test_contrast       正则, soup, Lxml 三种抓取方式进行对比 . 正则和Lxml相当. 基本是soup的6倍.

test_lxml           Lxml.html 的使用

Throttle            推迟调用线程的运行 -- time.sleep()



## cache

DiskCache           磁盘缓存 . 将下载的html存入磁盘文件中

Downloader          为链接爬虫添加缓存支持 -- 存入磁盘文件 .   __call__类的实例当函数调用.

link_crawler文件    Crawl from the given seed URL following links matched by link_regex

test



## captcha

test_regist         使用mechanicalsoup获得、填充、提交表单 -- 注册,  使用pytesseract获得图片中的文字

test_register       在注册页面中 . 1.抓取注册页面中的图片, 使用Base64解码图像数据--> 二进制   2.将图片转换为黑白, 将图片阈值化, 保存图片, image_to_string, 限定字符集, 返回名称和识别的字符   3.tesseract-ocr需要下载安装,设环境变量:参考pytesseract书签 .



## dynamic

countries.txt

test1               对Ajax接口的爬取. 存入countries.txt文件中.

此模块缺少 --  渲染动态网页. PySide, Selenium



## form_ui

edit                提交表单 -- 编辑国家人口.

gain_cookie         提交表单 :  获取表单, 添加cookie支持, 填表单, 提交, 返回Response.

submit_post         提交表单 :  获取表单, 添加cookie支持, 填表单, 提交, 返回Response.

test_mechanize      提交表单 :  login page + edit page . 使用mechanical模块, 在3.x版本中, 为mechanicalsoup模块, 详见https://piratefache.ch/python-3-mechanize-and-beautifulsoup/



## mongo

MongoCache          基于MongoDB的缓存 . 压缩解压, 索引

test1               -- mongodb, python CRUD , 排序, 多级元素操作

test2               -- mongodb, python 多级元素操作, 查询修改.

test3               测试 MongoCache

test4               抓取网页, 存入MongoDB中



## mongo_queue

MongoQueue          基于 MongoDB 实现的队列 . 定义了执行过程中的三种状态 : OUTSTANDING, PROCESSING, COMPLETE

process_test        测试process_crawler , 8进程

thread_test         1. 启动多进程, multiprocessing   2. 多线程下载网页 threading   3. 使用MongoDB -- 线程安全



## multi_thread

AlexaCallback       回调类 : 读取CSV文件.  下载读取zip文件

link_crawler        串行下载500个页面, 缓存至MongoDB中

test1               测试 link_crawler -- 串行下载500个页面, 缓存至MongoDB中

thread_test         1.多线程下载网页, threading  2.循环创建线程  3.队列的基本操作 -- 线程安全.


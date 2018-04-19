# spider-test
#测试python的爬虫
#coding:utf-8
import requests
from lxml import etree
#获取数据
url = 'https://book.douban.com/subject/1084336/comments/'
r = requests.get(url).text
#解析数据
s = etree.HTML(r)#解析html数据
#复制浏览器的xpath，print (s.xpath('//*[@id="comments"]/ul/li/div[2]/p/text()'))
#手写的xpath
print (s.xpath('//div[@class="comment"]/p/text()'))


# Notes from Tutorial
http://doc.scrapy.org/en/latest/intro/tutorial.html

scrapy startproject tutorial

1. make sure scrapy is installed
pip install scrapy

2. for the hello world example, run this command
git clone https://github.com/scrapy/dirbot.git && cd dirbot && scrapy crawl dmoz -o items.json && open items.json

### to start the shell at a domain
scrapy shell "http://www.dmoz.org/Computers/Programming/Languages/Python/Books/"
>>> response.xpath('//title')
[<Selector xpath='//title' data=u'<title>DMOZ - Computers: Programming: La'>]
>>> response.xpath('//title').extract()
[u'<title>DMOZ - Computers: Programming: Languages: Python: Books</title>']
>>> response.xpath('//title/text()')
[<Selector xpath='//title/text()' data=u'DMOZ - Computers: Programming: Languages'>]
>>> response.xpath('//title/text()').extract()
[u'DMOZ - Computers: Programming: Languages: Python: Books']
>>> response.xpath('//title/text()').re('(\w+):')
[u'Computers', u'Programming', u'Languages', u'Python']
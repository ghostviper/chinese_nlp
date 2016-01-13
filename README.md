#一些汉语言处理的东西

## segment 汉语言分词
- 原理：HHM
- 依赖：numpy scipy hhmlearn 
- 参考：
http://www.52nlp.cn/itenyh%E7%89%88-%E7%94%A8hmm%E5%81%9A%E4%B8%AD%E6%96%87%E5%88%86%E8%AF%8D%E5%9B%9B%EF%BC%9Aa-pure-hmm-%E5%88%86%E8%AF%8D%E5%99%A8
http://sbp810050504.blog.51cto.com/2799422/1251640
- TODO：
    没有针对英文单词、标点等处理，也没有窗口化操作

	
## 主题分类
- 原理：LDA & Labled LDA
- 依赖：gensim
- 参考:
http://blog.itpub.net/16582684/viewspace-1253901/
https://radimrehurek.com/gensim/models/ldamodel.html
https://shuyo.wordpress.com/
- TODO:
	感觉效果不是很好啊

## 情感分析
- 原理: 基于统计的方式
- 依赖：ntlk sklearn
- 语料：某东的商品评论，好评-差评
- 参考：
http://rzcoding.blog.163.com/

## 贝叶斯分类
- 用C/C++重新实现后，发现内存占用率和运算速度比Python要块很多。
- 通过Sogou的训练语料发现，10个分类下，10000特征词的分类准确率在75%左右，而在京东抓取的好评/差评语料训练后，测试分类精度达到91%左右。

## 最大熵分类器
- 原理：自行Google
- 参考：
http://www.fuqingchuan.com/2015/03/776.html
http://www.nltk.org/_modules/nltk/classify/maxent.html
http://www.umiacs.umd.edu/~hal/megam/index.html
- NOTE：
基本是按照nltk的GIS算法翻译过来的，没有实现IIS，所以训练的速度非常的慢。
- MEGAM
添加了MEGAM部分，底层调用的megam是基于L-BFGS实现的，所以速度还是挺快的，有实用价值了。另外底层调用的megam是
二进制程序（32位）的，所以你的系统要支持32位的运行库（dnf install glibc.i686）

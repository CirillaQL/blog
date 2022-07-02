---
title: "聚合搜索项目-leakedSearch开发记录（1）"
description: "研发一个基于Go爬虫的Onlyfans等流出视频的聚合搜索器"
date: 2022-07-02T19:28:30+08:00
draft: true
categories:
    - 技术
tags:
    - Golang
    - Colly
    - Vue
---
# leakedSearch开发记录(1)
在离职休息了一段时间后，准备着手开发一个基于Golang爬虫的后端项目，爬取的内容主要是诸如Spankbang、Porntn、DirtyShip爬取的一些Onlyfans的流出视频等等。方便一次搜索就可以获得所有的结果。
整个项目的核心便是**后端的搜索（爬虫）与数据处理**以及前端的优雅展示（这里其实就前端来说难度应该不算是很大，但是对我没怎么写过前端的人来说应当算是比较难的地方）。在后端的数据选择处理这里，考虑过两个框架选择：python的requests与beautifulSoup结合爬虫，或者学习使用Golang的Colly爬虫框架。在对比了二者之后，决定采用Golang的Colly进行爬虫处理。主要理由如下：
+ 使用Golang可以继续提高自己的Go技术。
+ 在本项目的情境下，会有涉及到多个网站的并行爬取，使用Go开发更合适。
+ 作为后端直接使用Gin来与前端交互。
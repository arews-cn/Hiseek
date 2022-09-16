# Hiseek
一个快速从web.archive.org找到目标的工具

#### 使用
```bash

  # 
  cat domains.txt | Hiseek 
  
  echo example.com | Hiseek

  Hiseek -d example.com 


  # 文件后缀查询
  echo example.com | Hiseek -s \.js

  # 多个关键字查询
  echo example.com | Hiseek -s proxy,url=,=http 

  # 关键字排除查询
  echo example.com | Hiseek -e www

  # 使用子域名 查询（example.com 存档记录太多时，有些记录查不到，可以使用 example.com 的子域名进行搜索）
  echo example.com | Hiseek -w dict.txt 

  # 查询结果导出 子域名、子域名字典
  # 生成 sub_domain_example.txt 、dict_example.txt 两个文件
  echo example.com | Hiseek -od example.txt

  # 使用代理 proxy 和xray、nuclei 等联动
  echo example.com | Hiseek -proxy http://127.0.0.1:7777 

```


#### 安装

```bash
  go install github.com/arews-cn/Hiseek@latest

```


#### 自己打包
```bash
 # 默认打包
 go build 

 # mac
 CGO_ENABLED=0 GOOS=darwin GOARCH=amd64 go build -o Hiseek main.go 
 
 # windows
 CGO_ENABLED=0 GOOS=windows GOARCH=amd64 go build -o Hiseek.exe main.go

 # linux
 CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o Hiseek main.go 

```

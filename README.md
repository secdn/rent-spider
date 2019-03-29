# rent-spider

豆瓣爬虫找房，支持以下功能

1. Docker直接部署
2. 新房源邮件提醒
3. 过滤相似房源


## 运行

1. 修改config.py配置

```py

# 邮箱配置，发送方qq邮箱需要授权码登陆，其他邮箱需要在设置中打开SMTP功能
mail = {
    'sender': '***@sina.cn',
    'host': 'smtp.sina.com',
    'receivers': ['***@qq.com'],
    'password': 'password',
    'subject_prefix': '租房爬虫信息'
}

# 数字为小组编号，有些英文的可以试下搜索，URL中能拿到这个
groups = [
    (106955, '深圳租房团'),
    (512841, '深圳南山租房（个人房源免费推广）'),
    (134156, '深圳租房★（个人房源免费推广）'),
    (512840, '深圳福田租房（个人房源免费推广）'),
]

# 这个是拼在搜索url中需要搜索的地方
locations = ('南山', '福田', '绿景虹湾', '侨香', '前海东岸')

# 标题需要排除的关键词
exclude_words = ('求租', '已租', '已出租')


```

2. 通过Docker Compose 运行

```py
    # cd到项目所在目录
    cd /app 
    docker-composr up -d
```

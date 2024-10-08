# 源码安装 GraphRAG

## 1. 安装 Python 3.10-3.12 （官网教程安装）

## 2. 安装 Poetry （官网教程安装）

## 3. Git 下载源码

## 4. 安装依赖 Instaal Dependencies

```
# 在源码根目录下 运行
# Install Python dependencies.
poetry install

```

## 4. 初始化 Init 

### 1. 创建测试文件夹.并初始化配置

```
# 创建文件夹
mkdir ./ragtest

# 初始化 
# python -m graphrag.index [--init] [--root PATH]
# poetry 命令为
poetry run poe index --init --root ./ragtest
```

### 2. 建立索引 
```
poetry run poe index --root ./ragtest
```

### 3. 查询结果

```
poetry run poe query --root ./ragtest --method global "请总结下故事大纲，并分析下主角的人物关系图"


```

### 4.  提示词格式：


请分析每张图片名称及图片内容，按照以下维度总结内容，不用直接显示图片，也不用OCR工具，不要输出图片序号,不用分割线，标题格式加粗
"""
文件名：{{ 文件名 }}
标题：{{ 标题 }}
内容总结：{{ 内容总结 }}
内容词条：{{ 内容词条 }}
用途：{{ 用途 }}
"""
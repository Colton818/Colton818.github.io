---
title: learning note
date: 2026-02-15 17:54
---
# the first title
## second title
*斜体*  
**粗体**
***粗斜体***

# 无序列表
- 1
- 2
- 3
  - 子项目
    - 子项目

# 有序列表
1. 1
2. 2
3. 3

![你好](https://cdn.luogu.com.cn/upload/image_hosting/wjq79htv.png?x-oss-process=image/resize,m_lfit,h_170,w_225 "百度")


# 插入代码片段
```python
def hello():
    print("Hello, World!")
```

```cpp
#include<bits/stdc++.h>
using namespace std;

int main(){
    cout<<"hello,world!";
    return 0;
}
```

> 引用
> > 嵌套引用
---  

水平线

| 左对齐 | 居中对齐 | 右对齐 |
| :--- | :---: | ---: |
| 3 | 3 | 1 |
| 长内容 | 这里也是 | 123 |

# 这是一个带有脚注的句子[^123]。这是另一个标注[^23]

[^123]: 这里是脚注的详细内容。它可以很长，并且支持**Markdown格式**。
[^23]: second

# 定义列表  
kramdown
: 一个功能丰富的 Markdown 处理器，是 Jekyll 的默认选择。

Jekyll
: 一个静态网站生成器，常用于博客和项目文档。

# 缩写 鼠标悬停时显示
*[HTML]: HyperText Markup Language
*[JAMstack]: JavaScript, APIs, and Markup stack

我们现在用 HTML 和 JAMstack 构建网站。

# 自定义属性
### 这是一个标题
{: #custom-id}

## 代码添加行数
```python
print("这个代码块有行号")
print("lll")
```
{: .line-numbers}

## 代码禁用高亮
```python
print("这个代码块没有高亮")
```
{: .language-plaintext}

## 数学公式


$$
H_n=1+\frac{1}{2}+\frac{1}{3}+...+\frac{1}{n}=\sum_{i=1}^{n}\frac{1}{i}=O(\log n)
$$

# 你好
$
\alpha
$

# 高级货 liquid

## 最新文章
{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}

以上列表由 Liquid 动态生成。
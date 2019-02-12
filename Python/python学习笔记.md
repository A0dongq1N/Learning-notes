# python



## 基础语法



## 进阶技巧

### 特殊的.py文件

#### sitecustomize.py

- 作用：一般用于设置默认编码

- 用法

  ```python
  import sys
  sys.setdefaultencoding('utf-8')
  ```

  

### 正则表达式

#### re

- 用法

  re.match(pattern, string, flags)

  pattern为模式串

  string为匹配串

  flags为标志位，用于控制正则表达式的匹配方式，比如：是否区分大小写，多行匹配等

  **注意**：pattern和string的位置不能互换，否则结果会出错

  

### 常见问题

#### 问题：IndentationError: unindent does not match any outer indentation level

- 解决方法：空格和tab键混用的结果，对齐就可以了








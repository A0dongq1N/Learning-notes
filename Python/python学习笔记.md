# python



## 基础语法

### os.path

#### os.path.expanduser()

- 作用：替换路径中的`~`

- 用法

  ```python
  >>>os.path.expanduser("~/Build")
  '/usr/testuser/Build'
  >>>os.path.exists(os.path.expanduser("~/Build"))
  True
  ```

  

#### os.path.expandvars()

- 作用：替换路径中的`$NAME`或者${NAME}

- 用法

  ```python
  >>>os.path.expandvars("$HOME")
  '/home/tt'
  ```

- 举一个在实际项目中用到的例子

  ```python
  def handle(self, **options):
          if options["filename"]:
              fileobj = open(expanduser(expandvars(options["filename"])), "w")
          else:
              fileobj = self.stdout
          fileobj = write_nexus(
              fileobj,
              options["language_list"],
              options["meaning_list"],
              set(["L", "X"]),  # exclude
              options["dialect"],  # dialect
              True,  # label cognate sets
              options["ascertainment_marker"])['fileobj']
          fileobj.close() 
  ```

#### os.path.realpath(path)

- 作用:返回path的`真实路径`
- **注意**：同`os.path.abspath`的区别就是当一个文件为连接文件时，`os.path.realpath`可以返回`链接文件所指向文件的路径`，而`os.path.realpath`则返回`链接文件的路径`

#### os.path.abspath(path)

- 作用:返回path的`绝对路径`

  

###  --file--

- 作用：输出当前执行文件的文件名，但是这里有个坑，如果执行文件是以相对路径的形式执行，那么--file--只能返回文件名，如果执行文件是以绝对路径的形式执行，那么--file--会返回绝对路径的文件名例如：

  ```python
  python config_helper.py ----> config_helper.py
  python /data/server/config_helper.py  --->/data/server/config_helper.py
  ```

  







## 进阶技巧

### pip

#### 问题1：pip安装出现errno[10061]

- 解决方法：
  1. fidder代理去掉
  2. 公司浏览器代理去掉，各个浏览器都看下

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

### 字符编码问题

#### 为什么在sys.setdefaultencoding之前要写reload(sys)

这是因为python模块的加载过程中首先加载了`site.py`，在`site.py`文件中有这么一段代码

```python
if hasattr(sys,"setdefaultencoding"):
    del sys.setdefaultencoding
```

所以在`sys`加载后，`setdefaultencoding`方法被删除了，所以需要`reload(sys)`来重新导入sys，来设置编码

### 常见问题

#### 问题：IndentationError: unindent does not match any outer indentation level

- 解决方法：空格和tab键混用的结果，对齐就可以了








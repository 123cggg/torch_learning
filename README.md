# pathlib 方法
  from pathlib import Path
# 获取上层目录
  Path.cwd().parent
# 获取上上层目录
  Path.cwd().parent.parent
# 模块安装与查看
  pip install pathlib
  pip show pathlib
# 获取绝对路径(两种方法)
>>> Path().cwd()
  WindowsPath('C:/Users/Mac/Desktop/Python_learning')
>>> Path().resolve()
  WindowsPath('C:/Users/Mac/Desktop/Python_learning')
# 创建文件/目录
创建目录时要注意两个参数：
  parents：默认为 False，如果父目录不存在，会抛出异常，True 则创建这些目录。
  exist_ok：默认为 False，目录已存在时会抛出异常。
这里我们在 Python_learning 目录下创建 path_test 文件夹
>>> p = Path('C:/Users/Mac/Desktop/Python_learning/path_test')
>>> p.mkdir(parents=True, exist_ok=True)
  touch()用于创建空文件，父目录必须存在，否则抛出异常。
>>> p = Path('E:/material/test1.txt')
>>> p.touch(exist_ok=True)
# 文件\目录判断
判断是否为文件夹：
>>> Path('E:/material/pathlib用法').is_dir()
  True
判断是否为文件：
>>> Path('E:/material/pathlib用法/txt文件.txt').is_file()
  True
判断路径是否存在：
>>> Path('E:/material/error.txt').exists()
  False
路径拼接/拆分(两种方法)：
>>> Path('E:/material', 'pathlib用法')
  WindowsPath('E:/material/pathlib用法')
>>> Path.cwd().parent.joinpath('pathlib用法')
  WindowsPath('E:/material/pathlib用法')
# 使用 '/' 进行路径拼接。
路径拼接：
  Path Object / Path Object
  str / Path Object
  Path Object / str 
>>> Path('E:/') / Path('/material/')
  WindowsPath('E:/material')
>>> 'E:/' / Path('/material/')
  WindowsPath('E:/material')
>>> Path('E:/') / '/material/'
  WindowsPath('E:/material')
按照分隔符将文件路径分割：
>>> p.parts
('E:\\', 'material', 'pathlib用法')
# 获取文件\目录信息
获取文件\目录名：
>>> p = Path('E:/material/pathlib用法/excel文件.xlsx')
>>> p.name
'excel文件.xlsx'
获取不包含后缀的文件名：
>>> p.stem
'excel文件'
获取文件后缀名：
>>> p.suffix
'.xlsx'
获取上层目录路径：
>>> p = path.cwd()
>>> p.parent
WindowsPath('E:/material')


————————————————
版权声明：本文为CSDN博主「Dream丶Killer」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_43965708/article/details/122537713

# NeShellLoopAndFileOpt Shell之循环和文件读写

## 一、for循环
### 1.1 循环遍历
`seq 1 10 ` 产生1-10的数据集合
```bash
#!/bin/bash
for i in `seq 1 10`
do
	echo "数字：$i"
done
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/loop_print.png)

### 1.2 循环求和
`expr 2 + 3` 表示求和运算
```bash
#!/bin/bash
j=0 # 不能有空格
for((i=0; i<=100; i++)) # “(())” 代表算术运算的集合
do
	j=`expr $i + $j` # 注意空格
done
echo $j
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/loop_print.png)

### 1.3 循环压缩文件
`find . -name "*.sh"` 寻找当前目录下所有以".sh"结尾的文件
```bash
#!/bin/bash
for i in `find . -name "*.sh"`
do
	j=`expr $i + $j` # 注意空格
done
echo $j
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/loop_compress_file.png)

## 二、while循环
### 2.1 循环遍历
#### 2.1.1 算术运算循环
```bash
#!/bin/bash
i=0
while((i<15))    # 算术运算集合
do
	echo "数字：$i"
	i=`expr $i + 1`
done
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/while_print1.png)

#### 2.1.1 逻辑运算循环
```bash
#!/bin/bash
i=0
while [[ i -lt 15 ]]    # 逻辑运算集合
do
	echo "数字：$i"
	i=`expr $i + 1`
done
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/while_print2.png)

### 2.1 循环读文件
`read line` 将输入/文件读到line中
```bash
#!/bin/bash
while read line
do
	echo $line
done<./text.txt
```
实操：  
![image](https://github.com/tianyalu/NeShellLoopAndFileOpt/blob/master/show/while_read.png)
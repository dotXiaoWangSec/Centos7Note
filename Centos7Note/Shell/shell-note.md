# Shell

Shell 是一个用 C 语言编写的程序，它是用户使用 Linux 的桥梁。Shell 既是一种命令语言，又是一种程序设计语言。Shell 是指一种应用程序，这个应用程序提供了一个界面，用户通过这个界面访问操作系统内核的服务。Ken Thompson 的 sh 是第一种 Unix Shell，Windows Explorer 是一个典型的图形界面 Shell。

Shell 脚本（shell script），是一种为 shell 编写的脚本程序。业界所说的 shell 通常都是指 shell 脚本，shell 和 shell script 是两个不同的概念。

Shell 编程跟 JavaScript、php 编程一样，只要有一个能编写代码的文本编辑器和一个能解释执行的脚本解释器就可以了。

Linux 的 Shell 种类众多，常见的有：

1. Bourne Shell（/usr/bin/sh或/bin/sh）

2. Bourne Again Shell（/bin/bash）

3. C Shell（/usr/bin/csh）

4. K Shell（/usr/bin/ksh）

5. Shell for Root（/sbin/sh



# 第一个脚本

```shell
打开文本编辑器(可以使用 vi/vim 命令来创建文件)，新建一个文件 test.sh，扩展名为 sh（sh代表shell），扩展名并不影响脚本执行，见名知意最好 
#!/bin/bash
echo "Hello World !"

#! 是一个约定的标记，它告诉系统这个脚本需要什么解释器来执行，即使用哪一种 Shell。
echo 命令用于向窗口输出文本。

执行代码：
chmod +x ./test.sh  #使脚本具有执行权限
./test.sh  #执行脚本

## bash和env bash的区别

#!/usr/bin/env bash  在不同的系统上提供了一些灵活性。
优点：
1.用户不需要去寻找程序在系统中的位置（因为在不同的系统，命令或程序存放的位置可能不同），只要程序在你的PATH中；
2.它会根据你的环境寻找并运行默认的版本，提供灵活性。（保存用户信息的文件/etc/passwd）
缺点:
有可能在一个多用户的系统中，别人在你的PATH中放置了一个bash，可能出现错误。
#!/usr/bin/bash  将对给定的可执行文件系统进行显式控制。
大部分情况下，/usr/bin/env是优先选择的，因为它提供了灵活性，特别是你想在不同的版本下运行这个脚本；而指定具体位置的方式#!/usr/bin/bash，在某些情况下更安全，因为它限制了代码注入的可能。
```





# 变量

## 定义变量

变量名不加美元符号（$）

```shell
your_name="runoob.com"
```

注意，变量名和等号之间不能有空格，

**变量名的命名须遵循如下规则：**

命名只能使用英文字母，数字和下划线，首个字符不能以数字开头。

中间不能有空格，可以使用下划线（_）。不能使用标点符号。

不能使用bash里的关键字（可用help命令查看保留关键字）。

使用一个定义过的变量，只要在变量名前面加美元符号即可

```shell
your_name="qinjx"

echo $your_name

echo ${your_name}
```

变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界

## 只读变量

使用 readonly 命令可以将变量定义为只读变量，只读变量的值不能被改变。类似于C语言中的常量

```shell
#!/bin/bash
myUrl="http://www.google.com"
readonly myUrl
myUrl="http://www.runoob.com"
```

## 删除变量

使用 unset 命令可以删除变量。语法：

```shell
unset variable_name
```

变量被删除后不能再次使用。unset 命令不能删除只读变量。



## 变量类型

运行shell时候会出现三种变量：

1) 局部变量 局部变量在脚本或命令中定义，仅在当前shell实例中有效，其他shell启动的程序不能访问局部变量。

2) 环境变量 所有的程序，包括shell启动的程序，都能访问环境变量，有些程序需要环境变量来保证其正常运行。必要的时候shell脚本也可以定义环境变量。

3) shell变量是由shell程序设置的特殊变量。shell变量中有一部分是环境变量，有一部分是局部变量，这些变量保证了shell的正常运行



## 追加内容

```shell

:<<EOF
注释内容...
注释内容...
注释内容...
EOF



EOF 也可以使用其他符号:
:<<'
注释内容...
注释内容...
注释内容...
'

:<<!
注释内容...
注释内容...
注释内容...
!
```



## 字符串操作

Shell 字符串

**单引号**

```shell
str='this is a string'
```

**单引号字符串的限制：**

单引号里的任何字符都会原样输出，单引号字符串中的变量是无效的；

单引号字串中不能出现单独一个的单引号（对单引号使用转义符后也不行），但可成对出现，作为字符串拼接使用。



**双引号**

````
your_name='this is test'
str="Hello, I know you are \"$your_name\"! \n"
echo -e $str


双引号里可以有变量 
双引号里可以出现转义字符   拼接字符串
your_name="runoob"
使用双引号拼接
greeting="hello, "$your_name" !"
greeting_1="hello, ${your_name} !"
echo $greeting  $greeting_1

使用单引号拼接
greeting_2='hello, '$your_name' !'
greeting_3='hello, ${your_name} !'
echo $greeting_2  $greeting_3


获取字符串长度
string="abcd"
echo ${#string} #输出 4
提取子字符串
以下实例从字符串第 2 个字符开始截取 4 个字符：
string="runoob is a great site"
echo ${string:1:4} # 输出 unoo



查找子字符串
查找字符 i 或 o 的位置(哪个字母先出现就计算哪个)：
string="hello is a great site"
echo `expr index "$string" io`  输出 4
````



# 基本运算符

## 算术运算符

变量 a 为 10，变量 b 为 20：

| 运算符 | 说明                                          | 举例                          |
| ------ | --------------------------------------------- | ----------------------------- |
| +      | 加法                                          | `expr $a + $b` 结果为 30。    |
| -      | 减法                                          | `expr $a - $b` 结果为 -10。   |
| *      | 乘法                                          | `expr $a \* $b` 结果为  200。 |
| /      | 除法                                          | `expr $b / $a` 结果为 2。     |
| %      | 取余                                          | `expr $b % $a` 结果为 0。     |
| =      | 赋值                                          | a=$b 将把变量 b 的值赋给 a。  |
| ==     | 相等。用于比较两个数字，相同则返回 true。     | [ $a == $b ] 返回 false。     |
| !=     | 不相等。用于比较两个数字，不相同则返回 true。 | [ $a != $b ] 返回 true。      |

注意：条件表达式要放在方括号之间，并且要有空格，例如: [$a==$b] 是错误的，必须写成 [ $a == $b ]。

```
#乘号(*)前边必须加反斜杠(\)才能实现乘法运算   注意expr的使用
val=`expr $a \* $b`
echo "a * b : $val"
```

在 MAC 中 shell 的 expr 语法是：$((表达式))，此处表达式中的 "*" 不需要转义符号 "\" 。

 

## 关系运算符

关系运算符只支持数字，不支持字符串，除非字符串的值是数字。

假定变量 a 为 10，变量 b 为 20：

| 运算符 | 说明                                                  | 举例                     |
| ------ | ----------------------------------------------------- | ------------------------ |
| -eq    | 检测两个数是否相等，相等返回 true。                   | [ a -eq b ] 返回 false。 |
| -ne    | 检测两个数是否不相等，不相等返回 true。               | [ a -ne b ] 返回 true。  |
| -gt    | 检测左边的数是否大于右边的，如果是，则返回 true。     | [ a -gt b ] 返回 false。 |
| -lt    | 检测左边的数是否小于右边的，如果是，则返回 true。     | [ a -lt b ] 返回 true。  |
| -ge    | 检测左边的数是否大于等于右边的，如果是，则返回 true。 | [ a -ge b ] 返回 false。 |
| -le    | 检测左边的数是否小于等于右边的，如果是，则返回 true。 | [ a -le ​b ] 返回 true。  |



## 布尔运算符

变量 a 为 10，变量 b 为 20：

| 运算符 | 说明                                                | 举例                                     |
| ------ | --------------------------------------------------- | ---------------------------------------- |
| !      | 非运算，表达式为 true 则返回 false，否则返回 true。 | [ ! false ] 返回 true。                  |
| -o     | 或运算，有一个表达式为 true 则返回 true。           | [ $a -lt 20 -o $b -gt 100 ] 返回 true。  |
| -a     | 与运算，两个表达式都为 true 才返回 true。           | [ $a -lt 20 -a $b -gt 100 ] 返回 false。 |

## 逻辑运算符

 假定变量 a 为 10，变量 b 为 20

| 运算符 | 说明       | 举例                                        |
| ------ | ---------- | ------------------------------------------- |
| &&     | 逻辑的 AND | [[  $a -lt 100 &&  $b -gt 100 ]] 返回 false |
| \|\|   | 逻辑的 OR  | [[ $a -lt 100 || $b -gt 100 ]] 返回 true    |

## 字符串运算符

变量 a 为 "abc"，变量 b 为 "efg"：

| 运算符 | 说明                                      | 举例                     |
| ------ | ----------------------------------------- | ------------------------ |
| =      | 检测两个字符串是否相等，相等返回 true。   | [ $a = $b ] 返回 false。 |
| !=     | 检测两个字符串是否相等，不相等返回 true。 | [ $a != $b ] 返回 true。 |
| -z     | 检测字符串长度是否为0，为0返回 true。     | [ -z $a ] 返回 false。   |
| -n     | 检测字符串长度是否为0，不为0返回 true。   | [ -n "$a" ] 返回 true。  |
| $      | 检测字符串是否为空，不为空返回 true。     | [ $a ] 返回 true。       |

## 文件测试

文件测试运算符用于检测 Linux 文件的各种属性。

| 操作符  | 说明                                                         | 举例                      |
| ------- | ------------------------------------------------------------ | ------------------------- |
| -b file | 检测文件是否是块设备文件，如果是，则返回 true。              | [ -b $file ] 返回 false。 |
| -c file | 检测文件是否是字符设备文件，如果是，则返回 true。            | [ -c $file ] 返回 false。 |
| -d file | 检测文件是否是目录，如果是，则返回 true。                    | [ -d $file ] 返回 false。 |
| -f file | 检测文件是否是普通文件（既不是目录，也不是设备文件），如果是，则返回 true。 | [ -f $file ] 返回 true。  |
| -g file | 检测文件是否设置了 SGID 位，如果是，则返回 true。            | [ -g $file ] 返回 false。 |
| -k file | 检测文件是否设置了粘着位(Sticky Bit)，如果是，则返回 true。  | [ -k $file ] 返回 false。 |
| -p file | 检测文件是否是有名管道，如果是，则返回 true。                | [ -p $file ] 返回 false。 |
| -u file | 检测文件是否设置了 SUID 位，如果是，则返回 true。            | [ -u $file ] 返回 false。 |
| -r file | 检测文件是否可读，如果是，则返回 true。                      | [ -r $file ] 返回 true。  |
| -w file | 检测文件是否可写，如果是，则返回 true。                      | [ -w $file ] 返回 true。  |
| -x file | 检测文件是否可执行，如果是，则返回 true。                    | [ -x $file ] 返回 true。  |
| -s file | 检测文件是否为空（文件大小是否大于0），不为空返回 true。     | [ -s $file ] 返回 true。  |
| -e file | 检测文件（包括目录）是否存在，如果是，则返回 true。          | [ -e $file ] 返回 true。  |

**文件测试测试文件是不是存在**

| 参数      | 说明                                 |
| --------- | ------------------------------------ |
| -e 文件名 | 如果文件存在则为真                   |
| -r 文件名 | 如果文件存在且可读则为真             |
| -w 文件名 | 如果文件存在且可写则为真             |
| -x 文件名 | 如果文件存在且可执行则为真           |
| -s 文件名 | 如果文件存在且至少有一个字符则为真   |
| -d 文件名 | 如果文件存在且为目录则为真           |
| -f 文件名 | 如果文件存在且为普通文件则为真       |
| -c 文件名 | 如果文件存在且为字符型特殊文件则为真 |
| -b 文件名 | 如果文件存在且为块特殊文件则为真     |

```
Shell还提供了与( -a )、或( -o )、非( ! )三个逻辑操作符用于将测试条件连接起来，其优先级为："!"最高，"-a"次之，"-o"最低。

案例:
[root@linuxprobe ~]# [ -d /etc/fstab ]  
[root@linuxprobe ~]# echo $?
1
上方代码的含义: //判断/etc/fstab是否为一个目录类型的文件,通过Shell解释器的内设$?变量显示上一条命令执行后的返回值。如果返回值为0，则目录存在；如果返回值为非零的值，则意味着目录不存在：

逻辑测试语句: 逻辑语句用于对测试结果进行逻辑分析
逻辑“与”的运算符号是&&，它表示当前面的命令执行成功后才会执行它后面的命令
[root@linuxprobe ~]# [ -e /dev/cdrom ] && echo "Exist"
Exist
[root@linuxprobe ~]# 
```



##  test测试

 test 命令用于检查**某个条件是否成立**，它可以进行数值、字符和文件三个方面的测试。

| 参数 | 说明           |
| ---- | -------------- |
| -eq  | 等于则为真     |
| -ne  | 不等于则为真   |
| -gt  | 大于则为真     |
| -ge  | 大于等于则为真 |
| -lt  | 小于则为真     |
| -le  | 小于等于则为真 |



## 字符串测试

| 参数      | 说明                     |
| --------- | ------------------------ |
| =         | 等于则为真               |
| !=        | 不相等则为真             |
| -z 字符串 | 字符串的长度为零则为真   |
| -n 字符串 | 字符串的长度不为零则为真 |

# 参数传递

## 传递参数

在执行 Shell 脚本时，向脚本传递参数，脚本内获取参数的格式为：$n。n 代表一个数字，1 为执行脚本的第一个参数，2 为执行脚本的第二个参数，多个参数进行传递

```shell
#!/bin/bash
echo "Shell 传递参数实例！";
echo "执行的文件名：$0";
echo "第一个参数为：$1";
echo "第二个参数为：$2";
echo "第三个参数为：$3";
#执行命令   加上+x权限   所有者 拥有组  其他人的权限 
#chmod +x test.sh 
#./test.sh 1 2 3 
```

**结果：**

执行的文件名：./test.sh

第一个参数为：1

第二个参数为：2

第三个参数为：3

几个特殊字符用来处理参数：

| 参数处理 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| $#       | 传递到脚本的参数个数                                         |
| $*       | 以一个单字符串显示所有向脚本传递的参数。 如"$*"用「"」括起来的情况、以"$1 $2 … $n"的形式输出所有参数。 |
| $$       | 脚本运行的当前进程ID号                                       |
| $!       | 后台运行的最后一个进程的ID号                                 |
| $@       | 与$*相同，但是使用时加引号，并在引号中返回每个参数。 如"$@"用「"」括起来的情况、以"$1" "$2" … "$n" 的形式输出所有参数。 |
| $-       | 显示Shell使用的当前选项，与[set命令](https://www.runoob.com/linux/linux-comm-set.html)功能相同。 |
| $?       | 显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。 |

**\$* 与 $@ 区别：**

**相同点**：都是引用所有参数。

**不同点**：只有在双引号中体现出来。假设在脚本运行时写了三个参数 1、2、3，，则 " * " 等价于 "1 2 3"（传递了一个参数），而 "@" 等价于 "1" "2" "3"（传递了三个参数）。



# 顺序

从上往下进行脚本的执行   可以理解为命令堆积的执行   





# 选择



## if

```
if condition
then
  command1 
  command2
  ...
  commandN 
fi


案例代码：
a= echo $?
if [ a=1 ]
then
	ls -al / 
else
	echo "Error！！" 
fi

if [ $(ps -ef | grep -c "ssh") -gt 1 ]; then echo "true"; fi

执行过程：
```

## if else

```
if condition
then
  command1 
  command2
  commandN
else
  command
fi
执行过程：
```



## if else-if else

```
if condition1
then
  command1
elif condition2 
then 
  command2
else
  commandN
fi
执行过程：
```



## case

```shell
多选择语句。可以用case语句匹配一个值与一个模式，如果匹配成功，执行相匹配的命令。case语句格式如下：
case 值 in
模式1)
  command1
  command2
  commandN
  ;;
模式2）
  command1
  command2
  commandN	
  ;;
esac
工作流程：取值后面必须为单词in，每一模式必须以右括号结束。取值可以为变量或常数。匹配发现取值符合某一模式后，其间所有命令开始执行直至 .

取值将检测匹配的每一个模式。一旦模式匹配，则执行完匹配模式相应命令后不再继续其他模式。如果无一匹配模式，使用星号 * 捕获该值，再执行后面的命令.

```



下面的脚本提示输入1到4，与每一种模式进行匹配：

```shell
echo '输入 1 到 4 之间的数字:'
echo '你输入的数字为:'
read aNum
case $aNum in
    1) echo '你选择了 1'
  ;;
    2) echo '你选择了 2'
  ;;
    3) echo '你选择了 3'
  ;;
    4) echo '你选择了 4'
  ;;
    *) echo '你没有输入 1 到 4 之间的数字'
  ;;
esac
```

# 循环

## for

```shell
for var in item1 item2 ... itemN
do
  command1
  command2
  ...
  commandN
done
写成一行：
for var in item1 item2 ... itemN; do command1; command2… done;
帮助命令的查看
[root@server01 demo]# help for 
for: for NAME [in WORDS ... ] ; do COMMANDS; done
    Execute commands for each member in a list.
    
    The `for' loop executes a sequence of commands for each member in a
    list of items.  If `in WORDS ...;' is not present, then `in "$@"' is
    assumed.  For each element in WORDS, NAME is set to that element, and
    the COMMANDS are executed.
    
    Exit Status:
    Returns the status of the last command executed.
for ((: for (( exp1; exp2; exp3 )); do COMMANDS; done
    Arithmetic for loop.
    
    Equivalent to
    	(( EXP1 ))
    	while (( EXP2 )); do
    		COMMANDS
    		(( EXP3 ))
    	done
    EXP1, EXP2, and EXP3 are arithmetic expressions.  If any expression is
    omitted, it behaves as if it evaluates to 1.
    
    Exit Status:
    Returns the status of the last command executed.
[root@server01 demo]#
```



当变量值在列表里，for循环即执行一次所有命令，使用变量名获取列表中的当前取值。命令可为任何有效的shell命令和语句。in列表可以包含替换、字符串和文件名。in列表是可选的，如果不用它，for循环使用命令行的位置参数。

例如，顺序输出当前列表中的数字：

```shell
for loop in 1 2 3 4 5
do
  echo "The value is: $loop"
done
```

结果：		

The value is: 1

The value is: 2

The value is: 3

The value is: 4

The value is: 5

顺序输出字符串中的字符：

```shell
for str in 'This is a string'
do
  echo $str
done
```

输出结果：

```shell
This is a string
```

 

## while 

```shell
while condition
do
  command
done
```

以下是一个基本的while循环，测试条件是：如果int小于等于5，那么条件返回真。int从0开始，每次循环处理时，int加1。运行上述脚本，返回数字1到5，然后终止。

```
#!/bin/bash
int=1
while(( $int<=5 ))
do
  echo $int
  let "int++"
done
```

运行脚本，输出：

```shell
1
2
3
4
5
```

以上实例使用了 Bash let 命令，它用于执行一个或多个表达式，变量计算中不需要加上 $ 来表示变量，

while循环可用于读取键盘信息。输入信息被设置为变量FILM，按<Ctrl-D>结束循环。

echo '按下 <CTRL-D> 退出'

```
echo -n '输入你最喜欢的网站名: '
while read FILM
do
  echo "是的！$FILM 是一个好网站"
done
```

运行脚本，输出类似下面：

按下 <CTRL-D> 退出

## 无限循环

无限循环语法格式：

```shell
while true
do
  command
done
for (( ; ; ))
```

## until 

until 循环执行一系列命令直至条件为 true 时停止。

until 循环与 while 循环在处理方式上刚好相反。

一般 while 循环优于 until 循环，但在某些时候—也只是极少数情况下，until 循环更加有用。

```shell
until 语法格式:
until condition
do
  command
done
condition 
一般为条件表达式，如果返回值为 false，则继续执行循环体内的语句，否则跳出循环。
```

 





## break和continue

**break：**

break命令允许跳出所有循环（终止执行后面的所有循环）

脚本进入死循环直至用户输入数字大于5。要跳出这个循环，返回到shell提示符下，需要使用break命令。

```shell
#!/bin/bash
while :
do
  echo -n "输入 1 到 5 之间的数字:"
  read aNum
  case $aNum in
   1|2|3|4|5) echo "你输入的数字为 $aNum!"
    ;;
   *) echo "你输入的数字不是 1 到 5 之间的! 游戏结束"
     break
   ;;
  esac
done
以上代码执行了三部分
第一部分进行循环
第二部分进行输入
第三部分进行 判断和选择 
```

执行以上代码，输出结果为：

输入 1 到 5 之间的数字:3

你输入的数字为 3!

输入 1 到 5 之间的数字:7

你输入的数字不是 1 到 5 之间的! 游戏结束

**continue**

continue命令与break命令类似，只有一点差别，它不会跳出所有循环，仅仅跳出当前循环。

```shell
#!/bin/bash

while :
do
  echo -n "输入 1 到 5 之间的数字: "
  read aNum
  case $aNum in
    1|2|3|4|5) echo "你输入的数字为 $aNum!"
   ;;
   *) echo "你输入的数字不是 1 到 5 之间的!"
      continue
      echo "游戏结束"
    ;;
  esac
done
```

运行代码发现，当输入大于5的数字时，该例中的循环不会结束，语句 echo "游戏结束" 永远不会被执行。

 

case的语法和C family语言差别很大，它需要一个esac（就是case反过来）作为结束标记

**每个case分支用右圆括号，用两个分号表示break。**



# 数组

bash支持一维数组（不支持多维数组），并且没有限定数组的大小。

类似于 C 语言，数组元素的下标由 0 开始编号。获取数组中的元素要利用下标，下标可以是整数或算术表达式，其值应大于或等于 0。

## 定义数组

用括号来表示数组，数组元素用"空格"符号分割开。定义数组的一般形式为：



```shell
语法：数组名=(值1 值2 ... 值n)
array_name=(value0 value1 value2 value3)
array_name=(
value0
value1
value2
value3
)
一行写法和分开写法
```

还可以单独定义数组的各个分量：

```shell
array_name[0]=value0
array_name[1]=value1
array_name[n]=valuen
```

可以不使用连续的下标，而且下标的范围没有限制。



```shell
读取数组
${数组名[下标]}
valuen=${array_name[n]}
使用 @ 符号可以获取数组中的所有元素，例如：
echo ${array_name[@]}
```

**获取数组的长度**

获取数组长度的方法与获取字符串长度的方法相同

```shell
# 取得数组元素的个数
length=${#array_name[@]}
# 或者
length=${#array_name[*]}
# 取得数组单个元素的长度
lengthn=${#array_name[n]}
```



## 注释

**多行注释:**

每一行加个#符号太费力了，可以把这一段要注释的代码用一对花括号括起来，定义成一个函数，没有地方调用这个函数，这块代码就不会执行，达到了和注释一样的效果。函数没有被执行  就是等同于注释

## 脚本的运行方式

方式有两种：交互式和批处理。

**交互式**（Interactive）：用户每输入一条命令就立即执行。

**批处理**（Batch）：由用户事先编写好一个完整的Shell脚本，Shell会一次性执行脚本中诸多的命令。

Shell脚本文件的名称可以任意，但为了避免被误以为是普通文件，建议将.sh后缀加上，以表示是一个脚本文件。

**一般脚本的内容结构**

第一行的脚本声明（#!）用来告诉系统使用哪种Shell解释器来执行该脚本；

第二行的注释信息（#）是对脚本功能和某些命令的介绍信息，使得自己或他人在日后看到这个脚本内容时，可以快速知道该脚本的作用或一些警告信息；

第三、四行的可执行语句也就是我们平时执行的Linux命令了。

```shell
以 # 开头的行就是注释，会被解释器忽略。
通过每一行加一个 # 号设置多行注释，像这样：
#--------------------------------------------
# 这是一个注释
# author：xiaowang
# site：www.baidu.com
# slogan：学的不仅是技术，更是梦想！
#--------------------------------------------
##### 用户配置区 开始 #####
#
#
# 这里可以添加脚本描述信息
# 
#
##### 用户配置区 结束  #####
```

# 函数

函数就是执行一个功能的代码段   多次调用某一个某一个功能  函数就产生了 

```
[ function ] funname [()]
{
    action;
    [return int;]
}
```

使用函数的名字进行定义和实现的  

说明：

- 1、可以带function fun()  定义，也可以直接fun() 定义,不带任何参数。
- 2、参数返回，可以显示加：return 返回，如果不加，将以最后一条命令运行结果，作为返回值。 return后跟数值n(0-255）

**注意**：所有函数在使用前必须定义。这意味着必须将函数放在脚本开始部分，直至shell解释器首次发现它时，才可以使用。调用函数仅使用其函数名即可。

在Shell中，调用函数时可以向其传递参数。在函数体内部，通过 $n 的形式来获取参数的值

Shell 函数中的 return 关键字用来表示函数的退出状态，而不是函数的返回值；

Shell 不像其它编程语言，没有专门处理返回值的关键字。

注意，10 不能获取第十个参数，获取第十个参数需要​{10}。当n>=10时，需要使用${n}来获取参数。

| 参数处理 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| $#       | 传递到脚本的参数个数                                         |
| $*       | 以一个单字符串显示所有向脚本传递的参数                       |
| $$       | 脚本运行的当前进程ID号                                       |
| $!       | 后台运行的最后一个进程的ID号                                 |
| $@       | 与$*相同，但是使用时加引号，并在引号中返回每个参数。         |
| $-       | 显示Shell使用的当前选项，与set命令功能相同。                 |
| $?       | 显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。 |

 **函数**

函数主要功能：就是实现重复的操作  

函数就是把语句块分成模块

代码量多写成函数形式

定义函数:组成部分是由函数名和函数体组成

help funcation

语法：

```shell
f_name(){
 	函数体
}
funcation f_name{}
funcation f_name(){
	函数体
}
declare作用：在第一种语法中可用来声明变量并设置变量的属性([rix]即为变量的属性），在第二种语法中可用来显示shell函数。
[root@server01 ~]# declare -h 
declare: usage: declare [-aAfFgilrtux] [-p] [name[=value] ...]
[root@server01 ~]# 


```

# 输入/输出重定向

一般情况下，每个Linux 命令运行时都会打开三个文件：

- 标准输入文件(stdin)：   stdin的文件描述符为0，   Unix程序默认从stdin读取数据。
- 标准输出文件(stdout)：stdout 的文件描述符为1，Unix程序默认向stdout输出数据。
- 标准错误文件(stderr)： stderr的文件描述符为2， Unix程序会向stderr流中写入错误信息。

**默认情况下，command > file 将 stdout 重定向到 file，command < file 将stdin 重定向到 file。**

**/dev/null文件**

dev/null 是一个特殊的文件，写入到它的内容都会被丢弃；如果尝试从该文件读取内容，那么什么也读不到。

但是 /dev/null 文件非常有用，将命令的输出重定向到它，会起到"禁止输出"的效果。

**shell文件的包含**

与其他语言一样，Shell 也可以包含外部脚本。这样可以很方便的封装一些公用的代码作为一个独立的文件。

使用方法：

```
. filename   # 注意点号(.)和文件名中间有一空格
source filename
执行流程 类似文件的包含
```

文件包含就是把别的脚本中需要的参数或者代码包含带自己的脚本文件中  常见使用的方法  **使用点**  加上空格 形式  或者使用source的形式大多数 UNIX 系统命令从你的终端接受输入并将所产生的输出发送回到您的终端。一个命令通常从一个叫标准输入的地方读取输入，默认情况下，这恰好是你的终端。同样，一个命令通常将其输出写入到标准输出，默认情况下，就是你的终端

重定向命令列表如下：

| 命令            | 说明                                               |
| --------------- | -------------------------------------------------- |
| command > file  | 将输出重定向到 file。                              |
| command < file  | 将输入重定向到 file。                              |
| command >> file | 将输出以追加的方式重定向到 file。                  |
| n > file        | 将文件描述符为 n 的文件重定向到 file。             |
| n >> file       | 将文件描述符为 n 的文件以追加的方式重定向到 file。 |
| n >& m          | 将输出文件 m 和 n 合并。                           |
| n <& m          | 将输入文件 m 和 n 合并。                           |
| << tag          | 将开始标记 tag 和结束标记 tag 之间的内容作为输入。 |

需要注意的是文件描述符 0 通常是标准输入（STDIN）

1 是标准输出（STDOUT）

2 是标准错误输出（STDERR）

 **输出重定向**

```shell
command1 > file1
```

上面这个命令执行command1然后将输出的内容存入file1。

注意任何file1内的已经存在的内容将被新内容替代。如果要将新内容添加在文件末尾，请使用>>操作符。

**实例**

执行下面的 who 命令，它将命令的完整的输出重定向在用户文件中(users):

```shell
$ who > users
```

执行后，并没有在终端输出信息，这是因为输出已被从默认的标准输出设备（终端）重定向到指定的文件。

你可以使用 cat 命令查看文件内容：

```
$ cat users
_mbsetupuser console  Oct 31 17:35 
tianqixin   console  Oct 31 17:35 
tianqixin   ttys000  Dec 1 11:33 
```



**输入重定向**

和输出重定向一样，Unix 命令也可以从文件获取输入，语法为：

```shell
command1 < file1
```

这样，本来需要从键盘获取输入的命令会转移到文件读取内容。

注意：输出重定向是大于号(>)，输入重定向是小于号(<)。

我们需要统计 users 文件的行数,执行以下命令：

```shell
$ wc -l users

    2 users
```

也可以将输入重定向到 users 文件：

```shell
$  wc -l < users

  2 
```

**注意**：上面两个例子的结果不同：第一个例子，会输出文件名；第二个不会，因为它仅仅知道从标准输入读取内容。

```shell
command1 < infile > outfile
```

同时替换输入和输出，执行command1，从文件infile读取内容，然后将输出写入到outfile中。







# 文本编辑命令

## sed

sed是一个精简的，非交互式的流式编辑器，它在命令行中输入编辑命令和指定的文件名，然后在屏幕上显示输出是一个流编辑器

 

**sed工作原理：**逐行读取文件内容存储在临时缓冲区中，称为模式空间      接着使用sed命令处理缓冲中的内容，处理完成后，把缓冲区的内容送到屏幕接着处理下一行，这样不断重复，直到文件末尾，源文件并没有改变

```shell
用法：

sed [option] files
	-e 连接多个编辑命令
	-f 指定sed脚本的文件
	-n 逐止输入啊很难过自动输出

sed 's/a/b/g'        含义是，在全局内，将a替换为b，这个直接简单快速；但是当面对转义符号时，需要特别处理
sed ‘4,$d’ test.in
sed ‘3p’ test.in
sed ‘s/public/PUBLIC’ test.in
sed -n ‘s/public/PUBLIC/P’ test.in
使用sed指定多个命令的方法：
sed ‘s/public/PUBLIC/;s/north/NORTH/’ test.in
每个命令前放置-e参数
sed -e 's/public/PUBLIC'; -e 's/NORTH/north' test.in 
```

 

**sed的定位方式：**

```
	n 表示行
	$ 表示最后一行
	m,n 从m行到n行
	/pattern/ 查询包含指定模式的行。
```

​	打印匹配的行

```shell
	sed -n ‘3,5p’ test.in 
	sed- -n ‘3p’ test.in
```

​	显示匹配的行：

```shell
sed -n '/north/=' test.in
sed -n '/north/p' test.in    //删除匹配的行号
sed -n 's/north/N/gp' test.in 
sed -n '3p' test.in
p打印 s替换  = 显示匹配的行 l显示指定的行
d删除匹配 r读文件  a\ 在指定的杭后追加文件  w写文件
i、指定的行前面插入  n读取指定行的下面一行 c\ 新闻本替换指定的行 q退出
```

# 15. sed awk grep 三剑客

awk   使用空格进行分割  

awk的格式化   格式化的输出  

awk不修改文件直接打印文件和显示文件 

printf格式化输出,  多个正则  加上双斜杠  

显示不已bin/bash结尾的行

```shell
grep -v "/bin/bash$" passwd  -n 
```

找出最少一个空白字符开头的文件 

```shell
grep "^[[:space:]].*" passwd  
```

找出root用户的行

```shell
grep "^root" passwd 
```

匹配与root开头或者nginx开头

```SHELL
[root@node ~]# grep -E "^(root|nginx)" passwd 
root:x:0:0:root:/root:/bin/bash
nginx:x:995:990:nginx user:/var/cache/nginx:/sbin/nologin
[root@node ~]#
```

过滤bin开头

```shell
[root@node ~]# grep -n "^bin" passwd 
2:bin:x:1:1:bin:/bin:/sbin/nologin
[root@node ~]#
```

除了root开头的行

```shell
[root@node ~]# grep -v "^root" passwd 
```

统计root开头的行数

```shell
[root@node ~]# grep -c "^root" passwd 
1
[root@node ~]# 
```

找出以大写或小写开头的行

```shell
grep -E "^(i|I)" passwd 
```



找出/etc/init.d/functions函数

```shell
grep -E "[a-zA-Z]+\(\)" /etc/init.d/functions
```



找出用户名和shell一样的行

```shell
grep -E "^([^:]+\>).*+1$" /etc/passwd 
```

替换文件的root为xiaowang   智能替换一次 与替换所有

```shell
sed 's/root/xiaowang/gp' passwd  -n 
sed 's/root/xiaowang/p' passwd -n 
```

 替换前10行 

```shell
sed -n '1,10p/^/bin/C/p' passwd
```

多次的编辑

```shell
[root@node ~]# sed  -n -e '1,10s/^bin/C/p' -e 's/^m/M/p'  passwd 
C:x:1:1:bin:/bin:/sbin/nologin
Mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
Mysql:x:27:27:MariaDB Server:/var/lib/mysql:/sbin/nologin
[root@node ~]# 
```

删除四行所有

```
sed '5,$d' passwd    //修改的只是内存中的数据  别忘记加上i  进行永久的修改
```

将文件中空白字符靠头的行 ,添加注释符号

```shell
sed -n -e 's/^[[:space:]]/#/g' -e 's/^$/#/g' passwd 
```

删除文件的空白行和注释行

```shell
sed '/^#/d' passwd 
sed '/^#/d;/^$/d' passwd  
```

给文件添加@符号

```shell
sed -r '1,3s/(^.)/@\1/' passwd 
```

取出IP地址

```shell
ifconfig eth0 | sed '2p' -n  | sed 's/^.*inet//' | sed 's/netmask.*//'
ifconfig eth0  | sed '2s/^.*inet//;s/netmask.*//p' -n 
```

找出系统版本

```shell
[root@node ~]# sed -r 's/^.*release[[:space:]]([^.]).**/\1/p' /etc/centos-release -n  
7
[root@node ~]# 
```

## awk

awk是一种用于**处理数据**和**生成报告**的编程语言

工作原理：awk逐行扫描输入，按给给定的模式查找匹配的行文，然后对这些行执行awk命令的指定操作

与sed不同的是awk不会修改输入的内容可以使用重定向保存到文件中

```shell
一般命令的格式：
	awk ‘BEGIN {ACTIONS}/PARTERN1/{SCTIONS}END{actions}’input_files
BEGIN和END是可选的


正则表达式：
	^只匹配首行的标志
	$匹配尾行
	*匹配所有的字符
	[] 匹配[]中的任意一个字符
	\ 屏蔽一个元字符的含义
	. 匹配单个字符
	+ 匹配一个或者是多个前一个字符
	？匹配0个或者前一个字符
	（）字符组
```




## grep

```shell
grep 选项  '关键字'   文件名    行过滤   
-i   不区分大小写  
-v   反向选择  
-w 单词的搜索
-o  打印匹配关键字
-E   扩展表达式   
--color-atuo     颜色显示  
```





## cut

```
cut列的截取工具    
-c 字符为单位进行分割
-d  自定义字符
-f指定那个区域的截取的
[root@server ~]# cut -d: -f1,7 passwd  | grep root 
root:/bin/bash
以上截取的就是使用cut加上截取的位置   第一列到第三类  和    第一列和第三列 
```



## sort排序的使用 

```shell
-u去除重复的文件
-r降序排列的  
-o排列结果输出到文件中
-t分隔符
-b忽略前导字符的使用 
```

##  uniq

```shell
除去连续的重复行  
-f 忽略大小写
-c重复的次数
-d只显示重复的行
```



## tee

tee工具从标准的输入  读取  并且写入到标准的输出          默认的是覆盖  

屏幕打印一份      文件中生成一份       双向覆盖      -a追加  

```shell
[root@server ~]# grep -v '^#' vsftpd.conf | grep -v '^$' | tee vsftpd.conf.back 
```

  



## diff

 **逐行比较文件的不同的**  

描述两个文件的不同的方式告诉我们怎样改变的文件 第一个文件 变成第二个文件如何进行改变

```shell
diff  选项  文件1   文件2
-b不检查大小写  
-u就是合并的模式 
```









## paste

```shell
paste合并文件的行   
-d自定义分隔符   
-s串行的执行    
```



## echo

```
颜色的显示  
echo -e "\033[40;37m  黑底白字 welcome to oldboy\033[0m"
0：黑色  1：深红  2.绿色  3. 黄色  4.蓝色  5.紫色 6.青色 7.白色
1.显示普通字符串:
echo "It is a test"

2.显示转义字符
echo "\"It is a test\""

3.显示变量
read 命令从标准输入中读取一行,并把输入行的每个字段的值指定给 shell 变量
#!/bin/sh
read name 
echo "$name It is a test"

4.显示换行
echo -e "OK! \n" # -e 开启转义
echo "It is a test"

输出结果：
OK!
It is a test

5.显示不换行
\#!/bin/sh
echo -e "OK! \c" # -e 开启转义 \c 不换行
echo "It is a test"

输出结果：
OK! It is a test
6.显示结果定向至文件
echo "It is a test" > myfile

7.原样输出字符串，不进行转义或取变量(用单引号)
echo '$name\"'

输出结果：
$name\"
8.显示命令执行结果
echo `date`
注意： 这里使用的是反引号 `, 而不是单引号 '。

结果将显示当前日期

Thu Jul 24 10:08:46 CST 2014
```



## scp

```shell
-P  端口
-r 递归 
-p保持属性  
```





# 脚本调试技巧

使用bash的命令参数调试
ssh [-nvx] scripts.sh
-n 不会执行脚本   仅仅查询脚本是不是有问题  

调试技巧  
1.要记得首先用dos2unix对脚本进行格式化
2.直接执行脚本根据报错来调试  
3.使用sh -x 调试整个脚本  
4.set -x 和set +x   调试部分脚本 
5.echo 输出变量及相关的内容  
6.最关键的是语法的熟练  编码的习惯  编程思想  将错误扼杀在萌芽之中  提高效率  



## 获取ip地址

```shell
ifconfig eth0  | grep 'inet' | awk '{print $2}'
使用sed获取IP地址的使用
获取IP地址的方法  :
ip add | sed -rn 's#^.*net (.*)/24.*$#1#gp'
ifconfig eth0 | awk 'NR==2{print $2}'
ifconfig eth0 | awk  -F "[: ]+" 'NR==2{print $4}'
ifconfig eth0 | sed -n 2p | sed 's#^.*inet ##g' | sed 's#  nettm.*##g'
stat /etc/hosts  
stat /etc/hosts   | sed -rn  's#^.*\(0(.*))/-.*#\1#gp'  最后获取的权限是644
```



## 获取状态码：

```shell
[root@localhost ~]# curl -I -s http://www.baidu.com | head -1
HTTP/1.1 200 OK
[root@localhost ~]# 
```



## 日志的路径

使用命令叠加的方式写脚本：

```
cd /var/log/
cat /dev/null > message 
echo "Logs cleand up"
echo $UID
```

**判断IP地址** 

```
#!/bin/bash 
read -p "Please Enter test ip:" ip
ping -c1 $ip &>/dev/null
if [ $? -eq 0  ];then
	echo "IP:可达!!"
else
	echo "IP:不可达!!"
fi
```

**判断服务是不是正常的** 

```
#!/bin/bash 

yum install -u pgrep 
pgrep httpd &>/dev/null
if [ $? -ne 0 ];then
	echo "不存在！！"
else
	echo "存在的文件"
fi
```



**判断域名是不是能ping通的** 

```shell
#!/bin/bash 
read -p "域名:" ip 
curl -L $ip &>/dev/null
if [ $? -eq 0  ]; then
	echo "域名是ok的"
else
	echo "域名不能访问请检查网络的链接是不是合法的或者没有网络的额链接  ！！ !"
	ping -c5 $ip &>/dev/null
	if [ $? -eq 0  ];then
		echo "可以通信的"
		else
	echo "请检查网络是不是可以通信的"
	fi
fi
```

编写判断是不是数字的脚本

```shell
#!/bin/bash
is_digit(){
	read -p "please input a number:" NUM
	[[ $NUM =~ ^[1-9][0-9]*$ ]]|| { echo "INPUT FALSE";exit;  }
}
is_digit
echo num=$NUM
```

**Local 关键字** 

```shell
export NUM     
脚本后面也是支持参数的
[root@VM-4-10-centos init.d]# cat /etc/init.d/functions
系统函数保存的位置 
action函数显示的颜色    打印红 或者绿色的 
```

```shell
[root@server01 demo]# cat action.sh 
#!/bin/bash
. /etc/init.d/functions
action "stopping sshd:" false
action "starting sshd:" 
[root@server01 demo]# ./action.sh 
stopping sshd:                                             [FAILED]
starting sshd:                                             [  OK  ]
[root@server01 demo]# 
引用当前目录下的文件. /etc/init.d/functions
```

```shell
expect 基于tcp 开发 管理工具   把交互式 问题直接自动进行登录的    可以远程执行脚本
使用监控关键字进行操作 只要出现expect就执行expect后面  
监控expect后面关键字只要 出现就会执行后面指定的命令
```

批量创建用户

```shell
#!/bin/bash
USERS="
xiaoming
xiaowang
xiaogang
xiaozhang
"
for USER in $USERS ;do 
	if id ${USER} &> /dev/null; then 
		echo "用户:${USER},已经存在，创建失败"
		userdel -r ${USER}
	else
		useradd  ${USER}
		echo ${USER} | passwd --stdin ${USER}
		echo "用户:${USER}创建成功"
	fi

done
```

判断程序是不是安装了

```shell
判断程序是不是安装：  
if type -p java; then
    echo 'java已安装.......'
    exit 0
else
   echo '开始安装java......'
```

获取主机名：

```
[root@master ~]# var=$(hostname)
[root@master ~]# echo var 
var
[root@master ~]# echo $var 
master
[root@master ~]#
```





grep '()' /etc/init.d/functions    查看系统内部的函数文件  

使用函数计算阶乘  制作病毒木马

空值会出现很大错误的

出现很多的错误文件



管道调用可以块石执行子进程
lld查看依赖的文件 

技术学习不是深入  不然最后吃亏的就是自己  



系信息号捕捉trap命令  kill -l 

解决脚本


fork炸弹 是一种恶意程序，它的内部是一个貒在fork进程的无线循环，实质是一个简单的递归程序，由于程序时递归的，如果没有任何限制，这会导致这个加单的程序迅速耗尽系统的所有资源。

fork炸弹的具体实现

:(){:|:&};:   具体的实现
bomb(){bomb | bomb &}; bomb 
脚本的使用 cat bomb,sh 



./$0|./$0&






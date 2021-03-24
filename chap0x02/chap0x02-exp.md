# 利用asciinema记录vimtutor学习过程

## 实验目的
* 学会使用asciinema进行命令行录屏
* 学习vimtutor

## 实验环境
* ubuntu 20.04
* 在asciinema注册账号，并在本地安装配置好asciinema
  
## 实验过程
1. 在官网找到适用于ubuntu系统的asciinema下载命令行，在终端进行指令输入，完成本地下载
   
   ```
      sudo apt-add-repository ppa:zanchey/asciinema
      sudo apt-get update
      sudo apt-get install asciinema
   ```
   
2. 关联asciinema账号
   
   ```
      asciinema auth
   ```
   
3. vimtutor操作录像
   #### Lesson1

   ##### Lesson1.1
   [![Lesson1.1](https://asciinema.org/a/401298.svg)](https://asciinema.org/a/401298)

   ##### Lesson1.2
   [![Lesson1.2](https://asciinema.org/a/401301.svg)](https://asciinema.org/a/401301)

   ##### Lesson1.3
   [![Lesson1.3](https://asciinema.org/a/401304.svg)](https://asciinema.org/a/401304)

   ##### Lesson1.4
   [![Lesson1.4](https://asciinema.org/a/401310.svg)](https://asciinema.org/a/401310)

   ##### Lesson1.5
   [![Lesson1.5](https://asciinema.org/a/401313.svg)](https://asciinema.org/a/401313)

   ##### Lesson1.6
   [![Lesson1.6](https://asciinema.org/a/401317.svg)](https://asciinema.org/a/401317)

   #### Lesson2.1-2.7
   [![Lesson2.1-2.7](https://asciinema.org/a/401328.svg)](https://asciinema.org/a/401328)

   #### Lesson3.1-3.4
   [![Lesson3.1-3.4](https://asciinema.org/a/401344.svg)](https://asciinema.org/a/401344)

   #### Lesson4.1-4.4
   [![Lesson4.1-4.4](https://asciinema.org/a/401356.svg)](https://asciinema.org/a/401356)

   #### Lesson5.1-5.4
   [![Lesson5.1-5.4](https://asciinema.org/a/401364.svg)](https://asciinema.org/a/401364)

   #### Lesson6.1-6.5
   [![Lesson6.1-6.5](https://asciinema.org/a/401387.svg)](https://asciinema.org/a/401387)

   #### Lesson7.1-7.3
   [![Lesson7.1-7.3](https://asciinema.org/a/401394.svg)](https://asciinema.org/a/401394)

## vimtutor的自查清单
1. vim有哪几种工作模式？
   - Normal mode 普通模式：vim启动后的默认模式，可移动光标，删除文本等等
   - Insert mode 插入模式：从普通模式通过i a A o s等进入，按'ESC'退出插入模式切换至普通模式
   - Command line mode 命令行模式：在命令行模式中可以输入会被解释成并执行的文本，如'：''/''?''!'命令执行后回到Nomal mode
   - Select mode 选择模式：在该模式中可以用鼠标或者光标键高亮选择文本
   - Vitual mode 可视模式：与普通模式类似，但移动命令会扩大高亮的文本区域。高亮区域可以是字符、行或者是一块文本。当执行一个非移动命令时，命令会被执行到这块高亮的区域上

2. Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？
   
   - 一次向下移动10行: '10j'
   - 移至文件开始: 'gg'
   - 移至文件结束行: 'G'
   - 快速移至第N行: 'NG' 或 'Ngg'

3. Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？
   - 删除单个字符: 'x'
   - 删除单个单词: 'dw'或'de'
   - 从当前光标删除到行尾: 'd$'
   - 删除单行: 'dd'
   - 删除当前行开始向下N行: 'Ndd'

4. 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？
   - 插入N个空行: 'No'
   - 快速插入80个-: 普通模式下输入'80i-'然后'ESC' 

5. 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？
   - 撤销最近一次操作: 'u'
   - 重做最后一次被撤销的操作: 'CTRL-R'

6. vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？
   - 剪切粘贴单个字符: 'x'然后'p'
   - 单个单词: 'dw'然后'p'
   - 单行: 'dd'然后'p'
   - 相似的复制粘贴操作:  'v'进入可视模式（visual mode），移动光标选择需要复制的内容，'y'复制文本，移动光标至指定位置'p'粘贴文本

7. 为了编辑一段文本你能想到哪几种操作方式（按键序列）？
   - 插入操作: 'i','I','a','A','o','O'
   - 删除操作: 'x','dw','d$','dd'
   - 复制粘贴操作: 'v','y','p'
   - 撤销与重做操作: 'u','U','CTRL-R'
   - 保存更改: ':w'
   - 退出: ':q!',':wq!'

8. 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？
   - :f或CTRL-G

9. 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？
   - 关键词搜索: /'key words'(Enter)
       - 查找下一个:'n',上一个'N'
   - 设置忽略大小写匹配搜索: set ic
   - 将匹配结果高亮显示: set hls is
   - 匹配到的关键词进行批量替换:
   - 替换当前行第一个字符: 's/old/new/'
   - 替换m行与n行之间所有字符: 'm,ns/old/new/g'
   - 全局替换: '%s/old/new/g'

10. 在文件中最近编辑过的位置来回快速跳转的方法？
   - Normal 模式下执行 CTRL-O 和 CTRL-I

11. 如何把光标定位到各种括号的匹配项？例如：找到(, [, or {对应匹配的),], or }
   - 光标停至某半括号处，按'%'，即跳转到对应匹配的括号

12. 在不退出vim的情况下执行一个外部程序的方法？
   - !command

13. 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？
   - :help[快捷键名] + enter
   - 在两个不同的分屏窗口移动光标:通过 ':set mouse=a'开启 vim 的鼠标支持模式，然后就可以通过鼠标直接改变分屏窗口大小和切换不同分屏窗口选中状态了

## 实验问题
1. 在终端进行asciinema下载时显示失败，问过老师之后发现时自己的ubuntu系统在设置网卡时将NAT设置成了NAT网络，导致无法联网。更改后下载成功。

2. 在学习lesson3.3时，借助'ce'操作修改'usf the ……'时，将光标停在f处,按下ce,结果将f后的空格以及'the'均删去
   完成修改时只能利用'i'指令重新加上空格和'the'.猜想原因可能是'ce'操作是删掉光标和光标所在单词的末尾之间的字母，f刚好在末尾,所以误将空格和'the'也删除。（具体原因有待考察555）

## 参考资料

[第二章实验课件](https://c4pr1c3.gitee.io/linuxsysadmin/chap0x02.exp.md.html#/3/2/'第二章实验课件')<br>
[Virtualbox虚拟网络实战](https://c4pr1c3.gitee.io/linuxsysadmin/get-networks-done-asap.md.html#/vb-net-conn-graph/'vb虚拟网络实战')



  



   

   
   











   




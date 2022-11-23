

# 一.教程网站

>  https://www.jianshu.com/p/65b514ecad9e
>
>  http://events.jianshu.io/p/d451a5b2d76e
>
>  https://zhuanlan.zhihu.com/p/426116032
>
>  https://www.cnblogs.com/deeround/p/14831776.html

> [Emoji Homepage 👀 - Copy and paste emoji. 💨 Fast and 👌 Simple.](http://emojihomepage.com/)
>
> [🎁 Emoji cheat sheet for GitHub, Basecamp, Slack & more (webfx.com)](https://www.webfx.com/tools/emoji-cheat-sheet/)

:keycap_ten:



# 二.入门

## 1.基本语法

> ```
> 分隔线 	*** 或者 ---
> 
> 高亮显示	==文字==	
> ```
>
> 



## 2.快捷键

> <kbd>Ctrl</kbd>+<kbd>B</kbd>	加粗
>
> <kbd>Ctrl</kbd>+<kbd>I</kbd>	斜体
>
> <kbd>Ctrl</kbd>+<kbd>U</kbd>	下划线
>
> <kbd>Ctrl</kbd>+<kbd>T</kbd>	表格
>
> <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>`</kbd>	代码
>
> <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>5</kbd>	删除线

## 3.段落和断行

> <kbd>Shift</kbd>+<kbd>Enter</kbd> 	另起一行
>
> <kbd>Enter</kbd>	另起一段

## 4.任务列表（活动列表、可选列表）

> ```
> - [ ] 			任务清单（ ]后还有一个空格 ）
> ```
>
> - [ ] 任务1
> - [x] 任务2
> - [ ] 任务3



## 5.脚注

这是一个计数[^Spring]

[^Spring]:这是一个框架



## 6.超链接

* 一般写法

   > 这是一个[参考链接][https://www.runoob.com/markdown/md-tutorial.html/ ]，没有使用id标签。

* 另一种写法

   > 这是一个[参考链接][id]，使用了id标签。
   >
   > [id]:https://www.runoob.com/markdown/md-tutorial.html/	"Markdown菜鸟教程"

* 空链接

   > 这是一个[参考链接][]
   >
   > [参考链接]:https://www.runoob.com/markdown/md-tutorial.html/





## typora设置

#### 1. 设置字体高亮颜色

>  偏好设置 ==> 打开主题文件 ==> 修改某个css文件（百度）

#### 2、添加字体高亮快捷设置

>  打开偏好设置 -->> 打开高级设置 -->> 使用记事本打开conf.user.json文件 -->> Ctrl + f 找到 keyBinding
>
>  ```json
>  "keyBinding": {
>      // for example: 
>      // "Always on Top": "Ctrl+Shift+P",
>  
>      "Highlight": "Ctrl+q"            //追加   "高亮": "快捷方式"
>  }
>  ```
>
>  



# 三.进阶用法

>  ```
>  [toc] + 回车		生成目录
>  
>  ```



##  1.画 图

### 1.1概述

> 通过 `mermaid` `flow` `sequence`实现

### 1.2纵向流程图(mermaid)

> ```mermaid
> graph TD
> A[方形] --> B(圆角)
>     B --> C{条件a}
>     C --> |a=1| D[结果1]
>     C --> |a=2| E[结果2]
>     F[竖向流程图]
> ```
>
> 

### 1.3横向流程图(mermaid)

> ```mermaid
> 
> graph LR
> A[方形] -->B(圆角)
>     B --> C{条件a}
>     C -->|a=1| D[结果1]
>     C -->|a=2| E[结果2]
>     F[横向流程图]
> ```

### 1.4流程图实现的思维导图

> ```mermaid
> graph TB
> A((七年之变)) --> 1(引言)
> A --> 2(理论研究)
> A --> 3(仿真模拟)
> A --> 4(工装系统)
> A --> 5(工艺应用)
> A --> 6(总结)
> linkStyle 0,1,2,3,4,5 stroke:#88d,stroke-width:2px
> 
> 1 --> 研究意义
> 1 --> 研究历史
> 1 --> 研究发展方向
> 
> 2 --> 依次介绍,形成脉络
> 3 --> 分类介绍,对比
> 4 --> 电源\控制\线圈等系统组成
> 5 --> 分别介绍工艺研究
> 
> 6 --> 简单总结各部分成果
> 6 --> 提出存在的问题,缺少的方面,目前的研究重点
> 6 --> 未来展望
> 
> classDef topic fill:#f88,stroke:#333,stroke-width:4px 
> classDef key fill:#ff8,stroke:#333
> 
> class A topic
> class 1,2,3,4,5,6 key
> ```
>
> 
>
> 



### 1.5 UML 标准时序图(mermaid)

> ```mermaid
> %% 时序图例子,-> 直线，-->虚线，->>实线箭头
>   sequenceDiagram
>     participant 张三
>     participant 李四
>     张三->王五: 王五你好吗？
>     loop 健康检查
>         王五->王五: 与疾病战斗
>     end
>     Note right of 王五: 合理 食物 <br/>看医生...
>     李四-->>张三: 很好!
>     王五->李四: 你怎么样?
>     李四-->王五: 很好!
> ```

### 1.6 状态图(mermaid)

> ```mermaid
> stateDiagram
>     [*] --> s1
>     s1 --> middle
>     middle-->s2
>     s2 --> [*]
> ```
>
> 

### 1.7 类图(mermaid)

> ```mermaid
> classDiagram
>       Animal <|-- Duck
>       Animal <|-- Fish
>       Animal <|-- Zebra
>       Animal : +int age
>       Animal : +String gender
>       Animal: +isMammal()
>       Animal: +mate()
>       class Duck{
>           +String beakColor
>           +swim()
>           +quack()
>       }
>       class Fish{
>           -int sizeInFeet
>           -canEat()
>       }
>       class Zebra{
>           +bool is_wild
>           +run()
>       }
> ```

### 1.8 甘特图(mermaid)

> ```mermaid
> gantt
>     title 任务计划
>     dateFormat  YYYY-MM-DD
>     section 流程1
>     任务A1            :1996-03-02, 48h
>     任务A2       :17d
>     section 流程2
>     任务B1   :1996-03-05  , 6d
>     任务B2      :5d
>     section 流程3
>     任务C1   :1996-03-16  , 6d
>     任务C2      :1996-03-16  , 10d    
> ```

> ```mermaid
> %% 语法示例
>         gantt
>         dateFormat  YYYY-MM-DD
>         title 软件开发甘特图
>         section 设计
>         需求                      :done,    des1, 2014-01-06,2014-01-08
>         原型                      :active,  des2, 2014-01-09, 3d
>         UI设计                     :         des3, after des2, 5d
>     未来任务                     :         des4, after des3, 5d
>         section 开发
>         学习准备理解需求                      :crit, done, 2014-01-06,24h
>         设计框架                             :crit, done, after des2, 2d
>         开发                                 :crit, active, 3d
>         未来任务                              :crit, 5d
>         耍                                   :2d
>         section 测试
>         功能测试                              :active, a1, after des3, 3d
>         压力测试                               :after a1  , 20h
>         测试报告                               : 48h
> ```

### 1.9饼图(mermaid)

> ```mermaid
> pie
>     title Key elements in Product X
>     "Calcium" : 42.96
>     "Potassium" : 50.05
>     "Magnesium" : 10.01
>     "Iron" :  5
> ```



### 1.10 git图(mermaid)

> ```mermaid
> gitGraph:
> options
> {
>     "nodeSpacing": 150,
>     "nodeRadius": 10
> }
> end
> commit
> branch newbranch
> checkout newbranch
> commit
> commit
> checkout master
> commit
> commit
> merge newbranch
> ```

### 1.11竖向标准流程图(flow)

> ```flow
> st=>start: 开始框
> op=>operation: 处理框
> cond=>condition: 判断框(是或否?)
> sub1=>subroutine: 子流程
> io=>inputoutput: 输入输出框
> e=>end: 结束框
> st->op->cond
> cond(yes)->io->e
> cond(no)->sub1(right)->op
> ```

### 1.12 横向标准流程图(flow)

> ```flow
> st=>start: 开始框
> op=>operation: 处理框
> cond=>condition: 判断框(是或否?)
> sub1=>subroutine: 子流程
> io=>inputoutput: 输入输出框
> e=>end: 结束框
> st(right)->op(right)->cond
> cond(yes)->io(bottom)->e
> cond(no)->sub1(right)->op
> ```

### 1.13标准流程图(flow)

> ```flow
> startID=>start: 开始框
> inputoutputID=>inputoutput: 输入输出框
> operationID=>operation: 操作框
> conditionID=>condition: 条件框
> conditionID2=>condition: 条件框2
> subroutineID=>subroutine: 子流程
> endID=>end: 结束框
> 
> startID->inputoutputID(left)->operationID->conditionID
> conditionID(no)->subroutineID
> conditionID(yes,right)->conditionID2(yes)->endID
> conditionID2(no)->conditionID
> ```
>
> 



### 1.14 uml时序图(sequence)

> ```sequence
> 对象A->对象B: 对象B你好吗?（请求）
> Note right of 对象B: 对象B的描述
> Note left of 对象A: 对象A的描述(提示)
> 对象B-->对象A: 我很好(响应)
> 对象A->对象B: 你真的好吗？
> ```

### 1.15 UML时序图源码(复杂)(sequence)

> ```sequence
> Title: 标题：复杂使用
> 对象A->对象B: 对象B你好吗?（请求）
> Note right of 对象B: 对象B的描述
> Note left of 对象A: 对象A的描述(提示)
> 对象B-->对象A: 我很好(响应)
> 对象B->小三: 你好吗
> 小三-->>对象A: 对象B找我了
> 对象A->对象B: 你真的好吗？
> Note over 小三,对象B: 我们是朋友
> participant C
> Note right of C: 没人陪我玩
> ```





## 2. LaTeX公式（了解）

#### 概述

> **Typora默认未开启，需要在文件>偏好设置>Markdown>勾选Markdown扩展语法才能支持**
>
> **插入公式**：
>
> * **行内公式**，使用 \$公式\$ 的格式在行中插入公式
> * **行间公式**，多行公式使用 \$\$…\$\$ 格式在行间插入公式

#### 上下标

> 上标使用`^`，下标使用`_`。多个上下标字符使用小括号`{}`括起来。例如
>
> ```
> $ y = f_1^2(x^{e^2}) $
> ```
>
> $ y = f_1^2(x^{e^2}) $		$ y = f_1^2(x^e^2) $
>
> 
>
> 如果符号两边都要加上下标，可以使用`\sideset`命令。`\sideset{1}{2}{3}` 参数1、2、3分别为左、右、中位置的符号，例如：
>
> ```
> $ \sideset{^{左上}_{左下}}{^{右上}_{右下}}{中} $
> ```
>
> $ \sideset{^{左上}_{左下}}{^{右上}_{右下}}{中} $



#### 括号与分隔符

> `()`，`[]`，`|`用符号本身表示，`{}`使用反斜杠`\`转义来表示，如此`\{\}`。
>
> 大括号或者分隔符要用到 `\left` `\right` 命令，例如 `\left(` 表示大括号左边，且必须成对存在（有left就要有right）
>
> ```
> $ f(x) = \left( x + \frac{2}{x^2} + \frac{3}{x^3} \over e \right) $
> ```
>
> $ f(x) = \left( x + \frac{2}{x^2} + \frac{3}{x^3} \over e \right) $
>
> ```
> $ a = \left. \frac {{\rm d}u}{{\rm d}t} \right |_{t=1} $
> ```
>
> $ a = \left. \frac {{\rm d}u}{{\rm d}t} \right |_{t=1} $
>
> **注**： `\rm` 命令使其后的一个字符显示为印刷字体，例 `\rm a` 显示为 $\rm a$， `a` 显示为 $a$ 。

* **特殊符号**

   > |   输入    |   显示    |   输入    |   显示    |
   > | :-------: | :-------: | :-------: | :-------: |
   > | `\langle` | $\langle$ | `\rangle` | $\rangle$ |
   > | `\lceil`  | $\lceil$  | `\rceil`  | $\rceil$  |
   > | `\lfloor` | $\lfloor$ | `\rfloor` | $\rfloor$ |
   > | `\lbrace` | $\lbrace$ | `\rbrace` | $\rbrace$ |

#### 分式

> 分式使用`\frac`， `\over` 命令。（ *fraction：分式* ）
>
> - `\frac abc`表示$\frac abc$ ，即`\frac`后面分别依次为分子和分母
> - `abcd \over efg` 表示 $abcd \over efg$，即`\over`之前全部为分子，之后全部为分母
>
> ```
> $ y_1 = \frac ab + \frac {a^2}{b^2} + \frac cde \over {\rm e} \tag{1} $
> ```
>
> $ y_1 = \frac ab + \frac {a^2}{b^2} + \frac cde \over {\rm e} \tag{1}$
>
> **可以使用 {} 来限制 \over 的作用范围**
>
> ```
> $y_2 = {{a \over b} \over {\frac cd}} \tag{2}$
> ```
>
> $y_2 = {{a \over b} \over {\frac cd}} \tag{2}$

> 分数： $ f(x,y) = \frac{x^2}{y^3} $
>
> 开根号： $ f(x,y) = \sqrt[n]{{x^2}{^3}} $
>
> 省略号： $ f(x_1, x_2, \ldots, x_n) = x_1 + x_2 + \cdots + x_n $



#### 矩阵、排列（对齐）

> 在书写公式的时候，我们通过排版使形式美观，内容分明。
>
> - 使用 `\begin{keyword} \end{keyword}` 命令创建一个特定格式区域
> - 关键词`keyword`有`align`、`matrix`、`vmatrix`、`bmatrix`、`pmatrix`等
> - `\\`命令，换行，在任何区域都能使用
> - `&`命令，对齐或分隔，具体作用在不同区域略有不同
>
> ```
> $$
>     \left \{ 
>         \begin{align}
>             &
>             \begin{bmatrix}
>             a_1 & b_1 & c_1 \\
>             a_2 & b_2 & c_2 \\
>             a_3 & b_3 & c_3 
>             \end{bmatrix}
>             = 
>             \begin{pmatrix}
>             x_1 \\ x_2 \\ x_3
>             \end{pmatrix}
>             \begin{bmatrix}
>             1 &   &   \\
>               & 1 &   \\
>               &   & 1 
>             \end{bmatrix}
>             \\
>             &
>             \begin{vmatrix}
>             a_1 & b_1 & c_1 \\
>             a_2 & b_2 & c_2 \\
>             a_3 & b_3 & c_3 
>             \end{vmatrix}
>             = \lambda^3
>              \\ 
>              & W = U + V
>         \end{align}
>     \right.
>     \tag{3}
> $$
> ```
>
> $$
> \left \{ 
>         \begin{align}
>             &
>             \begin{bmatrix}
>             a_1 & b_1 & c_1 \\
>             a_2 & b_2 & c_2 \\
>             a_3 & b_3 & c_3 
>             \end{bmatrix}
>             = 
>             \begin{pmatrix}
>             x_1 \\ x_2 \\ x_3
>             \end{pmatrix}
>             \begin{bmatrix}
>             1 &   &   \\
>               & 1 &   \\
>               &   & 1 
>             \end{bmatrix}
>             \\
>             &
>             \begin{vmatrix}
>             a_1 & b_1 & c_1 \\
>             a_2 & b_2 & c_2 \\
>             a_3 & b_3 & c_3 
>             \end{vmatrix}
>             = \lambda^3
>              \\ 
>              & W = U + V
>         \end{align}
>     \right.
>     \tag{3}
> $$



#### 运算符

> |         命令         |                 名称                 |            符号            |                      示例                      |                      结果                      |
> | :------------------: | :----------------------------------: | :------------------------: | :--------------------------------------------: | :--------------------------------------------: |
> |       `\times`       |               乘 times               |          $\times$          |                  `3 \times 5`                  |                  $3 \times 5$                  |
> |        `\div`        |              除 divide               |           $\div$           |                   `3 \div 5`                   |                   $3 \div 5$                   |
> |   `\ge \geqslant`    |     大于或等于 greater or equal      |    $\ge$ 或 $\geqslant$    |         `a \ge b \quad a \geqslant b`          |         $a \ge b \quad a \geqslant b$          |
> |   `\le \leqslant`    |      小于或等于 lesser or equal      |    $\le$ 或 $\leqslant$    |         `b \le c \quad b \leqslant c`          |         $b \le c \quad b \leqslant c$          |
> |        `\ne`         |           不等于 not equal           |           $\ne$            |                   `3 \ne 5`                    |                   $3 \ne 5$                    |
> |       `\equiv`       |          必等于 equivalent           |          $\equiv$          |                       -                        |                       -                        |
> |      `\approx`       |         约等于 approximately         |         $\approx$          |                       -                        |                       -                        |
> |      `\pm \mp`       |         加号 plus 减号 minus         |        $\pm$  $\mp$        |                       -                        |                       -                        |
> |        `\sin`        |                 正弦                 |           $\sin$           |                       -                        |                       -                        |
> |        `\cos`        |                 余弦                 |           $\cos$           |                       -                        |                       -                        |
> |        `\tan`        |                 正切                 |           $\tan$           |                       -                        |                       -                        |
> |        `\cot`        |                 余切                 |           $\cot$           |                       -                        |                       -                        |
> |      `\arcsin`       |                反正弦                |         $\arcsin$          |                       -                        |                       -                        |
> |      `\arctan`       |                反正切                |         $\arctan$          |                       -                        |                       -                        |
> |       `\sqrt`        |              开方 sqrt               |         $\sqrt 2$          |           `\sqrt 2 \quad \sqrt [n]3`           |           $\sqrt 2 \quad \sqrt [n]3$           |
> |        `\int`        |            积分 integral             |           $\int$           |          `\int_0^\pi f(x) {\rm d} x`           |          $\int_0^\pi f(x) {\rm d} x$           |
> |      `\partial`      |              偏 partial              |         $\partial$         |        `\frac {\partial f}{\partial v}`        |        $\frac {\partial f}{\partial v}$        |
> |       `\nabla`       |          矢量微分算子 nabla          |          $\nabla$          |       `\bold A = \nabla \times \bold B}`       |      $\bold A = \nabla \times {\bold B}$       |
> |        `\lim`        | 极限 limit 界限 limits 无穷 infinity |           $\lim$           | `\lim \limits_{n \to +\infty} \frac 1{n(n+1)}` | $\lim \limits_{n \to +\infty} \frac 1{n(n+1)}$ |
> |        `\sum`        |            求和 summation            |           $\sum$           |      `\sum \limits_{i=1}^n \frac 1{i^2}`       |      $\sum \limits_{i=1}^n \frac 1{i^2}$       |
> |       `\prod`        |             累乘 product             |          $\prod$           |        `\prod \limits_{i=1}^n \frac 1n`        |        $\prod \limits_{i=1}^n \frac 1n$        |
> |        `\vec`        |             向量 vector              |          $\vec a$          |                 `\vec {\rm u}`                 |                 $\vec {\rm u}$                 |
> |       `\cdot`        |           中点 center dot            |          $\cdot$           |             `\vec a \cdot \vec b`              |             $\vec a \cdot \vec b$              |
> |        `\cup`        |              （杯子）并              |           $\cup$           |           `\mathbf A \cup \mathbf B`           |           $\mathbf A \cup \mathbf B$           |
> |      `\bigcup`       |             （大杯子）并             |         $\bigcup$          |         `\mathbf A \bigcup \mathbf B`          |         $\mathbf A \bigcup \mathbf B$          |
> |        `\cap`        |              （帽子）交              |           $\cap$           |           `\mathbf A \cap \mathbf B`           |           $\mathbf A \cap \mathbf B$           |
> |      `\bigcap`       |             （大帽子）交             |         $\bigcap$          |         `\mathbf A \bigcap \mathbf B`          |         $\mathbf A \bigcap \mathbf B$          |
> |    `\complement`     |            补 complement             |       $\complement$        |                `\complement_UA`                |                $\complement_UA$                |
> |        `\in`         |           属于，在其中 in            |           $\in$            |                   `a \in A`                    |                   $a \in A$                    |
> |       `\notin`       |         不属于，不在 not in          |          $\notin$          |                  `b \notin A`                  |                  $b \notin A$                  |
> |       `subset`       |             子集 subset              |         $\subset$          |                 `A \subset U`                  |                 $A \subset U$                  |
> |      `subseteq`      |      子集或相等 subset or equal      |        $\subseteq$         |                `A \subseteq U`                 |                $A \subseteq U$                 |
> |      `\exists`       |             存在 exists              |         $\exists$          |                       -                        |                       -                        |
> |      `\forall`       |           对于所有 for all           |         $\forall$          |                       -                        |                       -                        |
> |        `\neg`        |           非,否定 negative           |           $\neg$           |                       -                        |                       -                        |
> | `\empty \varnothing` |                  空                  | $\empty$ 或者$\varnothing$ |                       -                        |                       -                        |



#### 符号 & 字体

> |     命令      |     显示      |      命令       |      显示       |
> | :-----------: | :-----------: | :-------------: | :-------------: |
> |      `a`      |      $a$      |       `A`       |       $A$       |
> |   `\varPhi`   |   $\varPhi$   | `\boldsymbol A` | $\boldsymbol A$ |
> |    `\rm a`    |    $\rm a$    |     `\rm A`     |     $\rm A$     |
> |  `\mathbf a`  |  $\mathbf a$  |   `\mathbf A`   |   $\mathbf A$   |
> |   `\bold a`   |   $\bold a$   |    `\bold A`    |    $\bold A$    |
> |  `\mathbb a`  |  $\mathbb a$  |   `\mathbb A`   |   $\mathbb A$   |
> | `\mathcal a`  | $\mathcal a$  |  `\mathcal A`   |  $\mathcal A$   |
> | `\mathfrak a` | $\mathfrak a$ |  `\mathfrak A`  |  $\mathfrak A$  |
> | `\mathscr a`  | $\mathscr a$  |  `\mathscr A`   |  $\mathscr A$   |

* **希腊字母**

   > |    命令    |    显示    |    命令    |    显示    |    命令    |    显示    |    命令    |    显示    |
   > | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
   > |  `\alpha`  |  $\alpha$  |  `\Alpha`  |  $\Alpha$  |  `\beta`   |  $\beta$   |  `\Beta`   |  $\Beta$   |
   > |  `\gamma`  |  $\gamma$  |  `\Gamma`  |  $\Gamma$  |  `\delta`  |  $\delta$  |  `\Delta`  |  $\Delta$  |
   > | `\epsilon` | $\epsilon$ | `\Epsilon` | $\Epsilon$ |  `\zeta`   |  $\zeta$   |  `\Zeta`   |  $\Zeta$   |
   > |   `\eta`   |   $\eta$   |   `\Eta`   |   $\Eta$   |  `\theta`  |  $\theta$  |  `\Theta`  |  $\Theta$  |
   > |  `\iota`   |  $\iota$   |  `\Iota`   |  $\Iota$   |  `\kappa`  |  $\kappa$  |  `\Kappa`  |  $\Kappa$  |
   > | `\lambda`  | $\lambda$  | `\Lambda`  | $\Lambda$  |   `\mu`    |   $\mu$    |   `\Mu`    |   $\Mu$    |
   > |   `\nu`    |   $\nu$    |   `\Nu`    |   $\Nu$    |   `\xi`    |   $\xi$    |   `\Xi`    |   $\Xi$    |
   > | `\omicron` | $\omicron$ | `\Omicron` | $\Omicron$ |   `\pi`    |   $\pi$    |   `\Pi`    |   $\Pi$    |
   > |   `\rho`   |   $\rho$   |   `\Rho`   |   $\Rho$   |  `\sigma`  |  $\sigma$  |  `\Sigma`  |  $\Sigma$  |
   > |   `\tau`   |   $\tau$   |   `\Tau`   |   $\Tau$   | `\upsilon` | $\upsilon$ | `\Upsilon` | $\upsilon$ |
   > |   `\phi`   |   $\phi$   |   `\Phi`   |   $\Phi$   |   `\chi`   |   $\chi$   |   `\Chi`   |   $\Chi$   |
   > |   `\psi`   |   $\psi$   |   `\Psi`   |   $\Psi$   |  `\omega`  |  $\omega$  |  `\Omega`  |  $\Omega$  |
   >
   > 可见，若要得到大写的希腊字母，只需将其命令英文名 *首字母大写* 即可。
   >
   > **部分字母有专用的 *变量* 形式，在原命令前面加 `\var` 即可：**
   >
   > |   原命令   |     变量      |              显示              |
   > | :--------: | :-----------: | :----------------------------: |
   > | `\epsilon` | `\varepsilon` | $\epsilon$       $\varepsilon$ |
   > |  `\theta`  |  `\vartheta`  |   $\theta$       $\vartheta$   |
   > |   `\rho`   |   `\varrho`   |     $\rho$       $\varrho$     |
   > |  `\sigma`  |  `\varsigma`  |   $\sigma$       $\varsigma$   |
   > |   `\phi`   |   `\varphi`   |     $\phi$      $\varphi$      |



#### 其他字符

> |          符号          |      名称      |         命令          |        符号        |      名称      |        命令        |
> | :--------------------: | :------------: | :-------------------: | :----------------: | :------------: | :----------------: |
> | $\overrightarrow {AB}$ |    顶右箭头    | `\overrightarrow{AB}` | $\overleftarrow A$ |    顶左箭头    | `\overleftarrow A` |
> |       $\hat{a}$        |       冒       |       `\hat{a}`       |   $\overline A$    |      横线      |    `\overline`     |
> |     $\rightarrow$      |     右箭头     |     `\rightarrow`     |   $\Rightarrow$    |     右推出     |   `\Rightarrow`    |
> |      $\leftarrow$      |     左箭头     |     `\leftarrow`      |    $\Leftarrow$    |     左推出     |    `\Leftarrow`    |
> |   $\leftrightarrow$    |    双向箭头    |   `\leftrightarrow`   | $\Leftrightarrow$  |     等价于     | `\Leftrightarrow`  |
> |   $\longrightarrow$    |    长右箭头    |   `\longrightarrow`   | $\Longrightarrow$  |    长右推出    | `\Longrightarrow`  |
> |    $\longleftarrow$    |    长左箭头    |   `\longleftarrow`    |  $\Longleftarrow$  |    长左推出    |  `\Longleftarrow`  |
> |         $\pi$          |       π        |          \pi          |        $~$         |      间隔      |        `~`         |
> |      $\triangle$       |     三角形     |      `\triangle`      |      $\odot$       |      圆点      |      `\odot`       |
> |        $\angle$        |       角       |       `\angle`        |      $\perp$       |      垂直      |      `\perp`       |
> |  $\underbrace{111}_3$  |    底大括号    | `\underbrace{111}_3`  |      $\infty$      |      无穷      |      `\infty`      |
> |       $\because$       |      因为      |      `\because`       |    $\therefore$    |      所以      |    `\therefore`    |
> |      $\centerdot$      |    居中的点    |     `\centerdot`      |      $\cdots$      | 省略号（中间） |      `\cdots`      |
> |       $\bullet$        |      大点      |       `\bullet`       |      $\dots$       | 省略号（底部） |      `\dots`       |
> |        $\ddots$        | 省略号（下降） |       `\ddots`        |      $\vdots$      | 省略号（垂直） |      `\vdots`      |
> |         $\sim$         |     波浪号     |        `\sim`         |     $\tilde a$     |      波浪      |      `\tilde`      |
> |     $\widetilde A$     |     宽波浪     |    `\widetilde A`     |     $\ddot a$      |      双点      |      `\ddot`       |



## 3.使用HTML

### 嵌入内容

> <iframe height = '300' src="//player.bilibili.com/player.html?aid=11266283&cid=18633990&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

* **设置iframe**

   > | 属性         | 值                                                           | 描述                                               |
   > | :----------- | :----------------------------------------------------------- | :------------------------------------------------- |
   > | frameborder  | 1 0 yes no                                                   | HTML5 不支持。规定是否显示 `<iframe>` 周围的边框。 |
   > | border       | pixels                                                       | 规定`<iframe>`的边框宽度。                         |
   > | framespacing | pixels                                                       | 规定`<iframe>`的边框宽度，与border同。             |
   > | height       | pixels                                                       | 规定 `<iframe>` 的高度。                           |
   > | name         | name                                                         | 规定 `<iframe>` 的名称。                           |
   > | sandbox      | allow-forms  allow-same-origin  allow-scripts  allow-top-navigation | 对 `<iframe>` 的内容定义一系列额外的限制。         |
   > | scrolling    | yes   no   auto                                              | HTML5 不支持。规定是否在 `<iframe>` 中显示滚动条。 |
   > | seamless     | seamless                                                     | 规定 `<iframe>` 看起来像是父文档中的一部分。       |
   > | src          | URL                                                          | 规定在 `<iframe>` 中显示的文档的 URL。             |
   > | width        | pixels                                                       | 规定 `<iframe>` 的宽度。                           |



### 视频

> 使用 `<video>` 标签可以嵌入视频。直接**拖拽**到Typora中将会自动生成一个基本的HTML代码，但是其他属性还需适当设置
>
> <video src="https://v.stream.tencentmusic.com/0b53w4askaabimapyfjldfrkbn6dew3qcjia.f140000.mp4?dis_k=9c6c82195fe34f0ebed04ee5f4ca5f25&dis_t=1669187854&fromtag=202&domain_white_key=fa460700c1e9ef4151f2d563b3fc8462:1669187854">网络出错</video>



* 设置video

   > | 属性     | 值       | 描述                                                         |
   > | :------- | :------- | :----------------------------------------------------------- |
   > | autoplay | autoplay | 如果出现该属性，则音频在就绪后马上播放。                     |
   > | controls | controls | 如果出现该属性，则向用户显示控件，比如播放按钮。             |
   > | loop     | loop     | 如果出现该属性，则每当音频结束时重新开始播放。               |
   > | preload  | preload  | 如果出现该属性，则音频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。 |
   > | src      | url      | 要播放的音频的 URL。                                         |





# 演示

> 



*[IC]: Integer Circuirt	简写














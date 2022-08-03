# 诺基亚维信 - 悠嘻猴躲避球 Nokia WidSet - Yoyo & Cici Dodge Ball

## 介绍 Intro

《悠嘻猴躲避球》是我在2008年外派上海诺基亚期间为诺基亚维信项目中国区编写的维信平台上的一个小游戏。这个游戏由当时大火的IP《悠嘻猴》授权及提供了基础美术设计（人物、背景），由一位当时在上海诺基亚实习的美术设计师（很抱歉忘记你的名字了）和我一起补充了道具设计。游戏的基本玩法由《悠嘻猴》提供，游戏细节主要由我判断把控。

_Yoyo & Cici Dodge Ball_ is a simple game I wrote for Nokia WidSet in China when I worked at Nokia Shanghai as an outsourced developer. _Yoyo & Cici_, a very hot IP in those days, warranted the game and provided basic visual designs(characters, backgrounds). An intern visual designer(sorry for having forgot your name) of Nokia Shanghai and I replenished item designs. Basic game rules were set by _Yoyo & Cici_, and game details were designed and decided by me.

游戏玩法很简单，玩家需要控制“悠悠”或”嘻嘻“左右移动不断躲避天上掉落并不断弹跳的皮球，在生命消耗完之前尽可能获取更多分数。玩家角色在碰到皮球时，会扣除一点生命并消除这个皮球。皮球的数量会随时间增加，并且皮球的弹跳速度会随时间加快。另外会不时有随机道具从天上降落，如果在落地前被玩家角色碰触到，则会触发各自对应的效果。

The gameplay is simple. Player needs to move Yoyo or Cici left or right to avoid bouncing balls from the sky above, and try to obtain as much score as possible before all lives are gone. When the player character is hit by a ball, one life is gone and the hitting ball vanishes. The number of balls grows with time passing, so does the velocity of balls. In other hand, random items will fall from the sky, and if they are touched by the player character, individual effects will be triggered.

## 说明 Explanation

维信平台上的应用（又称为“精灵”）固定包含一个名为`widget.xml`的文件，用于声明项目基本信息、入口代码文件、相关的资源文件以及一些样式。有效的代码文件有且只能有一个，并且以维信平台专用的编程语言 _Helium_ 编写。图片文件可以有任意多个，并且可以在`widget.xml`文件中对于每一个图片设置是否自动缩放。如果开启了自动缩放，那么对于一些低分辨率的机型，“精灵”被下载时包含的将是这个图片的低分辨率版本。另外，“精灵”支持MIDI格式的音频文件，但是由于《悠嘻猴》没有提供合规的游戏背景音乐，在这个游戏中没有用到。

PS：当时我收到的一个背景音乐是《檄！帝国华击团！》（著名的《樱花大战》主题歌）的片段，很明显不可能用在这个游戏里。

An application on WidSet platform, also called a _Widget_, always contains a file named as `widget.xml`, which declares basic info of the project, an entrance code file, corresponding recourse files and some styles. There is one and only one effective code file, and it has to be written in _Helium_, a programming language used exclusively on WidSet platform. There may be arbitary number of image files, and each image file may be declared scalable or not in `widget.xml`. If declared scalable, a down-sized version of the image file will be contained in the downloaded _Widget_ when the host device has a low resolution. Moreover, audio files in MIDI format are supported. But as _Yoyo & Cici_ did not provide any legal background music, there is no such file in this game.

PS: A piece of background music given to me was cut from _Geki! Teikoku Kagekidan_(famous theme song of _Sakura Wars_), which apparantly could not be used in this game.

_Helium_ 的语法接近于 _Java_ 。比较明显的不同有：

- _Helium_ 是一种面向过程的语言，仅在代码最外层固定声明为`class`，内部并不允许使用`class`。
- 出于运行效率的考虑， _Helium_ 不支持浮点数类型（`float`、`double`）。

作为对于以上的补偿， _Helium_ 支持`struct`、多元数据以及函数指针。

_Helium_ has syntax close to _Java_. The main differences are:

- _Helium_ is a POP language, and except for the fixed `class` at the outmost of code, `class` keyword is prohibited anywhere else.
- For the sake of running efficiency, _Helium_ does not support float value types(`float`、`double`).

As a compensation to the points above, _Helium_ supports structs, tuples and function pointers.

由于“精灵”在最初仅仅被设计为一些RSS阅读器，不难理解 _Helium_ 为什么会是一种面向过程的语言。但是，“精灵”可以做更多的事，比如这里的游戏。大家都知道，面向过程的代码不利于复杂逻辑的维护。为此，我基于`struct`和函数指针为 _Helium_ 设计了一套伪面向对象的编码风格。这套编码风格问世之后，被全世界许多“精灵”开发者采用。

As _Widgets_ are designed only as some RSS readers at first, it should be quite understandable why _Helium_ is a POP language. But _Widgets_ can be more, such as the game here. As we can all agree, procedure oriented code can do harm to maintaince of complicated logics. Therefore, I designed a pseudo OOP coding style for _Helium_ based on structs and function pointers. This coding style was adopted by many _Widget_ developers over the world.

## 运行 Running

简单来说，很遗憾，这个应用无法运行。

To make it simple, sadly, this application is not capable of running.

维信模拟器需要服务端数据支持，但是维信服务器早已停止运行。除非今后有人能够模拟出当时维信平台的网络环境，否则任何“精灵”都无法运行。

_WidSet_ simulator requires server data support, but _WidSet_ server had ceased running long long ago. Any _Widget_ cannot run, except for that someone reconstruct the network environment of _WidSet_ platform.

## 回顾 Review

通过阅读唯一的代码文件`YoyoCici.he`，不难发现其中基本没有任何注释。当年我秉持着“好代码需要自解释，注释是不必要的”这一信念，并将其实行到了极致。事实上，我有点做过火了。在这份代码中，存在着一些拼写错误（比如`virtual`错写成`virtue`）和一些词不达意（比如`mirror`函数名），这都增加了理解的难度。另外，还存在着一些未使用的代码，这也是应当避免的。

By reading the only code file `YoyoCici.he`, it is not difficult to tell there is little to no coding comments. I was convinced that Good Code Should Be Self-explanatory And Comments Should Not Be Required, and go for the extreme of it those days. In fact, I went a bit too far. Misspellings (such as `virtual` misspelled as `virtue`) and word misuses (such as the function name `mirror`) in the code increases the difficulty of understanding. There is also some unused code, which should be avoided too.

## 授权 License

在我的理解中，应该没有谁会需要这里的代码或图片资源。如果有需要，请私信给我或邮件至`17433201@qq.com`，我会加上一个合适的授权声明。

To my understanding, there should be nobody who needs the code or images in this repository. If there is one, please send me a private message or mail to `17433201@qq.com`, and I will then add a appropriate licence.

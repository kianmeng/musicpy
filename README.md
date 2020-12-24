﻿# musicpy
你们想过用代码来写音乐吗？

最近几个月学业繁忙，但是业余时间自己开发了很多python库，内容包括数学统计，各种游戏，还有音乐等等。其实还有试着写AI方面的，但是目前还是初期进度。今天我想先介绍一下我正在开发中的一个音乐代码语言库: musicpy。

这个库可以让你用非常简洁的语法，来表达一段音乐的音符，节奏等等信息，并且可以简单地输出成midi文件的格式。这个库里面涉及到非常多的乐理知识，所以个人推荐至少要先了解一部分乐理再来使用会比较上手。相对地，如果你是一个对乐理比较了解的人，那么看完我在[Wiki正在写的教程](https://github.com/Rainbow-Dreamer/musicpy/wiki
)之后你应该很快就上手了。

首先在musicpy文件夹里打开cmd, 跑一下pip install -r requirements.txt安装依赖库（如果本来就是pip install musicpy安装的就不需要这一步，
我也比较推荐直接pip install musicpy就行）

import这个库: from musicpy import *

我自己做的介绍与使用教程视频第一期：https://www.bilibili.com/video/BV1754y197a9/ （比较旧了，musicpy当前的最新版本有很多重大的更新与语法上的改进，这期教程很多地方跟最新版本已经不一样了，我会重新做这期教程）

musicpy作曲示例实际演示以及musicpy实验作曲日常：https://www.bilibili.com/video/BV18z4y1r7Pk/

详细的musicpy数据结构，基础语法以及使用教程，请看我正在写的Wiki，我会尽量把所有的细节都讲清楚。 

Wiki的地址： https://github.com/Rainbow-Dreamer/musicpy/wiki

在musicpy里面，几个基本的类是note（音符）, chord（和弦）和scale（音阶）。这几个类是构成音乐代码的基础。

在musicpy这门语言的数据结构设计中，音符类本身是等值为纯数字的，也就是完全可以作为纯数字使用。

和弦类是音符类的集合，也说明和弦类本身等值为一个全部都是数字的集合，也可以作为向量，甚至矩阵来看待（比如多个和弦的连接走向就可以看作多个向量的拼接，因此也就有了行列数，也就是矩阵的形式）。

也因此在这门语言的数据结构设计中，音符类，和弦类，音阶类都是可以进行数学运算的，比如线性代数领域的运算，离散数学领域的运算等等。也可以在这门语言的数据结构的基础上建立一整套乐理逻辑的算法，结合纯数学逻辑来进行多方面的音乐分析研究。

现代音乐领域的很多实验性质的音乐，比如序列主义，偶然音乐，后现代主义音乐（比如极简主义音乐），理论上全部都可以在这门语言的纯数字化的数据结构的基础上进行严格的创作。即使不提实验性质的音乐，这门语言也可以写任何的古典音乐，爵士音乐，流行音乐。


我几乎每隔两三天就会更新一次这个库的内容，具体的更新内容请大家看这个库里的“更新日志Changelog.txt”，里面有按照日期的每次更新的非常详细的细节与说明。

更新日志的链接：

https://github.com/Rainbow-Dreamer/musicpy/blob/master/%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97Changelog.txt

我开发这个语言主要的初衷有两点，第一，比起工程文件和midi文件单纯存储音符，力度，速度等单位化的信息，如果能够按照乐理上的角度来表示一段音乐从作曲上的角度是如何实现的，那就更加有表示的意义了。而且只要不是现代主义无调性音乐，大部分的音乐都是极其具有乐理上的规律性的，这些规律抽象成乐理逻辑语句可以大大地精简化。（比如一个midi文件1000个音符，实际上按照乐理角度可能可以简化到几句代码）。第二，开发这个语言是为了让作曲AI能够在真正懂得乐理的情况下来作曲（而不是深度学习，喂大量的数据），这个语言也算是一个接口，AI只要把乐理的语法搞懂了，那作曲就会拥有和人一样的思维。我们可以把乐理上的规则，做什么好不做什么好告诉AI，这些东西还是可以量化的，所以这个乐理库也可以作为一个乐理接口，沟通人和AI之间的音乐。因此，比如想让AI学习某个人的作曲风格，那么在乐理上面也同样可以量化这个人的风格，每种风格对应着一些不同的乐理逻辑规则，这些只要写给AI，经过我这个库，AI就可以实现模仿那个人的风格了。如果是AI自己原创风格，那就是从各种复杂的作曲规则里寻找可能性。

我在想不用深度学习，神经网络这些东西，直接教给AI乐理和某个人的风格化的乐理规则，那么AI或许可以做的比深度学习大数据训练出来的更好。因为大数据训练只是给AI模仿数据本身而已，这样其实AI并没有真正地和人类自己一样理解作曲是什么，乐理是什么，所以我才想通过这个库实现把人的乐理同样教给AI，让AI真正意义上地理解乐理，这样的话，作曲起来就不会生硬了，没有机器和随机的感觉了。所以我写这个库的初衷之一就是避开深度学习那一套。但是感觉抽象出不同音乐人的乐理规则确实很有难度，我会加油写好这个算法的qwq 另外其实也可以音乐人自己告诉AI他自己乐理上喜欢怎么写（也就是自己独特的乐理偏好规则），那么AI就会模仿的很到位，因为AI那时候确实懂得乐理了，作曲不可能会有机器感和随机感，此时AI脑子里想的就和音乐人脑子里想的是完全一样的东西。

AI不必完全按照我们给他的乐理逻辑规则来创作，我们可以设置一个“偏好度”的概念给AI，AI在自己作曲时会有一定程度地偏好某种风格，但是除此之外会有自己在“符合正确乐理”的规则里面找到的独特的风格，这样AI就可以说“受到了某些音乐人的影响下自己原创的作曲风格了”。当这个偏好度为0时，AI的作曲将会完全是自己通过乐理寻找到的风格，就像一个人自己学习了乐理之后，开始摸索自己的作曲风格一样。一个懂得乐理的AI很容易找到自己独特的风格来作曲，我们甚至都不需要给他数据来训练，而只要教给AI乐理就行。

那么怎么教给AI乐理呢？在音乐上面，暂时不考虑现代主义音乐的范畴，那么绝大部分的音乐都是遵循着一些很基本的乐理规则的。这里的规则指的是，怎么样写乐理上ok，怎么样写犯了乐理上的错误。比如写和声的时候，四部同向往往是要避免的，尤其是在编曲时写管弦乐的部分。比如写一个和弦，如果和弦里面的音出现小二度（或者小九度）会听着比较打架。比如当AI自己决定一首曲子要从A大调开始写，那么他应该从A大调音阶里按照级数来选取和弦，有可能适当地离调一下，加几个副属和弦，写完主歌部分可能按照五度圈转个调，或者大三度/小三度转调，同主音大小调转调等等。我们需要做的事情就是告诉AI作曲的时候怎么写是正确的，更进一步的，怎么写听着比较有水平。AI学好了乐理，不会忘记，也比较难犯错，因此可以写出真正属于AI自己的音乐。他们会真正懂得音乐是什么，乐理是什么。因为这个库的语言做的事情就是把乐理抽象成逻辑语句，那么我们每次给AI“上课”，就是把人自己的乐理概念用这个库的语言来表述，然后写进AI的数据库里。通过这种方式，AI真正的学习到了乐理。这样的作曲AI，不需要深度学习，不需要训练集，不需要大数据，而与之相比，那些深度学习训练出来的作曲AI实际上根本就不懂乐理是什么，也没有音乐的概念，他们只是从海量的训练数据里面照葫芦画瓢而已。还有一个重点是，既然可以用具体的逻辑来描述的事情，其实是不需要机器学习的。如果是文字识别，图像分类这些比较难以用抽象的逻辑来描述的事情，那才是深度学习的用武之地。

这个库我也上传到pypi上了，大家pip install musicpy就可以使用了。

我从去年的10月份开始开发musicpy，目前这个项目还在初期进度，不过已经有一套比较完整的乐理逻辑语法了。这个库的使用教程视频我会持续更新。我之前发的专栏也有一部分的使用教学。

感谢大家的支持~

# Rime 简体中文用户定制文件
以 [袖珍简化字拼音](https://github.com/rime/rime-pinyin-simp) 为基础，在此之上定制了适合简体中文用户使用习惯的定制文件。

## 为什么不用朙月拼音？

朙月拼音在输入简体中文时，是将繁体中文使用 [OpenCC](https://github.com/BYVoid/OpenCC) 转化成简体中文列在候选列表继而进行输入。

默认方案在简体中文使用场景时会出现一些小瑕疵。

如「乾」在组「乾坤」之外的词组后，再输入时会变成「干」；又或者输入「买」的时候会发现「𧹒」也在候选列表，而绝大部分场景不会用到这个字。

这些问题可能可以通过强大的定制能力去解决，但是对于一般的简体中文用户来说，使用以简体中文为出发点的方案会更好一些。

## 这个项目是做什么的？

Rime 为简体中文用户专门提供了袖珍简化字拼音，但是默认方案直接使用不够方便。本项目提供了作者个人使用的配置文件，帮助有意如此使用的用户快速上手。

**请注意，文件中包含了个人使用习惯，如不合适或不必要，请自行前往 [Rime 官方网站 ](https://rime.im/)查阅文档修改。**

## 文件组成

- `pinyin_simp.custom.yaml` ：袖珍简化字拼音方案的自定义修改，包含初始输出状态、符号输入等功能修改，**同时指定了新词库中心文件**，如果需实现其他功能修改请自行增删。

- `pinyin_simp.main.dict.yaml` ：中心词库文件，主要功能为引用其他词库，需在输入方案中指定方可使用。词库内容为 [袖珍简化字拼音](https://github.com/rime/rime-pinyin-simp) 默认方案词库修改而来，一般不做修改。

- `cn_en.dict.yaml` ：英文及中英混输词库，由中心词库文件引用使用。如需添加新的英文或中英混输词汇，建议编辑此文件。文件内容大部分是纯英文，可以考虑在朙月拼音中使用以方便繁体中文输入场景。

- `pinyin_simp_custom.dict.yaml` ：自定义词语，由中心词库文件引用使用。如需添加自定义短语，建议编辑此文件。

- `pinyin_simp_pin.txt` ：候选固定，使用另一个翻译器并给极高权重来达到固定候选列表的目的，编辑时请记得给极高权重。

  请注意，有时此列表中的字或词在输入时临时组词，将不会录入用户词库。我个人发现此类问题会自行修改自定义词语文件去手动添加，如介意或不需要候选固定请自行修改关闭此功能。
  
- `xiandaihanyuchangyongcibiao.dict.yaml` ：现代汉语常用词表，由中心词库文件引用使用，来源为项目 [https://github.com/alswl/Rime](https://github.com/alswl/Rime)，一般不做修改。
  
- ``zhwiki.dict.yaml`` ：肥猫词库，由中心词库文件引用使用，来源为项目 [https://github.com/felixonmars/fcitx5-pinyin-zhwiki](https://github.com/felixonmars/fcitx5-pinyin-zhwiki)，一般不做修改。

## 为什么会删除部分字词？

个人在使用过程中发现，部分只有声母的词语，会影响到只输入该声母时的候选列表，带来诸多不便。

考虑到这些字词的使用场景很小，故移除这部分字词以获得良好输入体验，如若不喜，可以自行加回。

移除的字词如下：

`pinyin_simp.main.dict.yaml` 词典：

```yaml
唔	n	
嗯	n	
唔	ng	
嗯	ng	
噷	hm	
呣	m	
嘸	m	
呒	m	
```

``zhwiki.dict.yaml``  词典：

```yaml
呒染挖啊嗯啊	wu ran wa a n a
嗯哈哈乐团	n ha ha yue tuan
```

## 使用方法

- 安装 Rime 输入法并安装 [袖珍简化字拼音](https://github.com/rime/rime-pinyin-simp) 方案，使用软件或修改 `default.custom.yaml` 文件加入该方案。
- 将上述文件复制到 Rime 用户文件夹内。
- 重新部署。
-  打开 Rime 方案选单，切换至「袖珍简化字拼音」即可开始使用。

## 补充说明

- 开始菜单找到 输入法设定 -> 获取更多输入方案 -> 输入 rime/rime-pinyin-simp 下载（需要能连接到GitHub的网络环境）。

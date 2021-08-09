# Mindustry-Myblueprint
萌新个人制作蓝图和逻辑，仅适用于战役。未照搬他人作品，如有雷同纯属雷同，欢迎体验！<br>
要快速查找蓝图，请点击上方"README.md"左侧的图标
<img src="https://css.gg/layout-list.svg" alt="列表图标" title="List" width="32" height="32"/>
或按<kbd>Ctrl</kbd>+<kbd>F</kbd>搜索页内关键词。<br>
此处分享的各种炮塔站点类蓝图是我为了图方便做的，请各位酌自行判断后使用。我建议还是动动手按地形建立防线比较妥当。<br>
**注意，我的游戏版本为<code>129.1</code>**<br>
本页链接均使用jsDelivrCDN，故存在一定延迟。<br>
![hits](https://data.jsdelivr.com/v1/package/gh/Hexrotor/Mindustry-Myblueprint/badge)

## v7

### 攻击
这里包含攻击相关的蓝图。

#### 雷霆敢死队v1.2(20210805)
控制雷霆自动从核心拿爆混后轰炸敌方炮塔或核心，并在低于一定生命值时自动返回核心。自动携带地面单位(最多4个，但跟随模式不受限制)，自动攻击地面敌人。附近有敌人(包括空军)自动释放单位，低生命值返回核心时自动释放单位，关闭携带开关时释放所有单位。单位携带数、最低生命值、携带物、轰炸对象可自定义。<br>
注意：由于代码过多，单位过多时某些功能可能效果不佳；单位携带功能不一定实用，请酌情使用；判断可携带单位使用了血量比对(仅携带900及以下，但跟随模式不受限制)，所以你如果安装了某些模组，这可能会引发问题。<br>

行为优先级：取携带物>跟随玩家=自爆=释放单位>攻击核心>低血量返回>攻击敌人>携带单位>攻击炮塔<br>

按钮的功能：<br>
* 左下为总开关，开启后从核心拿爆混后自动轰炸敌方炮塔，并在低于一定生命值时返回。若低于设定的自爆生命值，则会冲向敌方炮塔直到爆炸。<br>
* 左上为轰炸核心开关，开启后会直接拿爆混冲向敌方核心，不会返回。此开关比右上玩家操控开关优先级低，但此开关开启时影响玩家操控模式时的低血量返回程序，即低血量不会返回。<br>
* 右上为跟随玩家开关，开启后会覆盖轰炸核心的命令，优先跟随玩家。此开关开启时，玩家可以通过操控"电弧"来控制单位移动，玩家可带2~3个雷霆绕到敌方核心，并在接近时关闭并切换到轰炸核心命令。<br>
* 顶部为单位携带开关，开启后自动携带附近陆军，关闭后释放所有单位。<br>
* 分类器可以选择携带物，默认为爆混。<br>

**没有调用冲突检测！**<br>

[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/boom1.2.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/boom1.2.jpg)

</details>

#### 单位带货
此逻辑控制指定类型的单位到核心携带指定物品，携带后自动释放单位。<br>
**没有调用冲突检测!**<br>

[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/takeitem.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/takeitem.jpg)

</details>

#### 远程供弹演示
这些蓝图演示如何远程供弹。这些蓝图调用一个星辉单位从核心将弹药搬运到容器，且不与其他本蓝图冲突，你可以调整装卸器配置以选择要搬运的弹药。这些蓝图中的逻辑代码较简单，如果你想了解如何避免调用冲突，可以参考其代码。稍加修改代码可实现从非核心搬运弹药。<br>
**仅调用闲置的单位，调用中的单位会被赋予随机flag值以供其余处理器区分。**<br>

<details><summary>展开相关蓝图</summary>

##### 供弹模板
容器、处理器、开关与装卸器是必要的，其他部分均可自由搭配。如果你想调整位置，则需要重新配置处理器。

[获取模板](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/remotesup.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/remotesup.jpg)

</details>

##### 串联蜂群
如果你想，你可以从外部供弹。对于弹夹版，需要与<a href="#仓库转移">仓库转移</a>配合使用。<br>

[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/swarmer.txt)
[获取弹夹版](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/swarmerx.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/swarmer.jpg)

</details>

</details>

#### 煤站改
修改后的煤站，装弹效率有点低，但增加了库存。<br>

[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/coal2.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/coal2.jpg)

</details>

#### 钍站
需要放入钍来启动(也可自启动)，启动过程会轻微负电。Plus版有更多的炮塔但修复器不能将其完全覆盖。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tu.txt)
[Plus获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tuplus.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/tu.png)
![PLUS预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/tuplus.png)

</details>

#### 石油站
需要从左下供应石油，小心起火。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/petroleum.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/petroleum.png)

</details>

#### 跟随四联v1.1
一个较为完善的跟随逻辑，四个处理器分别控制陆辅T1~T4。通过"电弧"操控单位前往指定坐标攻击或跟随玩家攻击，可远程追踪玩家，距离超过50启动boost。玩家未控制时自动攻击敌人，但不会攻击敌方建筑。注意不要进入石油、深水区域。<br>

**没有调用冲突检测！**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/followplayer1.1.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/followplayer.jpg)
  
</details>

#### 集群攻击v1.1
控制一种单位(默认Arkyid)Pathfind并攻击范围内的敌方炮塔与核心，或召唤设定范围内的同类友军群攻敌人，带远程追踪（不能避障，当所有单位未在敌人范围内超过timeout设定的时间，退出追踪模式）。通过操控"电弧"可控制单位：长按任意区域进入玩家控制模式，再次长按退出控制。某种程度上此逻辑兼容任何单位。<br>

优先级：玩家控制>打范围内敌人>打范围内核心>打范围内炮塔>pathfind<br>
可控变量：$聚集半径、$援军半径、$timeout<br>

**没有调用冲突检测！**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/arkyid.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/arkyid.jpg)

</details>

#### 坐标移动
控制一种单位按记录的坐标顺序移动。左开关开，控制"电弧"开炮来记录坐标；右开关开，则使设定的单位(雷霆)按坐标顺序移动。当左开关关闭，坐标记录会清空；当左开关关闭，右开关开启，会同时恢复单位flag为0。由于内存上限，最多记录32个点。<br>
请注意，如果你记录了无法达到的坐标，单位会卡住。<br>

**没有调用冲突检测！**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/movepoint.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/movepoint.jpg)

</details>

#### T3&T4红飞机控制
通过"电弧"操控T3&T4红飞机单位前往指定坐标攻击。若玩家不控制，则自动锁定并攻击附近敌人。锁定后可远程追踪，需要手动操作才能切换锁定对象。<br>

**没有调用冲突检测！**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/airctrl.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/airctrl.jpg)

</details>

#### 钍炸弹
利用爆炸的钍堆消灭周围的一切。自动调用星辉或独影装填钍，钍堆生
命值低于500自动引爆，可手动引爆。<br>
按钮的功能：左侧按钮解除热量限制，即引爆；右侧按钮选择调用星辉
或独影，默认为星辉。<br>

**仅调用闲置的单位，调用的单位会被赋予随机flag值以供其余处理器区分，结束后恢复flag值为0。当心你的支援单位被误伤！**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/autoboom.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/autoboom.jpg)

</details>

#### 核弹投放
让雷霆带上钍堆，并在生命值低于1000时投放。<br>
此逻辑的行为：当钍堆过热时将其禁用，并让一个可用的雷霆单位(health>1500)带上它并重构钍堆。当检测到雷霆单位生命值低于1000时并未处于己方核心半径50以内时，使其投放携带的任意荷载(钍堆)，不论何地。<br>
总之，这个逻辑十分危险，不要轻易使用它。自带的开关可以停用其所有功能。<br>
**仅调用符合要求的、闲置的雷霆单位。如果构建钍堆的雷霆单位不存在，则调用一个幻型构建。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/thpush.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/thpush.jpg)

</details>

#### 污水站
放在污水里才能正常工作。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/dirtywater.txt)<br>

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/dirtywater.jpg)


</details>

#### 水站重制版
重新拼的大水站，可以在v7上工作。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/water7.txt)<br>

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/water7.jpg)

</details>

### 生产
这些蓝图与生产物资、后勤有关。

#### Mega自动采矿+攻击闪避(20210803)
调用巨像自动开采核心内最少的物品(铜铅钛)同时保留自动修复，可手动选择开采物，扣血量超过10自动返回基地。优先攻击敌人，并反复横跳躲避攻击。本逻辑兼容所有可飞行的矿机，自行更改unit bind即可(对于开采等级低的单位会出问题，可以通过分类器强制指定开采矿物)。由于技术原因自动修复功能仅对巨像单位开放。<br>

**仅调用闲置的0flag单位。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/megaplus.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/megaplus.jpg)

</details>

#### 单位修复模板
此逻辑调用一个单位修复受损结构，兼容所有能飞的单位。默认调用幻型单位。<br>

**仅调用未被处理器控制的单位。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/repairuni.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/repairuni.jpg)

</details>

#### 幻型修复经典版
时代的眼泪，纪念104。<br>

**仅调用未被处理器控制的单位。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/polyc.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/polyc.jpg)

</details>

#### 仓库搬运
显示物品统计并当仓库单物品容量仅剩50时控制独影将物品搬运到核心。需要手动链接仓库(一对一)，并在代码内设置仓库名称。<br>

**调用单位可自行修改，仅调用闲置的单位，调用的单位会被赋予同一随机flag值以供其余处理器区分。由于技术原因flag值不会恢复，但不影响本逻辑的运行。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/itemtrans.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/itemtrans.jpg)

</details>

#### 仓库转移v1.1(20210806)
[视频介绍](https://www.bilibili.com/video/BV13v411K76c)<br>
自动选择Mega/Quad并调用其转移容器或仓库，至少需要两个同类单位才能运行。<br>
用法：分为装载点与卸载点，需要进入逻辑内设置"单位配对码"以关联两个站点。左开关开即将此站点设为装载点，关闭则将此站点设为卸载点。中间为总开关。右侧选择器可选择检测物，默认为null(检测物品总和)。信息板可以看到已设置的参数。<br>
行为：当装载点的检测物数量检测值达到设置的最大容量(null为单容量上限\*种类，若选择了检测物则按单容量上限计算)时，调用一个空单位将仓库拾起，将此单位flag标记为设定的单位配对码。装载点缺少仓库(容器)时，调用一个flag值为"单位配对码相反数"的单位放置一个新的仓库；当卸载点仓库内检测物数量检测值低至设定的最小值，调用一个空单位将仓库(容器)拾起并标记其flag值为"单位配对码相反数"。卸载点缺少仓库时，调用对应flag为配对码的单位放置仓库，随后该单位flag恢复为0。自动将payloadcount为0的单位flag设置为0。为提升速度，用于兼容其它逻辑的调用冲突检测已移除，请避免使用其它逻辑时与本逻辑调用的单位类型相同。<br>

处理器内允许自定义的值: $坐标误差、$仓库、$物品最大值、$物品最小值、$单位配对码、$搜索半径倍数

**没有调用冲突检测！调用单位可自行修改，仅调用符合条件的单位，调用中的单位会被赋予唯一flag值以供其余处理器区分。请注意单位的payload容量。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/paytrans.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/paytrans.jpg)

</details>

#### T2神风核心
集成了[坐标移动](#坐标移动)、[单位带货](#单位带货)、[幻型修复经典版](#幻型修复经典版)。自动控制幻型的生产，默认生产2个，可调。<br>
左下处理器可自定义的值：$幻型数量<br>
**由于集成了多个逻辑，请去各逻辑描述处查看注意事项。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/coreunit.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/coreunit.jpg)

</details>

#### 废料冲击
可能需要绿带才能带动，稳定后发电量7.7k左右。带安全启动与低血自停。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/reactor.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/reactor.png)

</details>

#### 废料大超速
可能需要一些时间才能稳定运行，可以放入相织物使其稳定。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/fwbooster.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/fwbooster.jpg)

</details>

#### 智能力墙
人手一个的智能力墙。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/sforce.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/sforce.jpg)

</details>

#### 原地出硅
调用单位挖材料并生产硅放入仓库，没啥用，有时也许有奇效。可配合其他逻辑使用，比如仓库搬运。<br>
  
**调用策略同"Mega自动挖矿"逻辑，单位默认为耀星。**<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/si.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/si.jpg)

</details>

#### 五连冷冻液
下方进料，自带一个罐体。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/x5fluid.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/x5fluid.jpg)

</details>

#### 串联冷冻液
左方进料，五个一组。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/multifluid.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/multifluid.jpg)
![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/multifluid.jpg)

</details>

#### 6温差串联结构
以6温差为一组的串联结构，需要外部供应冷冻液与炻，净发电量9.4k。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tgen.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/tgen.jpg)

</details>

### 杂项
这里可能是一些工具，或者一些娱乐向蓝图。

#### 分析器
名字叫分析器但它并不能自己分析，它在屏幕上绘制荷载内的物品与液体变化曲线，所以你可以根据这些曲线知道你要做什么。<br>
需要手动链接荷载后在逻辑编辑中将荷载关联到变量。使用分类器选择要检测的物品，使用开关切换要检测的液体，一次只能检测一种物品和液体。<br>
为避免混乱，效率与进程曲线不会被绘制，进程进度被绘制为横向移动的紫色进度条。<br>
处理器内可自定义的值：$检测荷载、$x轴增量、$速率更新间隔<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/monitor.txt)

<details><summary>展开图片</summary>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/monitor.png)

</details>

#### Demos
演示系列<br>
名字乱写的，逻辑乱写的。没有预览图，这不重要。<br>
1.aidemo<br>
使一种单位满地图乱跑并攻击敌人，直到接近敌人出生点后停下。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/aidemo.txt)<br>
2.pdemo<br>
按顺序数数并打印到信息板。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/pdemo.txt)<br>
3.vdemo<br>
像传统的波形监视器一样显示仓库内铜数量的变化。是模仿别人的但是没模仿像，用了很多代码，比别人的延迟高很多。到现在我也不知道这个效果该怎么做。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/vdemo.txt)<br>
4.random<br>
在显示屏上随机显示很多有色点，最后铺满。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/random.txt)<br>
5.autobuild<br>
通过电弧控制一个poly修建一组纯电攻守结构。半成品，思路不清晰，写得非常乱，效果不太好。<br>
个人感想：原来建造中的建筑类型是build2；使用随机参数圆的效果不如直接随机坐标。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/autobuild.txt)<br>

# For old versions

这些蓝图只能在旧版本正常工作且不会再更新。

## v6

<details><summary>展开全部126.2</summary>

#### 水站

<details><summary>展开描述</summary>
需要大面积的水，局限性很大。<br>

[预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/oldversions/v6/126.2/images/water.png)
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/oldversions/v6/126.2/base64text/water.txt)<br>

</details>

#### 水站PLUS

<details><summary>展开描述</summary>
需要小面积水，大面积空地。<br>

[预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/oldversions/v6/126.2/images/waterplus.png)
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/oldversions/v6/126.2/base64text/waterplus.txt)

</details>

# Mindustry-Myblueprint
个人重要数据备份，包含一些黑历史。蓝图等未照搬他人作品，部分有参考。如有雷同纯属雷同，欢迎体验！<br>
__此处列出的蓝图逻辑均未在服务器测试过，请自行判断。如果执意要带入服务器使用，被骂了与我无关。__<br>

要快速查找蓝图，请点击上方"README.md"左侧的图标
<img src="https://css.gg/layout-list.svg" alt="列表图标" title="List" width="32" height="32"/>
或按<kbd>Ctrl</kbd>+<kbd>F</kbd>搜索页内关键词。<br>

jsDelivrCDN链接能保证访问，但缓存更新约有24h延迟，无法立即获取最新文件。<br>
RAW链接与Page链接实时同步最新文件，但国内有时无法访问。<br>

**注意，我的游戏版本为`131`**<br>

贴吧传送门：[旧贴](https://tieba.baidu.com/p/7369580895) [新贴](https://tieba.baidu.com/p/7477442066)<br>
鸣谢：[中文逻辑指南](https://github.com/LanluZ/Mindustry-guide)<br>

[![](https://data.jsdelivr.com/v1/package/gh/Hexrotor/Mindustry-Myblueprint/badge?style=rounded)](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint@main/)

## v7

### 攻击
这里包含攻击相关的蓝图。

#### 雷霆敢死队
v1.2(20210805)<br>
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

获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/boom1.2.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/boom1.2.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/boom1.2.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/boom1.2.jpg)

</details>

#### 单位带货
此逻辑控制指定类型的单位到核心携带指定物品，携带后自动释放单位。<br>
**没有调用冲突检测!**<br>

获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/takeitem.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/takeitem.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/takeitem.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/takeitem.jpg)

</details>

#### 远程供弹演示
这些蓝图演示如何远程供弹。这些蓝图调用一个星辉单位从核心将弹药搬运到容器，且不与其他本蓝图冲突，你可以调整装卸器配置以选择要搬运的弹药。这些蓝图中的逻辑代码较简单，如果你想了解如何避免调用冲突，可以参考其代码。稍加修改代码可实现从非核心搬运弹药。<br>
**仅调用闲置的单位，调用中的单位会被赋予随机flag值以供其余处理器区分。**<br>

<details><summary>展开相关蓝图</summary>

##### 供弹模板
(20211009)
容器、处理器、开关与装卸器是必要的，其他部分均可自由搭配。如果你想调整位置，则需要重新配置处理器。<br>

获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/remotesup.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/remotesup.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/remotesup.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/remotesup.jpg)

</details>
</details>

### 钍站

需要放入钍来启动(也可自启动)，启动过程会轻微负电。Plus版有更多的炮塔但修复器不能将其完全覆盖。<br>

获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tu.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/tu.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/tu.txt)<br>
PLUS获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tuplus.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/tuplus.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/tuplus.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/tu.png)
![PLUS预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/tuplus.png)

</details>

#### 通用跟随
v1.2<br>
一个几乎完善的跟随逻辑，通过调整可控变量几乎能适用于任何单位。由它控制的单位具有如下行为。<br>

* 跟随玩家并同步攻击，不会跟丢。除非单位撞墙了，否则它会始终同步前往玩家坐标。<br>
* 可通过"电弧"操控单位前往指定坐标攻击。<br>
* 当受控单位与目标位置距离超过`$boost距离`设定的值，启动boost(如果它可以)。<br>
* 玩家未有任何操作的时候，受控单位自动攻击附近敌人，但不会自动攻击敌方建筑。<br>
* 当玩家控制的单位死了或者玩家不控制那个单位了，受控单位会停在玩家存在的最后位置(这不影响他们自动攻击)，直到玩家使用电弧控制或受控单位雷达再次发现玩家。<br>
* 受控单位的开火坐标将按`$开火缩减比率`设定的值缩减。比如设定的值为3，则将target坐标缩减为之前的1/3。这有助于让单位接近目标之前提前开炮，在某些时候非常有用。此功能不适用于投射类子弹和有交叉角度的子弹。<br>

每种单位的参数不一致，默认的参数针对vela。如果你想尝试更多单位，请在沙盒中自行调试。<br>
可控参数：`$闲置半径`、`$电弧开火半径`、`$开火缩减比率`、`$boost距离`<br>

**没有调用冲突检测！**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/followplayer1.2.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/followplayer1.2.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/followplayer1.2.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/followplayer1.2.jpg)
  
</details>

#### 单位AI增强(集群攻击)
v1.1(20210825)<br>
某种程度上此逻辑比内置的单位AI更强，它具有如下行为：<br>
控制一种单位(默认Arkyid)Pathfind并群攻范围内的敌人、敌方炮塔与核心，若一个单位发现敌人，它会"召唤"设定范围内的同类友军群攻敌人，带远程追踪（不能避障，当所有单位未在敌人范围内超过`$timeout`设定的时间，取消追踪）。通过操控"电弧"可控制单位：长按任意区域(开炮)进入玩家控制模式，再次长按(开炮)退出控制。只要参数设置合理，就能驾驭任何单位。<br>

优先级：玩家控制\>打范围内敌人\>打范围内核心\>打范围内炮塔\>pathfind<br>
可控参数：`$聚集半径`、`$援军半径`、`$始终开炮`、`$timeout`、`UnitBind`<br>
关于`$聚集半径`，我没有选择自动检测单位攻击范围，例如Arkyid的的范围肯定不止5格，但它发射的激光才是它最强的武器，而激光的范围只有大约8格，且闪电球对空中目标没有伤害。经过多次实验，我将其设置为5格。<br>

**没有调用冲突检测！**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/arkyid.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/arkyid.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/arkyid.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/arkyid.jpg)

</details>

#### 坐标移动
(20210813)<br>
控制一种单位按记录的坐标顺序移动。左开关开，控制"电弧"开炮来记录坐标；右开关开，则使设定的单位(雷霆)按坐标顺序移动。当左开关关闭，坐标记录会清空；当左开关关闭，右开关开启，会同时恢复单位flag为0。由于内存上限，最多记录32个点。<br>
`$判定半径`是指单位位于记录点的该半径内时，跳转到下一点。该值能在单位较多的时候降低延迟。比如24台轰炸机集体出动，则设置为30以上效果较好。<br>
请注意，如果你记录了无法达到的坐标，单位会卡住。<br>
右侧处理器可控参数：`UnitBind`、`$判定半径`<br>

**没有调用冲突检测！**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/movepoint.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/movepoint.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/movepoint.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/movepoint.jpg)

</details>

#### T3&T4空攻控制
通过"电弧"操控T3&T4红飞机单位前往指定坐标攻击。若玩家不控制，则自动锁定并攻击附近敌人。锁定后可远程追踪，需要手动操作才能切换锁定对象。<br>

**没有调用冲突检测！**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/airctrl.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/airctrl.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/airctrl.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/airctrl.jpg)

</details>

#### 钍炸弹
利用爆炸的钍堆消灭周围的一切。自动调用星辉或独影装填钍，钍堆生命值低于500自动引爆，可手动引爆。<br>
按钮的功能：左侧按钮解除热量限制，即引爆；右侧按钮选择调用星辉或独影，默认为星辉。<br>

**仅调用闲置的单位，调用的单位会被赋予随机flag值以供其余处理器区分，结束后恢复flag值为0。当心你的支援单位被误伤！**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/autoboom.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/autoboom.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/autoboom.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/autoboom.jpg)

</details>

#### 核弹投放
让雷霆带上钍堆，并在生命值低于1000时投放。<br>
此逻辑的行为：当钍堆过热时将其禁用，并让一个可用的雷霆单位(health\>1500)带上它并重构钍堆。当检测到雷霆单位生命值低于1000时并未处于己方核心半径50以内时，使其投放携带的任意荷载(钍堆)，不论何地。<br>
总之，这个逻辑十分危险，不要轻易使用它。自带的开关可以停用其所有功能。<br>
**仅调用符合要求的、闲置的雷霆单位。如果构建钍堆的雷霆单位不存在，则调用一个幻型构建。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/thpush.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/thpush.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/thpush.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/thpush.jpg)

</details>

#### 污水石墨幽灵
放在污水里才能正常工作。<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/dirtywater.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/dirtywater.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/dirtywater.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/dirtywater.jpg)


</details>

### 生产
这些蓝图与生产物资、后勤有关。

#### Mega自动采矿+攻击闪避
(20210910)<br>
调用巨像自动开采核心内最少的物品(铜铅钛)同时保留自动修复，可手动选择开采物，扣血量超过10自动寻找维修点。优先攻击敌人，并反复横跳躲避攻击。本逻辑兼容所有可飞行的矿机，自行更改`UnitBind`即可(对于开采等级低的单位会出问题，可以通过分类器强制指定开采矿物)。由于技术原因自动修复功能仅对巨像单位开放。<br>

**仅调用闲置的0flag单位。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/megaplus.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/megaplus.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/megaplus.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/megaplus.jpg)

</details>

#### 单位修复模板
此逻辑调用一个单位修复受损结构，兼容所有能飞的单位。默认调用幻型单位。<br>
有时候我们可能造不了mega单位，这也许会有一定帮助。<br>

**仅调用未被处理器控制的单位。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/repairuni.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/repairuni.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/repairuni.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/repairuni.jpg)

</details>

#### 幻型修复经典版
调用一个幻型单位绕处理器旋转并修复受损结构。<br>
时代的眼泪，纪念104。<br>

**仅调用未被处理器控制的单位。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/polyc.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/polyc.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/polyc.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/polyc.jpg)

</details>

#### 仓库搬运
显示物品统计并当仓库单物品容量仅剩50时控制独影将物品搬运到核心。需要手动链接仓库(一对一)，并在代码内设置仓库名称。<br>

**调用单位可自行修改，仅调用闲置的单位，调用的单位会被赋予同一随机flag值以供其余处理器区分。由于技术原因flag值不会恢复，但不影响本逻辑的运行。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/itemtrans.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/itemtrans.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/itemtrans.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/itemtrans.jpg)

</details>

#### 仓库转移
v1.2(20210814)<br>
[视频介绍](https://www.bilibili.com/video/BV13v411K76c)<br>
自动选择Mega/Quad并调用其转移容器或仓库，至少需要两个同类单位才能运行。<br>
用法：分为装载点与卸载点，需要进入逻辑内设置"单位配对码"以关联两个站点。左开关开即将此站点设为装载点，关闭则将此站点设为卸载点。中间为总开关。右侧选择器可选择检测物，默认为null(检测物品总和)。信息板可以看到已设置的参数。<br>
行为：当装载点的检测物数量检测值达到设置的最大容量(null为单容量上限\*种类，若选择了检测物则按单容量上限计算)时，调用一个空单位将仓库拾起，将此单位flag标记为设定的单位配对码。装载点缺少仓库(容器)时，调用一个flag值为"单位配对码相反数"的单位放置一个新的仓库；当卸载点仓库内检测物数量检测值低至设定的最小值，调用一个空单位将仓库(容器)拾起并标记其flag值为"单位配对码相反数"。卸载点缺少仓库时，调用对应flag为配对码的单位放置仓库，随后该单位flag恢复为0。自动将payloadcount为0的单位flag设置为0。为提升速度，用于兼容其它逻辑的调用冲突检测已移除，请避免使用其它逻辑时与本逻辑调用的单位类型相同。<br>

Notice: 距离匹配造成匹配效率降低，现默认关闭。要启用，请更改`$跳过距离匹配`的布尔值。<br>

处理器内允许自定义的值: `$坐标误差`、`$仓库`、`$物品最大值`、`$物品最小值`、`$单位配对码`、`$搜索半径倍数`、`$跳过距离匹配`<br>

**没有调用冲突检测！调用单位可自行修改，仅调用符合条件的单位，调用中的单位会被赋予唯一flag值以供其余处理器区分。请注意单位的payload容量。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/paytrans.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/paytrans.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/paytrans.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/paytrans.jpg)


</details>

#### T2神风核心
(20210813)<br>
集成了[坐标移动](#坐标移动)、[单位带货](#单位带货)、[幻型修复经典版](#幻型修复经典版)。自动控制幻型的生产，默认生产2个，可调。<br>
左下处理器可自定义的值：`$幻型数量`<br>
**由于集成了多个逻辑，请去各逻辑描述处查看注意事项。**<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/coreunit.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/coreunit.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/coreunit.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/coreunit.jpg)

</details>

#### 废料大超速
可能需要一些时间才能稳定运行，可以放入相织物使其稳定。<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/fwbooster.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/fwbooster.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/fwbooster.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/fwbooster.jpg)

</details>

#### 智能力墙
人手一个的智能力墙。<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/sforce.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/sforce.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/sforce.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/sforce.jpg)

</details>

#### 五连冷冻液
下方进料，自带一个罐体。<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/x5fluid.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/x5fluid.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/x5fluid.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/x5fluid.jpg)

</details>

### 杂项
这里可能是一些工具，或者一些娱乐向蓝图。

#### 全局监视器
v1.5(20211009)<br>
显示屏显示：单位个数(0\~99)、净发电量(0K\~99K)、能量I/O记录和核心物品统计(需要生产任意一种单位)。信息板额定显示范围：单位个数(0\~999)；核心物品(0\~999K)。这可能是我技术力的极限了，转载请保留内置信息板以便用户获取后续更新。<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/monitorplus.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/monitorplus.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/monitorplus.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/monitorplus.jpg)

</details>

#### 分析器
名字叫分析器但它并不能自己分析，它在屏幕上绘制荷载内的物品与液体变化曲线，所以你可以根据这些曲线知道你要做什么。<br>
需要手动链接荷载后在逻辑编辑中将荷载关联到变量。使用分类器选择要检测的物品，使用开关切换要检测的液体，一次只能检测一种物品和液体。<br>
为避免混乱，效率与进程曲线不会被绘制，进程进度被绘制为横向移动的紫色进度条。<br>
处理器内可自定义的值：`$检测荷载`、`$x轴增量`、`$速率更新间隔`<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/monitor.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/monitor.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/monitor.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/monitor.png)

</details>

#### 简易单位血量测试器
(20210903)<br>
使用冰雹炮的雷达搜索一个单位，测算其血量变化速率，将相关结果打印到信息板。<br>
处理器内可自定义的项：`$血量检测秒`、`$连续搜索`、`Rader`<br>
获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/unithealthtester.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/unithealthtester.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/unithealthtester.txt)

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/unithealthtester.jpg)

</details>

#### 建造指挥台
v1.2(20211010)<br>
[视频介绍](https://www.bilibili.com/video/BV1M341127hd)<br>
战役跳科技神器，通过控制电弧调用`@nova`建造指定的建筑。点击显示器两侧切换方块，选好方块后，打开开关，电弧指哪儿建哪儿，拖拽转向；关闭开关，可取样并复制方块。点击墙壁可快速进入取样模式，再次点击墙壁退出取样模式。<br>
举个例子，我有硅钛了，但是没有解锁玻璃，所以不能建造这玩意儿的显示器。<br>
我将`$setblock`设置为`@kiln`来建造窑炉，于是就能解锁玻璃、塑钢等。顺便能补上这玩意儿的显示器。<br>

可自定义参数：`$setblock`、`$转向滑动长度`、`$转向判定时间`<br>

仅调用未被控制的单位。<br>

获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/buildhelper_plus.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/buildhelper_plus.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/buildhelper_plus.txt)<br>

<details><summary>展开图片</summary>

![预览](https://hexrotor.github.io/Mindustry-Myblueprint/images/schematics/buildhelper_plus.jpg)

</details>

#### 满物禁用器
如果选择的物品在核心中已满，则禁用连接到的荷载。需要存在任意可被绑定的单位。<br>

获取：
[CDN](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/disableifhomefull.txt)
[PAGE](https://hexrotor.github.io/Mindustry-Myblueprint/base64text/disableifhomefull.txt)
[RAW](https://raw.githubusercontent.com/Hexrotor/Mindustry-Myblueprint/main/base64text/disableifhomefull.txt)<br>

就一个微核，不放图了。

#### Demos
演示系列<br>
此系列多为我对逻辑玩法的探索或对实现一些功能的尝试。<br>
名字乱写的，逻辑乱写的。没有预览图，这不重要。<br>

<details><summary>展开所有</summary>

1.aidemo<br>
使一种单位满地图乱跑并攻击敌人，直到接近敌人出生点后停下。<br>
原理是检测前方地形是否能通过，若遇到墙则进行一组运算来面向一定夹角范围内的随机方向继续前进。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/aidemo.txt)<br>
2.pdemo<br>
按顺序数数并打印到信息板。这是对非IO式数据保存方式的一种猜测。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/pdemo.txt)<br>
3.vdemo<br>
像传统的波形监视器一样显示仓库内铜数量的变化，是将"pdemo"工作方式应用到显示面板的产物。是模仿别人的但是没模仿像，用了很多代码，比别人的延迟高很多。到现在我也不知道这个效果该怎么做。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/vdemo.txt)<br>
4.random<br>
在显示屏上随机显示很多有色点，最后铺满。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/random.txt)<br>
5.autobuild/multibuild<br>
通过电弧控制一个或所有poly修建一组纯电攻守结构。半成品，思路不清晰，写得非常乱，效果不太好。是模仿别人做的。<br>
autobuild只控制一个poly，multibuild控制所有poly。<br>
个人感想：原来建造中的建筑类型是`build&size`；使用随机参数圆的效果不如直接随机坐标，推测是因为圆心角在随机值中能生成的有效份有很大局限性，微小的圆心角变化也会在大半径圆的圆弧上造成很大的差异，这可能使得用这种方式找到空闲区域放置荷载的效率不佳。<br>
[获取autobuild](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/autobuild.txt)<br>
[获取multibuild](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/multibuild.txt)<br>
6.buildhelper<br>
调用一个poly在处理器上方构造一个荷载。需要自行设置荷载类型、荷载边长、荷载方向。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/buildhelper.txt)<br>
7.sensor<br>
本人调试逻辑构造用的工具，传感与之链接的建筑的坐标等数据并打印到信息板，会调用所有poly。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/sensor.txt)<br>
8.unindex<br>
依赖Lookup指令，依次列出荷载方块，打印图像、名称和ID。理论上通用。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/unindex.txt)<br>
9.autorepair<br>
尝试用一种简单的逻辑让受损的poly和mega自动前往维修点。如果没有维修点，会停在核心。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/autorepair.txt)<br>
10.arctrl<br>
像摇杆一样控制一种单位移动并射击。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/yg.txt)<br>
11.birdgame<br>
控制小飞机跳跃并避开障碍物。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/birdgame.txt)<br>
12.disableifpowerfull<br>
当连接到的荷载所在电网耗电量低于发电量时，将其禁用。我将其用于自动启动备用电源。稍加改动代码可以实现反向工作。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/disifpowerfull.txt)<br>
13.memreader<br>
读取内存。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/memreader.txt)<br>
14.g<br>
模拟单摆。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/g.txt)<br>
15.anysensor<br>
sensor\&print<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/anysensor.txt)<br>
16.stackunit<br>
叠放灾星。<br>
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/stackunit.txt)<br>

</details>

## TODO
一些想法，未来可能会实施。<br>

### ~~数据统计~~
最初构想：依赖`lookup`。从数字t开始lookup unit类型保存为`unitresult` ，然后进入`unitresult`的数量检测程序，将值存在内存t位。另一个处理器依次读取内存位，并`lookup`内存位表示的unit，直接循环就能打印出来。<br>
20210816<br>
计数部分制作完成，现正着手构建图像部分。目前在规划位置以计算坐标，以及构建数字显示模块。由于我从未研究过数字显示，这可能需要花一点时间。<br>
[获取计数模块](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/basic.txt)<br>
20210817<br>
制作完成。<br>
[全局监视器](#全局监视器)<br>

### ~~建造指挥台~~
最初构想：用显示器和逻辑仿制一个游戏右下角的建造选项卡，使用电弧实现触屏，支持滑动等操作。选择物品后，显示需要的资源数，电弧指哪儿建哪儿。<br>
20210917<br>
相关逻辑已由大猫制作完成，本人比较懒也比较菜，故只做了一个低配版。<br>
[建造指挥台](#建造指挥台)<br>

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
</details>

# 其他分享
一些非我原创的蓝图。<br>
点击查看：[SHARE.md](/SHARE.md)

一些自制测试地图。<br>
点击查看：[MAPS.md](/MAPS.md)

一些装饰品。<br>
点击查看：[ART.md](ART.md)

# Mindustry-Myblueprint
萌新个人制作蓝图和逻辑，仅适用于战役。未照搬他人作品，如有雷同纯属雷同，欢迎体验！<br>
要快速查找蓝图，请点击上方"README.md"左侧的<svg aria-hidden="true" viewBox="0 0 16 16" version="1.1" data-view-component="true" height="16" width="16" class="octicon octicon-list-unordered"><path fill-rule="evenodd" d="M2 4a1 1 0 100-2 1 1 0 000 2zm3.75-1.5a.75.75 0 000 1.5h8.5a.75.75 0 000-1.5h-8.5zm0 5a.75.75 0 000 1.5h8.5a.75.75 0 000-1.5h-8.5zm0 5a.75.75 0 000 1.5h8.5a.75.75 0 000-1.5h-8.5zM3 8a1 1 0 11-2 0 1 1 0 012 0zm-1 6a1 1 0 100-2 1 1 0 000 2z"></path></svg>，或按<kbd>Ctrl</kbd>+<kbd>F</kbd>搜索页内关键词。<br>
**注意，我的游戏版本为<code>127.1</code>**<br>

### 雷霆敢死队1.2
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/boom1.2.txt)<br>
<details><summary>展开描述</summary>
控制雷霆自动从核心拿爆混后轰炸敌方炮塔或核心，并在低于一定生命值时自动返回核心。自动携带地面单位(最多4个，但跟随模式不受限制)，自动攻击地面敌人。附近有敌人(包括空军)自动释放单位，低生命值返回核心时自动释放单位，关闭携带开关时释放所有单位。单位携带数、最低生命值、携带物、轰炸对象可自定义。<br>
注意：由于代码过多，单位过多时某些功能可能效果不佳；单位携带功能不一定实用，请酌情使用；判断可携带单位使用了血量比对(仅携带900及以下，但跟随模式不受限制)，所以您如果安装了某些模组，这可能会引发问题。<br>

行为优先级：取携带物>跟随玩家=自爆=释放单位>攻击核心>低血量返回>攻击敌人>携带单位>攻击炮塔<br>

按钮的功能：<br>
* 左下为总开关，开启后从核心拿爆混后自动轰炸敌方炮塔，并在低于一定生命值时返回。若低于设定的自爆生命值，则会冲向敌方炮塔直到爆炸。<br>
* 左上为轰炸核心开关，开启后会直接拿爆混冲向敌方核心，不会返回。此开关比右上玩家操控开关优先级低，但此开关开启时影响玩家操控模式时的低血量返回程序，即低血量不会返回。<br>
* 右上为跟随玩家开关，开启后会覆盖轰炸核心的命令，优先跟随玩家。此开关开启时，玩家可以通过操控"电弧"来控制单位移动，玩家可带2~3个雷霆绕到敌方核心，并在接近时关闭并切换到轰炸核心命令。<br>
* 顶部为单位携带开关，开启后自动携带附近陆军，关闭后释放所有单位。<br>
* 分类器可以选择携带物，默认为爆混。<br>

**没有调用冲突检测！**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/boom1.2.jpg)

</details>

### 煤站改
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/coal2.txt)<br>
<details><summary>展开描述</summary>
修改后的煤站，装弹效率有点低，但增加了库存。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/coal2.png)

</details>

### 陆辅T1~T4自动跟随玩家
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/followplayer.txt)<br>
<details><summary>展开描述</summary>
通过"电弧"操控单位前往指定坐标攻击或跟随玩家攻击。玩家未控制时自动攻击敌人，但不会攻击敌方建筑。注意不要进入石油、深水区域。<br>

**没有调用冲突检测！**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/followplayer.jpg)
  
</details>

### Arkyid集群攻击
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/arkyid.txt)<br>
<details><summary>展开描述</summary>
自动pathfind并集群攻击敌人，带远程追踪（不能避障）。通过操控"电弧"可控制单位：长按任意区域进入玩家控制模式，再次长按退出控制。经实测BOSS进入激光攻击范围后活不过10s。<br>
  
**没有调用冲突检测！**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/arkyid.jpg)

</details>

### T3&T4红飞机控制
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/airctrl.txt)<br>
<details><summary>展开描述</summary>
通过"电弧"操控T3&T4红飞机单位前往指定坐标攻击。若玩家不控制，则自动锁定并攻击附近敌人。锁定后可远程追踪，需要手动操作才能切换锁定对象。<br>

**没有调用冲突检测！**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/airctrl.jpg)

</details>

### Mega自动采矿+攻击闪避
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/megaplus.txt)<br>
<details><summary>展开描述</summary>
调用巨像自动开采核心内最少的物品(铜铅煤钛)同时保留自动修复，可手动选择开采物，扣血量超过10自动返回基地。优先攻击敌人，并反复横跳躲避攻击。本逻辑兼容所有"boostable"的矿机，自行更改unit bind即可(对于开采等级低的单位会出问题，可以通过分类器强制指定开采矿物)。由于技术原因自动修复功能仅对巨像单位开放。<br>

**仅调用闲置的0flag单位。众所周知煤是易燃物，进入核心有风险，故推荐使用分类器指定开采物。**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/megaplus.jpg)

</details>

### 钍炸弹
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/autoboom.txt)<br>
<details><summary>展开描述</summary>
利用爆炸的钍堆消灭周围的一切。自动调用星辉或独影装填钍，钍堆生命值低于500自动引爆，可手动引爆。<br>
按钮的功能：左侧按钮解除热量限制，即引爆；右侧按钮选择调用星辉或独影，默认为星辉。<br>

**仅调用闲置的单位，调用的单位会被赋予随机flag值以供其余处理器区分，结束后恢复flag值为0。当心您的支援单位被误伤！**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/autoboom.jpg)

</details>

### 仓库搬运
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/itemtrans.txt)<br>
<details><summary>展开描述</summary>
显示物品统计并当仓库单物品容量仅剩50时控制独影将物品搬运到核心。需要手动链接仓库(一对一)，并在代码内设置仓库名称。<br>

**调用单位可自行修改，仅调用闲置的单位，调用的单位会被赋予同一随机flag值以供其余处理器区分。由于技术原因flag值不会恢复，但不影响本逻辑的运行。**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/itemtrans.jpg)

</details>

### 仓库转移
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/paytrans.txt)<br>
<details><summary>展开描述</summary>
自动选择Mega/Quad并调用其转移仓库或容器，至少需要两个同类单位才能运行。<br>
用法：分为装载点与卸载点，需要进入逻辑内设置"单位配对码"以关联两个站点。左开关开即将此站点设为装载点，关闭则将此站点设为卸载点。中间为总开关。右侧选择器可选择检测物，默认为null(检测物品总和)。信息板可以看到已设置的参数。<br>
行为：当装载点的检测物数量检测值达到设置的最大容量(null为单容量上限\*种类，若选择了检测物则按单容量上限计算)时，调用一个空单位将仓库拾起，将此单位flag标记为设定的单位配对码。装载点缺少仓库(容器)时，调用一个flag为3(2)的单位放置一个新的仓库；当卸载点仓库内检测物数量检测值低至设定的最小值，调用一个空单位将仓库(容器)拾起并标记其flag为3(2)。卸载点缺少仓库时，调用对应flag为配对码的单位放置仓库，随后该单位flag恢复为0。自动将payloadcount为0的单位flag设置为0。为提升速度，用于兼容其它逻辑的调用冲突检测已移除，请避免使用其它逻辑时与本逻辑调用的单位类型相同。

**没有调用冲突检测！调用单位可自行修改，仅调用符合条件的单位，调用中的单位会被赋予唯一flag值以供其余处理器区分。请注意单位的payload容量。**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/paytrans.jpg)

</details>

### 石油站
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/petroleum.txt)<br>
<details><summary>展开描述</summary>
需要外部供应石油(供应点在左下)，可以在有石油的状态下自启动，非常强大。和煤站一样，容易火灾。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/petroleum.png)

</details>

### 水站
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/water.txt)<br>
<details><summary>展开描述</summary>
需要大面积的水，局限性很大。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/water.png)

</details>

### 水站PLUS
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/waterplus.txt)<br>
<details><summary>展开描述</summary>
需要小面积水，大面积空地。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/waterplus.png)

</details>

### 钍站
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tu.txt)
[PLUS获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tuplus.txt)<br>
<details><summary>展开描述</summary>
需要放入钍来启动(也可自启动)，启动过程会轻微负电。做成一体式是为了好看，实际操作还是按地形部署比较简便。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/tu.png)
![PLUS预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/tuplus.png)

</details>

### 废料冲击
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/reactor.txt)<br>
<details><summary>展开描述</summary>
可能需要绿带才能带动，稳定后发电量7.7k左右。带安全启动与低血自停。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/reactor.png)

</details>

### 废料大超速
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/fwbooster.txt)<br>
<details><summary>展开描述</summary>
可能需要一些时间才能稳定运行，可以放入相位物使其稳定。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/fwbooster.jpg)

</details>

### 原地出硅
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/si.txt)<br>
<details><summary>展开描述</summary>
调用单位挖材料并生产硅放入仓库，没啥用，有时也许有奇效。可配合其他逻辑使用，比如仓库搬运。<br>
  
**调用策略同"Mega自动挖矿"逻辑，单位默认为耀星。**<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/si.jpg)

</details>

### 6温差串联结构
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/tgen.txt)<br>
<details><summary>展开描述</summary>
以6温差为一组的串联结构，需要外部供应冷冻液与硫，净发电量9.4k。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/tgen.jpg)

</details>

### 分析器
[获取](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/base64text/monitor.txt)<br>
<details><summary>展开描述</summary>
名字叫分析器但它并不能自己分析，它在屏幕上绘制荷载内的物品与液体变化曲线，所以你可以根据这些曲线知道你要做什么。<br>
需要手动链接荷载后在逻辑编辑中将荷载关联到变量。使用分类器选择要检测的物品，使用开关切换要检测的液体，一次只能检测一种物品和液体。<br>

![预览](https://cdn.jsdelivr.net/gh/Hexrotor/Mindustry-Myblueprint/images/monitor.png)

</details>

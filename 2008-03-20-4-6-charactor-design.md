---
layout: post
title: 第四章第六节 角色设定
categories:
- Maya
tags:
- charactor
- design
- Maya
- 开始maya吧
- 第四章
published: true
comments: true
---
<p><!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/fourth-charactor-design.html" target="_blank">回节目录选择</a></p>

<p><h4>本节概述</h4>
通常来讲，动画中的角色一般是指人、动物或是其他生物，而Maya中关于角色(Character)的定义非常宽泛，角色(Character)是一个集中动画属性的节点。所以在本节中所提到的角色(Character)，都是节点的概念。这对于理解Maya中的角色设定会很有帮助。因为这个功能可以充分利用动画资源，大大提高制作效率，是团队协作必不可少的重要工具。</p>

<p>本节重点讲解角色的概念以及设定方法。
<h5>理解角色</h5>
<h6>什么是角色(Character)？</h6>
定义</p>

<p><em>角色（Character）是一个节点，它把将要同时设置动画的所有对象的属性集中到一个集合中。</em></p>

<p>角色可以是任何对象：一个人、一辆汽车、甚至可以是任何不相关的一组物体。Maya中角色的定义没有任何限制，完全根据动画的需要。在设置“角色”时是将动画对象的所有相关属性集中在一起，这样在调节动画时只需要选择这一“角色”就可以定义多个物体的多个动画属性的关键帧，而不影响物体的非动画属性。
<h6>角色的功能</h6>
在Maya 中，角色具有这样的能力：一旦创建了角色，就可使用Maya 的动画功能在角色的基础上制作动画。这能使Maya 提供了一种与典型传统动画技术紧密相关的直觉交互操作方式。使用角色，用户还可以使用Maya 的非线形角色动画功能，使用Trax Editor可更为艺术地控制和创建角色动画。在此基础上用户还可创建角色库，收集所有以通用方式设定的角色。</p>

<p>总之，Maya 的角色功能把所有作为动画基础的角色属性集中在一起。通过把这些属性集中在一起，用户可以更容易、更快的为动画创建角色。动画师可使用动画功能作为一个整体来角色，而不必担心使用设置角色的其他技术细节。
<h6>定义角色集(Character Set)</h6>
定义角色集包括创建角色集和编辑角色集。完成了角色集设置就等于完成了角色设置。</p>

<p>角色可以是传统概念上的角色，例如：一个人、一只鸟，也可以是作为一个动画整体的集合，例如：一根双节辊，一个人的五官。</p>

<p>在很多情况下需要为多个对象一起设置动画，可以将这些对象的一些或所有属性集合在一起，将他们定义为一个角色集。将多个对象定义为角色集为动画制作提供了很大的便利，因为可以在同一时间设定多个对象的多个属性，并且可以将某一动画功能作用于角色内的全部属性。</p>

<p>角色集内可以创建子角色集。子角色集允许用户保持角色各个部分之间的层级关系。一个子角色集是角色集的一个子集。例如：可以将一个人物的左臂定义为一个子角色集，在调节左臂的动画时，不影响身体其他部分。
<h5>角色集的创建与编辑</h5>
<h6>创建角色集(Create Character Set)</h6>
1 选择物体，要使用该物体的属性去动画角色。</p>

<p>2 选择Character &gt; Create Character Set 命令。</p>

<p>一个角色被创建，角色的节点（默认名：character<em>n</em>）提供了一组可设置关键帧属性，这些属性来自于所有被选择的物体。所有这些可设置关键帧属性被便利地组织在一个角色集中。用户可能并不需立即访问角色集中的全部属性，从角色集中去除一些不需要的属性可使通道栏的通道列表更短和更加便于管理。
<h6>创建子角色集(Create Subcharacter Set)</h6>
用户可在定义的角色集中创建子角色集。当用户创建子角色集时，Maya 就会把子角色集添加到当前角色集中。这个非常有用的功能可以帮助用户分离角色集的层次。</p>

<p>创建子角色集类似于角色集的创建：在当前角色集中选择用户想要定义子角色集的物体（比如，组成角色脸部的物体）并选择Character &gt; Create Subcharacter Set命令。子角色集的创建选项同角色集的创建选项一样。
<h6>编辑角色集</h6>
<h6>选择角色集</h6>
选择Character &gt; Select Character Set Nodes &gt; charactern，其中charactern 是角色集的默认名。</p>

<p>角色集被选中（注意但角色集中的物体并没被选择）。
<h6>选择角色集中的物体</h6>
选择Character &gt; Select Character Set Members &gt; charactern，其中charactern 是角色的默认名。</p>

<p>此时，角色集中的物体被选中，但角色自身不被选中。
<h6>添加通道(Channels)到角色集</h6>
通道(Channels)是节点(Node)显示在通道栏(Channel Box)中的属性,用户可迅速的为当前的角色集添加任意物体的通道(Channels)。此物体可以不是角色集中的物体。</p>

<p>1 确定用户所添加通道的角色集是当前角色集。</p>

<p>2 选择用户想添加其通道到角色集的物体。</p>

<p>3 在通道栏中，选择用户想要添加到角色的通道。</p>

<p>4 选择Character &gt; Add To Character Set 命令。</p>

<p>Maya 将所选择的通道添加到当前角色集中。
<h6>从角色集中去除通道(Channels)</h6>
通道(Channels)是节点(Node)显示在通道栏(Channel Box)中的属性,用户可以快速的从当前角色集中去除通道。</p>

<p>1 确定用户从中去除的通道的角色集为当前角色集。</p>

<p>2 在通道栏中，选择用户想要从角色集中去除的通道。</p>

<p>3 选择Character &gt; Remove From Character Set 命令。</p>

<p>从当前角色集中去除所选择的通道。
<h6>编辑角色集通道</h6>
1 选择角色。便利地选择方式是从Outliner 列表中选择角色。</p>

<p>2 在通道栏，角色的通道被默认列出。</p>

<p>3 使用鼠标左键单击通道名。</p>

<p>4 在场景中，按住鼠标中键左右移动鼠标。通过移动鼠标，用户可交互地改变被选择通道的值。</p>

<p>编辑角色属性</p>

<p>使用属性编辑器编辑属性：</p>

<p>1 选择角色，在Outliner 列表中可便利地选择角色。（注意用户还可以选择Character &gt;</p>

<p>Attribute Editor 访问属性编辑器）</p>

<p>2 打开属性编辑器选择Windows &gt; Attribute Editor 命令（默认快捷键：Ctrl+A）。注意用户还</p>

<p>可以在Outliner 中在角色图标上双击打开属性编辑器。</p>

<p>3 在属性编辑器中列出了下列属性：Character Set Attributes、Node Behavior 和Extra Attributes。</p>

<p>编辑角色集</p>

<p>编辑角色集包括从组中添加或去除属性。默认设置是角色集包含角色中物体所有可设置关键帧属性。在一般情况下，用户可能仅使用其中的一部分属性，这取决于角色中所包含的物体的数量和复杂程度，在角色集中保持所有的属性将导致通道栏中的通道列表过长。因而，在创建角色后，可以去除角色集中一些属性，当然还可以再将它们添加回角色集。
<h6>在角色集中察看某个物体</h6>
1 选择Window &gt; Relationship Editor &gt; Character Sets 命令，或者如果已经打开了Relationship Editor（关系编辑器），那么选择它的Character Editing 模式选项。编辑器的左栏列出了场景中所有的角色集。</p>

<p>2 选择角色集，使之高亮显示。</p>

<p>3 在Relationship Editor 中，选择Edit &gt; Select Character Set Members 命令。</p>

<p>现在角色中的物体在工作空间中全被选中，这个方法提供了选择和观看这些物体的快速方式。如果仅想检查哪些物体是某个特殊角色集的一部分，那么使用这种方式是非常有用的。
<h6>从角色集中去除属性</h6>
1 选择Window &gt; Relationship Editor &gt; Character Sets 命令，或者如果已经打开了Relationship Editor（关系编辑器），那么选择它的Character Editing 模式选项。编辑器的左栏列出了场景中所有的角色集。</p>

<p>2 选择一个角色集以使之高亮显示。</p>

<p>3 单击被选择角色旁边的+号图标使其列出角色集中所有的属性。</p>

<p>4 选择要从角色集中去除的属性，它们以灰色高亮显示。注意，用户可以使用Shift 键和鼠标左键选择相互临近的项目，按住Ctrl 键和鼠标左键可以选择互不临近的项目。</p>

<p>5 在Relationship Editor 中，从选择Edit &gt; Remove Highlighted from Character Set 命令。那么被选择属性从角色集中去除。</p>

<p>6 如果想返回到工作空间定位或动画角色，在保持角色集仍然被选择的状态下，选择Edit &gt; Select Highlighted 命令。在通道栏中列出了角色集中新属性集合。
<h6>为角色集添加属性</h6>
1 选择Window &gt; Relationship Editor &gt; Character Sets 命令，或者如果打开了Relationship Editor（关系编辑器），那么选择其Character Editing 模式选项。编辑器的左栏（角色集）列出了在场景中的所有角色集；右栏（物体）列出了在场景中的所有物体。</p>

<p>2 在左栏（角色集），选择要添加属性的角色集，使它高亮显示。</p>

<p>3 在右栏（物体），选择其属性要添加到角色集的物体。</p>

<p>4 伸展物体使它的属性被列出（单击物体名称旁的“+”图标）。当前被选择的角色集以灰色高亮显示。并且这些属性的名称以斜体显示。</p>

<p>5 在要添加到角色集中的属性名上单击。被选择属性将被添加到角色集。</p>

<p>6 如果要返回工作空间，并且要定位和动画角色，并且使角色集仍然被选择，那么选择Edit &gt;Select Highlighted 命令。通道栏列出角色集中新的属性集合。
<h6>观看和编辑角色分区</h6>
在系统默认设置下，用户创建的每个角色在系统默认设置的角色分区中有它的角色集。所有的角色集在相同的分区，用户可确认在一个角色集中的属性不会在其它的角色集。为察看默认角色分区，用户可使用Relationship Editor（关系编辑器）。</p>

<p>用户应该避免编辑角色分区，编辑角色集容易出现问题，因为在这样做时，可能在无意中去除多个角色集中的共有属性。</p>

<p>1 如果在打开的Relationship Editor 中编辑角色集，那么把Character Editing 项改为Partition Editing。</p>

<p>2 在Relationship Editor 中，注意角色分区（默认名：character Partition)。为找到在角色分区中的角色，在+号图标上单击。为找到在角色中的所有属性，单击+号图标旁的角色的角图标。
<h6>删除角色集</h6>
1 选择角色集，快捷的选择方式是在Outliner 中选择角色集。</p>

<p>2 选择Edit &gt; Delete 命令（默认快捷键：Backspace 键）。</p>

<p>角色集（角色节点）被删除，但是组成角色集的物体不被删除。</p>

<p>注意如果用户选择了角色集中的所有节点，并且要删除它们，那么角色节点也将被删除。
<h6>使用关系编辑器（Relationship Editor）删除角色集</h6>
当在Character Editing 模式下（Window &gt; Relationship Editors &gt; Character Sets）使用Relationship Editor 时，也可以删除角色。在Relationship Editor 中选择一个角色集，然后选择Edit &gt; Delete Highlighted 命令。注意主菜单中的Edit &gt; Undo 选项也应用于Relationship Editor 中的操作。
<h5>三毛的角色设定</h5>
实例教程
<h6>1 创建三毛的角色集</h6>
为了方便管理与操作，主角色集通常不包含任何物体的任何属性，仅仅作为一个管理子集合的总集合，然后将不同部分的物体属性划分到不同的子集合中。选择主菜单Animation&gt;Character&gt;Create Character Set&gt;Option打开设置窗口，</p>

<p>Name项填入sanmao，</p>

<p>Include项选择All Keyable，</p>

<p>单击Create Character Set按钮完成创建。这时在界面底部的Range Slider右侧的Character Set中“sanmao”为当前角色集，如图4.6.1所示</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347172361/" target="_blank"><img src="http://farm3.static.flickr.com/3064/2347172361_e0ecc551b2.jpg" border="0" alt="image001" /></a></p>

<p>图4.6.1
<h6>2 整理通道栏(Channel Box)</h6>
子角色集是角色集的子集，它是角色的不同部分的一部分或全部属性的集合，加入子角色集的属性通常是从通道栏（Channel Box）中获取的。在创建子角色集时，按照物体或关节设置动画的需要通常只选择通道栏（Channel Box）中一部分属性。为了方便设置子角色集，在创建子角色集之前需要减少通道栏（Channel Box）中的属性项目。</p>

<p>对于骨骼的动画，通常只对其Translate、Rotate属性和手动添加的属性设置动画，其余的属性可以从Channel Box中去掉。例如：选择RightFoot_ctrl，选择主菜单Window&gt;General Editors&gt;Channel Control打开设置窗口，在左侧Keyable窗口中选择scaleX、scaleY、scaleZ后按住ctrl键增加选择visibility，单击Move按钮将所选项移至右侧Non Keyable窗口，如图4.6.2所示</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2348002506/" target="_blank"><img src="http://farm3.static.flickr.com/2022/2348002506_0b1b036a53.jpg" border="0" alt="image003" /></a>图4.6.2</p>

<p>这时的通道栏（Channel Box）中只保存了设置动画时必须的属性，如图4.6.3所示</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2348002178/" target="_blank"><img src="http://farm3.static.flickr.com/3263/2348002178_4ff57b1123.jpg" border="0" alt="image005" /></a>图4.6.3</p>

<p>RightToe_ctrl设置如图4.6.4所示</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347176529/" target="_blank"><img src="http://farm3.static.flickr.com/3174/2347176529_51d6a6bc29.jpg" border="0" alt="image007" /></a>图4.6.4</p>

<p>RightBall_ctrl设置如图4.6.5所示</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2347176399/" target="_blank"><img src="http://farm3.static.flickr.com/2381/2347176399_309893cb0c.jpg" border="0" alt="image009" /></a>图4.6.5</p>

<p>右脚控制关节同左脚控制关节设置即可，在此不再重复。</p>

<p>注意：其余关节的属性可以进行类似的简化，根据设置动画时的需要，仅保留其Translate、Rotate属性和手动添加的属性即可。一个精简的Channel Box会对以后的工作带来很大的方便。</p>

<p>对于IK的属性，RotateX/Y/Z、ScaleX/Y/Z、Visibilty等7个属性在调解动画时是没必要的，可以去掉，剩下的属性是必要的，如图4.6.6所示</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2347176289/" target="_blank"><img src="http://farm3.static.flickr.com/2142/2347176289_e7ea0090dd.jpg" border="0" alt="image011" /></a>图4.6.6</p>

<p>对于Pole Vector约束中用到的Locater的属性，只需保留TranslateX\Y\Z属性即可，如图4.6.7所示</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2348006386/" target="_blank"><img src="http://farm3.static.flickr.com/2409/2348006386_fc23284ec9.jpg" border="0" alt="image013" /></a>图4.6.7
<h6>3 创建三毛的子角色集</h6>
a) 对于三毛这个角色，一共需要创建三个子集合，包括双腿动作部分、上身动作部分、面部表情部分。首先创建双腿子集合，确定在Range Slider右侧的角色集中“sanmao”为当前选项，如果不是则单击“No Character Set”左侧的箭头，从下拉菜单中选择sanmao。</p>

<p>选择RightFoot_ctrl关节，在Channel Box中选择全部属性，如图4.6.8所示</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347176027/" target="_blank"><img src="http://farm3.static.flickr.com/2177/2347176027_7dd63fa628.jpg" border="0" alt="image015" /></a>图4.6.8</p>

<p>选择主菜单Animation&gt;Character&gt;Create Subcharacter Set&gt;Option打开设置窗口，Name项填入“Leg”，Subcharacter Set Attributes项选择“From Channel Box”，单击Create Subcharacter Set按钮完成创建。如图4.6.9所示</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2347175769/" target="_blank"><img src="http://farm3.static.flickr.com/2365/2347175769_38b1141346.jpg" border="0" alt="image017" /></a>图4.6.9</p>

<p>这时在Channel Box的属性值都呈现黄色高亮显示，在Range Slider右侧的角色集中“Leg”为当前选项，如图4.6.10所示</p>

<p><a title="image018" href="http://www.flickr.com/photos/95019520@N00/2347175381/" target="_blank"><img src="http://farm3.static.flickr.com/3128/2347175381_0e72b6f642.jpg" border="0" alt="image018" /></a>图4.6.10</p>

<p>在设置脚部骨骼控制时，使用RightFoot_ctrl作为驱动帧的driver控制右脚的活动，在被动属性中包括RightFoot_ctrl自身的Rotate Z属性，在调试动画过程中Roll作为Leg子角色集的成员被设置关键帧，那么RightFoot_ctrl的Rotate Z就没有必要存在于，选择RightFoot_ctrl，在Channel Box中选择Rotate Z项，选择主菜单Animation&gt;Character&gt;Remove from Character Set将此项从Leg子角色集中去掉。此项转为浅红色高亮显示，如图4.6.11所示</p>

<p><a title="image020" href="http://www.flickr.com/photos/95019520@N00/2348005546/" target="_blank"><img src="http://farm3.static.flickr.com/3024/2348005546_16d8bb1e7d.jpg" border="0" alt="image020" /></a>图4.6.11</p>

<p>按照设置RightFoot_ctrl的步骤，设置LeftFoot_ctrl，将其Channel Box中的属性添加至Leg子角色集，并且排除不需要的Rotate Z项，完成后的Channel Box如图4.6.12所示</p>

<p><a title="image022" href="http://www.flickr.com/photos/95019520@N00/2347175087/" target="_blank"><img src="http://farm3.static.flickr.com/3066/2347175087_9a5cb6830b.jpg" border="0" alt="image022" /></a>图4.6.12</p>

<p>按照相同的步骤，根据调节动画的需要，将双腿中的相关关节与控制部分的属性添加至Leg子角色集，包括膝关节使用Pole Vector时添加的Locator属性。具体项目如下表
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="200" valign="top">LeftFoot_ctrl.tx</td></tr></tbody></table></p>

<p>LeftFoot_ctrl.ty</p>

<p>LeftFoot_ctrl.tz</p>

<p>LeftFoot_ctrl.rx</p>

<p>LeftFoot_ctrl.ry</p>

<p>LeftFoot_ctrl.roll
<td width="200" valign="top">RightFoot_ctrl.tx</td></p>

<p>RightFoot_ctrl.ty</p>

<p>RightFoot_ctrl.tz</p>

<p>RightFoot_ctrl.rx</p>

<p>RightFoot_ctrl.ry</p>

<p>RightFoot_ctrl.roll

<tr>
<td width="200" valign="top">Locator_Left.tx</td></tr></p>

<p>Locator_Left.ty</p>

<p>Locator_Left.tz
<td width="200" valign="top">Locator_Right.tx</td></p>

<p>Locator_Right.ty</p>

<p>Locator_Right.tz



b) 包括上身部分的子角色集可以定义为body，这个子角色集包括上身躯干部分和上肢部分。例如：由RightShoulder关节开始，首先将Range Slider右侧的Character Set中“sanmao”设为当前角色集，这时创建的子角色集是从属于“sanmao” 角色集，而不是从属于其他的角色集，如图4.6.13所示</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347172361/" target="_blank"><img src="http://farm3.static.flickr.com/3064/2347172361_e0ecc551b2.jpg" border="0" alt="image001" /></a></p>

<p>图4.6.13</p>

<p>选择RightShoulder关节，在Channel Box中选择全部属性，如图4.6.14所示</p>

<p><a title="image024" href="http://www.flickr.com/photos/95019520@N00/2348005292/" target="_blank"><img src="http://farm3.static.flickr.com/2300/2348005292_711ccc1a1e.jpg" border="0" alt="image024" /></a>图4.6.14</p>

<p>选择主菜单Animation&gt;Character&gt;Create Subcharacter Set&gt;Option打开设置窗口，Name项填入“Body”、Subcharacter Set Attributes项选择From Channel Box，单击Create Subcharacter Set按钮完成创建。如图4.6.15所示</p>

<p><a title="image026" href="http://www.flickr.com/photos/95019520@N00/2348005132/" target="_blank"><img src="http://farm3.static.flickr.com/2412/2348005132_9cfdb8f78f.jpg" border="0" alt="image026" /></a>图4.6.15</p>

<p>这时在Channel Box的属性值都呈现黄色高亮显示，在Range Slider右侧的角色集中出现“Body”选项，如图4.6.16所示</p>

<p><a title="image028" href="http://www.flickr.com/photos/95019520@N00/2347174503/" target="_blank"><img src="http://farm3.static.flickr.com/2365/2347174503_05c963582b.jpg" border="0" alt="image028" /></a>图4.6.16</p>

<p>保持角色集选择框内是“Body”选项，继续添加其余的关节属性，包括肘关节使用Pole Vector时添加的Locator属性。十指各关节被驱动帧控制的部分可以忽略。具体项目如下表
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="133" valign="top">CenterHead1.rx</td></tr></tbody></table></p>

<p>CenterHead1.ry</p>

<p>Centerhead1.rz
<td width="133" valign="top">RightShoulder.rx</td></p>

<p>RightShoulder.ry</p>

<p>RightShoulder.rz
<td width="133" valign="top">LeftShoulder.rx</td></p>

<p>LeftShoulder.ry</p>

<p>LeftShoulder.rz

<tr>
<td width="133" valign="top">CenterNeck.rx</td></tr></p>

<p>CenterNeck.ry</p>

<p>CenterNeck.rz
<td width="133" valign="top">RightElbow.rx</td></p>

<p>RightElbow.ry</p>

<p>RightElbow.rz
<td width="133" valign="top">LeftElbow.rx</td></p>

<p>LeftElbow.ry</p>

<p>LeftElbow.rz

<tr>
<td width="133" valign="top">cluster2Handle.tx</td></tr></p>

<p>cluster2Handle.ty</p>

<p>cluster2Handle.tz
<td width="133" valign="top">RightHand.rx</td></p>

<p>RightHand.ry</p>

<p>RightHand.rz
<td width="133" valign="top">LeftHand.rx</td></p>

<p>LeftHand.ry</p>

<p>LeftHand.rz

<tr>
<td width="133" valign="top">Cluster3Handle.tx</td></tr></p>

<p>Cluster3Handle.ty</p>

<p>Cluster3Handle.tz
<td width="133" valign="top">IkHandle_Righthand.tx</td></p>

<p>IkHandle_Righthand.ty</p>

<p>IkHandle_Righthand.tz
<td width="133" valign="top">ikHandle_Lefthand.tx</td></p>

<p>ikHandle_Lefthand.ty</p>

<p>ikHandle_Lefthand.tz

<tr>
<td width="133" valign="top">Cluster4Handle.tx</td></tr></p>

<p>Cluster4Handle.ty</p>

<p>Cluster4Handle.tz
<td width="133" valign="top">locator_Righthand.tx</td></p>

<p>locator_Righthand.ty</p>

<p>locator_Righthand.tz
<td width="133" valign="top">locator_Lefthand.tx</td></p>

<p>locator_Lefthand.ty</p>

<p>locator_lefthand.tz

<tr>
<td width="133" valign="top">IkHandle_Body.twi</td>
<td width="133" valign="top">IkHandle_Righthand.ikb</td>
<td width="133" valign="top">ikHand_Lefthand.ikb</td>
</tr>
<tr>
<td width="133" valign="top"></td>
<td width="133" valign="top">RightFinger.grasp</td>
<td width="133" valign="top">LeftFinger.grasp</td>
</tr>


c) 将面部表情的动画部分定义为Face子角色集，这个子角色集包括控制面部表情的各种控制器的相关属性。</p>

<p>选择locator_face，在Channel Box中选择全部属性，这里包括了Face子角色集的全部内容，如图4.6.17所示</p>

<p><a title="image030" href="http://www.flickr.com/photos/95019520@N00/2347174407/" target="_blank"><img src="http://farm3.static.flickr.com/3026/2347174407_565cb6dbe7.jpg" border="0" alt="image030" /></a>图4.6.17</p>

<p>将Range Slider右侧的角色集指定为“sanmao”，如图4.6.18所示</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347172361/" target="_blank"><img src="http://farm3.static.flickr.com/3064/2347172361_e0ecc551b2.jpg" border="0" alt="image001" /></a>图4.6.18</p>

<p>选择主菜单Animation&gt;Character&gt;Create Subcharacter Set&gt;Option打开设置窗口，Name项填入face、Subcharacter Set Attributes项选择From Channel Box，单击Create Subcharacter Set按钮完成创建。如图4.6.19所示</p>

<p><a title="image032" href="http://www.flickr.com/photos/95019520@N00/2348004540/" target="_blank"><img src="http://farm3.static.flickr.com/3191/2348004540_2f1cc1a6e6.jpg" border="0" alt="image032" /></a>图4.6.19</p>

<p>这时在Channel Box的属性值都呈现黄色高亮显示，在Range Slider右侧的角色集中出现“Face”选项，如图4.6.20所示</p>

<p><a title="image034" href="http://www.flickr.com/photos/95019520@N00/2347174037/" target="_blank"><img src="http://farm3.static.flickr.com/3148/2347174037_f6c264d164.jpg" border="0" alt="image034" /></a>图4.6.20</p>

<p>三毛的角色集创建完毕，单击Character显示框左侧的箭头，从下拉菜单中选择Character Sets…打开Relationship Editor窗口，在这里可以清楚地看到所有角色集与子角色集的情况，如图4.6.21所示</p>

<p><a title="image036" href="http://www.flickr.com/photos/95019520@N00/2347173879/" target="_blank"><img src="http://farm3.static.flickr.com/3287/2347173879_c3e7441127.jpg" border="0" alt="image036" /></a>图4.6.21
<h5>本节工具解析</h5>
<h6>Create Character Set</h6>
创建角色集。</p>

<p>Animation&gt;Character&gt;Create Character Set&gt;Option 如图4.6.22所示</p>

<p><a title="image038" href="http://www.flickr.com/photos/95019520@N00/2347173457/" target="_blank"><img src="http://farm3.static.flickr.com/2320/2347173457_e669017fa4.jpg" border="0" alt="image038" /></a>图4.6.22</p>

<p><strong>·Name:</strong>新建角色集名称<strong> </strong></p>

<p><strong>·Include(Hierarchy Below Selected Node)</strong>：勾选此项时，当前选择物体连同其层级以下的物体一同进入角色集。</p>

<p><strong>·Include:</strong>进入新建角色集的属性来源</p>

<p><strong>All Keyable: </strong>所有可设置关键帧的属性</p>

<p><strong>From Channel Box</strong><strong>：</strong>在Channel Box中选择的属性</p>

<p><strong>All Keyable Except</strong><strong>：</strong>排除下列选项的全部可设置关键帧的属性</p>

<p><strong>·Redirect Character：</strong>勾选时新建角色可重定向</p>

<p>Rotation and Translation: 旋转与位移属性</p>

<p>Rotation Only: 仅旋转属性</p>

<p>Translation Only: 仅位移属性
<h6>Create SubCharacter Set</h6>
创建子角色集。</p>

<p>Animation&gt;Character&gt;Create SubCharacter Set&gt;Option 如图4.6.23所示</p>

<p><a title="image040" href="http://www.flickr.com/photos/95019520@N00/2347173103/" target="_blank"><img src="http://farm3.static.flickr.com/3146/2347173103_f34d0c8495.jpg" border="0" alt="image040" /></a>图4.6.23</p>

<p><strong>·Name:</strong>新建子角色集名称</p>

<p><strong>·Subcharacter Set Attributes:</strong> 进入新建子角色集的属性来源</p>

<p><strong>All Keyable: </strong>所有可设置关键帧的属性</p>

<p><strong>From Channel Box</strong><strong>：</strong>在Channel Box中选择的属性</p>

<p><strong>All Keyable Except</strong><strong>：</strong>排除下列选项的全部可设置关键帧的属性
<h6>Channel Control</h6>
打开通道控制窗口。</p>

<p>Window&gt;General Editors&gt;Channel Control 如图4.6.24所示</p>

<p><a title="image042" href="http://www.flickr.com/photos/95019520@N00/2348003152/" target="_blank"><img src="http://farm3.static.flickr.com/3070/2348003152_70c0f13606.jpg" border="0" alt="image042" /></a> 图4.6.24</p>

<p><strong>·Keyable:</strong>当前Channel Box中显示的属性</p>

<p><strong>·Non Keyable:</strong>当前Channel Box未显示的属性</p>

<p><strong>·Change all selected objects of the same type:</strong>
<h6>Redirect</h6>
重新定向。</p>

<p>Animation&gt;Character&gt;Redirect&gt;Option 如图4.6.25所示</p>

<p><a title="image044" href="http://www.flickr.com/photos/95019520@N00/2348002770/" target="_blank"><img src="http://farm3.static.flickr.com/3121/2348002770_5e5031b17b.jpg" border="0" alt="image044" /></a>图4.6.25</p>

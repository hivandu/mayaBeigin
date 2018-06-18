---
layout: post
title: 第四章第二节 骨骼的创建
categories:
- Maya
tags:
- create
- Maya
- skeleton
- 开始maya吧
- 第四章
published: true
comments: true
---
<p> <!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/fourth-charactor-design.html" target="_blank">回节目录选择</a>
<h5>本节概述</h5>
骨骼是角色动画的基础，在本节中着重介绍创建骨骼系统的方法、骨骼系统的层级模式以及骨骼的命名方式。合理地创建骨骼才能让角色正常地运动，所以在创建骨骼时除了要求掌握软件的操作的同时，还要理解角色的身体结构。
<h5>了解骨骼</h5>
<h6>什么是骨骼(Skeleton)？</h6>
定义</p>

<p><em>骨骼是有层次的关节结构，可定位和动画可变形物体。建立骨骼是使用关节和骨头建造层次关联结构的过程。</em></p>

<p>一旦建立了骨骼，可使用平滑蒙皮或刚体蒙皮为角色建立蒙皮。另外用户可以使用成组命令（Group）或者建立父子关系命令（Parent）建立物体与骨骼的运动关系从而达到使用骨骼来控制物体运动的目的。
<h6>什么是关节(Joint)和骨头(Bone)？</h6>
定义</p>

<p><em>关节是骨骼中骨头和骨头之间的连接点。</em></p>

<p>每个关节可连接一个或多块骨头。关节控制着骨头的旋转和移动。关节属性可以设置关节的运动。例如，限制关节旋转的范围。</p>

<p>Ball joint（球关节）——球关节可绕它的三个局部坐标轴旋转。</p>

<p>Universal joint（普通关节）——普通关节可绕其中的两个局部坐标轴旋转。人的腕关节就是一个普通关节的典型例子，而且它有一个旋转限制范围。</p>

<p>Hinge joint（铰链关节）——铰链关节仅能绕一个局部坐标轴旋转。人的膝关节是铰链关节的典型例子。如图4.2.1所示。</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347913802/" target="_blank"><img src="http://farm3.static.flickr.com/2079/2347913802_df7ae40528.jpg" border="0" alt="image001" /></a></p>

<p>图4.2.1
<h6>什么是关节链（Joint Chain）？</h6>
定义</p>

<p><em>关节链是一系列关节及其连接在关节上的骨头的组合。</em></p>

<p>关节链中的关节是线性连接的。关节链的“开始”关节是整个关节链中层次最高的关节，此关节是关节链的根关节(Root Joint)。</p>

<p>当为角色创建关节链时，应考虑将如何使用IK 手柄去控制关节链。可使用IK手柄控制具有少量关节数目的关节链。当创建关节链时，避免关节链在一条直线上。使用IK 手柄在适当的角度稍微旋转关节就可以很容易的控制关节旋转的方向。如图4.2.2所示。</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2347084201/" target="_blank"><img src="http://farm3.static.flickr.com/3247/2347084201_5d4710bc5f.jpg" border="0" alt="image003" /></a></p>

<p>图4.2.2
<h6>什么是肢体链？</h6>
定义</p>

<p><em>肢体链是一个或多个连接的关节链的组合，肢体是一种树状结构，其中的骨关节并不是线性连接。</em></p>

<p>肢体链一般是从关节链中层次最高的关节开始的，此关节是肢体链的根关节。在创建带有对称性肢体链的骨骼时，要在场景的全局坐标原点开始创建（工作空间的中部）因为这样可便于创建带有对称部分的骨骼。如图4.2.3所示。</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2347913552/" target="_blank"><img src="http://farm3.static.flickr.com/2055/2347913552_d5a7a13816.jpg" border="0" alt="image005" /></a></p>

<p>图4.2.3
<h6>什么是骨骼层级（Skeleton Hierarchy）？</h6>
定义</p>

<p><em>骨骼层级是关节链中按父子关系前后顺序排列的层级关系。</em></p>

<p>根关节是骨骼中层次最高的关节。骨骼中只能有一个根关节。父关节可以是骨骼中任意的关节，只要其下有可以被其影响的关节即可。位于父关节之下的关节称为子关节。如图4.2.4所示。</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347913344/" target="_blank"><img src="http://farm3.static.flickr.com/3135/2347913344_c10294a2ff.jpg" border="0" alt="image007" /></a>图4.2.4
<h5>骨骼的创建与编辑</h5>
<h6>创建关节链</h6>
1 选择Skeleton &gt; Joint Tool 命令。</p>

<p>2 在工作视窗中单击要创建关节的地方。</p>

<p>3 在要建立下一个关节的地方再次单击。</p>

<p>4 继续单击直到已创建所需要的关节链。</p>

<p>5 按下Enter 键，完成关节链的创建。</p>

<p>使用Joint Tool 摆放最近创建关节：</p>

<p>1 当使用Joint Tool 时，按住鼠标的中键。</p>

<p>2 那么变换操纵器出现，可在任意方向移动当前关节。</p>

<p>在定位当前关节后，通过单击鼠标左键，可继续创建关节。</p>

<p>如图4.2.5所示。</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2347083617/" target="_blank"><img src="http://farm3.static.flickr.com/2117/2347083617_df724f1d05.jpg" border="0" alt="image009" /></a>图4.2.5
<h6>创建肢体链</h6>
创建肢体链与创建关节链相似。当使用Joint Tool 创建关节时，可使用键盘上的上下键在创建的关节层次中来回移动。通过使用键盘的光标键，可回到任何以前创建的关节中，创建新的关节，作为当前关节的分支。在创建完关节链后按Enter键结束。
<h6>显示关节的局部坐标轴</h6>
1 选择关节。</p>

<p>2 选择Display &gt; Object Components &gt; Local Rotation Axes 命令。</p>

<p>如图4.2.6所示。</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2347083405/" target="_blank"><img src="http://farm3.static.flickr.com/2160/2347083405_754daf3c72.jpg" border="0" alt="image011" /></a></p>

<p>图4.2.6
<h6>观察骨骼层级</h6>
可在Outliner 中（Window &gt; Outliner）或者（Window &gt; Hypergraph）观察骨骼的层级。使用Hypergraph 显示关节的排列。例如，可排列关节层级，使它看起来像实际的骨骼结构，这可方便、准确地选择关节。如图4.2.7所示。</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2347083265/" target="_blank"><img src="http://farm3.static.flickr.com/2384/2347083265_cc4f180bee.jpg" border="0" alt="image013" /></a>
<h6>插入关节(Insert Joint)</h6>
可在任何关节链插入关节。当插入关节时，可使用Insert Joint Tool(Skeleton&gt;Instert JointTool)。一般来讲，应该在添加IK 手柄或蒙皮前插入关节。在带有IK 手柄的关节链插入关节，可能需要重做IK 手柄。另外，蒙皮后插入手柄可能导致不需要的变形效果。</p>

<p>1 选择Skeleton &gt; Insert Joint Tool 命令。</p>

<p>2 移动鼠标指针到要作为新增关节的父关节处。</p>

<p>3 按住鼠标左键，拖拽指针到添加新关节的地方。</p>

<p>4 当已完成了插入关节后，按下Enter 或选择其它的工具。
<h6>去除关节(Remove Joint)+</h6>
除了根关节以外，可去除任何关节，使父关节的骨头延伸到关节的子关节。注意不应该去除已蒙皮的关节。</p>

<p>1 选择要去除的关节。</p>

<p>注意一次只能去除一个关节。</p>

<p>2 选择Skeleton &gt; Remove Joint 命令。</p>

<p>关节被去除。被去除关节上面的骨头延伸到该关节下层次关节。
<h5>为三毛创建骨骼</h5>
实例教程
<h6>1 调整视窗布局</h6>
打开三毛的模型文件，开始创建三毛的骨骼系统。开始创建骨骼之前需要设置一下视图布局，选择视图菜单Panels&gt;Layouts&gt;Two Panes Side by Side，将左面的视图切换至Side（Panel&gt;Orthographic&gt;Side），右边的视图切换至Front（Panel&gt;Orthographic&gt;Front），这样可以方便观察。
<h6>2 创建角色身体的骨骼</h6>
首先创建三毛的腿部关节，选择主菜单Skeleton&gt;Joint Tool&gt;Option&gt;Reset Tool恢复缺省设置。在右侧Front视图，配合X键（grid捕捉）将根关节定位在Y轴上，然后依次向下创建腿部和脚部的全部关节，然后在左侧Side视图中调整各关节的位置，如图4.2.8所示</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347920552/" target="_blank"><img src="http://farm3.static.flickr.com/2307/2347920552_20c4f9ba64.jpg" border="0" alt="image015" /></a>图4.2.8</p>

<p>然后创建三毛的脊椎骨骼，这部分骨骼属于根关节的子关节，创建的方法有两种：一种方法是由根关节开始继续创建，选择关节工具（Joint tool）点击根关节以定义新骨骼的开始点，然后配合X键（grid捕捉）依次在Y轴上创建其余的骨骼。另一种方法是独立创建脊椎骨骼，然后选择脊椎第一关节按Shift键增加选择根关节，按键盘P键，通过父子关系与根关节连接上。两种方法都可以使用，创建后在Side视图中调整位置，如图4.2.9所示</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2347920168/" target="_blank"><img src="http://farm3.static.flickr.com/2388/2347920168_6a6fedd313.jpg" border="0" alt="image017" /></a>图4.2.9</p>

<p>继续创建三毛的手臂骨骼，方法与创建脊椎骨骼类似，手臂的骨骼应该由胸部骨骼与颈椎之间开始，如图4.2.10所示。</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2347090193/" target="_blank"><img src="http://farm3.static.flickr.com/2294/2347090193_1027d4a009.jpg" border="0" alt="image019" /></a>图4.2.10</p>

<p>手臂的骨骼制作好以后，继续创建手的骨骼，如图4.2.11所示</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2347089777/" target="_blank"><img src="http://farm3.static.flickr.com/3182/2347089777_42712164dd.jpg" border="0" alt="image021" /></a>图4.2.11
<h6>3 调整骨骼的局部坐标轴</h6>
全部骨骼创建好以后，骨骼的局部坐标轴（local axes）都是根据默认设置的，即每个关节的X轴都是指向下一个关节，这样的局部坐标轴（local axes）虽然不影响角色的运动，但是对于动画师的工作会带来一定的麻烦。例如，手指关节的弯曲运动，在默认设置下创建的骨骼需要调整两个轴向的才能完成一个弯曲运动，这对调动画和编写表达式造成很多麻烦。</p>

<p>在十指的旋转运动中，拇指比较特殊，这里以拇指的旋转为例调节局部坐标轴（local axes）。拇指的两个关节旋转方向是一致的，但是与手掌平面不是平行或者垂直，而是有一定的角度，如果不修改局部坐标轴（local axes），仅仅调节拇指关节在Y轴向上的旋转不能满足要求，如图4.2.12所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2347089161/" target="_blank"><img src="http://farm3.static.flickr.com/3241/2347089161_508305f532.jpg" border="0" alt="image023" /></a></p>

<p>图4.2.12</p>

<p>如果希望实现比较准确的旋转运动，必须调节Y、Z两个轴向上的转动，这对于设置大量手指运动会造成很多麻烦，如图4.2.13所示。</p>

<p><a title="image025" href="http://www.flickr.com/photos/95019520@N00/2347088817/" target="_blank"><img src="http://farm3.static.flickr.com/2167/2347088817_4163936cdd.jpg" border="0" alt="image025" /></a>图4.2.13</p>

<p>选择拇指的根关节，按F9键进入元素(Component)级别，在状态栏中选择miscellaneous<a title="image027" href="http://www.flickr.com/photos/95019520@N00/2347088475/" target="_blank"><img src="http://farm3.static.flickr.com/2269/2347088475_f178d05c23.jpg" border="0" alt="image027" /></a>选项，这是显示出所选关节的局部坐标轴（local axes），如图4.2.14所示。</p>

<p><a title="image029" href="http://www.flickr.com/photos/95019520@N00/2347917856/" target="_blank"><img src="http://farm3.static.flickr.com/2122/2347917856_0904acc98c.jpg" border="0" alt="image029" /></a></p>

<p>图4.2.14</p>

<p>使用旋转工具调节局部坐标轴(local axes)，目的是使局部坐标轴的某一轴符合拇指的旋转，即旋转一个轴就可以实现对拇指的控制，关节的旋转状态会随着局部坐标轴(local axes)的调节不断地变化。如图4.2.15所示。</p>

<p><a title="image031" href="http://www.flickr.com/photos/95019520@N00/2347087807/" target="_blank"><img src="http://farm3.static.flickr.com/2128/2347087807_20c00ac274.jpg" border="0" alt="image031" /></a>图4.2.15</p>

<p>完成后按F8键返回物体级别，这时通过旋转Z轴这一个轴就可以控制关节运动了，如图4.2.16所示。</p>

<p><a title="image033" href="http://www.flickr.com/photos/95019520@N00/2347916676/" target="_blank"><img src="http://farm3.static.flickr.com/2236/2347916676_bc66a580a6.jpg" border="0" alt="image033" /></a>图4.2.16</p>

<p>按照同样方法调节全身骨骼的其余关节，对于创建时关节的局部坐标轴就可以满足控制要求的关节则不需要进行这一步的调节。
<h6>4 骨骼的命名</h6>
由于大部分角色在结构上是左右对称的，创建的骨骼也应该是左右对称的，用Joint Tool制作好一侧的骨骼以后，可以使用骨骼对称工具制作出另一半，对称骨骼时可以连同骨骼名称一起对称，因此对称之前需要调整一下现有骨骼的名称，这里我们使用MAYA6.0的标记工具—Retargeting。选择主菜单Skeleton&gt;Retargeting&gt;Joint Labelling，并且将工具条独立出来，这样便于下一步操作，如图4.2.17所示。</p>

<p><a title="image035" href="http://www.flickr.com/photos/95019520@N00/2347086777/" target="_blank"><img src="http://farm3.static.flickr.com/2253/2347086777_5526db32b8.jpg" border="0" alt="image035" /></a>图4.2.17</p>

<p>MAYA缺省设置不显示骨骼的标记，为了方便工作，在命名骨骼之前需要打开骨骼标记显示。选择主菜单Skeleton&gt;Retargeting&gt;Show All Labels显示骨骼标记。由于未对骨骼命名，因此骨骼标记都显示为None，如图4.2.18所示。</p>

<p><a title="image037" href="http://www.flickr.com/photos/95019520@N00/2347915970/" target="_blank"><img src="http://farm3.static.flickr.com/2007/2347915970_b1f931c3c7.jpg" border="0" alt="image037" /></a><a title="image039" href="http://www.flickr.com/photos/95019520@N00/2347086403/" target="_blank"><img src="http://farm3.static.flickr.com/3135/2347086403_a504250c6b.jpg" border="0" alt="image039" /></a>图4.2.18</p>

<p>首先，从三毛的脊椎开始命名。选择三毛整体骨骼的根关节，选择Label Center，这样根关节以上的脊椎部分骨骼都被定义为Label Center ，然后定义根关节的具体标记为Label Root，根关节向上关节依次定义，如图。</p>

<p>然后选择肩部骨骼，先定义为Label Left，然后依次定义，如图4.2.19所示。</p>

<p><a title="image041" href="http://www.flickr.com/photos/95019520@N00/2347086239/" target="_blank"><img src="http://farm3.static.flickr.com/3172/2347086239_8cb9070956.jpg" border="0" alt="image041" /></a>图4.2.19</p>

<p>然后选择腿部骨骼，先定义为Label Left，然后依次定义，如图4.2.20所示。</p>

<p><a title="image043" href="http://www.flickr.com/photos/95019520@N00/2347085849/" target="_blank"><img src="http://farm3.static.flickr.com/2398/2347085849_a283aa51a2.jpg" border="0" alt="image043" /></a>图4.2.20</p>

<p>三毛骨骼全部定义标记后，选择任意一个关节，查看右侧通道栏（Channelbox）中的名称，可以看到骨骼名称仍然是原始名称，这说明骨骼的名称和标记是相对独立的，定义标记后需要根据标记命名骨骼。选择根关节后，选择主菜单Skeleton&gt;Retargeting&gt;Rename joints from labels命令，这是骨骼名称全部更新为标记的名称。
<h6>5 镜像骨骼</h6>
重命名骨骼后可以开始对称生成另一次骨骼。选择主菜单Skeleton&gt;Mirror Joint&gt;Option打开设置面板。</p>

<p>首先对称上肢骨骼。选择肩部骨骼，选择主菜单Skeleton&gt;Mirror Joint&gt;Option打开设置面板，设置如图4.2.21所示。</p>

<p><a title="image045" href="http://www.flickr.com/photos/95019520@N00/2347915246/" target="_blank"><img src="http://farm3.static.flickr.com/3174/2347915246_ef297a69d0.jpg" border="0" alt="image045" /></a>图4.2.21</p>

<p>重命名时需要注意名称字母的大小写区分。对称后的骨骼名称应该都以“Right”字母开头，但是标记却与另一侧骨骼一样，如图4.2.22所示。</p>

<p><a title="image047" href="http://www.flickr.com/photos/95019520@N00/2347915036/" target="_blank"><img src="http://farm3.static.flickr.com/3121/2347915036_f768ddab2d.jpg" border="0" alt="image047" /></a>图4.2.22</p>

<p>这时需要根据骨骼名称来定义标记，选择新生骨骼后，选择主菜单Skeleton&gt;Retargeting&gt;Label based on joint names，骨骼标记全部更新。如图4.2.23所示。</p>

<p><a title="image049" href="http://www.flickr.com/photos/95019520@N00/2347914724/" target="_blank"><img src="http://farm3.static.flickr.com/2329/2347914724_fdb7bf709b.jpg" border="0" alt="image049" /></a>图4.2.7图4.2.23</p>

<p>根据命名上肢骨骼的步骤完成下肢骨胳的命名，如图4.2.24所示。</p>

<p><a title="image051" href="http://www.flickr.com/photos/95019520@N00/2347914552/" target="_blank"><img src="http://farm3.static.flickr.com/3210/2347914552_983b5a9de1.jpg" border="0" alt="image051" /></a></p>

<p>图4.2.24
<h5>本节工具解析</h5>
<h6>Joint Tool</h6>
骨骼工具用于连续地创建骨骼系统。创建的骨骼按照创建顺序成父子关系联接。</p>

<p>Skeleton&gt;Joint Tool&gt;Option 如图4.2.25所示。</p>

<p><a title="image053" href="http://www.flickr.com/photos/95019520@N00/2347084829/" target="_blank"><img src="http://farm3.static.flickr.com/3177/2347084829_072751237c.jpg" border="0" alt="image053" /></a>图4.2.25</p>

<p>·<strong>Degrees of freedom</strong></p>

<p>设置新建骨骼的local axes在IK作用下时允许旋转的轴向，包括X、Y、Z三个轴向。</p>

<p>·<strong>Orientation</strong></p>

<p>定义新建骨骼的local axes排列方式。缺省设置是xyz，使用这个选项创建骨骼时，每一个新关节创建后，上一个关节的第一个轴向——X轴会自动指向新建的关节，直到最后一个关节结束，由于最后一个关节没有下一个关节，因此它的local axes方向和World axes一致。其他的几种轴向排列选项，都是第一个字母表示第一个轴向。</p>

<p>如果在这里选择none，那么每一个新建关节的local axes方向都是World axes的方向。</p>

<p>·<strong>Second Axis World Orientation</strong></p>

<p>创建骨骼时，第一个轴的方向是新建关节的local axes的基准，根据Orientation的选项，Maya首先定义出第一个轴的方向。第一个轴确定后，需要定义出第二个轴的方向才能确定完整的local axes。Second Axis World Orientation就是定义这第二个轴的方向，有一个简便的方法来确定选择哪一个轴向作为第二个轴：将右手五指伸直，将拇指与其余四指形成近似的直角，将手掌平行于当前视图平面，拇指指向第一个轴的正方向，其余四指的指向就是第二个轴的正向，它可以定义为其余两轴的正方向或负方向。</p>

<p>·<strong>Scale Compensate</strong></p>

<p>是否受父关节缩放的影响。勾选后创建骨骼，在缩放某一骨骼时不影响其他骨骼。不勾选时创建骨骼，在缩放某一骨骼时会影响其所有下级骨骼一同缩放。</p>

<p>·<strong>Auto Joint Limits</strong></p>

<p><strong></strong>勾选后创建的骨骼，会对第三个轴的旋转产生约束。</p>

<p>·<strong>Create IK Handle</strong></p>

<p>勾选后创建的骨骼会自动生成IK。</p>

<p>·<strong>IK Handle Settings</strong></p>

<p>设置当选择Create IK Handle后生成的IK，与单独创建IK的设置一样。
<h6>Retargeting</h6>
将骨骼系统的各个关节设定便于识别标签。</p>

<p>Skeleton&gt;Retargeting&gt;Joint Labelling</p>

<p>Joint Labelling工具条分为上下两部分，定义标记时顺序由上至下，上半部分整体定义骨骼的所属范围，包括左部、中部、右部，下半部分定义骨骼的具体标记。
<h6>Mirror Joint</h6>
对于左右对称的角色，骨骼镜像功能可以很方便地将骨骼系统沿轴心平面进行镜像复制，而无需繁琐地重新制作另外一半骨骼。</p>

<p>Skeleton&gt;Mirror Joint&gt;Option，如图4.2.26所示。</p>

<p><a title="image055" href="http://www.flickr.com/photos/95019520@N00/2347084739/" target="_blank"><img src="http://farm3.static.flickr.com/2253/2347084739_c46ed9bf87.jpg" border="0" alt="image055" /></a>图4.2.26</p>

<p>·<strong>Mirror Across</strong></p>

<p>选择按照哪个坐标平面进行对称，包括XY平面、YZ平面、XZ平面。</p>

<p>·<strong>Mirror Function</strong></p>

<p>对称以后的骨骼与原始骨骼具有一定的关系，这里设置对称骨骼的方式，Behavior一般用于手臂骨骼的对称，Orientation一般用于腿部骨骼的对称，如图4.2.27所示。</p>

<p><a title="image057" href="http://www.flickr.com/photos/95019520@N00/2347084571/" target="_blank"><img src="http://farm3.static.flickr.com/2196/2347084571_35b2cd6870.jpg" border="0" alt="image057" /></a>图4.2.27</p>

<p>·<strong>Replacement names for duplicated joints</strong></p>

<p>将对称后新生的骨骼进行重命名，字母有大小写区别。</p>

<p>Search for : 输入原始骨骼名称需要更改的部分字母。</p>

<p>Replace with : 输入新生骨骼的名称将要替代原始部分的字母。</p>

<p>例如：制作好的左侧骨骼都是以“Left”开头的名字，对称以后的骨骼将要以“Right”开头，那么在Search for栏中输入Left，在Replace with栏中输入Right，对称后的新骨骼名称以“Right”开头，“Right”以后的部分保持与原始骨骼相同。</p>

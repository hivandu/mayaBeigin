---
layout: post
title: 第四章第五节 骨骼的控制方法
categories:
- Maya
tags:
- control
- Maya
- skeleton
- 开始maya吧
- 第四章
published: true
comments: false
---
<p><!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/fourth-charactor-design.html" target="_blank">回节目录选择</a></p>

<p><h5>本节概述</h5>
为角色创建骨骼并且将骨骼与角色模型进行蒙皮之后，下面就要讲解如何通过控制骨骼摆放角色姿态的方法。在三维动画中主要有两种方法控制骨骼的运动：反向动力学与前向动力学。前向动力学对创建细致的圆弧运动是非常需要的，因为它需要对每个关节旋转的直接设置。反向动力学对创建直接的目标运动是非常需要的，因为它仅需要设置关节链中的终关节到达的位置和运动方向。</p>

<p>本节重点讲解如何使用反向动力学方法控制骨骼的运动。
<h5>了解骨骼的控制方法</h5>
<h6>什么是前向动力学(Forward Kinematics/FK)？</h6>
在前向动力学中，当定位关节链时，要逐个地旋转每个关节。例如,为了使关节链能够到达空间某个特定的位置，必须逐个地旋转关键链中的每个关节。为完成上述操作，将先旋转关节链的父关节，然后是下一个关节，顺着关节链依次进行。当使用前向动力学动画骨骼时，Maya 从根关节开始添加关节旋转，然后是根关节的子关节，顺着骨骼的层次依次进行。</p>

<p>当设置细致的圆弧运动时，使用前向动力学定位和动画骨骼是一个理想的方法，但是，如果动画直接目标运动时，前向动力学不如反向动力学控制方便。
<h6>什么是反向动力学(Inverse Kinematics/IK)？</h6>
在反向动力学中，可以根据由IK控制的关节链中终关节要达到的空间位置来反向解算整条关节链中各个关节的空间位置。IK对于创建直接目标运动比FK更加直观，可以集中控制关节链要达到的目标上，而不必考虑每个关节如何旋转。反向动力学使用IK手柄和IK解算器进行定位和动画。
<h6>什么是IK手柄（IK Handle）?</h6>
IK手柄(IK Handle)像一条线，它从关节链的起点贯穿到关节链的终点，提供了控制整个关节链运动的方式。IK手柄控制的起始关节称为始关节，控制的最后关节称为终关节。始关节可以是骨骼的根关节，或者是终关节以上的任何关节，具有IK手柄的关节链称为IK链，IK手柄可定位关节链中所有的关节。当使用IK手柄定位和动画关节链时，通过使用IK解算器，IK手柄自动地推算出关节链中所有关节的旋转方式。如图4.5.1所示</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347977366/" target="_blank"><img src="http://farm3.static.flickr.com/2207/2347977366_44f15bb4fa.jpg" border="0" alt="image001" /></a>图4.5.1
<h6>什么是IK解算器（IK Solver）？</h6>
IK Solver(IK解算器)是IK手柄的运动控制信息。当使用IK手柄移动整个关节链到达空间某一特定位置，给出关节链要到达的位置后，IK解算器通过反向动力学方式，推算出如何旋转关节链中的所有关节。</p>

<p>常用的有4种类型的解算器：</p>

<p>·IK Rotate plane(RP) Solver——IK旋转平面解算器</p>

<p>·IK Single chain(SC) Solver——IK单链解算器</p>

<p>·Spline IK Solver——IK样条曲线解算器</p>

<p>·2 Bone IK Solver——双骨IK解算器
<h6>IK的工作原理</h6>
了解IK的工作原理可以帮助我们更好的理解和使用IK。创建一个IK以后，IK手柄的终点被放置在终关节处，称为终点效应器。终点效应器用来提供IK手柄如何旋转关节链中关节的信息，关节链的终点按照这些信息到达空间的某些位置。将IK手柄终点的位置传递给IK手柄的IK解算器，终点效应器可以为IK解算器提供如何旋转关节所需要的信息。</p>

<p>当定位和动画一个IK链时，真正需要做的是移动IK手柄的位置。IK解算器获取了终点效应器移动到下一个目标的位置和方向，IK解算器根据目标的位置以及当前终点效应器所在的位置，计算出如何旋转IK链中的所有关节以使终点效应器达到目标所在位置。</p>

<p>在一套骨骼当中，根关节只能作为IK链的始关节，而且不能位于IK链的始关节和终关节之间。当更改根关节以后，新的根关节位于某个IK关节链之中，而不是IK链的始关节，那么该IK链无效。
<h5>IK旋转平面手柄（ikRPhandle）</h5>
在缺省设置下创建的IK手柄（ikHandle）都使用IK旋转平面解算器(ikRPsolver)，而且每个IK手柄（ikhandle）都使用同一个IK旋转平面解算器(ikRPsolver)。</p>

<p>IK 旋转平面手柄(IkRPhandle)指导关节链中所有关节的关节旋转，用户可以直接控制关节链的全部旋转。如图4.5.2所示</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2347147101/" target="_blank"><img src="http://farm3.static.flickr.com/2278/2347147101_3db4a72213.jpg" border="0" alt="image003" /></a>图4.5.2</p>

<p>IK 旋转平面手柄(IkRPhandle)非常适合定位四肢的关节链。在定位关节链的时候，经常需要控制关节链中的一些关节保持在一个平面上，这时K旋转平面解算器(ikRPsolver)是最佳的选择。例如，肩部、肘部和腕关节可保持在一个平面上，但是，当肩关节旋转时旋转平面也跟着旋转。
<h6>开始关节(Start Joint)和终关节(End Joint)</h6>
开始关节是IK 手柄开始的地方。开始关节是受IK 手柄影响关节链的第一个关节。开始关节可以是骨骼的根关节，或者骨骼层级中在终关节层次以上的任何关节。开始关节必须是球关节类型。并且在其局部坐标轴上可进行任意的旋转。终关节是IK 手柄控制的关节链中最后的关节。终关节必须是在骨骼中开始关节层次以下的关节。
<h6>末端效果器(End Effecter)</h6>
系统默认设置，末端效果器不显示在场景中，但是它被定位在终关节的局部旋转轴。末端效果器是终关节的父关节的子物体，影响关节链中所有的关节。为观看末端效果器和关节之间的层次关系，用户可使用Hypergraph（超图）观看场景层次。</p>

<p>对于IK 旋转平面手柄，末端效果器的目标是IK手柄到达的位置。当用户移动IK 旋转平面手柄的位置时，IK 旋转平面解算器计算如何旋转关节链中所有的关节，以使末端效果器可到达IK手柄的位置。</p>

<p>末端效果器始终尽量与IK 手柄的位置保持一致。然而，能否保持一致也取决于关节链旋转的极限和关节链的整个范围长度，如果超出了范围，末端效果器将不可能到达IK 手柄。
<h6>手柄线(Handle Wire)</h6>
手柄线贯穿于IK手柄控制的关节链的所有的关节和骨头。手柄线在开始关节的局部坐标轴开始，在末端效果器结束。
<h6>手柄矢量(Handle Vector)</h6>
手柄矢量是一条从开始关节到IK 手柄末端效果器的直线。末端效果器通常被放置在IK 链的终关节位置。
<h6>极矢量(Pole Vector)</h6>
极矢量始于关节链的开始关节，使用极矢量可控制参考平面的方向。</p>

<p>移动极矢量可以改变参考平面的方向，因此移动极矢量也可直接改变关节链的方向，类似于使用扭曲盘改变关节链的方向的操作。这是因为关节链扭曲的度数是由参考平面和关节链平面之间角度差别定义的。</p>

<p>在定位的过程中，如果手柄矢量和极矢量恰巧交错在一起或指向相反的方向，关节链会突然的反转。关节链突然的反转是因为当矢量交错或指向相反时，与关节链平面相比的参考平面的方向的突然改变了180<br />
度。用户可通过移动极矢量使手柄矢量与极矢量不发生交错或指向相反，这样可以防止关节链的突然反转。
<h6>旋转盘(Rotate Disc)</h6>
旋转盘定位于开始关节。旋转盘指示关节如何旋转。
<h6>关节链平面(Joint Chain Plain)</h6>
关节链中所有关节构成关节链平面。关节链平面控制关节链如何扭曲(Twist)。关节链平面可绕手柄矢量旋转。关节链平面是不显示的，但用户可从关节链的关节位置推断它。关节链平面的投影在旋转盘的关节链平面指示器中显示出来。
<h6>参考平面(Reference Plane)</h6>
参考平面由手柄矢量和极矢量定义。当扭曲关节链平面时，关节链平面必须与其它平面相比较，以便测量扭曲的度数。与旋转关节链相比较的平面是参考平面。两个平面之间的差别表明了关节链扭曲的数量。
<h6>关节链平面指示器(Joint Chain Plain Indicator)</h6>
关节链平面指示器可被认为是旋转盘中关节链平面的投影，关节链平面指示器指示出关节链平面相对于参考平面的扭曲（Twist）角度，当IK手柄的扭曲（Twist）值为零时，关节链平面与参考平面重合。
<h6>参考平面指示器(Reference Plane Indicator)</h6>
参考平面指示器是位于扭曲盘的绿色圆点。参考平面指示器表明了参考平面的方向。用户可以把参考平面指示器作为在旋转盘中参考平面的投影。
<h6>扭曲盘(Twist Disc)</h6>
扭曲盘位于终关节。扭曲盘是扭曲关节链平面的操纵器。
<h6>扭曲指示器(Twist Indicator)</h6>
在旋转盘上，在参考平面指示器和关节链平面指示器之间的绿色圆弧是扭曲指示器。扭曲指示器表明了关节链平面相对于参考平面的旋转方向。如图4.5.3所示</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2347990480/" target="_blank"><img src="http://farm3.static.flickr.com/3227/2347990480_3315cee836.jpg" border="0" alt="image005" /></a></p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347160379/" target="_blank"><img src="http://farm3.static.flickr.com/2016/2347160379_a504a646c4.jpg" border="0" alt="image007" /></a></p>

<p>图4.5.3
<h5>使用IK旋转平面手柄控制骨骼</h5>
<h6>创建IK 旋转平面手柄</h6>
在创建IK 旋转平面之前，要检查IK Handle Tool 的工具设置（选择Skeleton &gt; IK HandleTool 命令）。当前解算器应当被设置为ikRPsolver。同时要注意开始关节必须是球关节,而且可在它的局部轴被任意的旋转,并确定开始关节没有旋转性限制或者锁定的属性。</p>

<p>1 选择Skeleton &gt; IK Handle Tool 命令。</p>

<p>2 在工作空间，在要开始IK 旋转平面的关节上单击。</p>

<p>3 在要结束IK 旋转平面的关节上再次单击。
<h6>定位手柄</h6>
<h6>移动手柄</h6>
1 选择IK 旋转平面手柄（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Move Tool（默认热键：W 键）。</p>

<p>3 在工作空间，按住鼠标的左键或中键，移动IK 手柄。继续操作，定位由IK 手柄控制的关</p>

<p>节链。
<h6>操纵极矢量</h6>
1 选择IK 旋转平面手柄（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Show Manipulator Tool（默认热键：T 键）。</p>

<p>IK 手柄的极矢量、扭曲盘和旋转盘显示。</p>

<p>3 在工作空间，按住鼠标左键或中键，移动极矢量。定位由IK 手柄控制的关节链。</p>

<p>注意当用户移动极矢量时，旋转盘的参考平面指示器（在系统默认设置下，沿扭曲盘的绿色圆点）移动，反应极矢量的运动。
<h6>操纵扭曲盘</h6>
1 选择IK 旋转平面手柄。（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Show Manipulator Tool（默认热键：T 键）。</p>

<p>IK 手柄的极矢量、扭曲盘和旋转盘显示。注意：在系统默认设置下，扭曲盘是蓝色的。</p>

<p>3 单击扭曲盘。在系统默认设置下，扭曲盘变为黄色。</p>

<p>4 按住鼠标的左键或中键，旋转扭曲盘。</p>

<p>由IK 手柄控制的关节链绕手柄矢量旋转。此操作改变了IK 手柄Twist 通道的值。
<h5>IK单链手柄 （ikSChandle）</h5>
IK单链手柄 （ikSChandle）是定位关节链手柄的一种方式。IK单链手柄 （ikSChandle）指导关节链中所有关节的旋转和关节链的整体方向，如图4.5.4所示</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2347160245/" target="_blank"><img src="http://farm3.static.flickr.com/2374/2347160245_61b2c73d4d.jpg" border="0" alt="image009" /></a>图4.5.4</p>

<p>IK单链手柄 （ikSChandle）是定位和动画关节链的直接工具。关节链将保持在一个平面上，并且最大限度的包括所有关节链的关节。同样，创建的每个IK单链手柄 （ikSChandle）也都使用同一个IK单链解算器(ikSCsolver)。如果编辑默认的IK单链解算器(ikSCsolver)的属性，所有的IK单链手柄 （ikSChandle）都受到影响，编辑默认的IK单链解算器(ikSCsolver)的属性，所有的IK单链手柄 （ikSChandle）都受到影响。</p>

<p>在创建IK单链手柄 （ikSChandle）时，始关节必须是球状关节，而且必须在它的三个局部轴都能够自由地转动，没有旋转的界限或锁定的属性。
<h5>使用IK单链手柄控制骨骼</h5>
<h6>创建IK 单链手柄</h6>
在创建一个IK 单链手柄前，确认选中IK Handle Tool 工具设置（选择Skeleton &gt; IK HandleTool 命令）。Current Solver 应该被设置为ikSCsolver。注意始节点必须是球状关节：它必须对它所在的三个轴能够自由的转动。确使始节点没有旋转的界限或锁定的属性。</p>

<p>1 选择Skeleton &gt; IK Handle Tool 命令。</p>

<p>2 在工作空间，在IK 单链手柄要开始的关节单击。</p>

<p>3 在IK 单链手柄要结束的关节单击，完成手柄的创建。
<h6>定位IK 单链手柄</h6>
<h6>移动手柄</h6>
1 选择IK 单链手柄（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Move Tool（默认热键：W 键）。</p>

<p>3 在工作空间，按住鼠标左键或鼠标中键，按需要移动IK 手柄。这样就定位了IK 手柄控制关节链。
<h6>旋转手柄</h6>
1 选择IK 单链手柄（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Rotate Tool（默认热键：E 键）。</p>

<p>3 在工作空间，按鼠标左键或中键时，根据需求旋转IK 手柄。这样就定位了IK 手柄控制关</p>

<p>节键。
<h5>IK双骨手柄(ik2Bhandle)</h5>
IK双骨手柄是一种有由两个或三个关节组成的短关节链定位工具。IK双骨手柄对于设置游戏中的角色非常有用，Maya包括此功能的源码，游戏开发者可以在游戏引擎中准确复制此功能的作用。如图4.5.5所示</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2347159887/" target="_blank"><img src="http://farm3.static.flickr.com/2117/2347159887_6b57655f58.jpg" border="0" alt="image011" /></a>图4.5.5</p>

<p>无论是为两个关节或三个关节创建ik2Bhandle，IK手柄一律把此关节链作为两个关节的情况处理。IK手柄把在关节链层级中第一个骨头（bone）到最后骨头（bone）之上的所有关节和骨头（joint and bone）作为一块骨头处理。
<h5>使用IK双骨手柄控制骨骼</h5>
<h6>创建IK 双骨解算器</h6>
Maya界面提供的默认IK手柄不包括IK双骨手柄，使用时需要手动进行加载。首先需要加载IK双骨手柄解算器的插件(plugin)，然后创建IK双骨手柄解算器,有两种方法可以完成上述操作：
<h6>方法一:</h6>
1 在Command Line 中输入下列内容：</p>

<p>loadPlugin ik2Bsolver;</p>

<p>2 在Command Line 中输入下列内容：</p>

<p>ik2Bsolver;
<h6>方法二:</h6>
1选择主菜单Window&gt;Settings/Preferences&gt;Plug-<br />
in Manager，弹出设置窗口，勾选ik2Bsolver.mll进行加载。如图4.5.6所示</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2347989470/" target="_blank"><img src="http://farm3.static.flickr.com/2048/2347989470_ea5ba76007.jpg" border="0" alt="image013" /></a>图4.5.6</p>

<p>2 在Command Line 中输入下列内容：</p>

<p>ik2Bsolver;</p>

<p>这时在IK Handle Tool设置窗口的Current solver选项中会增加ik2Bsolver选项。如图4.5.7所示</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347159305/" target="_blank"><img src="http://farm3.static.flickr.com/3248/2347159305_5a481249e0.jpg" border="0" alt="image015" /></a>图4.5.7</p>

<p>如果打开已有场景中使用了ik2Bhandle，那么Maya会自动加载并运行plugin。
<h6>使用IK 手柄创建关节链</h6>
1 选择Skeleton &gt; Joint Tool 命令。</p>

<p>2 在Tool Settings 视窗中，单击打开Create IK Handle 项。</p>

<p>3 在IK Handle Options 中设置Current Solver 为ik2Bsolver。</p>

<p>4 关闭Tool Settings 视窗。</p>

<p>5 创建一个双骨关节链。在按Enter 键后，Maya 将会创建一个IK 双骨关节链。</p>

<p>用户可使用IK 双骨手柄定位关节链。
<h6>创建IK 双骨手柄</h6>
在创建IK 旋转平面之前，要检查IK Handle Tool 的工具设置（选择Skeleton &gt; IK HandleTool 命令）。当前解算器应当被设置为ik2Bsolver。</p>

<p>1 选择Skeleton &gt; IK Handle Tool 命令。</p>

<p>2 在工作空间，在要开始IK 双骨手柄的关节上单击。</p>

<p>3 在要结束IK 双骨手柄的关节上再次单击。
<h6>定位手柄</h6>
<h6>移动手柄</h6>
1 选择IK 双骨手柄（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Move Tool（默认热键：W 键）。</p>

<p>3 在工作空间，按住鼠标的左键或中键，移动IK 手柄。
<h6>操纵极矢量</h6>
1 选择IK 双骨手柄（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Show Manipulator Tool（默认热键：T 键）。</p>

<p>IK 手柄的极矢量、扭曲盘和旋转盘显示。</p>

<p>3 在工作空间，按住鼠标左键或中键，移动极矢量。定位由IK 手柄控制的关节链。</p>

<p>注意当用户移动极矢量时，旋转盘的参考平面指示器（在系统默认设置下，沿扭曲盘的绿色圆点）移动，反应极矢量的运动。
<h6>操纵扭曲盘</h6>
1 选择IK 双骨手柄。（默认名：ikHandle<em>n</em>)。</p>

<p>2 单击Show Manipulator Tool（默认热键：T 键）。</p>

<p>IK 手柄的极矢量、扭曲盘和旋转盘显示。注意：在系统默认设置下，扭曲盘是蓝色的。</p>

<p>3 单击扭曲盘。在系统默认设置下，扭曲盘变为黄色。</p>

<p>4 按住鼠标的左键或中键，旋转扭曲盘。</p>

<p>由IK 手柄控制的关节链绕手柄矢量旋转。此操作改变了IK 手柄Twist 通道的值。
<h5>IK样条曲线手柄(IKSplineHandle)</h5>
IK 样条手柄提供了使用NURBS 曲线定位关节链的方法。IK样条曲线手柄(IKSplineHandle)的样条曲线贯穿于其作用的关节链，经常用于为尾巴、脖子、脊椎、胡须、长鞭、蛇等类似的对象设置动画。创建IK样条曲线手柄(IKSplineHandle)后，操纵手柄中的曲线时，IK样条曲线解算器会相应地旋转关节链中的各个关节。如图4.5.8所示。</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2347988780/" target="_blank"><img src="http://farm3.static.flickr.com/2288/2347988780_e982567463.jpg" border="0" alt="image017" /></a>图4.5.8
<h5>使用IK样条曲线手柄控制骨骼</h5>
<h6>创建IK 样条曲线手柄</h6>
用户可以为关节链添加IK样条曲线手柄。为动画关节链，用户可操纵手柄中的曲线，而不操纵手柄的变换。用户也可以使用便利的操纵器滚动和扭曲关节链。</p>

<p>关节链可是独立的骨骼层级或大层级中的一部分。系统默认，当用户创建IK 样条曲线手柄时，Maya为用户创建一条曲线。在创建手柄前，用户也可创建自己的曲线。在上述任何一种情况中，关节链会模拟曲线的形状。
<h6>使用默认曲线和选项创建IK 样条曲线手柄</h6>
1 创建关节链。为确保动画曲线时关节链平滑移动，创建许多相互靠近的关节（使用短骨）。</p>

<p>2 选择Skeleton &gt; IK Spline Handle Tool 命令。</p>

<p>3 选择IK 手柄的开始关节。</p>

<p>4 选择IK 手柄的终关节。</p>

<p>IK 样条手柄出现在关节链上，Maya自动创建一条曲线。旋转关节链的关节可调整曲线的形状。
<h6>使用自定义曲线和选项创建IK样条曲线手柄</h6>
1 使用建模工具创建曲线。如果用户创建一条CVs 很少的曲线，对曲线形状的控制和骨骼的运动将缺少精确性，但是能更容易地操纵曲线和它的关节链。开始使用较少的CVs，仅当需要更多的CVs 时再进行添加，以便于控制。</p>

<p>2 创建关节链。为确保动画曲线时，关节能平滑地运动，要创建多个相互靠近的关节（使用短骨）。</p>

<p>3 选择Skeleton &gt; IK Spline Handle Tool- 命令。</p>

<p>打开Tool Settings 视窗。请参看“在创建IK 样条曲线手柄前设置选项”设置选项。关闭“AutoCreate Curve”，保存选项设置，以便以后使用。</p>

<p>4 选择IK 手柄的开始关节。</p>

<p>5 选择IK 手柄的终关节。</p>

<p>6 选择曲线。</p>

<p>IK 样条曲线手柄出现在关节链上。旋转关节链中的关节，调整曲线的形状。如果IK曲线比关节链短，那么超出长度的关节链以一条直线从曲线的终点向外指出。
<h6>动画关节链</h6>
<h6>操纵曲线的CVs</h6>
1 选择曲线。</p>

<p>当用户使用CVs 时，显示CVs 和hulls 是非常有帮助的。当打开“Select by object type”模式<a title="image019" href="http://www.flickr.com/photos/95019520@N00/2347158693/" target="_blank"><img src="http://farm3.static.flickr.com/3174/2347158693_2658bdf565.jpg" border="0" alt="image019" /></a>时，打开Display &gt; NURBS Components &gt; CVs 和Hulls。</p>

<p>2 移动CVs。打开“Select by component type” 模式<a title="image021" href="http://www.flickr.com/photos/95019520@N00/2347158647/" target="_blank"><img src="http://farm3.static.flickr.com/2083/2347158647_d70b7c468c.jpg" border="0" alt="image021" /></a>，并使用Move tool。或者从Modeling 菜单选择select Curves &gt; Curve Editing Tool 命令。</p>

<p>3 选择Animate &gt; Set Key 设置关键帧。</p>

<p>如图4.5.9所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2347158605/" target="_blank"><img src="http://farm3.static.flickr.com/3137/2347158605_ebb4cf48e8.jpg" border="0" alt="image023" /></a>图4.5.9
<h6>扭曲和滚动关节链</h6>
1 选择IK 样条曲线手柄。在工作空间选择手柄，环绕终关节拖拽出一个选择框。系统默认选项优先权确保用户选择手柄，而不是终关节。</p>

<p>2 选择Modify &gt; Transformation Tools &gt; Show Manipulator Tool 命令。在终关节和开始关节处显示圆形操纵器。</p>

<p>3 为滚动整个关节链，在开始关节单击并旋转圆形操纵器。</p>

<p>4 为扭曲关节链，在终关节单击并旋转圆形操纵器。用户可通过选择IK 手柄在Channel Box 或Attribute Editor 中的Roll 和Twist 项中输入数值，调整扭曲和滚动。在Attribute Editor 中展开IK Solver Attributes 部分来查看这些属性。</p>

<p>5 为手柄的滚动和扭曲设置关键帧。</p>

<p>如图4.5.10所示。</p>

<p><a title="image025" href="http://www.flickr.com/photos/95019520@N00/2347158517/" target="_blank"><img src="http://farm3.static.flickr.com/3069/2347158517_7b7b7bcb9d.jpg" border="0" alt="image025" /></a>图4.5.10
<h6>沿曲线滑动关节链</h6>
1 选择IK 手柄。</p>

<p>2 选择Window &gt; Attribute Editor 命<br />
令，打开Attribute Editor。</p>

<p>3 展开IK Solver Attributes 选项。</p>

<p>4 打开Root on Curve 项。这限制了IK 样条手柄的开始关节到曲线的某一个位置。它也提供了一个偏移操纵器,沿曲线滑动开始关节。</p>

<p>5 选择Modify &gt; Transformation Tools &gt; Show Manipulator Tool 命令。偏移操纵器出现在开始关节。</p>

<p>6 拖拽操纵器沿曲线滑动关节。如果用户拖拽开始关节到曲线的终点，那么子关节呈直线状离开曲线终点。用户不能拖拽操纵器通过曲线的任何一端。用户可在属性编辑器(Attribute Editor) 中输入偏移值,并沿曲线移动开始关节的偏移操纵器。用户可通过使用不同的数值来得到需要的结果。如果关闭Curve on Root，那么Offset 属性可被忽略。</p>

<p>如图4.5.11所示。</p>

<p><a title="image027" href="http://www.flickr.com/photos/95019520@N00/2347988128/" target="_blank"><img src="http://farm3.static.flickr.com/3055/2347988128_aecd221a03.jpg" border="0" alt="image027" /></a>图4.5.11</p>

<p>7 为Offset 设置关键帧。如图4.5.12所示。</p>

<p><a title="image029" href="http://www.flickr.com/photos/95019520@N00/2347988054/" target="_blank"><img src="http://farm3.static.flickr.com/2152/2347988054_8dc9ecbfbe.jpg" border="0" alt="image029" /></a></p>

<p>图4.5.12
<h6>移动、旋转和缩放曲线</h6>
1 选择曲线。</p>

<p>2 使用移动、旋转和缩放工具来移动、旋转或缩放曲线。当创建手柄时，关闭Root on Curve 项，移动、旋转和缩放曲线并不变换开始关节。</p>

<p>3 为Translate，Rotate 和Scale 属性设置关键帧。
<h5>三毛的骨骼控制</h5>
<span style="color: #ff8000;">实例教程</span>
<h6>腿和手臂的IK双骨手柄控制</h6>
<h6>1 为四肢创建IK双骨手柄</h6>
打开蒙皮后三毛的文件。加载并运行IK双骨解算器。在Command Line 中输入下列内容：</p>

<p>loadPlugin ik2Bsolver;</p>

<p>ik2Bsolver;</p>

<p>选择主菜单Animation&gt;Skeleton&gt;IK Handle Tool&gt;Option打开设置窗口，在Current Solver中选择ik2Bsolver，双腿部分分别由LeftHip至LeftFoot、RightHip至RightFoot建立IK，两臂部分分别由LeftShoulder至LeftHand、RightShoulder至RightHand建立IK，如图。并将控制四肢的IK手柄分别命名为：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="200" valign="top">IK手柄</td>
<td width="200" valign="top">名称</td>
</tr>
<tr>
<td width="200" valign="top">左手</td>
<td width="200" valign="top">Ik_lefthand</td>
</tr>
<tr>
<td width="200" valign="top">右手</td>
<td width="200" valign="top">Ik_righthand</td>
</tr>
<tr>
<td width="200" valign="top">左脚</td>
<td width="200" valign="top">Ik_leftfoot</td>
</tr>
<tr>
<td width="200" valign="top">右脚</td>
<td width="200" valign="top">Ik_righthand</td>
</tr>
</tbody>
</table>
如图4.5.13所示。</p>

<p><a title="image031" href="http://www.flickr.com/photos/95019520@N00/2347987866/" target="_blank"><img src="http://farm3.static.flickr.com/2189/2347987866_c7e857c6c4.jpg" border="0" alt="image031" /></a></p>

<p>图4.5.13</p>

<p>如图4.5.14所示。</p>

<p><a title="image033" href="http://www.flickr.com/photos/95019520@N00/2347987496/" target="_blank"><img src="http://farm3.static.flickr.com/3168/2347987496_e69d2ec347.jpg" border="0" alt="image033" /></a></p>

<p>图4.5.14
<h6>2 编辑IK手柄的属性</h6>
选中整个骨骼根关节CenterRoot，按w键选择移动(Move)工具上下移动CenterRoot的位置。这时角色的双腿的姿态保持不变，整个骨骼跟随CenterRoot一起移动，如图。这并不是正确的运动控制，正确的运动控制应该是在CenterRoot下移的过程中，由IK手柄控制的双脚不移动位置，膝盖弯曲，整个身体做下蹲的动作。我们必须改变IK手柄的属性来达到这样的效果。 选中左脚的IK手柄ik_leftfoot，按Ctrl-A打开属性编辑器(Attribute Editor)。将IK Handle Attribute栏中的Stickiness（粘性）选项从默认的Off改为Sticky。用同样的方法将右脚IK手柄ik_rightfoot的Stickiness属性设置为Sticky。现在再次选择并上下移动CenterRoot的位置，角色就可以完成下蹲的动作了，如图4.5.15所示。</p>

<p><a title="image035" href="http://www.flickr.com/photos/95019520@N00/2347987170/" target="_blank"><img src="http://farm3.static.flickr.com/2365/2347987170_388653ef58.jpg" border="0" alt="image035" /></a><a title="image037" href="http://www.flickr.com/photos/95019520@N00/2347157365/" target="_blank"><img src="http://farm3.static.flickr.com/3072/2347157365_3887c99373.jpg" border="0" alt="image037" /></a></p>

<p>图4.5.15</p>

<p>对于双手的IK手柄则需要根据角色所做的不同动作来设置IK手柄的Stickiness属性。例如当角色用双手用力地推一个很重的物体的时候，双手在空间的位置保持不变，而身体会做出各种用力的姿势，这时就需要将IK手柄的Stickiness属性设置为Sticky。而如果角色在行走或是跳舞时，手臂基本上是跟随身体移动或是旋转，所以这时就需要将IK手柄的Stickiness属性设置为off。
<h6>3 使用极矢量约束（Pole vector constrain）控制关节链的旋转</h6>
IK双骨手柄的极矢量属性可以控制关节链平面的旋转，但是直接调整每个手柄的极矢量属性非常麻烦而且很不直观。用户可以先创建定位器，然后将定位器与IK双骨手柄进行极矢量约束。这样用户就可以直观地通过控制定位器的位置来调整极矢量的方向。选择主菜单Create&gt;Locator分别创建4个定位器（Locator），作为极矢量约束（Pole vector constrain）的目标物体。其中两个定位器（Locator）放置在上臂两肘的正后方，如图4.5.16所示</p>

<p><a title="image039" href="http://www.flickr.com/photos/95019520@N00/2347157211/" target="_blank"><img src="http://farm3.static.flickr.com/3149/2347157211_f9cf7dd27b.jpg" border="0" alt="image039" /></a>图4.5.16</p>

<p>将另外两个定位器（Locator）放置在双腿膝关节的正前方，如图4.5.17所示</p>

<p><img src="http://farm4.static.flickr.com/3030/2347156825_8cda75aabc.jpg?v=0" alt="" /> 图4.5.17</p>

<p>选择RightElbow后面的定位器（Locator）后按住Shift键增加选择控制右手的IK手柄，选择主菜单Animation&gt;Constrain&gt;PoleVector创建第一个约束。按照同样方法，先选择约束关节对应的定位器（Locator），然后按住Shift键增加选择相应的IK手柄，最后执行Animation&gt;Constrain&gt;PoleVector，依次创建其余的三个约束。这时移动创建的定位器（Locator），被约束的关节链平面会以定位器（Locator）为目标转动，如图4.5.18所示</p>

<p><a title="image043" href="http://www.flickr.com/photos/95019520@N00/2347156433/" target="_blank"><img src="http://farm3.static.flickr.com/3176/2347156433_198d7ce3bc.jpg" border="0" alt="image043" /></a>图4.5.18
<h6>脚部的控制</h6>
在角色动画中，角色的行走和跑跳运动会大量出现。在这些运动中脚部的动作是相对复杂的。现在使用已经创建的脚部骨骼已经可以调试动画了，但是操作起来既不方便也不准确。在这里介绍一种非常方便的控制方法，这种方法在角色动画中被大量地应用。
<h6>1 创建反转脚控制关节链</h6>
首先创建左脚的控制关节。为了方便操作，先选择RightFoot关节，按键盘的Ctrl+h键将其隐藏。进入Side视图，选择主菜单Animation&gt;Skeleton&gt;Joint Tool&gt;Option打开设置窗口，单击Reset Tool恢复缺省设置，在视图中创建骨骼，如图4.5.19所示</p>

<p><a title="image045" href="http://www.flickr.com/photos/95019520@N00/2347985890/" target="_blank"><img src="http://farm1.st atic.flickr.yahoo8.akadns.net/3010/2347985890_9b718b04ab.jpg" border="0" alt="image045" /></a>图4.5.19</p>

<p>将新建骨骼按照骨骼层级由上至下重命名，依次为Leftfoot_ctrl、Lefttoe_ctrl、Leftball_ctrl、Leftik_ctrl。命名的原则是控制关节的名称的前部分与蒙皮关节相对应，然后在名称后面加上Ctrl后缀为了和脚部蒙皮骨骼名称区别开来，以便于识别。如图4.5.20所示。</p>

<p><a title="image047" href="http://www.flickr.com/photos/95019520@N00/2347155717/" target="_blank"><img src="http://farm3.static.flickr.com/2034/2347155717_085ca16447.jpg" border="0" alt="image047" /></a>图4.5.20
<h6>2 将附加骨骼的关节与蒙皮骨骼的关节逐一对齐</h6>
使用移动工具，选择新建骨骼，按一次键盘Insert键后进入轴心点编辑状态，按住键盘的v键（point 捕捉的热键）将新建骨骼的关节位置进行调整，即Lefttoe_ctrl与LeftToe位置重和；Leftball_ctrl与LeftBall位置重合；Leftik_ctrl与LeftFoot位置重合，如图4.5.21所示</p>

<p><a title="image049" href="http://www.flickr.com/photos/95019520@N00/2347155605/" target="_blank"><img src="http://farm3.static.flickr.com/2221/2347155605_b88e7c2047.jpg" border="0" alt="image049" /></a>图4.5.21</p>

<p>再按一次键盘的Insert键后返回正常状态。这段附加骨骼的建立是为了控制脚部的蒙皮关节。这种控制的目的是使脚部的蒙皮关节跟随附加骨骼的相应关节一起移动或旋转。
<h6>3 用约束工具使附加骨骼控制蒙皮骨骼</h6>
下一步使用约束工具在附加骨骼与原有蒙皮骨骼之间建立控制关系。为了方便选择关节，可以打开Outliner。在Outliner窗口中选择Lefttoe_ctrl后按住Ctrl键增加选择LeftToe，选择主菜单Animation&gt;Constrain&gt;Orient&gt;Option弹出设置窗口，勾选 Maintain Offset (保持偏移量)项，单击Apply键完成操作。与此相同；在Leftball_ctrl与LeftBall之间建立方向约束（Orient Constrain）。然后选择关节Leftik_ctrl后增加选择控制腿关节的IK双骨手柄ik_leftfoot，选择主菜单Animation&gt;Constrain&gt;Point，建立点约束（Point Constrain）。如图4.5.22所示。</p>

<p><a title="image051" href="http://www.flickr.com/photos/95019520@N00/2347984968/" target="_blank"><img src="http://farm3.static.flickr.com/3174/2347984968_858c7ebb6b.jpg" border="0" alt="image051" /></a></p>

<p>图4.5.22</p>

<p>全部约束建立以后，操纵附加骨骼的各个关节的旋转属性，就可以实现对脚部骨骼的活动控制，如图4.5.23所示</p>

<p><a title="image053" href="http://www.flickr.com/photos/95019520@N00/2347984810/" target="_blank"><img src="http://farm3.static.flickr.com/2073/2347984810_7ef7e5ca2c.jpg" border="0" alt="image053" /></a></p>

<p>图4.5.23</p>

<p>恢复隐藏的RightFoot显示，然后将LeftFoot与Leftfoot_ctrl隐藏。与左脚的控制建立过程类似，创建右脚的附加骨骼并进行相应的命名，然后建立约束控制。
<h6>3 添加控制属性</h6>
脚在行走过程中的运动是循环的重复运动。在每一个周期中的抬起与落下都是相同的运动，每只脚在运动过程中都有四个关键的姿势，将这四个关键的姿势连续的重复排列就可以表现连贯的动作。这四个关键姿势分别是：</p>

<p>1． 脚跟着地、前脚掌抬起，如图</p>

<p>2． 全脚掌着地，如图</p>

<p>3． 前脚掌着地、脚跟抬起，如图</p>

<p>4． 脚尖着地、前脚掌、脚跟抬起，如图4.5.24所示</p>

<p><a title="image055" href="http://www.flickr.com/photos/95019520@N00/2347984330/" target="_blank"><img src="http://farm3.static.flickr.com/3176/2347984330_de0e166ed6.jpg" border="0" alt="image055" /></a><a title="image057" href="http://www.flickr.com/photos/95019520@N00/2347984090/" target="_blank"><img src="http://farm3.static.flickr.com/3276/2347984090_cd0a6987c2.jpg" border="0" alt="image057" /></a></p>

<p><a title="image059" href="http://www.flickr.com/photos/95019520@N00/2347983942/" target="_blank"><img src="http://farm3.static.flickr.com/2104/2347983942_05ab5ef7fe.jpg" border="0" alt="image059" /></a><a title="image061" href="http://www.flickr.com/photos/95019520@N00/2347153957/" target="_blank"><img src="http://farm3.static.flickr.com/3063/2347153957_cb80ebe240.jpg" border="0" alt="image061" /></a></p>

<p>图4.5.24</p>

<p>为了方便控制脚的运动姿态，使用驱动帧的方法用一个定制的属性的参数变化来控制脚的这四个关键姿势。首先为控制关节增加控制属性。</p>

<p>选择LeftFoot_ctrl，选择主菜单Modify&gt;Add Attribute打开设置窗口，Attribute Name指定为roll；Minimum设为-5；Maximum设为10；Default设为0，如图4.5.25所示</p>

<p><a title="image063" href="http://www.flickr.com/photos/95019520@N00/2347983722/" target="_blank"><img src="http://farm3.static.flickr.com/3051/2347983722_d12fca68a1.jpg" border="0" alt="image063" /></a>图4.5.25</p>

<p>选择RightFoot_ctrl，同样为其添加新的属性Roll，名称与设置同LeftFoot_ctrl。
<h6>4 设置驱动帧</h6>
在一个行走周期中，脚部的附加控制关节中有三个关节需要设置驱动帧，每个关节有四个关键状态。所以驱动关系是用一个驱动物体的一个属性驱动三个被驱动物体的同一个属性（旋转），而驱动帧需要设置四组，每组对应一个脚的关键姿态。</p>

<p>选择LeftFoot_ctrl，确认ChannelBox中的“RotateZ”为0；“Roll”为0。选择主菜单Animation&gt;Animate&gt;Set Driven Key&gt;Set&gt;Option打开设置窗口，单击Load Driver按钮。</p>

<p>打开Outliner窗口,选中LeftFoot_ctrl、LeftToe_ctrl、LeftBall_ctrl三个关节。在Set Driven Key窗口中单击Load Driven按钮，导入被驱动物体。然后再在“Driver”右侧栏选择“roll”属性，在“Driven”左侧栏选中三个物体，右侧栏中选择“rotateZ”属性，建立驱动关系。注意只有在“Driver”与“Driven”中的物体与属性都被高亮选中时，最下面的“Key”按钮才会变为可点击状态。</p>

<p>这时Driver与Driven的属性值都为0，脚处于第二个关键姿势——全脚掌着地。单击Key按钮设置第一组驱动帧，如图4.5.26所示</p>

<p><a title="image064" href="http://www.flickr.com/photos/95019520@N00/2347153265/" target="_blank"><img src="http://farm3.static.flickr.com/3016/2347153265_5e8e6aa8f9.jpg" border="0" alt="image064" /></a>图4.5.26</p>

<p>设置好的第一组驱动帧后设置第二组驱动帧：首先修改ChannelBox中的 “Roll”为-5，然后修改LeftFoot_ctrl 的“RotateZ”为10，其他属性不变，注意保持“Driven”栏中所有关节都被选中，单击Key按钮设置驱动帧。这一组驱动帧对应于脚的第一个关键姿态。</p>

<p>设置第三组驱动帧：首先修改ChannelBox中的 “Roll”为5，然后修改LeftFoot_ctrl 的“RotateZ”为0；修改LeftToe_ctrl 的“RotateZ”为0；修改LeftBall_ctrl的“RotateZ”为15；注意保持“Driven”栏中所有关节都被选中，单击Key按钮设置驱动帧。这一组驱动帧对应于脚的第三个关键姿态。</p>

<p>设置第四组驱动帧：首先修改ChannelBox中的 “Roll”为10，然后修改LeftFoot_ctrl 的“RotateZ”为0；修改LeftToe_ctrl 的“RotateZ”为30；修改LeftBall_ctrl的“RotateZ”为30；注意保持“Driven”栏中所有关节都被选中，单击Key按钮设置驱动帧。这一组驱动帧对应于脚的第四个关键姿态。四个驱动帧设置完成后，左脚在一个行走周期中的状态已经完整了。</p>

<p>具体参数按照下表设置。
<table border="0" cellspacing="0" cellpadding="2" width="502">
<tbody>
<tr>
<td width="87" valign="top">关键姿态</td>
<td width="90" valign="top">驱动属性</td>
<td width="117" valign="top">被驱动属性</td>
<td width="108" valign="top">被驱动属性</td>
<td width="98" valign="top">被驱动属性</td>
</tr>
<tr>
<td width="87" valign="top"></td>
<td width="90" valign="top">LeftFoot_ctrl(Roll)</td>
<td width="117" valign="top">LeftFoot_ctrl (Rotate Z)</td>
<td width="108" valign="top">LeftToe_ctrl(Rotate Z)</td>
<td width="99" valign="top">LeftBall_ctrl(Rotate Z)</td>
</tr>
<tr>
<td width="87" valign="top">1</td>
<td width="90" valign="top">-5</td>
<td width="117" valign="top">10</td>
<td width="108" valign="top">0</td>
<td width="99" valign="top">0</td>
</tr>
<tr>
<td width="87" valign="top">2</td>
<td width="90" valign="top">0</td>
<td width="117" valign="top">0</td>
<td width="108" valign="top">0</td>
<td width="99" valign="top">0</td>
</tr>
<tr>
<td width="87" valign="top">3</td>
<td width="90" valign="top">5</td>
<td width="117" valign="top">0</td>
<td width="108" valign="top">0</td>
<td width="99" valign="top">15</td>
</tr>
<tr>
<td width="87" valign="top">4</td>
<td width="90" valign="top">10</td>
<td width="118" valign="top">0</td>
<td width="109" valign="top">30</td>
<td width="100" valign="top">30</td>
</tr>
</tbody>
</table>
按照同样的方法步骤设置右脚的三个关节的驱动帧，具体参数按照下表设置。
<table border="0" cellspacing="0" cellpadding="2" width="517">
<tbody>
<tr>
<td width="74" valign="top">关键姿态</td>
<td width="119" valign="top">驱动属性</td>
<td width="119" valign="top">被驱动属性</td>
<td width="105" valign="top">被驱动属性</td>
<td width="98" valign="top">被驱动属性</td>
</tr>
<tr>
<td width="73" valign="top"></td>
<td width="120" valign="top">RightFoot_ctrl(Roll)</td>
<td width="120" valign="top">RightFoot_ctrl(Rotate Z)</td>
<td width="107" valign="top">RightToe_ctrl((Rotate Z)</td>
<td width="98" valign="top">RightBall_ctrl((Rotate Z)</td>
</tr>
<tr>
<td width="71" valign="top">1</td>
<td width="120" valign="top">-5</td>
<td width="120" valign="top">10</td>
<td width="108" valign="top">0</td>
<td width="98" valign="top">0</td>
</tr>
<tr>
<td width="70" valign="top">2</td>
<td width="120" valign="top">0</td>
<td width="120" valign="top">0</td>
<td width="109" valign="top">0</td>
<td width="98" valign="top">0</td>
</tr>
<tr>
<td width="70" valign="top">3</td>
<td width="120" valign="top">5</td>
<td width="120" valign="top">0</td>
<td width="110" valign="top">0</td>
<td width="98" valign="top">15</td>
</tr>
<tr>
<td width="69" valign="top">4</td>
<td width="120" valign="top">10</td>
<td width="120" valign="top">0</td>
<td width="111" valign="top">30</td>
<td width="98" valign="top">30</td>
</tr>
</tbody>
</table>
<h6>脊椎的IK样条曲线手柄控制</h6>
在控制人类脊椎的运动时，通常使用的IK样条曲线手柄（IK Spline Handle）。
<h6>1 为脊椎关节链创建IK样条曲线手柄</h6>
选择主菜单Animation&gt;Skeleton&gt;IK Spline Handle Tool，从靠近CenterRoot的脊椎关节CenterSpine1至CenterCollar关节创建IK Spline Handle Tool。创建顺序是先单击CenterSpine1关节，再单击CenterCollar关节。如图4.5.27所示</p>

<p><a title="image066" href="http://www.flickr.com/photos/95019520@N00/2347153077/" target="_blank"><img src="http://farm3.static.flickr.com/2350/2347153077_b4b47feb01.jpg" border="0" alt="image066" /></a>图4.5.27
<h6>2 用簇(Cluster)变形器控制样条曲线的变形</h6>
将视图窗口菜单Show中的Joints与IK Handles关闭，这时视图中只有创建IK样条曲线手柄(IK Spline Handle)时生成的NURBS曲线，选择这条NURBS曲线，按F8键进入元素（Component）级别，这时显示出曲线的四个CV点，如图4.5.28所示</p>

<p><a title="image068" href="http://www.flickr.com/photos/95019520@N00/2347982502/" target="_blank"><img src="http://farm3.static.flickr.com/3192/2347982502_6e30337ee2.jpg" border="0" alt="image068" /></a>图4.5.28</p>

<p>选择最上端的CV点，选择主菜单Animation&gt;Deform&gt;Create Cluster&gt;Option打开设置窗口，勾选Mode项的Relative。单击Create键完成操作。这时在所选CV点的位置出现“C”标志。按照同样方法将最下端以外的其余两个CV点创建簇变形器（Cluster），如图4.5.29所示</p>

<p><a title="image070" href="http://www.flickr.com/photos/95019520@N00/2347982274/" target="_blank"><img src="http://farm3.static.flickr.com/2359/2347982274_9499bc5872.jpg" border="0" alt="image070" /></a>图4.5.29</p>

<p>现在可以打开视图窗口Show下面的Joints选项，并且关闭NURBS Curves选项，然后移动不同的“C”标志可以控制脊椎的活动，如图4.5.30所示</p>

<p><a title="image072" href="http://www.flickr.com/photos/95019520@N00/2347152169/" target="_blank"><img src="http://farm3.static.flickr.com/2240/2347152169_79c4852a9e.jpg" border="0" alt="image072" /></a>图4.5.30</p>

<p>选择IK 样条曲线手柄，在通道栏（Channel Box）中调节Twist数值，可以控制上身的转动，如图4.5.31所示</p>

<p><a title="image074" href="http://www.flickr.com/photos/95019520@N00/2347981578/" target="_blank"><img src="http://farm3.static.flickr.com/2258/2347981578_9d00e502a0.jpg" border="0" alt="image074" /></a>图4.5.31</p>

<p>默认情况下创建的簇变形器（Cluster）在空间中是游离状态的，并不随着骨骼的运动而运动，为了使Cluster跟随骨骼一起运动，需要使Cluster成为骨骼的子物体。选择所有的“C”标记，按住Shift键增加选择CenterRoot关节，然后按键盘p键创建父子关系。这时移动CenterRoot时所有的簇变形器（Cluster）都随之一起运动。
<h6>定位器与手柄的整理</h6>
<h6>1 定位器与骨胳建立父子关系</h6>
用于极矢量约束的定位器（Locator）与整体骨骼是相对独立的，骨骼在运动之后，它们仍然停留在原地，因此需要将它们与骨骼建立父子关系。选择控制手臂IK的两个定位器（Locator），按住Shift键增加选择CenterCollar关节，按键盘p键建立父子关系。选择控制左腿关节链的定位器（Locator），按住Shift键增加选择左脚附加骨骼的根关节LeftFoot_ctrl，按键盘p键建立父子关系。然后选择控制右腿关节链的定位器（Locator），按住Shift键增加选择右脚附加骨骼节的根关节RightFoot_ctrl，按键盘p键建立父子关系。这时转动LeftFoot_ctrl或RightFoot_ctrl关节，定位器会跟随关节一起转动，更准确地符合人体的运动规律，如图4.5.32所示。</p>

<p><a title="image076" href="http://www.flickr.com/photos/95019520@N00/2347981096/" target="_blank"><img src="http://farm3.static.flickr.com/2029/2347981096_56280c516e.jpg" border="0" alt="image076" /></a>图4.5.32
<h6>2 显示并定位骨骼的选择手柄(Selection Handle)</h6>
为了在动画角色时，控制物体往往会被角色模型所遮挡而无法准确快捷地选中。为了能够方便地选择控制物体，例如场景中的骨骼、IK手柄或是变形器，可以在场景中显示出该物体的选择手柄(Selection Handle)，然后将选择手柄移出物体。首先，选中左脚的附加骨骼的根关节LeftFoot_ctrl，选择Display&gt;Component Display&gt;Selection Handles命令，显示该关节的选择手柄(Selection Handle)。按F9进入元素选择模式，点击Handles按钮<a title="image078" href="http://www.flickr.com/photos/95019520@N00/2347151203/" target="_blank"><img src=" http://farm3.static.flickr.com/2110/2347151203_f5c5ac837b.jpg" border="0" alt="image078" /></a>，激活选择手柄的可被选中状态，最好同时关闭其他元素类型的可选中状态。选中关节LeftFoot_ctrl的选择手柄，按W键使用Move工具将选择手柄向后移出一段距离，使其可以很方便地被选中。同理将右脚的附加骨骼的根关节RightFoot_ctrl的选择手柄也移出一段距离，如图4.5.33所示。</p>

<p><a title="image080" href="http://www.flickr.com/photos/95019520@N00/2347151075/" target="_blank"><img src="http://farm3.static.flickr.com/2210/2347151075_1581601c90.jpg" border="0" alt="image080" /></a></p>

<p>图4.5.33</p>

<p>然后用同样的方法将骨骼中的其他控制关节的选择手柄显示并移出模型。控制手腕运动的关节LeftHand、RightHand，控制手指运动的关节LeftFinger、RightFinger以及控制骨骼重心的关节CenterRoot。
<h6>3 显示并定位IK手柄的选择手柄(Selection Handle)</h6>
双手的关节很多所以也需要将IK手柄的选择手柄显示并移出模型。选中左手的IK手柄ik_lefthand，选择Display&gt;Component Display&gt;Selection Handles命令，显示该关节的选择手柄(Selection Handle)。按F9进入元素选择模式，点击Handles按钮<a title="image078" href="http://www.flickr.com/photos/95019520@N00/2347151203/" target="_blank"><img src="http://farm3.static.flickr.com/2110/2347151203_f5c5ac837b.jpg" border="0" alt="image078" /></a>，激活选择手柄的可被选中状态，最好同时关闭其他元素类型的可选中状态。选中ik_lefthand的选择手柄，按W键使用Move工具将选择手柄向上移出一段距离，使其可以很方便地被选中，如图4.5.34所示。同理将右手的IK手柄ik_lefthand的选择手柄也移出一段距离。</p>

<p><a title="image082" href="http://www.flickr.com/photos/95019520@N00/2347150887/" target="_blank"><img src="http://farm3.static.flickr.com/2089/2347150887_68a9d15a5b.jpg" border="0" alt="image082" /></a></p>

<p>图4.5.34
<h6>4 显示并定位变形器的选择手柄(Selection Handle)</h6>
脊椎使用IK样条曲线手柄控制，IK手柄的曲线又由簇变形器(Cluster)控制。由于簇变形器的“C”符号位于脊椎的关节链中，很难被选中。所以需要将簇变形器的选择手柄显示并移出模型。分别选中三个簇变形器(Cluster)，选择Display&gt;Component Display&gt;Selection Handles命令，显示该关节的选择手柄(Selection Handle)。按F9进入元素选择模式，点击Handles按钮<a title="image078" href="http://www.flickr.com/photos/95019520@N00/2347151203/" target="_blank"><img src="http://farm3.static.flickr.com/2110/2347151203_f5c5ac837b.jpg" border="0" alt="image078" /></a>，激活选择手柄的可被选中状态，最好同时关闭其他元素类型的可选中状态。分别选中三个簇变形器(Cluster)的选择手柄，按W键使用Move工具将选择手柄向前移出一段距离，使其可以很方便地被选中，如图4.5.35所示。</p>

<p><a title="image084" href="http://www.flickr.com/photos/95019520@N00/2347150267/" target="_blank"><img src="http://farm3.static.flickr.com/3212/2347150267_e51b10fafe.jpg" border="0" alt="image084" /></a>图4.5.35
<h6>表达式(Expression)控制</h6>
<h6>1控制站立姿态双脚与重心的位置关系</h6>
在人物行走运动中，四肢与身体是协调运动的，每部分的运动都有一定的规律，利用这些协调关系与运动规律可以简化动作的调试过程，简化骨骼的控制系统。</p>

<p>分析双脚的行走过程，可以归纳出一定的规律：</p>

<p>1、向前行走或向后行走时，双脚前后交替运动，骨盆在前后方向上始终位于两脚的中央。它们之间的数学关系是：</p>

<p>C=（A+B）/2</p>

<p>(C：骨盆的Z向位移；A：左脚的Z向位移；B：右脚的Z向位移)</p>

<p>2、在向侧向跨步的时候，骨盆仍然在左右方向上仍然位于两脚的中央。它们之间的数学关系是：</p>

<p>F=(D+E)/2</p>

<p>(F：骨盆的X向位移；D：左脚的X向位移；E：右脚的X向位移)</p>

<p>3、在转身动作中，双脚的转动会带动骨盆转动，它们之间的数学关系是：</p>

<p>I=(G+H)/2</p>

<p>(F：骨盆的Y向角度；D：左脚的Y向角度；E：右脚的Y向角度)</p>

<p>按照骨盆与双脚的数学关系，根据Maya表达式的语法将这种关系翻译为：</p>

<p>CenterRoot_ctrl.translateZ=(LeftFoot_ctrl.translateZ+RightFoot_ctrl.translateZ)/2-24; （注：24为调节数值）</p>

<p>CenterRoot_ctrl.translateX=(LeftFoot_ctrl.translateX+RightFoot_ctrl.translateX)/2;</p>

<p>CenterRoot_ctrl.rotateY=(LeftFoot_ctrl.rotateY+LeftFoot_ctrl.rotateY)/2</p>

<p>这些翻译的结果就是表达式控制动画的主要内容。骨盆对应的关节是CenterRoot，由于CenterRoot关节在调节动画过程中使用的地方很多，如果直接为它添加表达式会很不方便，因此需要为CenterRoot添加一个组，选择CenterRoot后按键盘ctrl+g组合键创建新的组，为这个组更名为Pelvis_ctrl。然后选择主菜单Window&gt;Animation Editors&gt;Expression Editor打开设置窗口，在“Expression Name”项填入CenterRoot_ctrl1，“Expression”项填入上述翻译结果，单击Create按钮完成创建，如图4.5.36所示</p>

<p><a title="image086" href="http://www.flickr.com/photos/95019520@N00/2347979756/" target="_blank"><img src="http://farm3.static.flickr.com/2104/2347979756_8c64f1ba75.jpg" border="0" alt="image086" /></a>图4.5.36</p>

<p>选择LeftFoot_ctrl或RightFoot_ctrl，沿着X/Z向移动或Y向旋转的时候，骨盆会随之进行相应的运动。如图4.5.37所示</p>

<p><a title="image088" href="http://www.flickr.com/photos/95019520@N00/2347149423/" target="_blank"><img src="http://farm3.static.flickr.com/2082/2347149423_130b1c4166.jpg" border="0" alt="image088" /></a></p>

<p>图4.5.37</p>

<p>当然很多时候，角色不能用这样的表达式来控制重心与双脚位置的关系。比如角色在横卧、爬行、翻跟头或是摔倒时，角色的重心就不能简单地用表达式来控制了，动画这些特殊动作或姿态需要手动调节重心与双脚的位置关系，这就需要动画师有良好的运动规律为基础才能做出生动的动画角色。
<h6>2手指的控制</h6>
在角色骨骼控制中，手部由于关节比较多，在控制的时候比较麻烦。但是手指的运动有一定的规律，如果在动画中不需要手指作特殊的动作，仅仅是一些伸手和握拳的简单动作，那么利用MAYA的表达式动画功能可以轻松的实现手部的动作控制。</p>

<p>表达式动画是用数学公式控制直观的动作变化，表达式动画中涉及的物体名称必须是唯一的，不能多个物体使用一个名称。因此，在设置表达式动画前需要调整手部各关节的名称。</p>

<p>这时可以不考虑关节的标签如何显示，因为表达式动画的内容与标签无关，需要修改的是在ChannelBox中的名称。在这里我们指定靠近手掌的指关节为第一关节，各关节名称如下：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="200" valign="top">左手</td></tr></tbody></table></p>

<p>手腕关节：LeftHand</p>

<p>手掌关节：LeftFinger
<td width="200" valign="top">食指第一节：LeftFinger_s1</td></p>

<p>食指第二节：LeftFinger_s2</p>

<p>食指第三节：LeftFinger_s3

<tr>
<td width="200" valign="top">拇指第一节：LeftThumb</td></tr></p>

<p>拇指第二节：LeftThumb1</p>

<p>拇指第三节：LeftThumb2
<td width="200" valign="top">中指第一节：LeftFinger_z1</td></p>

<p>中指第二节：LeftFinger_z2</p>

<p>中指第三节：LeftFinger_z3

<tr>
<td width="200" valign="top">无名指第一节：LeftFinger_w1</td></tr></p>

<p>无名指第二节：LeftFinger_w2</p>

<p>无名指第三节：LeftFinger_w3
<td width="200" valign="top">小指第一节：LeftFinger_x1</td></p>

<p>小指第二节：LeftFinger_x2</p>

<p>小指第三节：LeftFinger_x3



<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="206" valign="top">右手</td></tr></tbody></table></p>

<p>手腕关节：RightHand</p>

<p>手掌关节：RightFinger
<td width="193" valign="top">拇指第一节：RightThumb</td></p>

<p>拇指第二节：RightThumb1</p>

<p>拇指第三节：RightThumb2

<tr>
<td width="206" valign="top">食指第一节：RightFinger_s1</td></tr></p>

<p>食指第二节：RightFinger_s2</p>

<p>食指第三节：RightFinger_s3
<td width="193" valign="top">中指第一节：RightFinger_z1</td></p>

<p>中指第二节：RightFinger_z2</p>

<p>中指第三节：RightFinger_z3

<tr>
<td width="206" valign="top">无名指第一节：RightFinger_w1</td></tr></p>

<p>无名指第二节：RightFinger_w2</p>

<p>无名指第三节：RightFinger_w3
<td width="193" valign="top">小指第一节：RightFinger_x1</td></p>

<p>小指第二节：RightFinger_x2</p>

<p>小指第三节：RightFinger_x3



首先设置左手，选择LeftFinger关节，选择主菜单Modify&gt;Add Attribute打开设置面板，Attribute Name可以指定为grasp，Minimum设为-10，Maximum设为1，Default设为0，单击OK完成操作。这时在ChannelBox中会增加一个属性——grasp。</p>

<p>选择主菜单Window&gt;Animation Editors&gt;Expression Editor弹出设置窗口，在Expression Name栏中填入LeftFinger_grasp，在Expression栏中填入如下内容：</p>

<p>LeftFinger_s1.rotateZ=LeftFinger.grasp*11;</p>

<p>LeftFinger_s2.rotateZ=LeftFinger.grasp*12;</p>

<p>LeftFinger_z1.rotateZ=LeftFinger.grasp*11;</p>

<p>LeftFinger_z2.rotateZ=LeftFinger.grasp*12;</p>

<p>LeftFinger_w1.rotateZ=LeftFinger.grasp*11;</p>

<p>LeftFinger_w2.rotateZ=LeftFinger.grasp*12;</p>

<p>LeftFinger_x1.rotateZ=LeftFinger.grasp*11;</p>

<p>LeftFinger_x2.rotateZ=LeftFinger.grasp*12;</p>

<p>LeftThumb.rotateZ=LeftFinger.grasp*10;</p>

<p>LeftThumb_1.rotateZ=LeftFinger.grasp*10;</p>

<p>LeftThumb_1.rotateY=-LeftFinger.grasp*6;</p>

<p>填写完成后单击New Expression按钮，LeftFinger_grasp表达式出现在Selection列表中。</p>

<p>然后设置右手，选择RightFinger关节，选择主菜单Modify&gt;Add Attribute打开设置面板，Attribute Name可以指定为grasp，Minimum设为-10，Maximum设为1，Default设为0，单击OK完成操作。这时在ChannelBox中会增加一个属性——grasp。</p>

<p>选择主菜单Window&gt;Animation Editors&gt;Expression Editor弹出设置窗口，在Expression Name栏中填入RightFinger_grasp，在Expression栏中填入如下内容：</p>

<p>RightFinger_s1.rotateZ=RightFinger.grasp*11;</p>

<p>RightFinger_s2.rotateZ=RightFinger.grasp*12;</p>

<p>RightFinger_z1.rotateZ=RightFinger.grasp*11;</p>

<p>RightFinger_z2.rotateZ=RightFinger.grasp*12;</p>

<p>RightFinger_w1.rotateZ=RightFinger.grasp*11;</p>

<p>RightFinger_w2.rotateZ=RightFinger.grasp*12;</p>

<p>RightFinger_x1.rotateZ=RightFinger.grasp*11;</p>

<p>RightFinger_x2.rotateZ=RightFinger.grasp*12;</p>

<p>RightThumb.rotateZ=RightFinger.grasp*10;</p>

<p>RightThumb_1.rotateZ=RightFinger.grasp*10;</p>

<p>RightThumb_1.rotateY=RightFinger.grasp*6;</p>

<p>填写完成后单击New Expression按钮，RightFinger_grasp表达式出现在Selection列表中。</p>

<p>这时选择RightFinger或者LeftFinger后，调节其增加的属性-grasp的值，可以直接控制手部的伸展与握拳动作，如图4.5.38所示</p>

<p><a title="image090" href="http://www.flickr.com/photos/95019520@N00/2347978662/" target="_blank"><img src="http://farm3.static.flickr.com/2175/2347978662_7f0a7923b0.jpg" border="0" alt="image090" /></a>图4.5.38
<h5>本节工具解析</h5>
<h6>IK Handle</h6>
创建用于控制关节链运动的各种类型的IK手柄。</p>

<p>Animation&gt;Skeleton&gt;IK Handle Tool&gt;Option，如图4.5.39所示</p>

<p><a title="image092" href="http://www.flickr.com/photos/95019520@N00/2347978360/" target="_blank"><img src="http://farm3.static.flickr.com/3065/2347978360_3dcfde1e29.jpg" border="0" alt="image092" /></a>图4.5.39</p>

<p>·Current Solver: 设置IK手柄的解算器类型</p>

<p>·Autopriority: 选择时使用自动优先级别（对于ikRPsolver不适用）</p>

<p>·Solver Enable: 选择时IK解算器打开反向动力学定位</p>

<p>·Snap Enable: 选择时IK手柄吸附到IK手柄的终端效应器</p>

<p>·Sticky: 选择时用其他方法定位骨骼，Ikhandle保持原位置</p>

<p>·Priority: 设置优先级别（对于ikRPsolver不适用）。如果两个或多个ikSChandle交迭影响一些或所有的相同关节是很有用。Priority为1的Ikhandle首先旋转关节，下一个是Priority为2的手柄影响关节旋转，依此类推。</p>

<p>·Weight: 设置Ikhandle的权重（对于ikRPsolver、ikSCsolver不适用）</p>

<p>·POWeight: 设置位置/方向的权重。用于控制终端效应器是与IK手柄的位置匹配，还是与IK手柄的方向匹配。值为1时终端效应器尽力支持到达Ikhandle的位置，值为0时终端效应器尽力支持到达IK手柄的方向。值为0.5时终端效应器平衡支持到达Ikhandle的位置和方向。
<h6>IK Spline Handle</h6>
创建用于控制关节链运动的的IK样条曲线手柄。</p>

<p>Animation&gt;Skeleton&gt;IK Spline Handle Tool&gt;Option如图4.5.40所示</p>

<p><a title="image094" href="http://www.flickr.com/photos/95019520@N00/2347978076/" target="_blank"><img src="http://farm3.static.flickr.com/2050/2347978076_2987938331.jpg" border="0" alt="image094" /></a>图4.5.40</p>

<p>·Root On Curve:</p>

<p>如果用户把此项打开，IK 样条曲线手柄的开始关节被限制到曲线的某一位置。用户可拖拽偏移操纵器沿曲线滑动开始关节（及其子关节）。如果将此项关闭，用户可移动开始关节离开曲线。开始关节不再被限制到曲线。Maya 将忽略Offset 属性，并且开始关节不再存在偏移操纵器。如果关闭Root on Curve，用户可移动开始关节远离曲线以至没有关节可延伸到曲线，骨头直指向曲线的最近点。如果曲线是波形的，当用户向曲线移动直关节时，关节将从最近点跳向最近点。这样可以修正操作。</p>

<p>·Auto Create Root Axis</p>

<p>此选项创建开始关节的父变换节点。通过移动和旋转此变换节点，用户可通过移动和旋转开始关节而不是开始关节，可避免开始关节产生翻转。当Root on Curve 关闭时，可只打开Auto Create Root Axis 项。如果用户打开Auto Create Root Axis，若想将曲线作为运动路径，用户必须关闭Auto Parent Curve。另外一从属图循环出现，这导致警告信息的显示和错误手柄的操作。仅当用户创建IK 样条曲线手柄时，用户可在Tool Options 视窗可设置Auto Create Root Axis项。</p>

<p>·Auto Parent Curve</p>

<p>如果开始关节有父物体，此选项将曲线作为父物体的子物体；因此曲线和关节随父物体的移动而移动。如果用户创建一个手柄，手柄在骨骼根关节以下层次的关节链的关节开始。打开此项，使关节链随其父关节的移动而移动。仅当用户创建IK 样条曲线手柄时，才可在Tool Options 视窗设置此选项。</p>

<p>·Snap Curve To Root</p>

<p>如</p>

---
layout: post
title: 第二章第三节 非线性变形器（Nonlinear Deformer）的使用
categories:
- Maya
tags:
- Maya
- nonlinear deformer
- 开始maya吧
- 第二章
published: true
comments: true
---
<p><!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/second-morph-animation.html" target="_blank">回节目录选择</a>
<h5>本节概述</h5>
本节重点讲解Maya中的非线性变形工具，利用这些工具可以很方便地制作物体的变形效果，配合物体的运动轨迹，使物体的动画表现得更加生动。
<h5>扩张变形</h5>
<h6>了解扩张变形</h6>
扩张变形能沿两条轴扩张或细化所有可变形物体。它们可用于角色的创建，同时也是一个有力的建模工具。扩张变形包含手柄，它能使用户直观地控制扩张或细化作用的范围和曲率。
<h6>创建扩张变形</h6>
当创建扩张变形时，可先设置创建选项后创建变形，或使用当前创建选项直接创建变形。如果不清楚当前的创建选项设置，可先进行检查，这样可节省以后调节变形属性的时间。</p>

<p>1 选择要变形的物体。</p>

<p>2 选择Deform &gt; Create Nonlinear &gt; Flare 命令。</p>

<p>那么Maya 使用当前的创建选项创建扩张变形。</p>

<p>在场景中，非线形扩张变形手柄显示出来，作为当前的被选择物体。非线形扩张变形手柄被放置在物体的中心(和它的枢轴点)。在Outliner 中，非线形扩张变形手柄被列出（默认名：flarenHandle)。在通道盒中，flarenHandle 和flarenHandleShape 节点被选择。
<h6>编辑扩张变形效果</h6>
在创建扩张变形后，它的手柄显示在场景中，它的节点列在通道盒中。节点包括扩张手柄节点（默认名：flare<em>n</em>Handle)、扩张手柄形状节点（(flare<em>n</em>HandleShape)和扩张变形节点（默认名：flare<em>n</em>)。用户可通过编辑扩张手柄节点和非线形扩张变形节点来编辑扩张变形。可移动、旋转和缩放扩张手柄来编辑变形效果。也可以编辑扩张变形节点的可设置关键帧属性，它们被显示在通道盒中。
<h6>使用手柄操纵器编辑扩张变形</h6>
1 选择非线性扩张变形节点（默认名：flare<em>n</em>)。</p>

<p>2 选择Show Manipulator Tool（快捷键：T 键）。</p>

<p>3 注意在扩张变形手柄的操纵器。这样可使用户较为直观地编辑属性。</p>

<p>4 在场景中，选择扩张变形操纵器其中的一个手柄。按住鼠标中键左右拖动，可进行直观地编辑，通道盒也随着用户的操作而随时地更新。
<h6>通过移动、旋转或缩放手柄编辑</h6>
1 选择非线形扩张变形手柄节点（默认名：flare<em>n</em>Handle)。</p>

<p>2 移动、旋转或缩放手柄以改变变形效果。</p>

<p>3 按下键盘的Insert 键，移动或缩放手柄枢轴点，然后再次按下Insert 键。
<h6>编辑扩张变形通道</h6>
1 选择非线形扩张变形节点（默认名：flare<em>n</em>)。在场景中选择变形物体，然后在通道盒的（INPUTS 下）扩张变形节点历史中选择它们可快速的选择扩张变形节点。</p>

<p>2 在通道盒，列出了下列默认属性。</p>

<p>l?<strong>Envelope </strong>设置变形缩放系数。系统默认设置是1。</p>

<p>l?<strong>Start Flare X </strong>设置变形在下限位置沿X 轴的扩张或细化数值。扩张沿变形的局部X轴随曲线值而变化。默认值是1。</p>

<p>l?<strong>Start Flare Z </strong>设置变形在下限位置沿Z 轴的扩张或细化值。扩张变形作用沿变形的局部Z 轴到Low Bound 随曲线值变化。默认值为1。</p>

<p>l?<strong>End Flare X </strong>设置变形在上限位置沿X 轴作用的范围。变形在Low Bound 开始并沿变形的局部X 轴到High Bound 随曲线值变化。默认值为1。</p>

<p>l?<strong>End Flare Z </strong>设置变形在上限位置沿Z 轴作用的范围。变形在Low Bound 开始并沿变形的局部Z 轴到High Bound 随曲线值变化。默认值为1。</p>

<p>l?<strong>Curve </strong>设置在下限和上限之间曲线曲率（扩张曲线的轮廓）的数量。值为0时，没有弯曲（呈线形插补）。取正值时，曲线向外凸起；取负值时，曲线向内凹陷。默认值为0。</p>

<p>l?<strong>Low Bound </strong>此项设置变形沿物体局部Y 轴负向的下限。值可以取负数或0。系统默认值是-1。</p>

<p>l?<strong>High Bound </strong>此项设置变形沿物体局部Y 轴正向的上限。仅取正值（包括最小值0）。默认值为1。</p>

<p>3 使用鼠标左键在通道名上单击。</p>

<p>4 在场景中，按住鼠标中键左右移动。通过移动，用户可交互改变选择通道的值。移动鼠标时，按住Ctrl 键可进行精确地控制。按住Shift 键可进行粗略地控制。
<h5>挤压（Squash）变形</h5>
<h6>了解挤压（Squash）变形</h6>
挤压变形能使用户沿一条轴挤压或拉伸可变形物体。它们可用于创建角色(挤压和拉伸效果)和建模。挤压变形包含手柄，它能使用户以直观的方式控制挤压或拉伸效果的程度和范围。
<h6>创建挤压变形</h6>
1 选择要变形的物体。</p>

<p>2 选择Deform &gt; Create Nonlinear &gt; Squash 命令。</p>

<p>那么Maya 在当前设置创建选项下创建挤压变形。</p>

<p>挤压变形手柄作为当前被选择物体显示在场景中。挤压变形手柄（和它的枢轴点）显示在物体的中心。挤压变形手柄（默认名：squash<em>n</em>Handle)显示在Outliner 中。在通道盒中，squash<em>n</em>Handle 和squash<em>n</em>HandleShape 节点被选择。
<h6>编辑挤压变形效果</h6>
在创建一个挤压变形后，它的手柄显示在场景中，它的节点列在通道盒中。节点包括挤压手柄节点（默认名：squash<em>n</em>Handle)、挤压手柄形状节点（squash<em>n</em>HandleShape)和挤压变形节点（默认名：squash<em>n</em>)。</p>

<p>可通过编辑挤压手柄节点和挤压变形节点编辑挤压变形效果。可移动、旋转和缩放挤压手柄来编辑变形效果。也可编辑挤压变形节点的可设置关键帧属性（通道），它们被显示在通道盒中。
<h6>使用手柄操纵器进行编辑</h6>
1 选择挤压变形节点（默认名：squash<em>n</em>)。</p>

<p>2 选择Show Manipulator Tool（默认快捷键：T 键）。</p>

<p>3 注意在挤压变形手柄上的操纵器。这些能使用户交互地编辑属性。</p>

<p>4 在场景中，选择其中的一个挤压变形手柄的操纵器。按住鼠标中键移动鼠标进行直观地编辑。注意：在通道盒，数值也会相应更新。
<h6>通过移动、旋转或缩放手柄编辑</h6>
1 选择挤压变形手柄节点（默认名：squash<em>n</em>Handle)。</p>

<p>2 移动、旋转或缩放手柄以改变变形效果。</p>

<p>3 按下Insert 键，移动或旋转手柄枢轴点，然后再次按下Insert 键。</p>

<p>记住，选择Display &gt; Object Components &gt; Local Rotation Axes 命令，可以访问变形手柄的局部坐标轴；选择Display &gt; Object Components &gt; Rotate Pivots or Scale Pivots 命令，可以显示旋转和缩放轴点；选择Display &gt; Object Components &gt; Selection Handle 命令，可以显示选项手柄。
<h6>编辑挤压变形通道</h6>
通道是显示在通道盒中的可设置关键帧的属性。通道盒提供了编辑挤压变形的便利方式。使用属性编辑器可编辑所有的属性。
<h6>使用通道盒编辑挤压变形：</h6>
1 选择挤压变形节点（默认名：squashn）。在场景中选择变形物体，然后在通道盒的（INPUTS 下）节点历史中选择它们是选择挤压变形节点的一种快速方式。</p>

<p>2 在通道盒，在系统默认设置下，列出了下列通道。</p>

<p>l?<strong>Envelope </strong>设置变形缩放系数。默认值是1。</p>

<p>l?<strong>Factor</strong>（系数） 设置挤压或拉伸的数值。增加负值设置沿变形的局部Y 轴挤压；增加正值设置沿变形的局部Y 轴拉伸。默认值是0（没有挤压或拉伸）。</p>

<p>l?<strong>Expand</strong>（扩张） 此项设置的是：挤压时设置向外的扩张值，拉伸时设置向内的压缩值。最小值是0；最大值是10。默认值为1。</p>

<p>l?<strong>Max Expand Position</strong></p>

<p>l （最大扩展位置）设置上限位置和下限位置之间最大扩展范围的中心。值可在0.01（下限位置附近）到0.99 (上限位置附近)之间。默认值是0.5。</p>

<p>l?<strong>Start Smoothness</strong></p>

<p>l （初始平滑值）设置朝着下限位置的初始平滑数量（沿变形的局部负向Y 轴）。可以取0 到1 之间的数值。默认值是0。</p>

<p>l?<strong>End Smoothness</strong></p>

<p>l （终点平滑值）设置朝着下限位置的初始平滑数量（沿变形的局部正向Y 轴）。可选择0 到1 之间的值。默认值是0。</p>

<p>l?<strong>Low Bound</strong>（下限） 设置挤压变形（或者扩张变形）沿物体局部Y 轴负向下限的位置。默认值是-1。</p>

<p>l?<strong>High Bound</strong>（上限） 设置变形沿物体的局部Y 轴正向作用的上限（或拉伸）。默认值是1。</p>

<p>3 使用鼠标左键单击通道名。</p>

<p>4 在场景中，按住鼠标中键左右移动鼠标。通过移动鼠标，可交互地改变被选择通道的值。当移动鼠标时，按住键盘的Ctrl 键可进行精确地控制；按住Shift 键可进行粗略地控制。
<h5>制作小球弹跳动画（二）</h5>
在上一章中，我们分析了小球弹跳的运动规律并完成了小球弹跳的轨迹动画。在这一章中通过小球的受力分析，给小球的弹跳动画加上变形效果。</p>

<p>下面分析一下小球在极端姿态和过渡位置的受力以及形状。</p>

<p>在落地的一刹那由于受到地面的反弹力，球体被压缩积蓄能量产生弹性变形；</p>

<p>小球反弹到空中在到达最高点之前由于受到重力的作用，球体被拉长产生惯性变形；</p>

<p>在到达最高点时球体的速度为零球体恢复原状。</p>

<p>而小球在反弹过程中将要离开地面的那一刻被拉伸到最长状态。如图2.3.1所示。</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347592502/" target="_blank"><img src="http://farm3.static.flickr.com/3220/2347592502_e17d381360.jpg" border="0" alt="image001" /></a></p>

<p>图2.3.1</p>

<p>由于小球在向前跳跃的过程中接触地面时会受到阻力，因此小球在弹跳过程中会一直翻滚。</p>

<p>实例教程
<h6>1 制作小球弹跳过程中翻滚的动画</h6>
打开上一章做好的小球弹跳的文件。选中小球，在通道栏（Channel Box）中选中RotateX属性，单击鼠标右键选择Key Selected命令，设置关键帧。打开Auto Key按钮，分别在小球撞击地面的第25、49、73帧将小球的RotateX属性设置为180、360和540。
<h6>2 创建小球的挤压变形器</h6>
回到第1帧，选中小球，选择Deform &gt; Create Nonlinear &gt; Squash 命令，创建挤压变形器，如图所示。为了使变形器跟随小球一起运动，选择变形器，按Shift键增加选择小球，按p键将变形器归为小球的子物体，如图2.3.2所示。</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2347592346/" target="_blank"><img src="http://farm3.static.flickr.com/2224/2347592346_0a1eb34676.jpg" border="0" alt="image003" /></a><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2346761365/" target="_blank"><img src="http://farm3.static.flickr.com/2032/2346761365_2c104f5a71.jpg" border="0" alt="image005" /></a>图2.3.2
<h6>3制作小球的挤压的变形效果</h6>
选中通道栏中INPUT下的Squash1节点的Factor属性，单击鼠标右键选择Key Selected命令。将Factor属性设置为－0.3，然后在第25、49、73帧选择Animate &gt; Hold Current Key命令，如图2.3.3所示。</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347592142/" target="_blank"><img src="http://farm3.static.flickr.com/3061/2347592142_e5d83092c1.jpg" border="0" alt="image007" /></a></p>

<p>图2.3.3</p>

<p>在第13、37以及61帧，将小球的Factor属性设置为0，并设置关键帧，如图2.3.4所示。</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2346761147/" target="_blank"><img src="http://farm3.static.flickr.com/2103/2346761147_6e425eddc2.jpg" border="0" alt="image009" /></a></p>

<p>图2.3.4
<h6>4制作小球被拉伸的变形效果</h6>
在第2、23、25、48、50以及72帧将小球的Factor属性设置为0.3，并设置关键帧，如图2.3.5所示。</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2346760987/" target="_blank"><img src="http://farm3.static.flickr.com/2296/2346760987_062856f8f9.jpg" border="0" alt="image011" /></a></p>

<p>图2.3.5
<h6>5 调整小球的位置</h6>
由于小球的变形效果使小球在撞击地面时无法接触到地面，需要细微调整一下小球位置，如图2.3.6所示。</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2346760875/" target="_blank"><img src="http://farm3.static.flickr.com/2168/2346760875_991497f992.jpg" border="0" alt="image013" /></a></p>

<p>图2.3.6</p>

<p>可以直接在关键帧位置调节小球的TranslateY参数。也可以为小球增加一个坐标系整体调整位置。这里选择后一种方法。选中小球，按Ctrl+G成立一个组（Group），调节Group1的TranslateY参数，使小球在下落到最低点时能够接触到地面，如图2.3.7所示。</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347591656/" target="_blank"><img src="http://farm3.static.flickr.com/3254/2347591656_225622a078.jpg" border="0" alt="image015" /></a></p>

<p>图2.3.7
<h6>6 显示物体的变形动画曲线</h6>
选中小球，选择Windows &gt; Animation Editors &gt; Graph Editor，打开图表编辑器。在左侧的大纲列表中，选中Factor属性，动画曲线如图2.3.8所示。</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2347591564/" target="_blank"><img src="http://farm3.static.flickr.com/2124/2347591564_d4ba317b74.jpg" border="0" alt="image017" /></a></p>

<p>图2.3.8
<h6>7 播放动画</h6>
小球开始有弹性地向前弹跳了。
<h6>8 显示运动轨迹</h6>
选中小球，选择Animate &gt; Create Motion Trail，显示小球弹跳的运动轨迹。选择Animate &gt; Ghost Selected，显示小球在关键帧附近的形状变化，如图2.3.9所示。</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2346760525/" target="_blank"><img src="http://farm3.static.flickr.com/3235/2346760525_9dd141a3e1.jpg" border="0" alt="image019" /></a></p>

<p>图2.3.10
<h5>螺旋（Twist）变形</h5>
<h6>了解螺旋（Twist）变形</h6>
螺旋变形能沿一条轴扭曲任何可变形物体。此功能对于角色的创建和建模都是非常有用的。螺旋变形包含有手柄，它能以直观的方式控制螺旋的程度和范围。
<h6>创建螺旋变形</h6>
1 选择要变形的物体。</p>

<p>2 选择Deform &gt; Create Nonlinear &gt; Twist 命令，那么Maya 在当前创建选项下创建螺旋变形。</p>

<p>螺旋变形手柄作为当前选择物体显示在场景中。螺旋变形手柄（和它的枢轴点）被放置在物体的中心。螺旋变形手柄（默认名：twist<em>n</em>Handle）被列出在Outliner 中。在通道盒中，twist<em>n</em>Handle 和twist<em>n</em>HandleShape 节点被选择。
<h6>编辑螺旋变形的变形效果</h6>
创建螺旋变形后，它的手柄显示在场景中，它的节点列在通道盒中。节点包含螺旋手柄节点（默认名：twist<em>n</em>Handle)、螺旋手柄形状节点（twist<em>n</em>HandleShape)和螺旋变形节点（默认名：twist<em>n</em>)。用户可通过编辑螺旋手柄节点和螺旋变形节点编辑螺旋节点效果。可通过移动、旋转和缩放螺旋手柄编辑变形效果。也可编辑螺旋变形节点的可设置关键帧属性，它们显示在通道盒中。
<h6>利用手柄操纵器编辑</h6>
1 选择螺旋变形节点。（默认名：twist<em>n</em>)</p>

<p>2 选择Show Manipulator Tool（默认热键：T 键）。</p>

<p>3 注意在螺旋变形手柄上的三个操纵器，这些能交互地编辑属性。</p>

<p>4 在场景中，选择其中的一个螺旋操纵器手柄。按住中键移动鼠标可进行直观地编辑。
<h6>利用移动、旋转或缩放手柄进行编辑</h6>
1 选择螺旋变形手柄节点（默认名：twist<em>n</em>Handle)。</p>

<p>2 移动、旋转或缩放手柄，改变变形效果。</p>

<p>3 按下键盘的Insert 键，移动或旋转枢轴点，然后再次按下Insert 键。
<h6>编辑螺旋变形通道</h6>
通道是显示在通道盒中可设置关键帧的属性。通道盒提供了编辑螺旋变形通道的便利方式。使用属性编辑器可编辑所有的属性。</p>

<p>1 选择螺旋变形节点（默认名：twist<em>n</em>)。</p>

<p>在场景中选择变形物体，然后在通道盒的（INPUTS 下面）的历史节点中进行选择可快速选择挤压变形节点。注意使用Channel Control（选择Window &gt; General Editors &gt; Channel Control 命令），可控制通道盒中作为可关键帧属性（通道）的属性显示。</p>

<p>2 在通道盒中，列出下列各种属性：</p>

<p>l?<strong>Envelope </strong>设置变形缩放系数。默认值是1。</p>

<p>l?<strong>Start Angle</strong>（开始角度） 设置变形在物体变形手柄的局部Y 轴负向下限位置的扭曲度数。系统默认设置是0。</p>

<p>l?<strong>End Angle</strong>（结束角度） 设置变形在物体变形手柄的局部Y 轴正向上限位置的扭曲度数。系统默认设置是0。</p>

<p>l?<strong>Low Bound</strong>（下限） 设置变形在物体的局部Y 轴开始角度扭曲的位置。值必须是负数或0。默认值为-1。</p>

<p>l?<strong>High Bound</strong>（上限） 设置变形在物体的局部Y 轴结束角度扭曲结束的位置。值必须正数。默认值是1。</p>

<p>3 使用鼠标左键单击通道名。</p>

<p>4 在场景中，按住鼠标中键左右移动。通过移动鼠标可直观地改变选择通道的值。当用户移动鼠标时，按住Ctrl 可进行精确地控制；按住Shift 键可进行粗略地控制。
<h5>弯曲变形(Twist)</h5>
<h6>了解弯曲变形</h6>
弯曲变形能使用户沿圆弧弯曲所有的可变形物体。它们对于角色的创建和建模都非常有用。弯曲变形含有手柄，它能以直观的方式使用户控制弯曲的范围和曲率。
<h6>创建弯曲变形</h6>
1 选择要变形的物体。</p>

<p>2 选择Deform &gt; Create Nonlinear &gt; Bend 命令。</p>

<p>那么Maya 使用当前设置选项创建弯曲变形。</p>

<p>在该场景中，只有变形物体被选择时，弯曲手柄才显示。弯曲手柄（及其枢轴点）被放在物体的中心。在Outliner 中，弯曲变形被列出（默认名：bendnHandle)。在通道盒中，bendnHandle 和bendnHandleShape 节点被选择。
<h6>编辑弯曲变形效果</h6>
在创建一个弯曲变形后，它的手柄显示在场景中，它的节点列在通道盒中。节点包括弯曲手柄节点（默认名：bend<em>n</em>Handle)、弯曲手柄形状节点（默认名：(bend<em>n</em>HandleShape)和弯曲变形节点（默认名：bend<em>n</em>)。</p>

<p>用户可通过编辑弯曲手柄节点和弯曲变形节点来编辑弯曲变形。用户可通过移动、旋转和缩放变形手柄编辑变形效果；也可以编辑弯曲变形节点的可设置关键帧属性，它们显示在通道盒中。
<h6>使用手柄编辑器编辑</h6>
1 选择弯曲变形节点（默认名：bend<em>n</em>）。</p>

<p>2 选择Show Manipulator Tool（快捷键：T 键）。</p>

<p>3 注意弯曲变形手柄的操纵器。这些能使用户直观地编辑属性。</p>

<p>4 在场景中，选择其中的一个弯曲变形手柄操纵器。按住鼠标中键并移动鼠标进行直观地编辑。注意随着用户的编辑，通道盒中相应的通道数值也在相应地更新。
<h6>通过移动、旋转或缩放手柄编辑弯曲变形</h6>
1 选择弯曲变形手柄节点（默认名：bend<em>n</em>Handle)。</p>

<p>2 移动、旋转或缩放手柄以改变变形的影响。</p>

<p>3 按下键盘的Insert 键，移动或缩放手柄枢轴点，然后再次按下Insert 键。
<h6>编辑弯曲变形通道</h6>
1 选择弯曲变形节点（默认名：bend<em>n</em>)。在场景中选择变形物体，然后在通道盒的（INPUTS 下面）弯曲变形节点历史中选择它们可快速地选择弯曲变形节点。</p>

<p>2 在通道盒中，在系统默认设置下，列出了下列通道：</p>

<p>l?<strong>Envelope </strong>设置变形缩放系数。系统默认值是1。</p>

<p>l?<strong>Curvature </strong>设置弯曲数值。负值设置向着X 轴负向弯曲，正值设置向着X 轴正向弯曲。系统默认值为0，它设置没有弯曲作用。</p>

<p>l?<strong>Low Bound </strong>设置弯曲变形Y 轴负向的下限位置。值可以取负数或0，系统默认值是-1。</p>

<p>l?<strong>High Bound </strong>设置沿弯曲变形Y 轴正向弯曲的上限。值取正数（包括最小值0.0000），使用滑块可选择0.0000 到10.0000 的值。系统默认值是1。</p>

<p>3 使用鼠标左键单击通道名。</p>

<p>4 在场景中，按住鼠标中键左右拖动，可交互改变选择通道的值。当拖动鼠标时，按住Ctrl键，可进行精确地控制。按住Shift 键，可进行粗略地控制。
<h5>制作简单的角色动画</h5>
使用三维动画软件往往会专注于技术层面的问题而忽略了动画的要义。因此通过这个简单的例子，希望能够引发出你们做动画的乐趣。</p>

<p>实例教程
<h6>1 创建角色</h6>
创建三个Nurbs球体，调整其位置以及大小，如图2.3.11所示。</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2347591326/" target="_blank"><img src="http://farm3.static.flickr.com/3227/2347591326_806ffa7afe.jpg" border="0" alt="image021" /></a></p>

<p>图2.3.11</p>

<p>分别命名为head（头）、body（躯干）、left_leg（左腿）、right_leg（右腿）。这是一个最简单的角色，怎么让它生动地“活”起来呢？下面看看Maya的魔力吧。选择head、left_leg以及right_leg三个小球，然后增加选择body大球，按p键建立父子关系。打开Outliner，球体之间的层级关系如图2.3.12所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2347591162/" target="_blank"><img src="http://farm3.static.flickr.com/2262/2347591162_36ccf1e361.jpg" border="0" alt="image023" /></a>图2.3.12
<h6>2 创建弯曲变形器</h6>
选中body，选择Deform &gt; Create Nonlinear &gt; Bend 命令。用移动、缩放工具调整bend1Handle的位置及大小，在通道栏（ChannelBox）中将bend1的lowBound属性设置为零。然后在通道栏中选中bend1的Curvature属性，鼠标中键在视窗中横向拖动，角色可以作前后弯腰的动作了，如图2.3.13所示。将Curvature属性恢复为0。</p>

<p><a title="image025" href="http://www.flickr.com/photos/95019520@N00/2346760151/" target="_blank"><img src="http://farm3.static.flickr.com/3044/2346760151_4763bd7f08.jpg" border="0" alt="image025" /></a>图2.3.13</p>

<p>重新选中body，再次选择Deform &gt; Create Nonlinear &gt; Bend 命令。用移动、缩放工具调整bend2Handle的位置及大小，因此需要将bend2Handle的RotateY属性设置为90。然后在通道栏（ChannelBox）中将bend2的highBound属性设置为0.4。然后在通道栏中选中bend2的Curvature属性，鼠标中键在视窗中横向拖动，角色可以做抬腿的动作了，如图2.3.14所示。将Curvature属性恢复为0。</p>

<p><a title="image027" href="http://www.flickr.com/photos/95019520@N00/2346760037/" target="_blank"><img src="http://farm3.static.flickr.com/2227/2346760037_e32f06cc12.jpg" border="0" alt="image027" /></a>图2.3.14
<h6>3 创建螺旋变形器</h6>
选中两个创建好的弯曲变形器bendHandle1、bendHandle2，按Ctrl+h将它们隐藏。选中body，选择Deform &gt; Create Nonlinear &gt; Twist 命令。用移动、缩放工具调整twist1Handle的位置及大小。然后在通道栏中分别选中twist1的startAngle和endAngle属性，鼠标中键在视窗中横向拖动，角色可以做扭转身体的动作了，如图2.3.15所示。将startAngle和endAngle属性恢复为0。</p>

<p><a title="image029" href="http://www.flickr.com/photos/95019520@N00/2346759909/" target="_blank"><img src="http://farm3.static.flickr.com/2017/2346759909_3e0f89764f.jpg" border="0" alt="image029" /></a>图2.3.15
<h6>4 创建扩张变形器</h6>
选中创建好的弯曲变形器twistHandle1，按Ctrl+h将它们隐藏。选中body，选择Deform &gt; Create Nonlinear &gt; Squash 命令。用移动、缩放工具调整squash1Handle的位置及大小。在通道栏中将maxExpandPos属性设置为0.2；将lowBand和highBound的属性分别设置为-0.1和1.2。然后在通道栏中选中squash1的factor属性，鼠标中键在视窗中横向拖动，角色的身体可以身长和收缩了，如图2.3.16所示。将factor属性恢复为0。</p>

<p><a title="image031" href="http://www.flickr.com/photos/95019520@N00/2346759787/" target="_blank"><img src="http://farm3.static.flickr.com/2084/2346759787_ab21935fcc.jpg" border="0" alt="image031" /></a>图2.3.16
<h6>5 分析角色行走的动画规律</h6>
角色的变形器已经设定完了，角色已经可以做很多丰富的动作了。现在以制作一段走路的动画为例来说明任何简单的形体都可以做出有趣的动画。</p>

<p>首先分析角色的运动规律，这个角色的身体会在运动过程中产生适当的变形，身体的姿态曲线也可以表现出角色的情绪，这些都可以让一个角色“活”起来。任何角色变形原理都可以参照小球弹跳的变形原理来分析。角色在行走过程中可以分为两个关键姿态：</p>

<p>1． 双脚着地时，角色在积蓄力量，因此角色的整个身体会被压缩，身体向一侧扭转并且前倾。</p>

<p>2． 一脚着地，另一只脚向上抬起迈出，因此角色的身体由于向上的趋势而被拉长，身体不扭转并且略后仰。</p>

<p>确定角色单脚迈一步持续20帧，一个完整的双脚迈步的循环单位需要40帧，第40帧的姿态与第1帧的姿态相同。
<h6>6 设置角色弯曲变形器的关键帧动画</h6>
打开Outliner，选中bend1Handle和bend2Handle，选择Display&gt;Show&gt;Show Selection命令，显示弯曲变形器。选中其它变形器，按Ctrl＋h隐藏。</p>

<p>在时间条（Timeline）上回到第1帧，设置角色起始走路的第一个关键姿态——双脚着地。将bend1的curvature属性设置为-0.5，角色的身体前倾，选中通道栏中curvature属性的名称，右键点击选择Key Selected命令，设置关键帧。将bend2的curvature属性设置为0。选中通道栏中curvature属性的名称，右键选择Key Selected命令，设置关键帧。角色姿态如图2.3.17所示。</p>

<p><a title="image033" href="http://www.flickr.com/photos/95019520@N00/2346759681/" target="_blank"><img src="http://farm3.static.flickr.com/2402/2346759681_cfc0f51f76.jpg" border="0" alt="image033" /></a>图2.3.17</p>

<p>在时间条上的第10帧，设置角色走路的第二关键姿态——右脚着地，左脚向上抬起。将bend1的curvature属性设置为0.5，角色的身体后仰，选中通道栏中curvature属性的名称，右键点击选择Key Selected命令，设置关键帧。将bend2的curvature属性设置为-1，角色抬起左脚，上身向同侧倾斜。选中通道栏中curvature属性的名称，右键选择Key Selected命令，设置关键帧。角色姿态如图2.3.18所示。</p>

<p><a title="image035" href="http://www.flickr.com/photos/95019520@N00/2346759583/" target="_blank"><img src="http://farm3.static.flickr.com/3117/2346759583_9753124359.jpg" border="0" alt="image035" /></a>图2.3.18</p>

<p>在时间条（Timeline）上回到第20帧，设置角色起始走路的第三个关键姿态——双脚着地。将bend1的curvature属性设置为-0.5，角色的身体前倾，选中通道栏中curvature属性的名称，右键点击选择Key Selected命令，设置关键帧。将bend2的curvature属性设置为0。选中通道栏中curvature属性的名称，右键选择Key Selected命令，设置关键帧。</p>

<p>在时间条上的第30帧，设置角色走路的第四关键姿态——左脚着地，右脚向上抬起（与第20帧动作相反）。将bend1的curvature属性设置为0.5，角色的身体后仰，选中通道栏中curvature属性的名称，右键点击选择Key Selected命令，设置关键帧。将bend2的curvature属性设置为1，角色抬起左脚，上身向同侧倾斜。选中通道栏中curvature属性的名称，右键选择Key Selected命令，设置关键帧。角色姿态如图2.3.19所示。</p>

<p><a title="image037" href="http://www.flickr.com/photos/95019520@N00/2346759499/" target="_blank"><img src="http://farm3.static.flickr.com/2376/2346759499_6a6a3921d7.jpg" border="0" alt="image037" /></a>图2.3.19</p>

<p>在时间条（Timeline）上移到第40帧，设置角色起始走路的第三个关键姿态——双脚着地（同第1帧姿态相同）。将bend1的curvature属性设置为-0.5，角色的身体前倾，选中通道栏中curvature属性的名称，右键点击选择Key Selected命令，设置关键帧。将bend2的curvature属性设置为0。选中通道栏中curvature属性的名称，右键选择Key Selected命令，设置关键帧。
<h6>7 设置角色螺旋变形器的关键帧动画</h6>
打开Outliner，选中twist1Handle，选择Display&gt;Show&gt;Show Selection命令，显示螺旋变形器。选中其它变形器，按Ctrl＋h隐藏。</p>

<p>在时间条（Timeline）上回到第1帧，设置角色起始走路的第一个关键姿态——双脚着地，左脚在后、右脚在前。将twist1的startAngle和endAngle属性分别设置为-70和30，角色的身体扭转了，上半身与下半身向不同方向扭转。选中通道栏中startAngle和endAngle属性的名称，右键点击选择Key Selected命令，设置关键帧。角色姿态如图2.3.20所示。</p>

<p><a title="image039" href="http://www.flickr.com/photos/95019520@N00/2347590296/" target="_blank"><img src="http://farm3.static.flickr.com/2391/2347590296_3a670a571e.jpg" border="0" alt="image039" /></a>图2.3.20</p>

<p>在时间条（Timeline）上移到第20帧，设置角色起始走路的第三个关键姿态——双脚着地，右脚在后、左脚在前。将twist1的startAngle和endAngle属性分别设置为70和-30，角色的身体扭转了，上半身与下半身向不同方向扭转。选中通道栏中startAngle和endAngle属性的名称，右键点击选择Key Selected命令，设置关键帧。角色姿态如图2.3.21所示。</p>

<p><a title="image041" href="http://www.flickr.com/photos/95019520@N00/2347590152/" target="_blank"><img src="http://farm3.static.flickr.com/2408/2347590152_d8095c888a.jpg" border="0" alt="image041" /></a>图2.3.21</p>

<p>在时间条（Timeline）上移到第40帧，设置角色起始走路的第五个关键姿态——双脚着地，左脚在后、右脚在前（与第1帧相同）。将twist1的startAngle和endAngle属性分别设置为-70和30，角色的身体扭转了，上半身与下半身向不同方向扭转。选中通道栏中startAngle和endAngle属性的名称，右键点击选择Key Selected命令，设置关键帧。播放一下动画，角色已经开始原地走动了，但好像还差点什么，弹性变形！
<h6>8 设置角色扩张变形器的关键帧动画</h6>
打开Outliner，选中squash1Handle，选择Display&gt;Show&gt;Show Selection命令，显示扩张变形器。选中其它变形器，按Ctrl＋h隐藏。</p>

<p>在时间条（Timeline）上回到第1帧，设置角色起始走路的第一个关键姿态——双脚着地，身体被压缩。将squash1的factor和expand属性设置为-0.4和1，角色的身体被压扁并且横向扩张，选中通道栏中factor和expand属性的名称，右键点击选择Key Selected命令，设置关键帧。角色姿态如图2.3.22所示。</p>

<p><a title="image043" href="http://www.flickr.com/photos/95019520@N00/2346759107/" target="_blank"><img src="http://farm3.static.flickr.com/2329/2346759107_5d39d84f5e.jpg" border="0" alt="image043" /></a>图2.3.22</p>

<p>在时间条（Timeline）上移到第10帧，设置角色起始走路的第二个关键姿态——右脚着地，左脚向上抬起，身体被拉伸。将squash1的factor和expand属性设置为1和4，角色的身体被拉伸成细长状，选中通道栏中factor和expand属性的名称，右键点击选择Key Selected命令，设置关键帧。角色姿态如图2.3.23所示。</p>

<p><a title="image045" href="http://www.flickr.com/photos/95019520@N00/2347589894/" target="_blank"><img src="http://farm3.static.flickr.com/2342/2347589894_e281d6639a.jpg" border="0" alt="image045" /></a>图2.3.23</p>

<p>在时间条（Timeline）上移到第20帧，设置角色起始走路的第三个关键姿态——双脚着地，身体被压缩。将squash1的factor和expand属性设置为-0.4和1，角色的身体被压扁并且横向扩张，选中通道栏中factor和expand属性的名称，右键点击选择Key Selected命令，设置关键帧。</p>

<p>在时间条（Timeline）上移到第30帧，设置角色起始走路的第四个关键姿态——左脚着地，右脚向上抬起，身体被拉伸。将squash1的factor和expand属性设置为1和4，角色的身体被拉伸成细长状，选中通道栏中factor和expand属性的名称，右键点击选择Key Selected命令，设置关键帧。</p>

<p>在时间条（Timeline）上移到第40帧，设置角色起始走路的第三个关键姿态——双脚着地，身体被压缩（同第1帧）。将squash1的factor和expand属性设置为-0.4和1，角色的身体被压扁并且横向扩张，选中通道栏中factor和expand属性的名称，右键点击选择Key Selected命令，设置关键帧。
<h6>9设置角色的位移关键帧动画</h6>
角色在行走过程中会一直向前移动，并且重心的高度也随着走路的节奏高低变化。</p>

<p>为了使变形器能够跟随角色一起运动保持对角色形状的正确影响，需要将变形器成为body的子物体。打开Outliner，选中bend1Handle、bend2Handle、twist1Handle以及squash1Handle，然后增加选择body，按p键，建立父子关系，层级关系如图2.3.24所示。</p>

<p><a title="image047" href="http://www.flickr.com/photos/95019520@N00/2346758889/" target="_blank"><img src="http://farm3.static.flickr.com/3073/2346758889_d5be1b1588.jpg" border="0" alt="image047" /></a>图2.3.24</p>

<p>在时间条（Timeline）上回到第1帧，选中body。在通道栏中将TranslateY设置为0.9，角色重心下降。选中TranslateX和TranslateY属性的名称，右键点击选择Key Selected命令，设置关键帧。</p>

<p>在时间条（Timeline）上移到第10帧，在通道栏中将TranslateY属性设置为1.5，角色重心上升。选中TranslateY右键点击选择Key Selected命令，设置关键帧。</p>

<p>在时间条（Timeline）上移到第20帧，在通道栏中将TranslateY属性设置为0.9，角色重心下降。将TranslateX设置为-1.6，角色向前行进。选中TranslateX和TranslateY右键点击选择Key Selected命令，设置关键帧。</p>

<p>在时间条（Timeline）上移到第30帧，在通道栏中将TranslateY属性设置为1.5，角色重心上升。选中TranslateY右键点击选择Key Selected命令，设置关键帧。</p>

<p>在时间条（Timeline）上移到第40帧，选中body。在通道栏中将TranslateY设置为0.9，角色重心下降。将TranslateX设置为-3.2，角色向前行进。选中TranslateX和TranslateY属性的名称，右键点击选择Key Selected命令，设置关键帧。</p>

<p>播放动画，在一个迈步循环单元中，这个简单的角色已经走得很“神气活现”了。
<h6>10 修改动画曲线</h6>
选择Windows&gt;Animation Editors&gt;Graph Editor，打开图表编辑器。选中body，显示动画曲线。</p>

<p>选择第1帧、第20帧和第40帧的所有关键帧，点击Flat Tangent按钮<a title="image049" href="http://www.flickr.com/photos/95019520@N00/2346758793/" target="_blank"><img src="http://farm3.static.flickr.com/2387/2346758793_2e115ec132.jpg" border="0" alt="image049" /></a>，选择第10帧、和第30帧的所有关键帧，点击Spline Tangent按钮<a title="image051" href="http://www.flickr.com/photos/95019520@N00/2347589638/" target="_blank"><img src="http://farm3.static.flickr.com/3202/2347589638_1d2c849769.jpg" border="0" alt="image051" /></a>，修改后的动画曲线如图2.3.25所示。</p>

<p><a title="image053" href="http://www.flickr.com/photos/95019520@N00/2347589564/" target="_blank"><img src="http://farm3.static.flickr.com/2268/2347589564_1528066880.jpg" border="0" alt="image053" /></a></p>

<p>图2.3.25
<h6>11 设置动画曲线的无限循环</h6>
选中除TranslateX属性外的所有动画曲线，选择Curves&gt;Post Infinity&gt;Cycle命令，设置动画曲线的后无限循环。然后选择View&gt;Infinity命令，显示动画曲线的无限循环，如图2.3.26所示。</p>

<p><a title="image055" href="http://www.flickr.com/photos/95019520@N00/2347589472/" target="_blank"><img src="http://farm3.static.flickr.com/2326/2347589472_a1c764c208.jpg" border="0" alt="image055" /></a>图2.3.26</p>

<p>选中TranslateX属性的动画曲线，选择Curves&gt;Post Infinity&gt;Cycle with Offset命令，设置动画曲线的后无限循环，如图2.3.27所示。</p>

<p><a title="image057" href="http://www.flickr.com/photos/95019520@N00/2347589352/" target="_blank"><img src="http://farm3.static.flickr.com/2029/2347589352_440048256f.jpg" border="0" alt="image057" /></a>图2.3.27</p>

<p>播放动画，角色很生动地一直向前走下去。
<h6>12 思考</h6>
想想这个简单的角色还能做什么动作？如果抬腿时身体前倾，双腿着地时身体后仰，走路又是什么样子?发挥你的创造力吧！
<h5>波形变形(Wave)</h5>
<h6>了解波形变形</h6>
波形变形与正弦变形相似。正弦变形的正弦曲线在变形的局部X 轴传播，振幅沿Y 轴。波形变形正弦曲线沿变形的局部X 轴和Z 轴传播，振幅沿Y 轴。波形变形包含有手柄，使用手柄可直观地控制波形作用的范围、振幅和波长。
<h6>创建波形变形</h6>
当创建波形变形手柄时，可先设置创建选项后创建变形，或使用当前创建选项直接创建变形。如果不能确定当前的创建选项，可先检查它们。这可节省用户以后调节变形属性的时间。</p>

<p>1 选择要变形的物体。</p>

<p>2 选择Deform &gt; Create Nonlinear &gt; Wave 命令。</p>

<p>Maya 在当前创建选项下创建波形变形。</p>

<p>变形手柄作为当前被选择物体显示在场景中。波形手柄（和它的枢轴点）被放置在物体的中心。在Outliner 中，波形变形手柄被列出（默认名wave<em>n</em>Handle)。在通道盒中wave<em>n</em>Handle和wave<em>n</em>HandleShape 节点被选择。
<h6>编辑波形变形效果</h6>
在创建波形变形后，它的手柄显示在场景中，它的节点被列在通道盒中。节点包含有波形手柄节点（默认名wave<em>n</em>Handle)、波形手柄形状节点(wave<em>n</em>HandleShape)和波形变形节点（:默认名wave<em>n</em>)。可通过编辑波形手柄节点和波形变形节点编辑波形变形效果。可通过移动、旋转和缩放波形手柄来编辑变形效果。也可以编辑波形变形节点的可设置关键帧属性（通道），它们被显示在通道盒中。
<h6>使用手柄操纵器编辑</h6>
1 选择波形变形节点（默认名：wave<em>n)</em>。</p>

<p>2 选择Show Manipulator Tool（或按下热键T 键）。</p>

<p>3 注意波形变形手柄上的操纵器，这可交互地编辑变形属性。</p>

<p>4 在场景中，在波形变形手柄上选择其中的一个操纵器。按住鼠标中键并移动进行交互地进行编辑。随着用户的改变，通道盒中的数据也会即使改变。</p>

<p>注意在默认状况下Offset 和Min Radius 操纵器都位于手柄的中部。
<h6>通过移动、旋转或缩放手柄进行编辑</h6>
1 选择波形变形手柄节点（默认名：wave<em>n</em>Handle)。</p>

<p>2 移动、旋转或缩放手柄以改变变形效果。</p>

<p>3 按下键盘的Insert 键，移动或缩放手柄的枢轴点，然后再次按下Insert 键。
<h6>编辑波形变形通道</h6>
通道是显示在通道盒中可设置关键帧的属性。通道盒提供了编辑螺旋变形通道的便利方式。使用属性编辑器可编辑所有的属性。</p>

<p>1 选择波形变形节点(default name 默认名：waven)。</p>

<p>在场景中选择变形物体，然后在通道盒的（INPUTS 下面）历史节点中进行选择可快速的选择挤压变形节点。</p>

<p>2 在通道盒中，列出了下列默认通道：</p>

<p>l?<strong>Envelope </strong>设置变形缩放系数。默认值为1。</p>

<p>l?<strong>Amplitude</strong>（振幅） 设置正弦波形的振幅（最大波形数量）。默认值为0（没有波形）。</p>

<p>l?<strong>Wavelength</strong></p>

<p>l （波长） 设置正弦曲线的频率。减小波长可增加频率；增大波长可降低频率。默认值为1。</p>

<p>l?<strong>Offset</strong>（偏移） 设置正弦曲线相对于变形手柄中心的位置。改变此值可创建波纹效果。默认值为0。</p>

<p>l?<strong>Dropoff</strong>（衰减） 设置振幅衰减方式。负值设置向变形手柄的中心衰减，正值设置从变形手柄的中心向外衰减。默认值是0（没有衰减）。</p>

<p>l?<strong>Dropoff Position</strong>（衰减位置） 设置在最小半径和最大半径之间的最大振幅的位置（当Dropoff 的值不是0 时才有效）。取值范围为从0 到1。0 设置衰减位置在最小半径。1</p>

<p>l 设置衰减位置在最大半径。0.5 设置放置衰减位置放在最小半径和最大</p>

<p>l 半径的中间位置。默认值为0。</p>

<p>l?<strong>Min Radius</strong>（最小半径） 设置圆形正弦曲线最小半径。最小值是0；最大值是1。默认值为0。</p>

<p>l?<strong>Max Radius</strong>（最大半径） 设置圆形正弦曲线最大半径。最小值是0；最大值是1。默认值是1。</p>

<p>3 使用鼠标左键单击通道名。</p>

<p>4 在场景中，按住鼠标中键左右移动。通过移动鼠标，可直观地改变选择通道值。当移动鼠标时，按住Ctrl 键可进行精确地控制；按住Shift 可进行粗略地控制。
<h5>正弦变形(Sine)</h5>
<h6>了解正弦变形</h6>
正弦变形能使用户沿正弦曲线起伏可变形物体。它们可应用于角色创建和建模。正弦变形包含手柄，使用它可直观地控制正弦作用的范围、振幅和波长。
<h6>创建正弦变形</h6>
1 选择要变形的物体。</p>

<p>2 选择Deform &gt; Create Nonlinear &gt; Sine 命令。</p>

<p>Maya 使用当前创建选项创建正弦变形。</p>

<p>正弦变形手柄作为当前选择物体显示在场景中。正弦变形手柄（及其枢轴点）被放置在物体的中心。在Outliner 中，正弦变形手柄被列出（默认名是：sine<em>n</em>Handle）。在通道盒，sine<em>n</em>Handle 和sine<em>n</em>HandleShape 节点被选择。
<h6>编辑正弦变形效果</h6>
在创建正弦变形后，它的手柄显示在场景中，它的节点在通道盒列出。节点包括正弦手柄节点（默认名：sine<em>n</em>Handle)、正弦手柄形状节点（sine<em>n</em>HandleShape)和正弦变形节点（默认名：sine<em>n</em>)。可通过编辑正弦手柄节点和正弦变形节点编辑正弦变形效果。可移动、旋转和缩放正弦手柄来编辑变形效果。也可以编辑正弦变形节点的可设置关键帧属性（通道），它们显示在通道盒中。
<h6>使用手柄操纵器编辑正弦变形效果</h6>
1 选择正弦变形节点（默认名：sinen)。</p>

<p>2 选择Show Manipulator Tool（快捷键：T 键）。</p>

<p>3 注意正弦变形手柄的操纵器。这些能使用户直观地编辑属性。</p>

<p>4 在场景中，选择其中的一个正弦变形操纵器。按住鼠标中键，移动鼠标进行交互式地编辑。注意在通道盒中会即时改变用户所改变的参数值。
<h6>通过移动、旋转或缩放手柄编辑</h6>
1 选择正弦变形手柄节点（默认名：sine<em>n</em>Handle)。</p>

<p>2 移动、旋转或缩放手柄改变变形效果。</p>

<p>3 按下键盘上的Insert 键，移动或缩放手柄，然后再次按下Insert 键。记住用户可以访问变形手柄的局部坐标轴(Display &gt; Object Components &gt; Local RotationAxes)，旋转和缩放枢轴(Display &gt; Object Components &gt; Rotate Pivots 或者Scale Pivots)和选择手柄(Display &gt; Object Components &gt; Selection Handle)。
<h6>编辑正弦变形通道</h6>
通道是显示在通道盒中，可设置关键帧的属性。通道盒提供了编辑正弦变形手柄的便利方式。使用属性编辑器可编辑所有的属性。</p>

<p>1 选择正弦变形节点（默认名：sine<em>n</em>)。</p>

<p>选择变形物体，然后在通道盒的变形历史中（在INPUTS 下）选择变形节点，这是一种选择变形节点的快速方式。</p>

<p>2 在通道盒中，在系统默认设置下，列出了下列属性。</p>

<p>l?<strong>Envelope </strong>设置变形缩放系数。默认值为1。</p>

<p>l?<strong>Amplitude</strong>（振幅） 设置正弦曲线的振幅（最大波动数量）。默认值为0（没有波动）。</p>

<p>l?<strong>Wavelength</strong>（波长） 设置沿变形的局部Y 轴的正弦曲线频率。频率值增大，将减少波长；频率减小，波长增大。使用滑块可设置从-0.1000 到10.0000 间的值。默认值为2。</p>

<p>l?<strong>Offset</strong>（偏移） 设置正弦曲线与变形手柄中心的位置关系。改变该值可创建扭动效果。系统默认设置为0。</p>

<p>l?<strong>Dropoff</strong>（衰减） 设置振幅的衰减方式。负值设置向变形手柄的中心衰减（最大值是-1），正值设置从变形手柄中心向外衰减（最大值是1）。默认值为0(没有衰减)。</p>

<p>l?<strong>Low Bound</strong>（下限）设置变形沿物体的局部Y 轴负向作用的范围。值可以是负数或0。默认值为-1。</p>

<p>l?<strong>High Bound</strong>（上限）设置变形沿物体的局部Y 轴正向作用的范围。值可为正数（包括最小值0）。默认值为1。</p>

<p>3 使用鼠标左键单击通道名。</p>

<p>4 在场景中，按下鼠标中键并左右移动。通过移动鼠标，可直观地改被变选择通道的值。当移动鼠标时，按住Ctrl 键，可进行精确地控制；按住Shift 键，可进行粗略地控制。
<h5>制作鱼类游行的动画</h5>
鱼类游行的运动规律可以分解为两个主要运动：</p>

<p>一、鱼类向前游行的路线</p>

<p>二、鱼类向前游行过程中身体的摇摆</p>

<p>因此对于第一种运动，可以用路径动画来实现，第二种运动则可以使用变形工具来实现。</p>

<p>实例教程
<h6>1 创建鱼的模型</h6>
为了方便显示，在这个例子中使用Nurbs曲线表现鱼的形状，如图2.3.28所示。你可以自己创建一个鱼的实体模型。然后将曲线成组，命名为fish。</p>

<p><a title="image059" href="http://www.flickr.com/photos/95019520@N00/2347593570/" target="_blank"><img src="http://farm3.static.flickr.com/3245/2347593570_e813be7e51.jpg" border="0" alt="image059" /></a>图2.3.28
<h6>2 创建鱼的正弦变形器</h6>
选中fish，选择Deform&gt;Create Nonlinear&gt;Sine命令。设置sine1的属性，如图2.3.29所示。调节Offset参数，鱼就开始自然的摆动了。在Outliner中，选中sine1Handle，按Ctrl键增加选中fish组，按p键建立父子关系。Sine1Handle成为了fish的子物体，将随fish一起移动。</p>

<p><a title="image061" href="http://www.flickr.com/photos/95019520@N00/2347593432/" target="_blank"><img src="http://farm3.static.flickr.com/3069/2347593432_f5618b06cc.jpg" border="0" alt="image061" /></a></p>

<p>图2.3.29
<h6>3 用表达式制作鱼身体摆动的动画</h6>
选择Windows&gt;Animation Editors&gt;Expression Editor命令。打开表达式编辑器，如图2.3.30所示。</p>

<p><a title="image063" href="http://www.flickr.com/photos/95019520@N00/2347593224/" target="_blank"><img src="http://farm3.static.flickr.com/3012/2347593224_2e11c1c8cc.jpg" border="0" alt="image063" /></a>图2.3.30</p>

<p>在红色选框内，输入以下表达式：</p>

<p>sine1.offset=time;</p>

<p>点击Create按钮，生成了一个表达式Expression1。这个表达式的含义是sine1节点的offset属性随着time参数的变化而变化。Time就是时间线上的时间值，单位是秒。也就是说，当时间经过一秒时，sine1的offset值等于1。</p>

<p>播放动画，鱼已经随着时间推移，自由的摆动了。你可以通过修改表达式来控制鱼摆动的速度。
<h6>4 创建路径动画</h6>
按F3键切换到建模模块。创建一条路径曲线，命名为path，如图所示。选中path，选择Edit Curves&gt;Open/Close Curves命令，将曲线闭合。如图2.3.31所示。</p>

<p><a title="image065" href="http://www.flickr.com/photos/95019520@N00/2346762103/" target="_blank"><img src="http://farm3.static.flickr.com/3267/2346762103_15f8fdfcf0.jpg" border="0" alt="image065" /></a>图2.3.31</p>

<p>按F2键切换到动画模块。在Outliner中，先选中fish组，按住Ctrl键增加选择path，选择Animate&gt;Motion Paths&gt;Attach to Motion Path命令选项，打开选项窗口。</p>

<p>注意：鱼头的方向指向X轴的负方向，因此在选项窗口中要勾选Inverse Front选项。</p>

<p>将路径动画的时间长度设置为从第1帧到第1000帧。选项设置如图2.3.32所示。点击Attach按钮，创建鱼的动画路径。</p>

<p><a title="image067" href="http://www.flickr.com/photos/95019520@N00/2347592916/" target="_blank"><img src="http://farm3.static.flickr.com/2118/2347592916_cb4e47554c.jpg" border="0" alt="image067" /></a>图2.3.32</p>

<p>播放动画，这条鱼已经悠然自得地绕圈游动了。
<h6>5 设置鱼绕圈游行的无限循环</h6>
当播放到第1000帧以后时，鱼会停在那里不再向前游动，怎么让它继续向前游行呢？</p>

<p>选中fish，打开Graph Editor，如图2.3.33所示。</p>

<p><a title="image069" href="http://www.flickr.com/photos/95019520@N00/2347592736/" target="_blank"><img src="http://farm3.static.flickr.com/2063/2347592736_e6ce3a89c2.jpg" border="0" alt="image069" /></a>图2.3.33</p>

<p>选择Curves&gt;Post Infinity&gt;Cycle命令，创建鱼路径动画曲线的后无限循环。勾选View&gt;Infinity选项，显示无限循环，如图2.3.34所示。</p>

<p><a title="image071" href="http://www.flickr.com/photos/95019520@N00/2347592632/" target="_blank"><img src="http://farm3.static.flickr.com/3083/2347592632_0d933308f0.jpg" border="0" alt="image071" /></a>图2.3.34</p>

<p>再次播放动画，在1000帧以后，鱼也会顺畅地向前游动了。</p>

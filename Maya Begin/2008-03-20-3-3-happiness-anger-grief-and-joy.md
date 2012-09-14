---
layout: post
title: 第三章第三节 口型、喜怒哀乐
categories:
- Maya
tags:
- anger
- grief
- happiness
- joy
- Maya
- 开始maya吧
- 第三章
published: true
comments: true
---
<p><!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/third-expression.html" target="_blank">回节目录选择</a>
<h5>本节概述</h5>
表情动画中另一个重要部分就是嘴部的动画，嘴部的动画除了可以表现角色的喜怒哀乐以外，更重要的是表现角色的语言表达。下面首先讲解使用Maya在制作嘴部的动画时主要使用的是混合变形（BlendShape）工具，并且通过这个工具的一些练习，理解Maya的面部表情动画制作方法。
<h5>混合变形（Blend Shape）的使用</h5>
定义</p>

<p><em>混合变形（</em><em>Blend Shape</em><em>）是变形动画中经常使用的工具之一。它是通过将多个形状不同的物体混合产生动画，这些物体要求拓扑结构相同，形状的区别存在于物体的顶点级别，而不是外形的区别。</em></p>

<p>实例教程
<h6>1 创建混合变形物体</h6>
新建一个场景，创建一个Polygon球体，通过复制一共得到三个结构相同的球体，如图3.3.1所示</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347767806/" target="_blank"><img src="http://farm3.static.flickr.com/2093/2347767806_fc4720bb63.jpg" border="0" alt="image001" /></a>图3.3.1</p>

<p>最左边的是原始的球体，保持不变，作为混合变形的目标物体。中间的球体在物体选择级别通过缩放得到一个椭球体，右边的球体通过编辑顶点（Vertex）得到一个不规则物体，如图3.3.2所示</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2347767348/" target="_blank"><img src="http://farm3.static.flickr.com/2031/2347767348_6ca059e9d6.jpg" border="0" alt="image003" /></a>图3.3.2
<h6>2 创建混合变形</h6>
返回物体选择级别。选择中间物体后按住Shift键增加选择左面的物体，选择主菜单Animation&gt;Deform&gt;Create Blend Shape&gt;Option打开设置窗口，选择窗口菜单Edit&gt;Reset Settings恢复缺省设置，单击Create键创建的一个Blend Shape。取消所有选择，然后选择右边的物体，按住Shift键增加选择左面的物体，创建第二个Blend Shape。</p>

<p>选择主菜单Window&gt;Animation Editors&gt;Blend Shape打开控制窗口，如图3.3.3所示</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2347766874/" target="_blank"><img src="http://farm3.static.flickr.com/2004/2347766874_ce5f84e543.jpg" border="0" alt="image005" /></a>图3.3.3</p>

<p>通过调节blendShape1的控制滑块改变变形程度，场景中目标物体没有任何变化。调节blendShape2的控制滑块改变变形程度，目标物体发生变化。说明混合变形作用于物体的元素级别，物体级别的变形（位移、旋转、缩放）都不会影响混合变形的结果。
<h5>表情动画的制作</h5>
打开AA.mb文件，这是一个三毛头部的基础模型。三毛所有的脸部表情动作都将从这个基础上通过编辑修改完成。</p>

<p>在Maya 6.0版本之前，在系统内制作面部表情的方法通常有三种方法：</p>

<p>1． 是直接编辑模型的顶点。</p>

<p>2． 对头部整体添加Lattice进行变形。</p>

<p>3． 使用雕刻刀工具。</p>

<p>Maya 6.0新增的柔性编辑工具—Soft Modification Tool工具为这一工作提供更多的方法。</p>

<p>选择主菜单Modify&gt;Transformation Tools&gt;Soft Modification Tool&gt;Option 如图3.3.4所示</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2346937013/" target="_blank"><img src="http://farm3.static.flickr.com/2350/2346937013_07a05731f4.jpg" border="0" alt="image007" /></a>图3.3.4</p>

<p>柔性编辑工具可以在物体选择级别工作。它可以编辑当前模型表面上任一点，选择点附近的表面根据距离的大小，不同程度的受到编辑作用，随着距离的增加作用力逐渐减小，这种衰减的速度可以通过调整Falloff Radius与Falloff Curve进行控制。这种柔性的编辑效果非常适合修改光滑连贯的表面。</p>

<p>三毛的表情主要使用柔性编辑工具进行调节，对于个别的地方可以编辑个别的Vertex。根据角色动画的需要调节出三毛的一些典型的表情，如图3.3.5所示</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2346936615/" target="_blank"><img src="http://farm3.static.flickr.com/2072/2346936615_39264e6071.jpg" border="0" alt="image009" /></a></p>

<p>图3.3.5</p>

<p>每一行是一组相关的表情，由左至右呈现一种渐进的变化，确定了这些典型的状态后，通过Blend shape将每一组表情连贯起来表达一种情绪。</p>

<p>实例教程
<h6>1创建各种表情的混合变形</h6>
配合Shift键，由左至右逐个选择第一行的三个模型，最后选择右侧基础目标模型，选择主菜单Animation&gt;Deform&gt;Create Blend Shape&gt;Option打开设置窗口，BlendShape Node项填入Laugh，勾选In-Between与Check Topology选项，单击Create键完成创建。</p>

<p>按照相同的方法和步骤，创建另外两组表情动画，分别为新建Blendshape结点命名为Cry、Angry，选择主菜单Window&gt;Animation Editors&gt;Blend Shape打开控制窗口，每一组表情动画对应一组Blend shape控制，如图3.3.6所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2347765622/" target="_blank"><img src="http://farm3.static.flickr.com/2336/2347765622_0c4917a867.jpg" border="0" alt="image011" /></a></span></span></strong>图3.3.6
<h6>2 对混合变形节点设置关键帧动画</h6>
分别调节各自的控制滑块，可以看到三毛表情的逐渐变化。位于滑块右侧的“key”按钮可以为当前数值设置关键帧，通过在不同时间设置不同的数值，连贯播就可以产生动画效果了。</p>

<p>以一个三毛大笑的动画片段为例，在第一帧的时候单击Laugh部分的key按钮设定第一个关键帧，根据大笑的动作特点，在不同的时间确定不同的状态并设置关键帧，具体设置如下表：</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="Snap2" href="http://www.flickr.com/photos/95019520@N00/2346938493/" target="_blank"><img src="http://farm3.static.flickr.com/3121/2346938493_1a62121932.jpg" border="0" alt="Snap2" /></a></span></span></strong></p>

<p>设置完成后，播放动画就可以看到三毛的笑容了。
<h5>口型动画的制作</h5>
口型动画主要是用来表现角色说话的过程。与制作表情动画类似，首先需要制作出多个特定的动作状态。在口型动画中主要是根据不同语言发音的需要确定动作状态，三毛的口型动画有以下几种状态，如图3.3.7所示</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2347765274/" target="_blank"><img src="http://farm3.static.flickr.com/3087/2347765274_9cdbcc0aee.jpg" border="0" alt="image013" /></a></p>

<p>图3.3.7</p>

<p>实例教程
<h6>1创建口型的混合变形</h6>
选择A1模型后，按住Shift键增加选择最右侧的基础目标模型，选择主菜单Animation&gt;Deform&gt;Create Blend Shape&gt;Option打开设置窗口，选择窗口菜单Edit&gt;Reset Settings恢复缺省设置，在BlendShape Node项填入A1，单击Create键创建第一个Blend Shape。</p>

<p>按照同样方法和步骤创建其余五个Blend Shape。如图3.3.8所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347764618/" target="_blank"><img src="http://farm3.static.flickr.com/2370/2347764618_172c971b4a.jpg" border="0" alt="image015" /></a></span></span></strong>图3.3.8
<h6>2 对口型的混合变形设置关键帧动画</h6>
在设置关键帧的时候，与上述设置表情动画有所不同，在设置表情动画时，每一种情绪只有一个Blendshape参与动画，而在口型动画全过程中，需要多个Blendshape参与动画，因此在调整某一个Blendshape以后需要将其余的所有Blendshape一同设置关键帧。</p>

<p>例如：在第1帧静止状态时，单击A1~A6滑块后面的key按钮设置第一个关键帧，将时间设定在第10帧，将A6设为0.8，单击A1~A6滑块后面的key按钮完成第二个关键帧。按照同样步骤完成其余关键帧设置，具体参数如下表。</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="Snap1" href="http://www.flickr.com/photos/95019520@N00/2346938719/" target="_blank"><img src="http://farm3.static.flickr.com/3131/2346938719_94249ccb93.jpg" border="0" alt="Snap1" /></a></span></span></strong></p>

<p>播放动画就可以让三毛开口说话了。</p>

<p>小结</p>

<p>混合变形工具除了制作角色的面部表情还可以对角色的其他部位进行变形动画。由于混合变形制作简单、而且便于控制变形结果，所以混合变形是三维动画中最常用的变形工具。但是混合变形也有局限，就是两个物体之间的顶点拓扑结构必须相同，否则就会出现变形出错或是无法完成变形操作的结果。因此对角色的建模的要求就比较高，要保证角色模型的布线能够尽可能多地满足角色各种表情的要求。
<h5>本节工具解析</h5>
<h6>Blend Shape</h6>
使用多个具有相同顶点拓扑结构的几何物体制作混合变形效果。</p>

<p>Animation&gt;Deform&gt;Create Blend Shape&gt;Option 如图3.3.9所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2346934697/" target="_blank"><img src="http://farm3.static.flickr.com/2077/2346934697_81397e96b3.jpg" border="0" alt="image017" /></a></span></span></strong>图3.3.9</p>

<p>·BlendShape Node：混合变形结点名称</p>

<p>·Envelope：混合程度</p>

<p>·Origin：混合变形的坐标方式</p>

<p>·Target Shape Options：目标物体形状选项</p>

<p>In-Between：连续变形方式</p>

<p>Check Topology：检查拓扑结构</p>

<p>Delete Targets：删除目标物体
<h6>Add</h6>
在已有的混合变形效果中，添加新的变形元素。</p>

<p>Animation&gt;Deform&gt;Edit Blend Shape&gt;Add&gt;Option 如图3.3.10所示</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2347764148/" target="_blank"><img src="http://farm3.static.flickr.com/3083/2347764148_ab328ab5fa.jpg" border="0" alt="image019" /></a>图3.3.10</p>

<p>·Specify Node：指定结点</p>

<p>·BlendShape Node：混合变形节点名称</p>

<p>·Existing Nodes：已有节点</p>

<p>·Add In-Between Target：增加连续变形目标</p>

<p>Target Index：目标顺序</p>

<p>In-Between Weight：混合程度权重</p>

<p>·Target Shape Options：目标物体形状选项</p>

<p>Check Topology：检查拓扑结构
<h6>Remove</h6>
在已有的混合变形效果中，删除其中的变形元素。</p>

<p>Animation&gt;Deform&gt;Edit Blend Shape&gt;Remove&gt;Option 如图3.3.11所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2347768546/" target="_blank"><img src="http://farm3.static.flickr.com/3204/2347768546_4ce32d9dbc.jpg" border="0" alt="image021" /></a></span></span></strong>图3.3.11</p>

<p>·Specify Node：指定结点</p>

<p>·BlendShape Node：混合变形节点名称</p>

<p>·Existing Nodes：已有节点</p>

<p>·Specify Target：指定目标</p>

<p>·Target Name：目标名称
<h6>Swap</h6>
在已有的混合变形效果中，替换其中的变形元素。</p>

<p>Animation&gt;Deform&gt;Edit Blend Shape&gt;Swap&gt;Option 如图3.3.12所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2346938897/" target="_blank"><img src="http://farm3.static.flickr.com/2408/2346938897_98e20ebce6.jpg" border="0" alt="image023" /></a></span></span></strong>图3.3.12</p>

<p>·Specify Node：指定结点</p>

<p>·BlendShape Node：混合变形节点名称</p>

<p>·Existing Nodes：已有节点</p>

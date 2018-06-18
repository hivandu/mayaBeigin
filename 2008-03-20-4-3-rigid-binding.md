---
layout: post
title: 第四章第三节 刚体蒙皮
categories:
- Maya
tags:
- Maya
- rigid binding
- 开始maya吧
- 第四章
published: true
comments: true
---
<p><!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/fourth-charactor-design.html" target="_blank">回节目录选择</a></p>

<p><h4>本节概述</h4>
蒙皮是将创建的骨骼与角色模型建立控制关系的重要步骤，蒙皮方法的选择非常关键，蒙皮的效果直接影响角色的身体动作。本节主要讲解蒙皮的概念、蒙皮方法中的刚体蒙皮及使用晶格变形器(Lattice)进行间接蒙皮的方法。
<h5>了解蒙皮(Skinning)</h5>
角色的模型与骨骼制作好以后，下面需要将模型连接到骨骼上，这就是蒙皮(Bind)过程。Maya里的蒙皮方式有两种：刚体蒙皮（Rigid Skinning）与平滑蒙皮（Smooth Skinning）。
<h6>什么是刚体蒙皮(Rigid Skinning)？</h6>
定义</p>

<p><em>刚体蒙皮（Rigid Skinning</em><em>）的</em><em>每个</em><em>Nurbs</em><em>控制顶点</em><em>、多边形（Polygon）顶点或晶格点仅能被一个关节影响。</em></p>

<p>刚体蒙皮的特点是运算速度快，但是在骨骼关节部位的变形比较坚硬。这一缺陷可以使用簇变形器（Cluster）、曲肌变形器（Flexor）或晶格变形器（Lattice）对角色关节部位的弯曲进行平滑处理来弥补。平滑蒙皮（Smooth Bind）依靠各个骨骼关节对于蒙皮的权重分配来控制蒙皮作用效果，所以平滑蒙皮在由关节部位旋转造成的物体的弯曲效果也非常自然平滑。如图4.3.1所示。</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347094861/" target="_blank"><img src="http://farm3.static.flickr.com/2362/2347094861_817ff592e9.jpg" border="0" alt="image001" /></a><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2347924210/" target="_blank"><img src="http://farm3.static.flickr.com/3237/2347924210_73a7dc1eab.jpg" border="0" alt="image003" /></a>图4.3.1
<h6>什么是刚体蒙皮物体(Rigid Skin Objects)和刚体蒙皮点(Rigid Skin Points)？</h6>
在刚体蒙皮过程中，用户可绑定一个或多个可变形物体（蒙皮物体或皮肤）到骨骼。被绑定的物体成为刚体蒙皮物体，它的位置、方向和缩放受骨骼关节的控制。可变形物体的点（(CVs、顶点或晶格点)成为刚体蒙皮点或皮肤点。Maya 以关节簇(Joint Cluster)节点的方式绑定刚体物体到关节。可通过编辑关节簇(Joint Cluster)属性改变刚体蒙皮变形效果。
<h6>什么是直接蒙皮(Direct Skinning)？</h6>
定义</p>

<p><em>直接蒙皮就是将物体与骨胳通过刚体蒙皮或者平滑蒙皮方式直接绑定的蒙皮方法。</em></p>

<p>对于任何类型的模型，都可以使用平滑蒙皮方式将物体与骨骼进行直接蒙皮。对于顶点数量较少的Nurbs曲面模型或者多边形，也可以使用刚体蒙皮方式进行直接蒙皮。
<h6>什么是间接蒙皮(Indirect Skinning)？</h6>
定义</p>

<p><em>间接蒙皮是先用晶格变形器(Lattice)</em><em>或者包裹变形器（Wrap</em><em>）较少的控制点来影响外形复杂的模型表面，然后再对晶格变形器(Lattice)</em><em>或者包裹变形器（Wrap</em><em>）进行刚体蒙皮的蒙皮方式。</em></p>

<p>间接蒙皮方式比直接蒙皮方式中间增加了一个环节，就是使用变形器控制外形复杂、顶点数量极多的模型的形变。减少蒙皮点的数量才能便于使用成员编辑工具（Edit Membership Tool）以及元素编辑器（Component Editor）对蒙皮点的权重进行调整。</p>

<p>在这一节中我们对角色的身体的躯干以及手的部分采用刚体蒙皮（Rigid Bind）与晶格变形器(Lattice)结合的间接蒙皮方式，其余部分使用刚体蒙皮的直接蒙皮方式。
<h5>刚体蒙皮的绑定与编辑</h5>
<h6>绑定刚体蒙皮(Rigid Bind)</h6>
1 选择一个或多个可变形物体，然后选择骨骼的根关节或肢体链的父关节。</p>

<p>2 选择Skin &gt; Bind Skin &gt; Rigid Bind。</p>

<p>Maya 使用当前设置的刚体蒙皮选项绑定蒙皮。
<h6>恢复绑定姿势(Go to Bind Pose)</h6>
绑定姿势是当用户绑定蒙皮时骨骼的初始姿势。当用户在调整蒙皮后角色的骨骼时，骨骼的动作会引起皮肤的变形。唯一不引起皮肤变形的姿势是绑定姿势。如果用户要蒙皮另外的物体或添加影响物体，必须回到绑定姿势。</p>

<p>1 选择角色的骨骼。</p>

<p>2 选择Skin &gt; Go to Bind Pose 命令。</p>

<p>骨骼回到了它的绑定姿势。</p>

<p>如果关节的任何一个属性被锁定，那么骨骼将不能立即回到绑定姿势。关节属性可被约束(Constrain)、表达式(Expression)以及IK手柄锁定。这些功能为了驱动某些关节的属性值，或为了其它的用途而将属性锁定，而导致关节无法回到绑定姿势。然而，如果用户想让骨骼系统回到绑定姿势，必须首先使正在锁定属性的节点失效。使节点失效的快速方式是：选择Modify &gt; Disable Nodes &gt; All，然后选择Skin &gt; Go to Bind Pose，然后选择Modify &gt; Enable Nodes &gt; All，使所有的节点再次恢复作用。</p>

<p><strong> </strong>
<h6>编辑刚体蒙皮点权重(Edit Rigid Skin Point Weight)</h6>
使用元素编辑器（Component Editor），用户可直接修改刚体蒙皮点的权重值。
<h6>查询刚体蒙皮点权重</h6>
1 选择要编辑权重的刚体蒙皮点。</p>

<p>2 选择Windows &gt; General Editors &gt; Component Editor。把元素编辑器（Component Editor）打开。元素编辑器中显示了当前在工作空间被选择的元素。</p>

<p>3 在Rigid Skin栏中，Joint Clusters 标签下列出了使用刚体蒙皮绑定到骨骼关节的CVs、顶点或晶格点的权重。
<h6>修改刚体蒙皮点的权重</h6>
1 在元素编辑器（Component Editor）的伸展栏中，单击要编辑的元素信息输入栏。元素编辑器中显示的元素与工作空间中被选中的元素相对应。</p>

<p>2 输入新数值。
<h6>分离刚体蒙皮的皮肤(Detach Skin)</h6>
在用户已绑定蒙皮后，可能想修改骨骼、改变绑定姿势或对皮肤做进一步的建模。为完成上述操作，必须先分离皮肤和骨骼，当用户完成其它操作后，再次绑定蒙皮。<strong> </strong></p>

<p>1 选择骨骼。</p>

<p>2 使用当前设置的分离选项，选择Skin &gt; Detach Skin
<h6>分离和连接骨骼(Attach and Detach Skeleton)</h6>
从蒙皮物体中分离骨骼，不锁定物体的变换属性，使用户可重新定位它们。与分离皮肤不同，分离骨骼保留了刚体蒙皮点组和刚体蒙皮点权重。如果用户想直接移动、旋转或缩放蒙皮物体而不改变关节对应影响的刚体蒙皮点，分离和连接骨骼操作是特别有用的。
<h6>分离骨骼</h6>
1 选择骨骼的根关节，或骨骼中的任何关节。</p>

<p>2 选择Skin &gt; Edit Rigid Skin &gt; Preserve Skin Groups &gt; Detach Skeleton。</p>

<p>现在，蒙皮物体恢复到未变形状态；物体变换属性（Translate，Rotate、Scale）不被锁定，所以可移动、旋转或缩放物体。
<h6>连接骨骼</h6>
1 选择骨骼的根关节，或骨骼中其它的任何关节。</p>

<p>2 Select Skin &gt; Edit Rigid Skin &gt; Preserve Skin Groups &gt; Reattach Skeleton。
<h6>分离和连接选择关节(Attach and Detach Joint)</h6>
这个过程与分离和连接骨骼相似，它只是使用于选择的关节。从蒙皮物体中分离选择关节，它们影响物体不锁定的属性，所以用户可重新定位它们。分离选择的关节后，这个过程保留了刚体蒙皮点组和刚体蒙皮点权重。如果用户想直接移动、旋转或缩放某些蒙皮物体，而不改变关节对应影响的刚体蒙皮点，分离和连接选择的关节是特别有用的。
<h6>分离选择的关节</h6>
1 选择用户要分离的关节。</p>

<p>2 选择Skin &gt; Edit Rigid Skin &gt; Preserve Skin Groups &gt; Detach Selected Joints。</p>

<p>蒙皮物体恢复到未变形位置。物体的变换(Translate, Rotate, and Scale)属性现在不被锁定，所以用户可移动、旋转或缩放物体。
<h6>重新连接选择的关节</h6>
1 选择需要重新连接的关节。</p>

<p>2 选择Skin &gt; Edit Rigid Skin &gt; Preserve Skin Groups &gt; Reattach Selected Joints。
<h6>创建屈肌(Create Flexor)</h6>
1 将骨骼恢复到绑定姿势。</p>

<p>2 如果用户想创建一个或多个关节晶格、关节造型或关节簇屈肌，选择要创建屈肌的关节。</p>

<p>3 如果用户想创建一个或多个晶格或骨头造型屈肌，选择要创建屈肌的骨头。</p>

<p>4 选择Skin &gt; Edit Rigid Skin &gt; Create Flexor。
<h6>复制屈肌(Copy Flexor)</h6>
在创建一个屈肌并调整它后，用户可能在其它的地方需要一个相似的屈肌。例如，如果环绕一个人物的左肘关节创建屈肌，用户可能确定在右肘关节创建一个相似的屈肌。当用户复制屈肌时，所有的属性值和连接关系被复制。</p>

<p>1 进入绑定姿势（Skin &gt; Go to Bind Pose)。</p>

<p>2 选择屈肌。</p>

<p>3 选择要复制屈肌的关节。</p>

<p>4 选择Skin &gt; Edit Rigid Skin &gt; Copy Flexor。
<h5>为三毛进行蒙皮</h5>
实例教程
<h6>1 制作角色上身的晶格变形器</h6>
为角色制作Lattice时，一般是上身用一个晶格（Lattice）包围、臀部用一个晶格（Lattice）包围。首先，制作包围上身的Lattice。将当前视图切换至Front，选择三毛的身体、上衣、腰带、所有纽扣、裤子，按F9键进入顶点元素（Vertex）级别，选择上半身的顶点（Vertex），注意选择时需要包括一部分裤子的顶点（Vertex），如图4.3.2</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2347938318/" target="_blank"><img src="http://farm3.static.flickr.com/2223/2347938318_b3d0d6885f.jpg" border="0" alt="image005" /></a>图4.3.2</p>

<p>选定多边形顶点（Vertex）以后，选择主菜单Deform&gt;Create Lattice&gt;Option打开设置面板，在Divisions中的分别输入8，8，5，然后单击Create创建晶格变形器（Lattice），如图4.3.3所示。</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347937820/" target="_blank"><img src="http://farm3.static.flickr.com/2306/2347937820_8ac15266dc.jpg" border="0" alt="image007" /></a>图4.3.3
<h6>2 制作角色臀部的晶格变形器</h6>
上身的晶格（Lattice）制作好以后，开始创建臀部的晶格（Lattice）。选择三毛的身体、上衣、腰带、所有纽扣、裤子，按F9键进入顶点（Vertex）级别。臀部的晶格（Lattice）与上身的晶格（Lattice）应该是紧接在一起，中间不要有没有被这两个晶格控制的顶点（Vertex），否则会给角色控制带来麻烦。这样就需要紧接着上身的晶格（Lattice）控制的顶点（Vertex）选择臀部的顶点（Vertex）。选择主菜单Window&gt;Relationship Editors&gt;Deformer Sets，在弹出窗口的左侧显示出上一步创建的晶格（Lattice）的集合（Set）名称——ffd1Set，选择ffd1Set后选择Relationship Editor窗口菜单Edit&gt;Select Set Members，如图4.3.4所示。</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2347107875/" target="_blank"><img src="http://farm3.static.flickr.com/2303/2347107875_e34e649339.jpg" border="0" alt="image009" /></a>图4.3.4</p>

<p>这时为三毛上身创建的晶格（Lattice）控制的顶点（Vertex）全部以高亮显示，如图4.3.5所示。</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2347937080/" target="_blank"><img src="http://farm3.static.flickr.com/2165/2347937080_ae337278b7.jpg" border="0" alt="image011" /></a>图4.3.5</p>

<p>现在选择创建臀部晶格的顶点。在这里需要使用Shift键的一个选择技巧：当按住Shift键选择物体时，未被选择的物体会加入到选择集合中，已被选择的物体会被排除出当前选择集合，使用这个方法可以准确的排除上身晶格控制的顶点，而且选中臀部晶格控制的顶点。这次的选择需要两个步骤，首先，按住Shift键由下向上选择所有臀部将要包括的顶点和一部分上身晶格控制的顶点，这时两部分的分界线已经产生了，如图4.3.6所示。</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2347936586/" target="_blank"><img src="http://farm3.static.flickr.com/2286/2347936586_028222c4cb.jpg" border="0" alt="image013" /></a>图4.3.6</p>

<p>然后按住Ctrl键框选上半身余下的顶点来取消对它们的选择，这时的选择范围是完整的臀部晶格控制范围，如图4.3.7所示。</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347936048/" target="_blank"><img src="http://farm3.static.flickr.com/3233/2347936048_83b4456b68.jpg" border="0" alt="image015" /></a>图4.3.7</p>

<p>选定顶点以后，选择主菜单Deform&gt;Create Lattice&gt;Option打开设置面板，在Divisions中的分别输入8，5，3，然后单击Create创建晶格，如图4.3.8所示。</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2347935680/" target="_blank"><img src="http://farm3.static.flickr.com/2365/2347935680_33894f15fe.jpg" border="0" alt="image017" /></a>图4.3.8
<h6>3 制作角色手部的晶格变形器</h6>
手的每个关节以后都要使用曲肌变形器（Flexor）进行控制，但是大拇指的根关节活动情况比较特殊，比其它四个手指稍微复杂一些，使用曲肌变形器（Flexor）的效果不是很理想，因此需要用晶格（Lattice）来控制这部分受影响的顶点（Vertex）。</p>

<p>进入Top视图，选择将要加入晶格的顶点，选择主菜单Deform&gt;Create Lattice&gt;Option打开设置面板，在Divisions中的分别输入6，3，5，然后单击Create创建晶格，如图4.3.9所示。</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2347935316/" target="_blank"><img src="http://farm3.static.flickr.com/2179/2347935316_4cb358c035.jpg" border="0" alt="image019" /></a>图4.3.9</p>

<p>对于另一只手，使用同样的方法制作晶格即可。到此为止，三毛身体上需要制作的晶格变形器已经全部完成，下一步可以将模型与骨骼进行刚体蒙皮。
<h6>4 刚体蒙皮</h6>
这一步工作的目的是将物体级别的全部晶格变形器加上不受晶格控制的其余定点与骨骼进行蒙皮。通常情况下，眼睛不参加与骨骼的绑定，而是通过在相应关节上进行父化来控制。将眼球与眼睑隐藏后，选择视窗菜单Show&gt;Deformers将Lattice关闭显示，选择三毛当前显示的全部模型，按F9键进入顶点元素（Vertex）级别，下面的操作与第二步方法类似，选择主菜单Window&gt;Relationship Editors&gt;Deformer Sets，在弹出窗口的左侧选择ffd1Set、ffd2Set、ffd3Set、ffd4Set，然后选择Relationship Editor窗口菜单Edit&gt;Select Set Members，这样所有晶格控制的顶点都被选择，如图4.3.10所示。</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2347105413/" target="_blank"><img src="http://farm3.static.flickr.com/3044/2347105413_f348017742.jpg" border="0" alt="image021" /></a>图4.3.10</p>

<p>按住Shift键，框选全部的顶点，这时选区被反选，如图4.3.11所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2347105131/" target="_blank"><img src="http://farm3.static.flickr.com/2106/2347105131_91c1399e7c.jpg" border="0" alt="image023" /></a>图4.3.11</p>

<p>选中不受所有晶格控制的顶点以后，需要增加选择物体级别的所有晶格，这样的选择方式需要使用Outliner或者Hypergraph。在这里我们使用Outliner，选择主菜单Window&gt;Outliner打开视窗，找到ffd1Lattice~ffd4Lattice和与其对应的ffd1Base~ffd4Base，按住Ctrl键依次增加对它们的选择。这时已经将物体级别的全部晶格变形器和不受晶格控制的其余顶点选择完毕。这时可以打开视窗菜单Show&gt;Deformers将Lattice显示出来，如图4.3.12所示。</p>

<p><a title="image025" href="http://www.flickr.com/photos/95019520@N00/2347934270/" target="_blank"><img src="http://farm3.static.flickr.com/2107/2347934270_80a35b3c20.jpg" border="0" alt="image025" /></a>图4.3.12</p>

<p>选择完成后，按住Ctrl键，在Outliner中选择骨骼根关节，选择主菜单Skin&gt;Bind Skin&gt;Rigid Bind进行蒙皮，如图4.3.13所示。</p>

<p><a title="image027" href="http://www.flickr.com/photos/95019520@N00/2347104433/" target="_blank"><img src="http://farm3.static.flickr.com/3191/2347104433_e398bcb31c.jpg" border="0" alt="image027" /></a>图4.3.13
<h6>5 调节蒙皮点的分配及其权重值（Skin Weight）</h6>
进行刚体蒙皮以后，模型的顶点（Vertex）以及晶格点（Lattice Point）会受到邻近关节的控制，默认的蒙皮结果一般不能实现准确的变形，用户必须通过手动操作进行调整。包括调节受关节影响的蒙皮点的分配及其权重值（Skin Weight）。</p>

<p>调节受关节影响顶点的分配需要使用成员编辑工具（Edit Membership Tool）和Artisan的绘制集合成员工具（Paint Set Membership Tool）；调节它们的权重值（Weight）需要使用元素编辑器（Component Editor）和Artisan的绘制簇权重工具（Paint Cluster Weight Tool）。</p>

<p>在蒙皮时角色的身体姿势是一种缺省状态，这时的成员（Membership）和权重值（Weight）仅仅适合当前的姿势。当角色开始动作后，蒙皮就会出现不自然的变形，所以在调整成员（Membership）和权重值（Weight）时需要不断的运动角色的各个关节，调节的最终目的是让角色进行各种运动时蒙皮都能保持比较自然的变形。</p>

<p>以肩部调节为例，选择肩关节LeftShoulder，使用旋转工具将其旋转一定角度，选择主菜单Deform&gt;Edit Membership Tool，此关节控制的晶格点（Lattice Point）以高亮显示出来，如图4.3.14所示。</p>

<p><a title="image029" href="http://www.flickr.com/photos/95019520@N00/2347933636/" target="_blank"><img src="http://farm3.static.flickr.com/2399/2347933636_ed1f5580e0.jpg" border="0" alt="image029" /></a>图4.3.14</p>

<p>这时的控制情况不是很理想，需要进行调整。按住Shift键，可以增加新的顶点或晶格点（Lattice Point），按住Ctrl键，可以取消此关节对该顶点或晶格点（Lattice Point）的影响。LeftShoulder的控制范围不包括肘关节的顶点，调整以后的情况如图4.3.15所示。</p>

<p><a title="image031" href="http://www.flickr.com/photos/95019520@N00/2347933134/" target="_blank"><img src="http://farm3.static.flickr.com/2258/2347933134_8cbf3b0705.jpg" border="0" alt="image031" /></a>图4.3.15</p>

<p>取消LeftShoulder对肘关节蒙皮的控制，蒙皮出现不正确的变形，这时应该使用Edit Membership Tool 工具增加LeftElbow关节对这部分的控制，如图4.3.16。</p>

<p><a title="image033" href="http://www.flickr.com/photos/95019520@N00/2347103037/" target="_blank"><img src="http://farm3.static.flickr.com/2057/2347103037_db83c7431c.jpg" border="0" alt="image033" /></a>图4.3.16</p>

<p>使用Edit Membership Tool以后，可以开始调节晶格点（Lattice Point）的权重值（Weight）。选择主菜单Window&gt;General Editors&gt;Component Editor打开设置面板。如图4.3.17所示。</p>

<p><a title="image036" href="http://www.flickr.com/photos/95019520@N00/2347932160/" target="_blank"><img src="http://farm3.static.flickr.com/2196/2347932160_60432d080a.jpg" border="0" alt="image036" /></a>图4.3.17</p>

<p>Component Editor上有用于调节Weight值的三种Tab，Weighted Deformers用于修改簇（Cluster）的权重值（Weight）；Rigid Skins用于修改进行刚体蒙皮后蒙皮点的权重值（Weight）；Smooth Skins用于修改进行平滑蒙皮后的权重值（Weight）。三毛的蒙皮使用的是刚体蒙皮，因此需要调节Rigid Skins下面的值。</p>

<p>在调节数值的时候，可以将多个数值选定后同时输入新数值，也可以使用下面的滑动条来调节。肩部的调节结果如图4.3.18所示。</p>

<p><a title="image037" href="http://www.flickr.com/photos/95019520@N00/2347102347/" target="_blank"><img src="http://farm3.static.flickr.com/2026/2347102347_da49d6a461.jpg" border="0" alt="image037" /></a>图4.3.18</p>

<p>LeftShoulde关节调节好以后，继续调节LeftElbow关节。肘关节在转动时不影响上衣的袖口部分，由于肘部关节将要使用曲肌变形器（Flexor）工具进行控制，调节时只需要分配正确的Vertex即可，对Weight值的调节不需要非常精确，如图4.3.19所示。</p>

<p><a title="image039" href="http://www.flickr.com/photos/95019520@N00/2347931088/" target="_blank"><img src="http://farm3.static.flickr.com/2082/2347931088_2c191eb62e.jpg" border="0" alt="image039" /></a>图4.3.19</p>

<p>然后是手腕关节的调节。手腕关节的控制将要使用曲肌变形器（Flexor），因此分配好适当的晶格点和顶点即可，对于蒙皮顶点的权重值不需要非常精确，如图4.3.20所示。</p>

<p><a title="image041" href="http://www.flickr.com/photos/95019520@N00/2347101105/" target="_blank"><img src="http://farm3.static.flickr.com/3096/2347101105_b1267f0de8.jpg" border="0" alt="image041" /></a>图4.3.20</p>

<p>手指的关节全部都使用曲肌变形器（Flexor）控制，除拇指以外的手指运动很规则，在静止状态下调整好晶格点（Lattice Point）和顶点（Vertex）即可。调节拇指时需要一边旋转关节，一边调整晶格点（Lattice Point）和顶点（Vertex）的分配，尽可能的让手指的运动十分自然，如图4.3.21所示。</p>

<p><a title="image043" href="http://www.flickr.com/photos/95019520@N00/2347930368/" target="_blank"><img src="http://farm3.static.flickr.com/3023/2347930368_f52e1781d7.jpg" border="0" alt="image043" /></a>图4.3.21</p>

<p>最后调节骨盆部分的晶格点（Lattice Point）分布。调节的目的是使大腿部分的运动自然灵活，主要是向两侧分腿和前后抬腿运动。选择LeftHip关节，向外侧或前后旋转一定的角度后调节晶格点（Lattice Point）分布。正常情况下，一侧腿部运动会对另一侧的裤子产生影响，因此晶格点（Lattice Point）或者顶点（Vertex）的权重值不应该沿着中分线严格划分，在中间交接部分是一个过渡阶段。由于在创建Lattice时考虑到这一点，Lattice在正中间没有划分，是沿着中线对称创建的，这一步调解工作会比较容易，两条腿的Lattice Point应该对称调节，如图4.3.22所示。</p>

<p><a title="image045" href="http://www.flickr.com/photos/95019520@N00/2347100359/" target="_blank"><img src="http://farm3.static.flickr.com/3099/2347100359_5bc615d808.jpg" border="0" alt="image045" /></a>图4.3.22</p>

<p>三毛骨骼的调整基本完成，在晶格点或顶点数量不多的情况下，可以逐个对其调整，对于复杂的模型，调整顶点的工作量会很大，可以使用Artisan的Paint Set Membership Tool工具。</p>

<p>首先选择蒙皮表面，然后选择主菜单Deform&gt;Paint Set Membership&gt;Option打开设置窗口，根据晶格点或顶点增减的需要调节设置后直接用笔刷绘制。
<h6>6 为关节添加曲肌变形器（Flexor）</h6>
设定权重值以后，在三毛主要的活动关节加入曲肌变形器（Flexor）进行控制。以肘部关节为例，选择LeftElbow关节，选择主菜单Skin&gt;Edit Rigid Skin&gt;Create Flexor，在Lattice Options中采用缺省数值，按Create键，创建曲肌变形器（Flexor）。如图4.3.23所示。</p>

<p><a title="image047" href="http://www.flickr.com/photos/95019520@N00/2347929400/" target="_blank"><img src="http://farm3.static.flickr.com/3178/2347929400_f32a3e6382.jpg" border="0" alt="image047" /></a>图4.3.23</p>

<p>创建的曲肌变形器（Flexor）大小可能不太合适，直接调整Flexor的大小会影响蒙皮的外形，调整时需要将曲肌变形器（Flexor）在整体组（Hierarchy and Combinations）级别选定，选择当前的曲肌变形器（Flexor）后按键盘的向上箭头键，这时选择的是曲肌变形器（Flexor）的组级别。另一种方法是选择Flexor后，打开Outliner窗口，按F键将当前选定的曲肌变形器（Flexor）突出显示。当前选择的是jointFfd1Lattice项，按住Ctrl键增加选择jointFfd1Base项，或者直接选择jointFfd1LatticeGroup也可以选择Flexor的整体组级别。这时缩放曲肌变形器（Flexor）不会影响蒙皮的外形，如图4.3.24所示。</p>

<p><a title="image049" href="http://www.flickr.com/photos/95019520@N00/2347099161/" target="_blank"><img src="http://farm3.static.flickr.com/2238/2347099161_59e11e4b82.jpg" border="0" alt="image049" /></a>图4.3.24</p>

<p>创建好的曲肌变形器（Flexor）需要进一步的调整，选择曲肌变形器（Flexor），在SHAPES项目下调节参数可以使关节的运动更加自然。</p>

<p>使用同样的方法创建手腕和手指上的全部曲肌变形器（Flexor），根据各个关节的活动情况调节Channel Box中的参数。如图4.3.25所示。</p>

<p><a title="image051" href="http://www.flickr.com/photos/95019520@N00/2347928182/" target="_blank"><img src="http://farm3.static.flickr.com/3202/2347928182_8ccbc63d01.jpg" border="0" alt="image051" /></a>图4.3.25</p>

<p>使用同样的方法创建腿部关节的Flexor，根据各个关节的活动情况调节Channel Box中的参数。如图4.3.26所示。</p>

<p><a title="image053" href="http://www.flickr.com/photos/95019520@N00/2347097843/" target="_blank"><img src="http://farm3.static.flickr.com/3191/2347097843_b7664c1d7c.jpg" border="0" alt="image053" /></a>图4.3.26
<h6>7 曲肌变形器（Flexor）的复制</h6>
创建并调节好一侧骨骼的曲肌变形器（Flexor）以后，需要在另一侧创建同样的曲肌变形器控制。在已有曲肌变形器的基础上，可以使用Copy Flexor工具将一侧的曲肌变形器复制到另一侧，这种复制可以保持原有Flexor设置好的属性，但是新建Flexor的会恢复缺省的大小，经过缩放的Flexor被复制后，缩放的属性不能被复制。</p>

<p>首先复制LeftElbow关节的曲肌变形器。选择曲肌变形器后按住Shift键增加选择另一侧的RightElbow，选择主菜单Skin&gt;Edit&gt;Edit Rigid Skin&gt;Copy Flexor进行复制，如图4.3.27所示。</p>

<p><a title="image055" href="http://www.flickr.com/photos/95019520@N00/2347097465/" target="_blank"><img src="http://farm3.static.flickr.com/2355/2347097465_a6552ac4a6.jpg" border="0" alt="image055" /></a>图4.3.27</p>

<p>按照这个步骤，完成所有曲肌变形器的创建工作。对于复制后新建曲肌变形器的外形大小，需要重新进行调整，尽可能与另一侧保持一致，全部的骨骼与关节控制已经全部完成，如图4.3.28所示。</p>

<p><a title="image057" href="http://www.flickr.com/photos/95019520@N00/2347926468/" target="_blank"><img src="http://farm3.static.flickr.com/3073/2347926468_9c6124f091.jpg" border="0" alt="image057" /></a> 图4.3.28
<h5>本节工具解析</h5>
<h6>Rigid Bind</h6>
刚体蒙皮。将可变形物体与骨骼进行刚体蒙皮。</p>

<p>Animation&gt;Skin&gt;Bind Skin&gt;Rigid Bind&gt;Option 如图4.3.29所示：</p>

<p><a title="image059" href="http://www.flickr.com/photos/95019520@N00/2347926244/" target="_blank"><img src="http://farm3.static.flickr.com/2226/2347926244_6b5ec601f4.jpg" border="0" alt="image059" /></a>图4.3.29</p>

<p>·Bind To</p>

<p>Complete Skeleton是在整个骨架上进行绑定。如果需要部分地进行绑定，先把需要的关节选定，然后在这里选择Selected Joint进行绑定。</p>

<p>·Coloring</p>

<p>勾选Color Joints后进行蒙皮，骨骼会显示出不同的颜色，每段骨骼所作用的蒙皮部分的Vertes会显示对应的颜色，这样在编辑memberships时会很方便。</p>

<p>·Bind Method</p>

<p>（绑定方式） 设置用户是使用Closest Point 方式蒙皮还是使用Partition Set 方式蒙皮。选择Closest Point 方式，Maya会根据每个点到关节距离，自动将变形物体点组成蒙皮点组。对于每个带有骨头的关节，Maya 都将为其创建蒙皮点组，蒙皮点组包括最靠近关节的点。顶点被定义为皮肤点，每一个皮肤点仅能作为一个皮肤点组元素。Maya 将皮肤点组放置在一个分区中，这确保每个点只能在一个组中。最后，每个组被绑定到最近的关节。选择Partition Set 方式，Maya会绑定在分区中已被组织成组的点。分区中的组的数量应该和关节的数量一样多。每个组将被绑定到最近关节。
<h6>Paint Set Membership Tool</h6>
绘制集合成员工具。用笔刷绘制的方式选取集合的成员。</p>

<p>Deform&gt;Paint Set Membership&gt;Option，打开设置面板，如图4.3.30所示。</p>

<p><a title="image061" href="http://www.flickr.com/photos/95019520@N00/2347096467/" target="_blank"><img src="http://farm3.static.flickr.com/2232/2347096467_4b02faa793.jpg" border="0" alt="image061" /></a>图4.3.30</p>

<p>·Brush</p>

<p>设置权重笔刷的U、V向的半径大小；笔刷作用力的透明度大小；和笔触的形状。</p>

<p>·Paint Operations</p>

<p>在Select Set To Modify中列出所有控制当前所选蒙皮的控制合，包括Joint控制集合和Lattice控制集合。</p>

<p>Add：在当前场景中不是仅有一个Joint控制集合或Lattice控制集合的时候，为当前集合添加其他集合的控制点，所增加的点在属于当前集合的同时仍然属于原集合。</p>

<p>Transfer：在当前场景中不是仅有一个Joint控制集合或Lattice控制集合的时候，为当前集合添加其他集合的控制点，所增加的点只属于当前集合。</p>

<p>Remove：从当前集合中去除所选择的点，被去除的点不属于任何集合，不受任何集合控制。
<h6>Add Attribute</h6>
为物体增加属性。</p>

<p>Modify&gt;Add Attribute 如图4.3.31所示。</p>

<p><a title="image063" href="http://www.flickr.com/photos/95019520@N00/2347096073/" target="_blank"><img src="http://farm3.static.flickr.com/2122/2347096073_e13b4faa5e.jpg" border="0" alt="image063" /></a>图4.3.31</p>

<p>·Attribute Name：新建属性名称</p>

<p>·Make Attribute Keyable：勾选时，新建属性可以设置关键帧</p>

<p>·Data Type：新建属性数据类型，缺省为Float</p>

<p>·Attribute Type：新建属性类型</p>

<p>·Numeric Attribute Properties：新建属性数值范围</p>

<p>·Minimum：新建属性数值的最小值</p>

<p>·Maximum：新建属性数值的最大值</p>

<p>·Default：新建属性数值的缺省值</p>

<p>·Enum Names：
<h6>Create Flexor</h6>
创建屈肌变形。</p>

<p>Skin&gt;Edit Rigid Skin&gt;Create Flexor，打开设置面板，如图4.3.32所示。</p>

<p><a title="image065" href="http://www.flickr.com/photos/95019520@N00/2347095285/" target="_blank"><img src="http://farm3.static.flickr.com/2236/2347095285_38069b2389.jpg" border="0" alt="image065" /></a>图4.3.32</p>

<p>·Flexor Type</p>

<p>创建Flexor的类型，通常选择Lattice。</p>

<p>·Joints</p>

<p>At Selected Joint(s)：只为所选关节添加Flexor</p>

<p>At All Joint(s)：为所有关节添加Flexor</p>

<p>·Bones</p>

<p>At Selected Bone(s)：只为所选骨骼添加Flexor</p>

<p>At All Bone(s)：为所有骨骼添加Flexor</p>

<p>·Lattice Options</p>

<p>设置创建Lattice栅格的细分数量，包括S、T、U三个方向。</p>

<p>·Position the Flexor：在创建时勾选此项，创建后独立移动Lattice不会影响蒙皮的外形。不勾选时创建时，蒙皮会跟随Lattice一起移动。</p>

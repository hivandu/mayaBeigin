---
layout: post
title: 第三章第二节 眼睛和眉毛的控制
categories:
- Maya
tags:
- eye
- eyebrows
- Maya
- 开始maya吧
- 第三章
published: true
comments: true
---
<p> <!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/third-expression.html" target="_blank">回节目录选择</a></p>

<p><h5>本节概述</h5>
在表情动画中，眼睛及眉毛是动作的重点，角色的情绪可以由这两部分直观的表现出来。眼睛的动作包括眼球的转动和眼睑开闭，眉毛的动作主要是扬起和下垂。这些动作的组合调节可以表现出角色的很多情绪。下面首先讲解使用Maya制作角色面部表情所必须使用的几个重要工具，并且通过这些工具的一些练习，理解Maya的面部表情动画制作方法。
<h5>驱动帧（Set Driven key）的使用</h5>
定义</p>

<p><em>驱动帧（Driven Key</em><em>）的基本概念就是使用一个物体的一个参数去驱动另外一个或多个物体上的一个或多个参数。它的用处很广泛而且主要用于角色动画中的角色设定中。</em></p>

<p>在调节表情动画时，每个部分的一个动作可能需要选择不同的物体然后分别调节一个或几个相关参数，这种逐一调节的方法在表现复杂动画时是非常麻烦的，驱动帧工具可以很好地解决这一问题，它可以将很多物体的调节控制集中在某一物体上（例如Locator），通过调节一个物体的几个属性可以控制多个物体的变化。下面我们通过两个例子熟悉并理解Driven Key的用法。</p>

<p>实例教程
<h6>实例一：齿轮齿条的运动配合</h6>
<h6>1设置驱动帧的起始帧</h6>
打开gear-rack文件。这是一个齿轮和齿条的场景。在真实的运动过程中，可以是齿轮带动齿条，也可以是齿条带动齿轮。在这里我们按照齿轮带动齿条来设置动画。</p>

<p>首先，在Z方向调整齿条的位移，使齿条的左侧第一个齿与齿轮开始接触，如图3.2.1所示</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2346894297/" target="_blank"><img src="http://farm3.static.flickr.com/2256/2346894297_259c9d3b78.jpg" border="0" alt="image001" /></a>图3.2.1</p>

<p>选择主菜单Animation&gt;Animate&gt;Set Driven Key&gt;Set&gt;Option打开设置窗口。选择gear后单击Load Driver，在Driver项目右侧选择rotateY；选择rack后单击Load Driven，在Driven项目右侧选择translateZ，如图3.2.2所示</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2346893887/" target="_blank"><img src="http://farm3.static.flickr.com/3086/2346893887_dc97fcaa2c.jpg" border="0" alt="image003" /></a>图3.2.2</p>

<p>这时作为驱动物体的是gear，被驱动物体是rack，。改变gear的rotateY会直接影响rack的translateZ。选择完成后单击Key键设置第一个驱动帧，这时在ChannelBox中rack的Translate Z项出现桔黄色高亮显示，说明该项目被设置了动画。
<h6>2 设置驱动帧的结束帧</h6>
在Z方向调整齿条的位移，使齿条的右侧第一个齿与齿轮接触，为了使齿轮的相应齿与齿条对应，选择gear后在ChannelBox中的RotateY中输入215.46，设置完成后单击Key键设置第二个驱动帧，如图3.2.3所示</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2346893571/" target="_blank"><img src="http://farm3.static.flickr.com/2158/2346893571_39b5cd0acf.jpg" border="0" alt="image005" /></a>图3.2.3</p>

<p>选择gear后让它在Y轴上旋转，让RotateY参数在0~215.46之间变化时，rack会在Z方向进行相应的位移变化，如图3.2.4所示</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347722832/" target="_blank"><img src="http://farm3.static.flickr.com/2155/2347722832_c5fbd45c1d.jpg" border="0" alt="image007" /></a></p>

<p>图3.2.4
<h6>3 设置关键帧动画</h6>
现在设置齿轮的关键帧就可以完成动画了。确认Time Slider中当前时间是第0帧，选择gear齿轮，在ChannelBox中将RotateY设为0，这时齿条回到起始位置，在RotateY上单击右键选择Key Selected设置第一个关键帧。然后将Time Slider中的时间调到100帧，在Channel Box中将RotateY设为215.46，这时齿条到结束位置，在RotateY上单击右键选择Key Selected设置第二个关键帧。单击播放按钮播放动画，可以看到在0~100帧之间，齿轮带动齿条运动。
<h6>实例二：小球撞门</h6>
在齿轮齿条动画中，使用Driver的Rotate属性驱动Driven的Translate属性，在这个实例中，我们将使用Driver的Translate属性驱动Driven的Rotate属性。
<h6>1 使用驱动帧设定小球与门的运动关系</h6>
进入Top视图。创建一个Polygon的Sphere作为撞门的球，再创建一个Cube作为门，在Channel Box中将门的Scale X设为1，Scale Y设为5，Scale Z设为8。选择门后按键盘的Insert键一次，进入轴心编辑状态，将门的旋转轴心移动到一侧，如图3.2.5所示</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2347740686/" target="_blank"><img src="http://farm3.static.flickr.com/2010/2347740686_1ecc0a8bac.jpg" border="0" alt="image009" /></a></p>

<p>图3.2.5</p>

<p>选择主菜单Animation&gt;Animate&gt;Set Driven Key&gt;Set&gt;Option打开设置窗口。选择pSphere1后单击Load Driver，在Driver项目右侧选择translateX；选择pCube1后单击Load Driven，在Driven项目右侧选择rotateY，如图3.2.6所示</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2347740320/" target="_blank"><img src="http://farm3.static.flickr.com/3139/2347740320_ac6785fa7d.jpg" border="0" alt="image011" /></a>图3.2.6</p>

<p>选择完成后开始设置驱动帧。球在撞击门的过程中可以分解为几个状态：</p>

<p>球开始运动时，门没有相应的运动</p>

<p>球接触门的瞬间，门没有相应的运动</p>

<p>球撞门而过以后，门打开了</p>

<p>球远离了门以后，门关上了</p>

<p>按照撞击过程中的四个状态设置驱动帧，球撞门的动画就基本完成了，如图3.2.7所示</p>

<p><a href="http://blog.ivandoo.com/wp-content/uploads/2008/03/clip-image014.jpg" target="_blank"></a></p>

<p><a href="http://blog.ivandoo.com/wp-content/uploads/2008/03/clip-image020.jpg" target="_blank"></a><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2346909549/" target="_blank"></a><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2347739900/" target="_blank"><img src="http://farm3.static.flickr.com/3132/2347739900_8c7964e853.jpg" border="0" alt="image013" /></a><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2346909983/" target="_blank"><img src="http://farm3.static.flickr.com/2119/2346909983_5b527f7e1f.jpg" border="0" alt="image015" /></a><a href="http://blog.ivandoo.com/wp-content/uploads/2008/03/clip-image020.jpg" target="_blank"></a><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2346909549/" target="_blank"><img src="http://farm3.static.flickr.com/2408/2346909549_7f0d886b70.jpg" border="0" alt="image017" /></a><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2347739900/" target="_blank"></a><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2346908985/" target="_blank"><img src="http://farm3.static.flickr.com/2027/2346908985_a37056b770.jpg" border="0" alt="image019" /></a></p>

<p>图3.2.7
<h6>2 设置关键帧动画</h6>
这时改变pSphere1的TranslateX值，作为门的pCube1相应的开启和关闭。为了让动画可以连贯的播放，可以将pSphere1的TranslateX设置关键帧。将当前时间定在第一帧，选择pCube1后选择主菜单Animation&gt;Animate&gt;Set Driven Key&gt;Go to Previous/Go to Next可以逐一切换到设置的四个驱动帧的状态，将当前状态切换到起始位置的第一帧，选择pSphere1，在Channel Box中右键单击选择Key Selected设置第一个关键帧。然后将时间调到第100帧，选择pCube1，将驱动帧切换到撞门的最后一个状态，选择pSphere1后，为Translate X设置第二个关键帧，单击播放按钮播放动画，可以看到球撞击门后，门受撞击打开，当球远离后门自动关上。</p>

<p>小结</p>

<p>Set Driven Key工具是动画制作中非常重要的工具，它主要应用于制作多个物体之间有运动关系的动画。
<h5>约束（Constrain）的使用</h5>
定义</p>

<p><em>约束（Constrain</em><em>）工具是角色动画中使用频率很高的工具之一。主要用于制定动画物体之间的相互约束关系，包括约束位移、约束角度、约束缩放。</em></p>

<p>灵活的使用Constrain工具可以有效的简化制作过程，提高工作效率。本节教程通过两个实例介绍常用Constrain工具的使用方法。</p>

<p>实例教程
<h6>实例一：火车车轮转动动画</h6>
<h6>1创建车轮转动动画中的主要部件。</h6>
新建一个场景，创建三个Polygon物体模拟车轮转动动画中的主要部件。选择主菜单Create&gt;Polygon Primitives&gt;Cylinder建立一个圆柱体，在右侧的Channelbox中将圆柱体的名称改为arm_1；Rotate Z改为90；Scale Y改为15，在INPUTS项目中将Radius改为0.9，结果如图3.2.8所示</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2346908571/" target="_blank"><img src="http://farm3.static.flickr.com/2274/2346908571_f8f36c5519.jpg" border="0" alt="image021" /></a></p>

<p>图3.2.8</p>

<p>创建第二个圆柱体并命名为arm_2 ，具体参数设置为：Translate X改为25；Rotate Z改为90；Scale Y改为15，在INPUTS项目中将Radius保持为1。创建第三个圆柱体并命名为Wheel，设置参数为：Translate Z改为-3；Rotate X改为90；在INPUTS项目中将Radius改为15；Height改为4，结果如图3.2.9所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2347736912/" target="_blank"><img src="http://farm3.static.flickr.com/3259/2347736912_d4c1374537.jpg" border="0" alt="image023" /></a></p>

<p>图3.2.9
<h6>2使用目标约束工具制作两个连杆同轴运动的效果</h6>
通过对真实车轮转动的观察，我们可以发现车轮的两根连杆在车轮转动过程中保持着同轴并且同方向的状态，这种关系用MAYA的约束原理可以解释为arm_1以arm_2为对准的目标物体、arm_2以arm_1为对准的目标物体，通过连杆的相互对准可以实现在转动过程中保持同轴和同向。这种约束关系可以通过aim-constrain实现。</p>

<p>Aim-constrain是通过约束的物体的Local Axis来实现约束作用的 ，因此需要将物体的Local Axis显示出来。选择视图内的三个圆柱体，选择主菜单Display&gt;Component Display&gt;Local Rotation Axes显示出每个物体的Local Axis，如图3.2.10所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image026" href="http://www.flickr.com/photos/95019520@N00/2347736110/" target="_blank"><img src="http://farm3.static.flickr.com/3294/2347736110_1f488da65e.jpg" border="0" alt="image026" /></a></span></span></strong>图3.2.10</p>

<p>进入Animation模块，选择主菜单Constrain&gt;Aim&gt;Option打开设置面板，其中各项设置功能解释请查阅本节工具解析部分。</p>

<p>通过对两根连杆Local Axis的分析，首先用arm_1约束arm_2，即arm_2的Y轴正方向始终对准arm_1的Y轴正方向。打开Aim Constraint的设置面板，选择Edit&gt;Reset Setting恢复缺省设置，设置Aim Vector为0 1 0， 设置Up Vector为0 1 0，在视图中选择arm_1 后按住Shift键，增加选择arm_2，单击Apply键应用约束。这时通过移动工具任意移动arm_1时，arm_2始终以arm_1为目标进行转动，如图3.2.11</p>

<p><a title="image027" href="http://www.flickr.com/photos/95019520@N00/2347735928/" target="_blank"><img src="http://farm3.static.flickr.com/3039/2347735928_58fb589a3d.jpg" border="0" alt="image027" /></a>图3.2.11</p>

<p>按z键取消移动操作。然后用arm_2约束arm_1，即arm_1的Y轴的负方向始终对准arm_2的Y轴负方向。打开Aim Constraint的设置面板，设置Aim Vector为0 -1 0， 设置Up Vector为0 -1 0，在视图中选择arm_2 后按住Shift键，增加选择arm_1，单击Apply键，应用约束。这是无论我们移动那一根连杆都会带动另一根产生同轴同向的效果。
<h6>3 使用定点约束工具制作连杆与车轮关联运动的效果</h6>
连杆的约束关系设置完成后，我们需要连杆跟随车轮的转动而转动，即用车轮约束连杆。通过分析实际车轮的转动，我们发现arm_1最外端的某一点始终与车轮上的某一点保持相对静止，这一效果可以通过Point Constraint实现。由于约束关系都是通过轴向与轴心点实现的，因此需要调整arm_1的轴心点位置。但是，考虑到arm_1与arm_2之间的aim-constraint约束，arm_1轴心点的调整必须是在Y轴上进行。切换至Front视图，使用移动工具选择arm_1，按Insert键，进入轴心点编辑状态，将arm_1的轴心点移动到外侧末端附近。然后调整Wheel的轴心点到arm_1的轴心点附近，再次按Insert键恢复，如图3.2.12所示</p>

<p><a title="image029" href="http://www.flickr.com/photos/95019520@N00/2347735184/" target="_blank"><img src="http://farm3.static.flickr.com/2279/2347735184_9dfa399483.jpg" border="0" alt="image029" /></a>图3.2.12</p>

<p>选择Wheel后按住Shift键增加选择arm_1，打开Point Constraint的设置面板，选择Maintain Offset选项，保持当前相对位移，单击Apply键应用约束。这时移动Wheel会同时带动arm_1和arm_2，而连杆之间仍然保持同轴同向关系。
<h6>4 为车轮创建新的旋转坐标系</h6>
Wheel的轴心移动后，车轮已经不能按照正常的情况转动，这时需要给车轮增加一个正常的轴心点来实现转动，同时又不能破坏原有的约束关系。选择Wheel之后，按Ctrl+g键为车轮曾加一个组—group1， group1的轴心位于World坐标系的中心，同时也在Wheel的Y轴上，可以实现车轮的正常转动，使用转动工具沿Y轴转动group1测试车轮的转动，如图3.2.13所示</p>

<p><a title="image031" href="http://www.flickr.com/photos/95019520@N00/2346905035/" target="_blank"><img src="http://farm3.static.flickr.com/2019/2346905035_87c7eec4d4.jpg" border="0" alt="image031" /></a>图3.2.13</p>

<p>通过对group1的RotateZ设置关键帧可以很容易的实现车轮转动的动画。需要注意的是每次选择车轮时会选择wheel而不是group1，这就需要按键盘的向上箭头选择其所在组，对group1设置动画。
<h6>实例二：发射跟踪导弹动画</h6>
<h6>1创建模拟炮台打飞机动画的基本物体。</h6>
新建一个场景，选择主菜单Create&gt;Polygon Primitives&gt;Sphere建立一个球体作为炮台的主体。在Channelbox中将球体的名字改为base，在INPUTS栏中将Radius改为2。选择base后进入face级别，使用选择工具框选球体下半部分的面并将其删除。按F8键返回物体编辑级别。</p>

<p>选择主菜单Create&gt;Polygon Primitives&gt;Cylinder建立一个圆柱体作为炮管。在Channelbox中将圆柱体的名字改为shoot，在INPUTS栏中将Radius改为0.2、Height改为3。使用移动工具将shoot沿Y轴移动到X-Z平面以上，如图。</p>

<p>选择主菜单Create&gt;Polygon Primitives&gt;Sphere建立一个球体作为射击目标。在Channelbox中球体的名字改为marker，在INPUTS栏中将Radius改为0.5。使用移动工具将shoot沿Y轴移动到X-Z平面以上，如图。</p>

<p>选择主菜单Create&gt;Polygon Primitives&gt;Cone建立一个圆锥体作为炮弹。在Channelbox中球体的名字改为bullet，在INPUTS栏中将Radius改为0.1，Height改为1，如图3.2.14所示。</p>

<p><a title="image033" href="http://www.flickr.com/photos/95019520@N00/2347734000/" target="_blank"><img src="http://farm3.static.flickr.com/3022/2347734000_0ae4b914aa.jpg" border="0" alt="image033" /></a>图3.2.14
<h6>2 使用目标约束制作炮管与飞机的瞄准关系</h6>
在炮台打飞机的过程当中，炮管的底部始终位于炮台内部，顶端则是以射击物体为目标随时变化的。这一效果可以通过aim-constraint实现。aim-constrain是通过约束的物体的Local Axis来实现约束作用的 ，因此需要将物体的Local Axis显示出来。选择所有物体，选择主菜单Display&gt;Component Display&gt;Local Rotation Axes显示出每个物体的Local Axis，如图3.2.15所示</p>

<p><a title="image035" href="http://www.flickr.com/photos/95019520@N00/2346903681/" target="_blank"><img src="http://farm3.static.flickr.com/2172/2346903681_0f2bc73e0e.jpg" border="0" alt="image035" /></a>图3.2.15</p>

<p>在这里我们需要marker作为目标物体约束shoot，即shoot的Y轴正方向始终指向marker的Y轴正方向。选择marker后按住shift键增加选择shoot，选择主菜单Constrain&gt;Aim&gt;Option打开设置面板，设置Aim Vector为0 1 0， 设置Up Vector为0 1 0，单击Apply键应用约束。</p>

<p>这时移动marker会带动shoot一起转动，但是shoot转动的轴心不是理想的位置，按Z键取消对marker的移动操作，切换至front视图，选择shoot后按Insert键进入轴心点编辑状态，使用移动工具将shoot的轴心点移至炮管的底部，按Insert键返回物体编辑状态。这时再移动marker球体，shoot的转动情况正常，如图3.2.16所示</p>

<p><a title="image037" href="http://www.flickr.com/photos/95019520@N00/2347732756/" target="_blank"><img src="http://farm3.static.flickr.com/3137/2347732756_04169d7e29.jpg" border="0" alt="image037" /></a>图3.2.16
<h6>3使用目标约束制作炮弹与飞机的瞄准关系</h6>
在炮台射击目标过程中，炮弹由炮管发射出去，炮弹与炮管始终保持同轴同方向，与 marker球体约束炮管的方法一样，在这里需要marker作为目标物体约束bullet，即bullet的Y轴正方向始终指向marker的Y轴正方向。选择marker后按住shift键增加选择bullet，选择主菜单Constrain&gt;Aim&gt;Option打开设置面板，设置Aim Vector为0 1 0， 设置Up Vector为0 1 0，单击Apply键应用约束。移动marker球体，炮管与炮弹同时对准目标，如图3.2.17所示</p>

<p><a title="image039" href="http://www.flickr.com/photos/95019520@N00/2347732298/" target="_blank"><img src="http://farm3.static.flickr.com/2235/2347732298_51a9f6dcb1.jpg" border="0" alt="image039" /></a>图3.2.17
<h6>4 使用定点约束工具设定炮弹在炮台与飞机之间位置关系</h6>
选择marker后按住shift增加选择bullet，选择菜单Constrain&gt;Point&gt;Option打开设置面板，选择面板菜单Edit&gt;Reset Settings恢复缺省设置，单击Apply应用约束。</p>

<p>选择base后按住shift增加选择bullet，选择菜单Constrain&gt;Point应用约束。这时bullet同时受到marker与base两个物体的约束，系统会为被约束物体定义两个权重参数：Marker W0与Base W1，缺省值都为1，结果如图3.2.18所示。</p>

<p><a title="image041" href="http://www.flickr.com/photos/95019520@N00/2346902241/" target="_blank"><img src="http://farm3.static.flickr.com/2034/2346902241_65d5f809da.jpg" border="0" alt="image041" /></a>图3.2.18</p>

<p>调节权重的数值可以使某一方对炮弹的作用力增大或减小，当两者相等时作用力相等，炮弹位于两者的中间。
<h6>5 调节定点约束的权重参数制作炮弹的飞行动画</h6>
切换当前视图到front视图，在屏幕下方的Time Slider中设置当前帧为第1帧。沿X轴负方向移动marker球体至某一位置，在channelbox中用选择TranslateX、按RMB出现弹出菜单，选择Key Selected设置marker的第一个关键帧。</p>

<p>选择bullet炮弹，在channelbox中的SHAPES栏下将Marker W0设置为0、Base W1设置为1，同时选择Marker W0与Base W1两项，在名称上按RMB出现弹出菜单，选择Key Selected设置bullet的第一个关键帧，如图3.2.19所示</p>

<p><a title="image043" href="http://www.flickr.com/photos/95019520@N00/2347731060/" target="_blank"><img src="http://farm3.static.flickr.com/3099/2347731060_9a19ee93ff.jpg" border="0" alt="image043" /></a>图3.2.19</p>

<p>设置当前帧为第50帧，沿X轴正方向移动marker球体至某一位置，在channelbox中用选择TranslateX、按RMB出现弹出菜单，选择Key Selected设置marker的第二个关键帧。</p>

<p>选择bullet炮弹，在channelbox中的SHAPES栏下将Marker W0设置为1、Base W1设置为0，同时选择Marker W0与Base W1两项，在名称上按RMB出现弹出菜单，选择Key Selected设置bullet的第二个关键帧，如图3.2.20所示</p>

<p><a title="image045" href="http://www.flickr.com/photos/95019520@N00/2347730654/" target="_blank"><img src="http://farm3.static.flickr.com/2362/2347730654_11d00c7050.jpg" border="0" alt="image045" /></a>图3.2.20</p>

<p>播放动画。
<h5>眼睛的动画控制</h5>
在基本掌握了Set Driven Key和Constrain两个工具，并理解了约束动画的概念之后，我们开始进入正题，如何制作面部表情的动画。首先在下面的操作中，我们要先学会如何使用我们所学的工具来控制眼睛和眉毛的各种动作。</p>

<p>实例教程
<h6>1创建眼睑和眼球的控制。</h6>
为了方便操作，隐藏头部以外的其他部分。选择一侧的眼睑，查看右侧Channel Box中的属性，调整其中的一些参数：Rotate X为-180；Rotate Y为-55；Rotate Z为-90；INPUTS项目中的makeNurbSphere2，Start Sweep为5；End Sweep为300，如图所示3.2.21。</p>

<p><a title="image047" href="http://www.flickr.com/photos/95019520@N00/2347730240/" target="_blank"><img src="http://farm3.static.flickr.com/2283/2347730240_179653da36.jpg" border="0" alt="image047" /></a>图3.2.21</p>

<p>另一侧眼睑也进行同样的调节。选择三毛左侧的眼球和眼睑，按键盘Ctrl+g键为其创建一个组，修改新建组的名称为Left_eye，选择三毛右侧的眼球和眼睑，按键盘Ctrl+g键为其创建一个组，修改新建组的名称为Right_eye。然后分别选择Left_eye组、Right_eye组后，选择主菜单Modify&gt;Center Pivot将新建组的轴心调整到组的几何中心。
<h6>2创建Bend变形。</h6>
选择三毛的两条眉毛，按键盘的Ctrl+g键创建一个组，将新建组命名brow。选择brow后选择主菜单Deform&gt;Create Nonlinear&gt;Bend创建Bend弯曲变形控制。默认情况下创建的Bend平行于Y轴，这时需要调节ChannelBox中的RotateZ为90，使其平行于X轴。如图3.2.22所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image049" href="http://www.flickr.com/photos/95019520@N00/2346900497/" target="_blank"><img src="http://farm3.static.flickr.com/2079/2346900497_379cc47a16.jpg" border="0" alt="image049" /></a></span></span></strong>图3.2.22
<h6>3创建眼睛控制节点</h6>
以上都是调节表情动画时的具体控制，分别控制某个部位的某个动作。控制设置的目的是为了在调节动画时尽可能的简单方便，这一步我们将使用Driven Key工具将上面的调节控制集中到一个物体上。</p>

<p>选择主菜单Create&gt;Locator创建一个Locator作为调节物体，将其命名为locator_face。将新建Locator移动到三毛头部的正前方，这样方便选择，如图3.2.23所示</p>

<p><a title="image051" href="http://www.flickr.com/photos/95019520@N00/2347729652/" target="_blank"><img src="http://farm3.static.flickr.com/3045/2347729652_1a72b277e3.jpg" border="0" alt="image051" /></a>图3.2.23</p>

<p>选择新建locator_face，选择主菜单Modify&gt;Add Attribute弹出设置面板。Data Type选择为Float，然后为新建locator_face创建以下属性，每一属性设置后单击Add按钮完成创建。
<table border="0" cellspacing="0" cellpadding="0" width="472">
<tbody>
<tr>
<td width="42" valign="top"></td>
<td width="111" valign="top">Attribute Name</td>
<td width="69" valign="top">Minimum</td>
<td width="79" valign="top">Maximum</td>
<td width="66" valign="top">Default</td>
<td width="103" valign="top">说明</td>
</tr>
<tr>
<td width="44" valign="top">1</td>
<td width="111" valign="top">Left_blink</td>
<td width="70" valign="top">0</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="103" valign="top">眨左眼</td>
</tr>
<tr>
<td width="43" valign="top">2</td>
<td width="111" valign="top">Right_blink</td>
<td width="71" valign="top">-5</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="103" valign="top">眨右眼</td>
</tr>
<tr>
<td width="42" valign="top">3</td>
<td width="111" valign="top">Left_big</td>
<td width="72" valign="top">-5</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">睁左眼</td>
</tr>
<tr>
<td width="44" valign="top">4</td>
<td width="110" valign="top">Right_big</td>
<td width="72" valign="top">-5</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">睁右眼</td>
</tr>
<tr>
<td width="44" valign="top">5</td>
<td width="110" valign="top">Eye_move</td>
<td width="72" valign="top">-5</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">升降双眼</td>
</tr>
<tr>
<td width="44" valign="top">6</td>
<td width="110" valign="top">Eye_rotate</td>
<td width="72" valign="top">-5</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">旋转双眼</td>
</tr>
<tr>
<td width="44" valign="top">7</td>
<td width="110" valign="top">Brow_bend</td>
<td width="72" valign="top">0</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">弯曲眉毛</td>
</tr>
<tr>
<td width="44" valign="top">8</td>
<td width="110" valign="top">Brow_wide</td>
<td width="72" valign="top">0</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">扩展眉毛</td>
</tr>
<tr>
<td width="44" valign="top">9</td>
<td width="110" valign="top">Brow_high</td>
<td width="72" valign="top">0</td>
<td width="79" valign="top">5</td>
<td width="66" valign="top">0</td>
<td width="102" valign="top">扬起眉毛</td>
</tr>
</tbody>
</table>
这时在右侧ChannelBox中会多出上述的9个属性，对于这个Locator控制器，除了这9个新增属性外，其原有的属性暂时不需要，为了方便设置驱动帧，我们将其原有的属性从ChannelBox显示中去除。选择locator_face，选择主菜单Window&gt;General Editors&gt;Channel Control，弹出设置窗口，在左侧栏目中选择9个新增属性以外的属性，单击Move按钮，所选属性被去除，单击Close按钮关闭窗口。调整后的ChannelBox中只包含新增加的9个属性，如图3.2.24所示。</p>

<p><a title="image053" href="http://www.flickr.com/photos/95019520@N00/2346899733/" target="_blank"><img src="http://farm3.static.flickr.com/2324/2346899733_f5c8932da0.jpg" border="0" alt="image053" /></a>图3.2.24
<h6>4 使用驱动帧设置控制节点与眼睛的控制关系</h6>
①．现在通过Driven Key工具设置Locator_face的9个新建属性控制三毛眼睛眉毛部分的表情。选择主菜单Animate&gt;Set Driven Key&gt;Set&gt;Option弹出设置窗口，选择Locator_face后单击设置窗口的Load Driver按钮，Locator_face出现在Driver栏目中；然后在视图中选择右侧眼睑，单击ChannleBox中的makeNurbSphere1项，此项作为被驱动的内容，在Set Driven Key设置窗口中单击Load Driven按钮，makeNurbSphere1与nurbsSphere1出现在Driven栏目中；如图3.2.25所示</p>

<p><a title="image055" href="http://www.flickr.com/photos/95019520@N00/2347728998/" target="_blank"><img src="http://farm3.static.flickr.com/3210/2347728998_4a72fefcda.jpg" border="0" alt="image055" /></a>图3.2.25</p>

<p>②．在makeNurbSphere1的属性中，startSweep和endSweep是控制作为眼睑的球体回转的角度，下面我们将使用Locator_face的Right_blink属性控制右眼睑——makeNurbSphere1的startSweep和endSweep的变化，从而实现眼睑的开闭。</p>

<p>在Set Driven Key窗口Driver栏左侧选择locator_face、在右侧选择Right_blink，这时ChannelBox中显示出locator_face的内容。查看ChannelBox中的Right_blink的数值应该为0。然后在Driven栏左侧选择makeNurbSphere1、在右侧选择starSweep，这时ChannelBox中显示出makeNurbSphere1的内容。查看ChannelBox中的startSweep数值设置为5。然后在Set Driven Key窗口中单击Key按钮设置第一个驱动帧，如图3.2.26所示</p>

<p><a title="image057" href="http://www.flickr.com/photos/95019520@N00/2346899259/" target="_blank"><img src="http://farm3.static.flickr.com/2048/2346899259_74466bd171.jpg" border="0" alt="image057" /></a>图3.2.26</p>

<p>③．保持在Driver栏目中的选择不变，在Driven栏左侧选择makeNurbSphere1、在右侧选择endSweep项，查看ChannelBox中的endSweep数值应该为300。这时单击Key按钮设置第二个驱动帧，这时ChannelBox中的startSweep和endSweep数值被黄色标记，说明这两项被设置了关键帧，如图3.2.27所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image059" href="http://www.flickr.com/photos/95019520@N00/2346898953/" target="_blank"><img src="http://farm3.static.flickr.com/3063/2346898953_f1247f8ab9.jpg" border="0" alt="image059" /></a></span></span></strong>图3.2.27</p>

<p>④．设置好右侧眼睑睁开时的状态，然后设置闭合的状态。在Driver栏左侧选择locator_face，在右侧选择Right_blink，在ChannelBox中将Right_blink设置为5，在Driven栏左侧选择makeNurbSphere1，在右侧选择startSweep，这时makeNurbSphere1出现在ChannelBox中，在ChannelBox中将startSweep设置为0，单击Key按钮设置关键帧。</p>

<p>⑤．保持Driver栏中的选项，在Driven栏左侧选择makeNurbSphere1,在右侧选择endSweep项，在ChannelBox中将endSweep项设置为360，单击Key按钮设置关键帧。如图3.2.28所示</p>

<p><a title="image061" href="http://www.flickr.com/photos/95019520@N00/2346898853/" target="_blank"><img src="http://farm3.static.flickr.com/3100/2346898853_779b1a4e51.jpg" border="0" alt="image061" /></a>图3.2.28</p>

<p>⑥．这时改变Locator_face的Right_blink的数值，可以看到右侧眼睑的开闭。按照同样的步骤设置左侧眼睑的开闭，不同的是在Load Driven的时候需要选择左侧眼睑的makeNurbSphere2项。Driver和Driven的数值关系如下：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="80" valign="top">Driver</td>
<td width="80" valign="top">Right_blink</td>
<td width="80" valign="top"></td>
<td width="80" valign="top">0</td>
<td width="80" valign="top">5</td>
</tr>
<tr>
<td width="80" valign="top">Driven</td>
<td width="80" valign="top">makeNurbSphere1</td>
<td width="80" valign="top">startSweep</td>
<td width="80" valign="top">5</td>
<td width="80" valign="top">0</td>
</tr>
<tr>
<td width="80" valign="top"></td>
<td width="80" valign="top"></td>
<td width="80" valign="top">endSweep</td>
<td width="80" valign="top">300</td>
<td width="80" valign="top">360</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="0" cellpadding="2" width="402">
<tbody>
<tr>
<td width="80" valign="top">Driver</td>
<td width="80" valign="top">Left_blink</td>
<td width="80" valign="top"></td>
<td width="80" valign="top">0</td>
<td width="80" valign="top">5</td>
</tr>
<tr>
<td width="80" valign="top">Driven</td>
<td width="80" valign="top">makeNurbSphere2</td>
<td width="80" valign="top">startSweep</td>
<td width="80" valign="top">5</td>
<td width="80" valign="top">0</td>
</tr>
<tr>
<td width="80" valign="top"></td>
<td width="80" valign="top"></td>
<td width="80" valign="top">endSweep</td>
<td width="80" valign="top">300</td>
<td width="80" valign="top">360</td>
</tr>
</tbody>
</table>
<h6>5 控制眼睛的大小</h6>
在角色动画中，为了表现角色的情绪变化，有时需要使眼睛的大小跟随情绪的变化而变化。兴奋的时候眼睛会睁大，忧郁的时候眼睛会暗淡无光、甚至缩小。locatot_face的Left_big与Right_big属性用于控制眼睛大小的变化。设置方法与步骤与同STEP 4，具体设置参考下表：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="158" valign="top">Locator_face(Left_big)</td>
<td width="58" valign="top">0</td>
<td width="51" valign="top">5</td>
<td width="52" valign="top">-5</td>
</tr>
<tr>
<td width="78" valign="top">Driven</td>
<td width="156" valign="top">Left_eye(Scale Y)</td>
<td width="58" valign="top">1</td>
<td width="51" valign="top">1.5</td>
<td width="53" valign="top">0.6</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="158" valign="top">Locator_face(Left_big)</td>
<td width="58" valign="top">0</td>
<td width="51" valign="top">5</td>
<td width="52" valign="top">-5</td>
</tr>
<tr>
<td width="78" valign="top">Driven</td>
<td width="156" valign="top">Right_eye(Scale Y)</td>
<td width="58" valign="top">1</td>
<td width="51" valign="top">1.5</td>
<td width="53" valign="top">0.6</td>
</tr>
</tbody>
</table>
<h6>6 控制眼睛的上下位移</h6>
在locator_face的属性中，Eye_move用于控制眼睛在垂直方向上的轻微移动，设置方法与步骤与同STEP 4，具体设置参考下表：
<table border="0" cellspacing="0" cellpadding="0" width="400">
<tbody>
<tr>
<td width="80" valign="top">Driver</td>
<td width="173" valign="top">Locator_face(Eye_move)</td>
<td width="39" valign="top">0</td>
<td width="50" valign="top">5</td>
<td width="56" valign="top">-5</td>
</tr>
<tr>
<td width="80" valign="top">Driver</td>
<td width="173" valign="top">Left_eye(Translate Y)</td>
<td width="39" valign="top">0</td>
<td width="50" valign="top">0.3</td>
<td width="56" valign="top">-0.3</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="0" cellpadding="0" width="400">
<tbody>
<tr>
<td width="80" valign="top">Driver</td>
<td width="173" valign="top">Locator_face(Eye_move)</td>
<td width="39" valign="top">0</td>
<td width="50" valign="top">5</td>
<td width="56" valign="top">-5</td>
</tr>
<tr>
<td width="80" valign="top">Driver</td>
<td width="173" valign="top">Right_eye(Translate Y)</td>
<td width="39" valign="top">0</td>
<td width="50" valign="top">0.3</td>
<td width="56" valign="top">-0.3</td>
</tr>
</tbody>
</table>
<h6>7 控制眼睛的转动</h6>
在locator_face的属性中，Eye_rotate用于控制眼睛在X轴方向上的轻微转动，设置方法与步骤与同STEP 4，具体设置参考下表：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="177" valign="top">Locator_face(Eye_rotate)</td>
<td width="36" valign="top">0</td>
<td width="52" valign="top">5</td>
<td width="54" valign="top">-5</td>
</tr>
<tr>
<td width="79" valign="top">Driven</td>
<td width="177" valign="top">Left_eye(Rotate X)</td>
<td width="36" valign="top">0</td>
<td width="53" valign="top">-30</td>
<td width="55" valign="top">30</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="177" valign="top">Locator_face(Eye_rotate)</td>
<td width="36" valign="top">0</td>
<td width="52" valign="top">5</td>
<td width="54" valign="top">-5</td>
</tr>
<tr>
<td width="79" valign="top">Driven</td>
<td width="177" valign="top">Right_eye(Rotate X)</td>
<td width="36" valign="top">0</td>
<td width="53" valign="top">-30</td>
<td width="55" valign="top">30</td>
</tr>
</tbody>
</table>
<h6>8 控制眉毛的弯曲</h6>
在locator_face的属性中，Brow_bend用于控制眉毛的弯曲，被驱动的对象不是单个眉毛或是眉毛的组—Brow，而是控制Brow弯曲的变形器—bend1Handle的Curvature属性，设置方法与步骤与同STEP 4，具体设置参考下表：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="177" valign="top">Locator_face(Brow_bend)</td>
<td width="36" valign="top">0</td>
<td width="52" valign="top">5</td>
<td width="54" valign="top">-5</td>
</tr>
<tr>
<td width="79" valign="top">Driven</td>
<td width="177" valign="top">Bend1Handle(Curvature)</td>
<td width="36" valign="top">0</td>
<td width="53" valign="top">1</td>
<td width="55" valign="top">-1</td>
</tr>
</tbody>
</table>
<h6>9 控制眉毛的伸展</h6>
在locator_face的属性中，Brow_wide用于控制眉毛向两侧扩展，这时被驱动的对象是Brow组，设置方法与步骤与同STEP 4，具体设置参考下表：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="177" valign="top">Locator_face(Brow_wide)</td>
<td width="36" valign="top">0</td>
<td width="52" valign="top">5</td>
<td width="54" valign="top">-5</td>
</tr>
<tr>
<td width="79" valign="top">Driven</td>
<td width="177" valign="top">Brow(Scale X)</td>
<td width="36" valign="top">1</td>
<td width="53" valign="top">1.2</td>
<td width="55" valign="top">0.8</td>
</tr>
</tbody>
</table>
<h6>10 控制眉毛的扬起或下垂</h6>
在locator_face的属性中，Brow_high用于控制眉毛扬起或下垂，被驱动的对象是Brow组，设置方法与步骤与同STEP 4，具体设置参考下表：
<table border="0" cellspacing="0" cellpadding="2" width="400">
<tbody>
<tr>
<td width="79" valign="top">Driver</td>
<td width="177" valign="top">Locator_face(Brow_high)</td>
<td width="36" valign="top">0</td>
<td width="52" valign="top">5</td>
<td width="54" valign="top">-5</td>
</tr>
<tr>
<td width="79" valign="top">Driven</td>
<td width="177" valign="top">Brow(Translate Y)</td>
<td width="36" valign="top">1</td>
<td width="53" valign="top">1</td>
<td width="55" valign="top">-1</td>
</tr>
</tbody>
</table>
到此为止，眼睛与眉毛的控制设置全部完成，根据不同情绪的需要，可以调节Locator_face的9个参数值搭配出相应的表情，通常的几种表情与参数设置如图3.2.29a~h所示：</p>

<p><a title="image071" href="http://www.flickr.com/photos/95019520@N00/2347726712/" target="_blank"><img src="http://farm3.static.flickr.com/2380/2347726712_7b76640ded.jpg" border="0" alt="image071" /></a></p>

<p>图3.2.29-a</p>

<p>Left_blink : 0 Right_blink : 0</p>

<p>Left_big : 0 Right_big : 0</p>

<p>Eye_move : 0 Eye_rotate : 0</p>

<p>Brow_bend : 0 Brow_wide : 0</p>

<p>Brow_high : 0</p>

<p><a title="image067" href="http://www.flickr.com/photos/95019520@N00/2346897999/" target="_blank"><img src="http://farm3.static.flickr.com/3183/2346897999_5a1d83157d.jpg" border="0" alt="image067" /></a></p>

<p>图3.2.29-b</p>

<p>Left_blink : 0 Right_blink : 0</p>

<p>Left_big : 5 Right_big : 5</p>

<p>Eye_move : 0 Eye_rotate : 0</p>

<p>Brow_bend : 0 Brow_wide : 0</p>

<p>Brow_high : 0</p>

<p><a title="image065" href="http://www.flickr.com/photos/95019520@N00/2346898365/" target="_blank"><img src="http://farm3.static.flickr.com/3131/2346898365_a931eaa574.jpg" border="0" alt="image065" /></a></p>

<p>图3.2.29-c</p>

<p>Left_blink : 5 Right_blink : 5</p>

<p>Left_big : 0 Right_big : 0</p>

<p>Eye_move : 0 Eye_rotate : 0</p>

<p>Brow_bend : 0 Brow_wide : 0</p>

<p>Brow_high : 0</p>

<p><a title="image069" href="http://www.flickr.com/photos/95019520@N00/2346897645/" target="_blank"><img src="http://farm3.static.flickr.com/3004/2346897645_9eb1991920.jpg" border="0" alt="image069" /></a></p>

<p>图3.2.29-d</p>

<p>Left_blink : 0 Right_blink : 0</p>

<p>Left_big : 0 Right_big : 0</p>

<p>Eye_move : 0 Eye_rotate : 0</p>

<p>Brow_bend : 0 Brow_wide : -5</p>

<p>Brow_high : 0</p>

<p><a title="image063" href="http://www.flickr.com/photos/95019520@N00/2346898699/" target="_blank"><img src="http://farm3.static.flickr.com/2309/2346898699_8813c03b2b.jpg" border="0" alt="image063" /></a></p>

<p>图3.2.29-e</p>

<p>Left_blink : 0 Right_blink : 0</p>

<p>Left_big : 0 Right_big : 0</p>

<p>Eye_move : 0 Eye_rotate : 0</p>

<p>Brow_bend : 0 Brow_wide : 0</p>

<p>Brow_high : 5</p>

<p><a title="image075" href="http://www.flickr.com/photos/95019520@N00/2347725972/" target="_blank"><img src="http://farm3.static.flickr.com/3083/2347725972_c47f49a95a.jpg" border="0" alt="image075" /></a></p>

<p>图3.2.29-f</p>

<p>vLeft_blink : 4 Right_blink : 4</p>

<p>Left_big : -5 Right_big : -5</p>

<p>Eye_move : 0 Eye_rotate : 5</p>

<p>Brow_bend : -1 Brow_wide : 1</p>

<p>Brow_high : -4</p>

<p><a title="image073" href="http://www.flickr.com/photos/95019520@N00/2347726358/" target="_blank"><img src="http://farm3.static.flickr.com/2002/2347726358_bfe7a96d4d.jpg" border="0" alt="image073" /></a></p>

<p>图3.2.29-g</p>

<p>Left_blink : 0.5 Right_blink : 0.5</p>

<p>Left_big : 5 Right_big : 5</p>

<p>Eye_move : 0 Eye_rotate : 0</p>

<p>Brow_bend : 1 Brow_wide : 5</p>

<p>Brow_high : 5</p>

<p><a title="image077" href="http://www.flickr.com/photos/95019520@N00/2346896233/" target="_blank"><img src="http://farm3.static.flickr.com/3228/2346896233_dd3a1c8630.jpg" border="0" alt="image077" /></a></p>

<p>图3.2.29-h</p>

<p>Left_blink : 0.7 Right_blink : 0.7</p>

<p>Left_big : -5 Right_big : -5</p>

<p>Eye_move : 0 Eye_rotate : -1</p>

<p>Brow_bend : -1 Brow_wide : -5</p>

<p>Brow_high : -5
<h6>11 将控制物体与头部建立父子关系</h6>
在设置表情动画中，增加了许多额外的控制器，例如：Locator、bend1Handle，这些控制器没有参与与骨骼的绑定，因此它们与骨骼是相对独立的，在角色身体运动以后，这些变形器仍然会停留在原地不动，这是不应该出现的现象，为了解决这个问题，需要在变形器与骨骼之间建立父子关系。</p>

<p>选择控制眼睛的Locator，按住Shift键增加选择bend1Handle，最后增加选择CenterHead1关节，按键盘“p”键，将所有控制表情的控制器成为头部关节的子物体，这样在角色进行整体活动时，控制器会随之一起运动。</p>

<p>另外对于头部不参加与骨骼绑定的部分，例如：Right_eye组、Left_eye组、Brow组，都需要与CenterHead1关节建立父子关系，这样才能跟随角色一起运动。
<h6>12 创建眼睛的目标约束</h6>
Locator_face除了作为驱动帧的属性集合外，还有一个重要的作用，那就是作为双眼看东西时的聚焦点，也就是应用目标约束时的目标点。为了方便选择，首先打开Outliner，在视图中选择locator_face后，配合ctrl键在outliner中增加选择Right_eye组，选择主菜单Animation&gt;Constrain&gt;Aim&gt;Option打开设置窗口，勾选Maintain Offset选项后按Add键完成创建约束。同样方法创建locator_face于Left_eye之间的约束。这时移动locator_face，双眼会跟随其位置的变化而转动，这样一来，需要将locator_face的位移属性添加至ChannelBox中，方法与从ChannelBox中删除属性相反，结果如图3.2.30所示</p>

<p><strong><span style="text-decoration: underline;"><span style="color: #ff0000;"><a title="image079" href="http://www.flickr.com/photos/95019520@N00/2346895549/" target="_blank"><img src="http://farm3.static.flickr.com/3250/2346895549_5e29482003.jpg" border="0" alt="image079" /></a></span></span></strong>图3.2.30</p>

<p>小结</p>

<p>约束工具(Constrain)主要应用于制作多个物体之间的运动约束关系的动画。其中包括位置约束、方向约束，目标约束等等。通过使用约束工具来控制眼睛的动作，又通过驱动帧将眼睛的多种动作行集中的管理，便于动画师对角色的表情进行调节。
<h5>本节工具解析</h5>
<h6>Driven Key</h6>
使用一个物体的某个属性驱动另一物体的某个属性，或者一个物体的多个属性分别驱动多个物体的多个属性。</p>

<p>Animation&gt;Animate&gt;Set Driven Key&gt;Set&gt;Option 如图3.2.31所示</p>

<p><a title="image081" href="http://www.flickr.com/photos/95019520@N00/2347724836/" target="_blank"><img src="http://farm3.static.flickr.com/2232/2347724836_900e1f143b.jpg" border="0" alt="image081" /></a>图3.2.31</p>

<p>·Driver：执行驱动的物体及属性</p>

<p>·Driven：被驱动的物体及属性</p>

<p>·Key：设置关键帧</p>

<p>·Load Driver：加载执行驱动物体及属性</p>

<p>·Load Driven：加载被驱动物体及属性</p>

<p>·Close：关闭
<h6>Bend</h6>
Nonlinear变形的一种，通过变形曲线控制物体的弯曲变形，创建后可以在Channel Box中调节参数。</p>

<p>Deform&gt;Create Nonlinear&gt;Bend 如图3.2.32所示</p>

<p><a title="image083" href="http://www.flickr.com/photos/95019520@N00/2346895239/" target="_blank"><img src="http://farm3.static.flickr.com/2030/2346895239_cfe3793f3d.jpg" border="0" alt="image083" /></a>图3.2.32</p>

<p>·Low Bound：物体底部的变形程度，为0时不发生弯曲</p>

<p>·High Bound：物体顶部的变形程度，为0时不发生弯曲</p>

<p>·Curvature：变形曲线的弯曲程度，为0时不发生弯曲
<h6>Add Attribute</h6>
为物体增加额外的属性。</p>

<p>Modify&gt;Add Attribute 如图3.2.33</p>

<p><a title="image085" href="http://www.flickr.com/photos/95019520@N00/2347724584/" target="_blank"><img src="http://farm3.static.flickr.com/2181/2347724584_3ee4573e94.jpg" border="0" alt="image085" /></a>图3.2.33</p>

<p>·Attribute Name：新建属性名称</p>

<p>·Make Attribute Keyable：勾选时，新建属性可以设置关键帧</p>

<p>·Data Type：新建属性数据类型，缺省为Float</p>

<p>·Attribute Type：新建属性类型</p>

<p>·Numeric Attribute Properties：新建属性数值范围</p>

<p>·Minimum：新建属性数值的最小值</p>

<p>·Maximum：新建属性数值的最大值</p>

<p>·Default：新建属性数值的缺省值</p>

<p>·Enum Names：
<h6>Channel Control</h6>
编辑ChannelBox中的项目。</p>

<p>Window&gt;General Editors&gt;Channel Control 如图3.2.34所示</p>

<p><a title="image087" href="http://www.flickr.com/photos/95019520@N00/2346894839/" target="_blank"><img src="http://farm3.static.flickr.com/2285/2346894839_dfdf251bd8.jpg" border="0" alt="image087" /></a>图3.2.34</p>

<p>·Keyable：当前ChannelBox项目</p>

<p>·Non Keyable：可添加至ChannelBox中的项目</p>

<p>·Change all selected objects of the same type：当勾选此项时，如果一次选择多个物体，Keyable栏目中只显示所选物体的相同属性</p>

<p>·Move：将当前栏目中的项目移到另一栏目</p>

<p>·Close：关闭窗口
<h6>Aim Constraint</h6>
目标约束</p>

<p>Animation&gt;Constrain&gt;Aim&gt;Option 如图3.2.35所示</p>

<p><a title="image089" href="http://www.flickr.com/photos/95019520@N00/2347724096/" target="_blank"><img src="http://farm3.static.flickr.com/2012/2347724096_87b958990c.jpg" border="0" alt="image089" /></a>图3.2.35</p>

<p>·Maintain Offset：未选择时，保持目标物体与被约束物体当前的位移关系。选择时，按照offset选项后指定的X、Y、Z的数值指定两者间的位移关系。</p>

<p>·Offset ：指定物体间的相对位移大小，包括X、Y、Z三个轴向上的数值。</p>

<p>·Aim Vector：设置目标物体的作用约束方向，包括X、Y、Z三个轴向的数值，0表示在该轴向上不产生约束影响，1表示对该轴的正方向产生作用，-1表示对该轴的负方向产生作用。</p>

<p>·Up Vector：设置被约束物体的作用约束方向，包括X、Y、Z三个轴向的数值，0表示在该轴向上不产生作用，1表示对该轴的正方向产生作用，-1表示对该轴的负方向产生作用。</p>

<p>·World Up Type：设置世界坐标系竖直向上轴的定义方式，缺省选项为Vecto r—按照World Up Vector项输入值定义，另有选项Object Up—按照所选择物体的竖直向上轴方向定义；Scene Up—场景竖直向上轴方向定义；None—不定义。</p>

<p>·World Up Vector：当World Up Type设置为Vector时可用，包括X、Y、Z三个轴向的数值，0表示该轴不起作用，1表示定义为该轴正方向，-1表示定义为该轴负方向。通常这里设置为与Maya缺省定义方式一至，即Y轴正方向。</p>

<p>·World Up Object：当World Up Type设置为Object Up时可用，在空格处指定选择物体。</p>

<p>·Constraint Axes：指定在某几个轴向上进行约束还是在所有轴向上进行约束。</p>

<p>·Weight：约束力量的权重，缺省值为1。</p>

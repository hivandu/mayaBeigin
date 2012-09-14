---
layout: post
title: 第七章第二节 食草动物的角色设定
categories:
- Maya
tags:
- animal
- Maya
- vegetarian
- 开始maya吧
- 第七章
published: true
comments: true
---
<p><span style="color: #bb0000;">此文出自国际Maya认证教师:王之纲(我的老师),转载请注明出处以及撰写人!</span> <!--more--></p>

<p><a href="http://blog.hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://blog.hivan.me/2008/03/22/seventh-animal-key-animation.html" target="_blank">回节目录选择</a>
<h5>本节概述</h5>
<h5>马的角色设定</h5>
食草动物的运动控制以马为代表进行介绍。马的模型可以使用通用模型库的现有文件，读者也可以使用在豹子建模部分介绍的建模方法创建更为理想的模型。</p>

<p>马的骨骼结构如图7.2.1所示。</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2352464574/" target="_blank"><img src="http://farm3.static.flickr.com/3227/2352464574_64c4286731.jpg" border="0" alt="image001" /></a>图7.2.1</p>

<p>实例教程
<h6>1 创建骨骼</h6>
进入Side视图，选择主菜单Skeleton&gt;Joint Tool&gt;Option&gt;Reset Tool恢复缺省设置。根据在三毛的骨骼创建部分介绍的骨骼创建方法，创建马的大致骨骼轮廓，其中的根关节放置在马的腹部靠上的位置。如图7.2.2所示。</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2352463818/" target="_blank"><img src="http://farm3.static.flickr.com/2309/2352463818_0aacb0d3e8.jpg" border="0" alt="image003" /></a>图7.2.2</p>

<p>创建基本骨骼框架之后，在Perspective视图中调整骨骼的空间位置，主要是调整腿部骨骼在X轴向上的位置，如图7.2.3所示。</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2351633781/" target="_blank"><img src="http://farm3.static.flickr.com/3044/2351633781_4224e55ca1.jpg" border="0" alt="image005" /></a>图7.2.3
<h6>2 骨骼重命名</h6>
为了便于下一步的操作，这时需要对现有的骨骼进行标记与重命名。这里仍然使用Maya的Retargeting工具。选择主菜单Skeleton&gt;Retargeting&gt;Joint Labelling，并且将工具条独立出来。根据马的结构特点与设置需要为现有骨骼创建标记。对于我们需要的一些特别的标记，在工具条中没有提供，这就需要手动进行添加。例如：控制右前腿的关节，我们需要将它标记为RightHand_ctrl，在Retargeting工具条中没有此项，选择该关节后按ctrl+a打开属性设窗口，在Joint&gt;Joint Labelling层级下将Type项设置为Other，然后other Type项中输入RightHand_ctrl，最后勾选Draw Label项打开标记的显示，具体设置如图7.2.4所示。</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2351633079/" target="_blank"><img src="http://farm3.static.flickr.com/3284/2351633079_7ab7d211f1.jpg" border="0" alt="image007" /></a>图7.2.4</p>

<p>对于在Retargeting工具条中提供的关节标记，尽可能使用现有的名称对关节进行标记，没有的名称手动进行设置。为了方便下一步的操作，我们将四足动物的关节名称按照两足动物关节的命名习惯进行命名，即分为左右臂和左右腿。当前骨骼的标记后各个关节的标记名称如下：</p>

<p>Label Center：Head1—Head2—Neck—Collor—Spine1—Root—Spine2—Spine3—Tail1—Tail2—Tail3—Tail4—Tail5—Tail6</p>

<p>Label Right（右前腿）：Shoulder_ctrl—Shoulder1—Shoulder2—Shoulder3—Elbow—Hand1—Hand2—Hand3</p>

<p>Lable Right（右后腿）：Hip_ctrl—Hip1—Hip2—Hip3—Knee—Foot1—Foot2—Foot3</p>

<p>标记定义后按照标记对骨骼名称进行重命名。选择根关节，选择主菜单Animation&gt;Skeleton&gt;Retargeting&gt;Rename joints from labels，这时骨骼名称全部更新。如图7.2.5所示。</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2351632313/" target="_blank"><img src="http://farm3.static.flickr.com/3024/2351632313_c3bd43b90d.jpg" border="0" alt="image009" /></a>图7.2.5
<h6>3 镜像骨骼</h6>
完成一侧骨骼的创建后，通过骨骼对称工具生成另一侧的骨骼。方法参照三毛骨骼创建部分，结果如图7.2.6所示。</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2351631369/" target="_blank"><img src="http://farm3.static.flickr.com/2247/2351631369_5601b4294b.jpg" border="0" alt="image011" /></a>图7.2.6
<h6>4 调整关节的局部旋转轴</h6>
马的主体骨骼创建完成后，在进行下一步设置之前需要调整骨骼的Local Axes。调节时仍然按照Y轴向上、X轴指向下一关节的规律，对于四肢的Hand/Foot关节，由于将会使用附加的反向控制关节控制，因此可以省略Local Axes的调节。如图7.2.7所示。</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2352459670/" target="_blank"><img src="http://farm3.static.flickr.com/2338/2352459670_25325ed917.jpg" border="0" alt="image013" /></a>图7.2.7
<h6>5 设置四肢的IK控制手柄</h6>
马的四条腿都使用IK进行控制。分别由Shoulder3至Hand1、Hip3至Foot1建立4个IK，IK solver类型使用ik2Bsolver然后为新建IK重命名为：ikHandle_LeftHand、ikHandle_LeftFoot、ikHandle_RightHand、ikHandle_RightFoot。如图7.2.8所示。</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2351629805/" target="_blank"><img src="http://farm3.static.flickr.com/2133/2351629805_d15b9b3d64.jpg" border="0" alt="image015" /></a>图7.2.8
<h6>6 设置腿的反向控制关节</h6>
马的足部反向控制骨骼与豹子的略有不同，如果将一只足的全部运动控制都集中到一套反向控制骨骼中，控制起来十分麻烦，因此反向控制骨骼需要结合原始骨骼共同完成马的运动控制。</p>

<p>选择RightShoulder_ctrl与RightHip_ctrl关节，将其隐藏。首先创建左侧的反向控制关节。进入Side视图，分别创建前腿与后退的反向控制关节，如图7.2.8所示。</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2352470888/" target="_blank"><img src="http://farm3.static.flickr.com/2420/2352470888_a0741861fb.jpg" border="0" alt="image017" /></a>图7.2.9</p>

<p>选择新建的两组关节，沿X轴正方向移动2的距离，与左侧腿在X轴方向对齐。然后对新建关节进行重命名。前腿关节依次为LeftHand_ctrl1—LeftHand_ctrl2—LeftHand_ctrl3—LeftHand_ctrl；后腿关节依次为LeftFoot_ctrl1—LeftFoot_ctrl2—LeftFoot_ctrl3—LeftFoot_ctrl4。</p>

<p>使用移动工具，配合点捕捉键—v键，将新建反向控制关节与原始骨骼进行对齐，LeftHand_ctrl1、LeftHand_ctr13与LeftHand1重合；LeftHand_ctrl2与LeftHand2重合；LeftFoot_ctrl1、LeftFoot_ctrl3与LeftFoot1重合；LeftFoot_ctrl2与Foot2重合。如图7.2.10所示。</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2351641275/" target="_blank"><img src="http://farm3.static.flickr.com/2078/2351641275_505c8f1381.jpg" border="0" alt="image019" /></a>图7.2.10</p>

<p>反向控制骨骼位置调整好以后，开始建立控制骨骼与腿部骨骼之间的约束关系。建立方法与步骤与三毛脚部控制骨骼约束相似，例如：选择LeftHand_ctrl2后按住Shift键增加选择LeftHand1，选择主菜单Animation&gt;Constrain&gt;Orient&gt;Option弹出设置窗口，勾选Maintain Offset项，单击Apply键完成操作。前腿与后腿一共需要创建四组约束关系，具体如下：</p>

<p>LeftHand_ctrl2+ LeftHand1&gt;orientConstraint</p>

<p>LeftHand_ctrl3+ikHandle_LeftHand&gt;pointConstraint</p>

<p>LeftFoot_ctrl2+ LeftFoot1&gt; orientConstraint</p>

<p>LeftFoot_ctrl3+ ikHandle_LeftFoot&gt; pointConstraint</p>

<p>约束关系建立完成后，左侧的前后腿的控制骨骼系统全部完成，恢复右侧的前后腿骨骼显示，按照左侧控制骨骼的创建方法与步骤建立右侧的控制骨骼系统，结果如图7.2.11所示。</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2352470032/"><img src="http://farm3.static.flickr.com/2157/2352470032_a8efdc9f4a.jpg" border="0" alt="image021" /></a>图7.2.11
<h6>7 设置马尾的样条曲线IK</h6>
马的尾部关节使用IK Spline Handle控制。选择主菜单Animation&gt;Skeleton&gt;IK Spline Handle Tool&gt;Option打开设置窗口，将Number of Spans项设置为4，由CenterTail1至CenterTail6建立IK Spline Handle，如图7.2.12所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2351639709/" target="_blank"><img src="http://farm3.static.flickr.com/2305/2351639709_7670e90a28.jpg" border="0" alt="image023" /></a>图7.2.12</p>

<p>由IK Spline Handle生成的curve1使用cluster控制。选择curve1，按F9键进入NURBS CV选择级别，由第一个cv开始，每两个cv点创建一个cluster，一共创建4个cluster。
<h6>8 显示关节的选择手柄</h6>
为了方便对关节进行设置关键帧，因此需要将设置关键帧的关节选择手柄显示出来，如图7.2.13所示。</p>

<p><a title="image025" href="http://www.flickr.com/photos/95019520@N00/2351639423/" target="_blank"><img src="http://farm3.static.flickr.com/3172/2351639423_ff194c741d.jpg" border="0" alt="image025" /></a>图7.2.13</p>

<p>各个选择手柄的名称及对应位置参考下图7.2.14所示：</p>

<p><a title="image027" href="http://www.flickr.com/photos/95019520@N00/2351638857/" target="_blank"><img src="http://farm3.static.flickr.com/2217/2351638857_edc018afdd.jpg" border="0" alt="image027" /></a>图7.2.14
<h6>9 创建马的角色集</h6>
创建一个主角色集—All，然后在主角色集层级下创建4个子角色集：CenterBody、leftFoot、leftHand、RightFoot、RightHand，然后将相关骨骼与控制骨骼的有关属性添加至相应的角色集，如图7.2.15所示。</p>

<p><a title="image029" href="http://www.flickr.com/photos/95019520@N00/2352467356/" target="_blank"><img src="http://farm3.static.flickr.com/2156/2352467356_c90992336b.jpg" border="0" alt="image029" /></a>图7.2.15</p>

<p>各角色集中关节属性内容如下：
<table border="0" cellspacing="0" cellpadding="2" width="387">
<tbody>
<tr>
<td width="98" valign="top"><strong>CenterBody:</strong></td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top">CenterSpine1.rx<br />
CenterSpine1.ry<br />
CenterSpine1.rz</td>
<td width="76" valign="top">CenterSpine2.rx<br />
CenterSpine2.ry<br />
CenterSpine2.rz</td>
<td width="89" valign="top">cluster1Handle.tx cluster1Handle.ty cluster1Handle.tz</td>
<td width="122" valign="top">cluster2Handle.tx cluster2Handle.ty cluster2Handle.tz</td>
</tr>
<tr>
<td width="98" valign="top">cluster3Handle.tx cluster3Handle.ty cluster3Handle.tz</td>
<td width="76" valign="top">cluster4Handle.tx cluster4Handle.ty cluster4Handle.tz</td>
<td width="89" valign="top">CenterNeck.rx CenterNeck.ry CenterNeck.rz</td>
<td width="122" valign="top">CenterRoot.sx</td>
</tr>
<tr>
<td width="98" valign="top">CenterHip.tx CenterHip.ty CenterHip.tz</td>
<td width="76" valign="top">Centerhip.rx CenterHip.ry CenterHip.rz</td>
<td width="89" valign="top">CenterHead2.rx CenterHead2.ry CenterHead2.rz</td>
<td width="122" valign="top">CenterCollor.rx CenterCollor.ry CenterCollor.rz</td>
</tr>
<tr>
<td width="98" valign="top">CenterRoot.tx CenterRoot.ty CenterRoot.tz</td>
<td width="76" valign="top">CenterRoot.rx CenterRoot.ry CenterRoot.rz</td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top"><strong>LeftFoot:</strong></td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top">LeftHip1.rx<br />
LeftHip1.ry<br />
LeftHip1.rz</td>
<td width="76" valign="top">Lefthip_ctrl.rx</td>
<td width="89" valign="top">Left_ctrl.ry<br />
Left_ctrl.rz</td>
<td width="122" valign="top">LeftFoot2.rx LeftFoot2.ry LeftFoot2.rz</td>
</tr>
<tr>
<td width="98" valign="top">LeftFoot_ctrl1.tx<br />
LeftFoot_ctrl1.ty<br />
LeftFoot_ctrl1.tz</td>
<td width="76" valign="top">LeftFoot_ctrl1.rx<br />
LeftFoot_ctrl1.ry<br />
LeftFoot_ctrl1.rz</td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top"><strong>LeftHand</strong></td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top">LeftShoulder1.rx<br />
LeftShoulder1.ry<br />
LeftShoulder1.rz</td>
<td width="76" valign="top">LeftShoulder_ctrl.rx<br />
LeftShoulder_ctrl.ry<br />
LeftShoulder_ctrl.rz</td>
<td width="89" valign="top">LeftHand_ctrl1.tx<br />
LeftHand_ctrl1.ty<br />
LeftHand_ctrl1.tz</td>
<td width="122" valign="top">LeftHand_ctrl1.rx<br />
LeftHand_ctrl1.ry<br />
LeftHand_ctrl1.rz</td>
</tr>
<tr>
<td width="98" valign="top">LeftHand2.rx<br />
LeftHand2.ry<br />
LeftHand2.rz</td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top"><strong>RightFoot</strong></td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top">RightHip1.rx<br />
RightHip1.ry<br />
RightHip1.rz</td>
<td width="76" valign="top">RightHip_ctrl.rx<br />
RightHip_ctrl.ry<br />
RightHip_ctrl.rz</td>
<td width="89" valign="top">RightFoot_ctrl1.tx<br />
RightFoot_ctrl1.ty<br />
RightFoot_ctrl1.tz</td>
<td width="122" valign="top">RightFoot_ctrl1.rx<br />
RightFoot_ctrl1.ry<br />
RightFoot_ctrl1.rz</td>
</tr>
<tr>
<td width="98" valign="top">RightFoot2.rx<br />
RightFoot2.ry<br />
RightFoot2.rz</td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top"><strong>RightHand</strong></td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
<tr>
<td width="98" valign="top">RightShoulder1.rx<br />
RightShoulder1.ry<br />
RightShoulder1.rz</td>
<td width="76" valign="top">RightShoulder_ctrl.rx<br />
RightShoulder_ctrl.ry<br />
RightShoulder_ctrl.rz</td>
<td width="89" valign="top">RightHand_ctrl1.tx<br />
RightHand_ctrl1.ty<br />
RightHand_ctrl1.tz</td>
<td width="122" valign="top">RightHand_ctrl1.rx<br />
RightHand_ctrl1.ry<br />
RightHand_ctrl1.rz</td>
</tr>
<tr>
<td width="98" valign="top">RightHand2.rx<br />
RightHand2.ry<br />
RightHand2.rz</td>
<td width="76" valign="top"></td>
<td width="89" valign="top"></td>
<td width="122" valign="top"></td>
</tr>
</tbody>
</table>
10 给马蒙皮并添加影响物体</p>

<p>骨骼系统与控制系统创建完成后，可以进行蒙皮操作。马的蒙皮使用Smooth Bind方式。由于马的腹部没有创建单独的关节控制，可以添加一个Influence物体，创建一个NURBS球体，调整大小与位置，如图7.2.16所示。</p>

<p><a title="image031" href="http://www.flickr.com/photos/95019520@N00/2351637715/" target="_blank"><img src="http://farm3.static.flickr.com/2226/2351637715_2b4f1b8767.jpg" border="0" alt="image031" /></a>图7.2.16</p>

<p>选择马的模型后按住Shift键增加选择NURBS球体，选择主菜单Animation&gt;Skin&gt;Edit Smooth Skin&gt;Add Influence完成创建，如图7.2.17所示。</p>

<p><a title="image033" href="http://www.flickr.com/photos/95019520@N00/2352465992/" target="_blank"><img src="http://farm3.static.flickr.com/2126/2352465992_05871634ee.jpg" border="0" alt="image033" /></a>图7.2.17</p>

<p>蒙皮后进行相应的绘制权重工作，具体方法与三毛角色创建中相同，在此不再重复。</p>

<p><span style="color: #bb0000;"><strong><span style="text-decoration: underline;">此文出自国际Maya认证教师:王之纲(我的老师),转载请注明出处以及撰写人!</span></strong></span></p>

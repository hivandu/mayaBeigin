---
layout: post
title: 第七章第一节 肉食动物的角色设定
categories:
- Maya
tags:
- animal
- carnivore
- Maya
- 开始maya吧
- 第七章
published: true
comments: true
---
<p><!--more--></p>

<p><span style="color: #ff0000;"><!--more--></span></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/22/seventh-animal-key-animation.html" target="_blank">回节目录选择</a></p>

<p><strong>本节概述</strong>
<h5>豹子的角色设定</h5>
四足动物的骨骼结构与两足动物不同，尤其使腿部的区别很大，因此运动控制系统应该有所改变。腿部控制系统仍然使用反向控制，但是创建的方法相比两足动物复杂一些。</p>

<p>猫科动物骨骼结构如图7.1.1所示。</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2352411474/" target="_blank"><img src="http://static.flickr.com/2319/2352411474_bb1dac0fd8.jpg" border="0" alt="image001" /></a>图7.1.1</p>

<p>实例教程
<h6>1 创建骨骼</h6>
打开豹子模型文件，进入Side视图，选择主菜单Animation&gt;Skeleton&gt;Joint Tool&gt;Option&gt;Reset Tool恢复缺省设置。根据在三毛的骨骼创建部分介绍的骨骼创建方法，创建豹子的大致骨骼轮廓，其中的根关节放置在豹子的腹部靠上的位置。如图7.1.2</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2351582949/" target="_blank"><img src="http://static.flickr.com/2408/2351582949_dd6f1daec5.jpg" border="0" alt="image003" /></a>图7.1.2</p>

<p>创建基本骨骼框架之后，在Perspective视图中调整骨骼的空间位置，主要是调整腿部骨骼在X轴向上的位置，如图7.1.3所示。</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2351582083/" target="_blank"><img src="http://static.flickr.com/2395/2351582083_884d704aa4.jpg" border="0" alt="image005" /></a>图7.1.3
<h6>2 骨骼重命名</h6>
为了便于下一步的操作，这时需要对现有的骨骼进行标记与重命名。这里仍然使用Maya的Retargeting工具。选择主菜单Skeleton&gt;Retargeting&gt;Joint Labelling，并且将工具条独立出来。根据马的结构特点与设置需要为现有骨骼创建标记。对于我们需要的一些特别的标记，在工具条中没有提供，这就需要手动进行添加。例如：控制右前腿的关节，我们需要将它标记为RightHand_ctrl，在Retargeting工具条中没有此项，选择该关节后按ctrl+a打开属性设窗口，在Joint&gt;Joint Labelling层级下将Type项设置为Other，然后other Type项中输入RightHand_ctrl，最后勾选Draw Label项打开标记的显示，具体设置如图7.1.4所示。</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2351581319/" target="_blank"><img src="http://static.flickr.com/3171/2351581319_077102e4ed.jpg" border="0" alt="image007" /></a>图7.1.4</p>

<p>对于在Retargeting工具条中提供的关节标记，尽可能使用现有的名称对关节进行标记，没有的名称手动进行设置。为了方便下一步的操作，我们将四足动物的关节名称按照两足动物关节的命名习惯进行命名，即分为左右臂和左右腿。当前骨骼的标记后各个关节的标记名称如下：</p>

<p>Label Center：Head1—Head2—Neck—Collor—Spine1—Root—Spine2—Spine3—Spine4—Tail1—Tail2—Tail3—Tail4—Tail5—Tail6—Tail7—Tail8</p>

<p>Label Right（右前腿）：Shoulder_ctrl—Shoulder1—Shoulder2—Elbow—Hand1—Hand2—Hand3</p>

<p>Lable Right（右后腿）：Hip_ctrl—Hip—Knee—Foot1—Foot2—Foot3</p>

<p>标记定义后按照标记对骨骼名称进行重命名。选择根关节，选择主菜单Animation&gt;Skeleton&gt;Retargeting&gt;Rename joints from labels，这时骨骼名称全部更新。如图7.1.5所示。</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2351580561/" target="_blank"><img src="http://static.flickr.com/2262/2351580561_0072e6f158.jpg" border="0" alt="image009" /></a>图7.1.5
<h6>3 镜像骨骼</h6>
完成一侧骨骼的创建后，通过骨骼对称工具生成另一侧的骨骼。方法参照三毛骨骼创建部分，结果如图7.1.6所示。</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2351579773/" target="_blank"><img src="http://static.flickr.com/2375/2351579773_6c3a1898b0.jpg" border="0" alt="image011" /></a>图7.1.6
<h6>4 调整关节的局部旋转轴</h6>
豹子的主体骨骼创建完成后，在进行下一步设置之前需要调整骨骼的Local Axes。调节时仍然按照Y轴向上、X轴指向下一关节的规律，对于四肢的Hand1、Foot2以下的关节，由于将会使用附加的反向控制关节控制，因此可以省略Local Axes的调节。如图7.1.7所示。</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2352407100/" target="_blank"><img src="http://static.flickr.com/2182/2352407100_fac02a05a5.jpg" border="0" alt="image013" /></a>图7.1.7
<h6>5 设置四肢的IK控制手柄</h6>
豹子的四条腿都使用IK进行控制。分别由Shoulder2至Hand1、Knee至Foot2建立4个IK，IK solver类型使用ik2Bsolver，然后为新建IK重命名为：ikHandle_LeftHand、ikHandle_LeftFoot、ikHandle_RightHand、ikHandle_RightFoot。如图7.1.8所示。</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2351578007/" target="_blank"><img src="http://static.flickr.com/3274/2351578007_5137a80659.jpg" border="0" alt="image015" /></a>图7.1.8
<h6>6 设置腿的反向控制关节</h6>
豹子的足部反向控制骨骼与三毛的略有不同，前后腿的控制方法也略有不同。</p>

<p>选择RightShoulder_ctrl与RightHip_ctrl关节，将其隐藏。首先创建左侧的反向控制关节。进入Side视图，分别创建前腿与后退的反向控制关节，如图7.1.9所示。</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2352405444/" target="_blank"><img src="http://static.flickr.com/2229/2352405444_af30933c71.jpg" border="0" alt="image017" /></a>图7.1.9</p>

<p>选择新建的两组关节，沿X轴正方向移动2的距离，与左侧腿在X轴方向对齐。然后对新建关节进行重命名。前腿关节依次为LeftHand_ctrl1—LeftHand_ctrl2—LeftHand_ctrl3—LeftHand_ctrl4；后腿关节依次为LeftFoot_ctrl1—LeftFoot_ctrl2—LeftFoot_ctrl3—LeftFoot_ctrl4。</p>

<p>使用移动工具，配合点捕捉键—v键，将新建反向控制关节与原始骨骼进行对齐，LeftHand_ctrl2与LeftHand3重合、LeftHand_ctr13与LeftHand2重合；LeftHand_ctrl4与LeftHand1重合；LeftFoot_ctrl2、LeftFoot_ctrl4与LeftFoot2重合；LeftFoot_ctrl3与Foot3重合。如图7.1.10所示。</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2352404692/" target="_blank"><img src="http://static.flickr.com/3131/2352404692_69b009dac6.jpg" border="0" alt="image019" /></a>图7.1.10</p>

<p>反向控制骨骼位置调整好以后，开始建立控制骨骼与腿部骨骼之间的约束关系。建立方法与步骤与三毛脚部控制骨骼约束相似，例如：选择LeftHand_ctrl2后按住Shift键增加选择LeftHand1，选择主菜单Animation&gt;Constrain&gt;Orient&gt;Option弹出设置窗口，勾选Maintain Offset项，单击Apply键完成操作。前腿与后腿一共需要创建四组约束关系，具体如下：</p>

<p>LeftHand_ctrl2+ LeftHand2&gt;orientConstraint</p>

<p>LeftHand_ctrl3+ LeftHand1&gt;orientConstraint</p>

<p>LeftHand_ctrl4+ikHandle_LeftHand&gt;pointConstraint</p>

<p>LeftFoot_ctrl3+ LeftFoot2&gt; orientConstraint</p>

<p>LeftFoot_ctrl4+ ikHandle_LeftFoot&gt; pointConstraint</p>

<p>约束关系建立完成后，左侧的前后腿的控制骨骼系统全部完成，恢复右侧的前后腿骨骼显示，按照左侧控制骨骼的创建方法与步骤建立右侧的控制骨骼系统，结果如图7.1.11所示。</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2352403942/" target="_blank"><img src="http://static.flickr.com/3004/2352403942_3cd2cd6c1e.jpg" border="0" alt="image021" /></a>图7.1.11
<h6>7 显示关节的选择手柄</h6>
为了方便直接对关节进行设置关键帧，因此需要将设置关键帧的关节选择手柄显示出来，如图7.1.12所示。</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2352403188/" target="_blank"><img src="http://static.flickr.com/3100/2352403188_a2bf3d1560.jpg" border="0" alt="image023" /></a>图7.1.12</p>

<p>各个选择手柄的名称及对应位置参考下图7.1.13所示：</p>

<p><a title="image025" href="http://www.flickr.com/photos/95019520@N00/2351574199/" target="_blank"><img src="http://static.flickr.com/3152/2351574199_ca3fb08cea.jpg" border="0" alt="image025" /></a>图7.1.13
<h6>8 创建豹子的角色集</h6>
创建一个主角色集—All，然后在主角色集层级下创建4个子角色集：CenterBody、leftFoot、leftHand、RightFoot、RightHand，然后将相关骨骼与控制骨骼的有关属性添加至相应的角色集，如图7.1.14所示。</p>

<p><a title="image027" href="http://www.flickr.com/photos/95019520@N00/2352402044/" target="_blank"><img src="http://static.flickr.com/2098/2352402044_24e2fc9464.jpg" border="0" alt="image027" /></a>图7.1.14</p>

<p>各角色集中关节属性内容如下：
<table border="0" cellspacing="0" cellpadding="2" width="608">
<tbody>
<tr>
<td width="160" valign="top"><strong>CenterBody:</strong></td>
<td width="149" valign="top"></td>
<td width="124" valign="top"></td>
<td width="173" valign="top"></td>
</tr>
<tr>
<td width="160" valign="top">CenterTail1.rx CenterTail1.ry CenterTail1.rz</td>
<td width="152" valign="top">CenterTail2.rx<br />
CenterTail2.ry<br />
CenterTail2.rz</td>
<td width="127" valign="top">CenterTail3.rx CenterTail3.ry CenterTail3.rz</td>
<td width="170" valign="top">CenterTail4.rx<br />
CenterTail4.ry CenterTail4.rz</td>
</tr>
<tr>
<td width="161" valign="top"></td>
<td width="153" valign="top">CenterTail5.rx<br />
CenterTail5.ry CenterTail5.rz</td>
<td width="128" valign="top">CenterTail6.rx CenterTail6.ry CenterTail6.rz</td>
<td width="169" valign="top">CenterTail7.rx CenterTail7.ry CenterTail7.rz</td>
</tr>
<tr>
<td width="162" valign="top">CenterHip.rx CenterHip.ry CenterHip.rz</td>
<td width="153" valign="top">CenterSpine3.rx<br />
CenterSpine3.ry CenterSpine3.rz</td>
<td width="128" valign="top">LeftHip_ctrl.rx LeftHip_ctrl.ry LeftHip_ctrl.rz</td>
<td width="169" valign="top">RightHip_ctrl.rx<br />
RightHip_ctrl.ry<br />
RightHip_ctrl.rz</td>
</tr>
<tr>
<td width="162" valign="top">RightShoulder_ctrl.rx<br />
RightShoulder_ctrl.ry<br />
RightShoulder_ctrl.rz</td>
<td width="153" valign="top">LeftShoulder_ctrl.rx LeftShoulder_ctrl.ry LeftShoulder_ctrl.rz</td>
<td width="128" valign="top">CenterSpine1.rx CenterSpine1.ry CenterSpine1.rz</td>
<td width="169" valign="top">CenterSpine2.rx CenterSpine2.ry CenterSpine2.rz</td>
</tr>
<tr>
<td width="162" valign="top">CenterCollor.rx CenterCollor.ry CenterCollor.rz</td>
<td width="153" valign="top">CenterNeck.rx CenterNeck.ry CenterNeck.rz</td>
<td width="128" valign="top">CenterRoot.tx CenterRoot.ty CenterRoot.tz</td>
<td width="169" valign="top">CenterRoot.rx CenterRoot.ry<br />
CenterRoot.rz</td>
</tr>
<tr>
<td width="162" valign="top"><strong>LeftFoot:</strong></td>
<td width="153" valign="top"></td>
<td width="128" valign="top"></td>
<td width="169" valign="top"></td>
</tr>
<tr>
<td width="162" valign="top">LeftFoot_ctrl1.rx LeftFoot_ctrl1.ry LeftFoot_ctrl1.rz</td>
<td width="153" valign="top">IkHandle_LeftFoot.pvx<br />
IkHandle_LeftFoot.pvy<br />
IkHandle_LeftFoot.pvy</td>
<td width="128" valign="top">LeftFoot_ctrl2.rx<br />
LeftFoot_ctrl2.ry LeftFoot_ctrl2.rz</td>
<td width="169" valign="top">LeftFoot2.rx LeftFoot2.ry LeftFoot2.rz</td>
</tr>
<tr>
<td width="162" valign="top"><strong>LeftHand</strong></td>
<td width="153" valign="top"></td>
<td width="128" valign="top"></td>
<td width="169" valign="top"></td>
</tr>
<tr>
<td width="162" valign="top">IkHandle_LeftHand.pvx IkHandle_LeftHand.pvy IkHandle_LeftHand.pvz</td>
<td width="153" valign="top">LeftHand_ctrl1.rx LeftHand_ctrl1.ry LeftHand_ctrl1.rz</td>
<td width="128" valign="top">LeftHand_ctrl2.rx LeftHand_ctrl2.ry LeftHand_ctrl2.rz</td>
<td width="169" valign="top">LeftHand_ctrl3.rx LeftHand_ctrl3.ry LeftHand_ctrl3.rz</td>
</tr>
<tr>
<td width="162" valign="top">LeftHand_ctrl1.tx LeftHand_ctrl1.ty LeftHand_ctrl1.tz</td>
<td width="153" valign="top">LeftHand2.rx Lefthand2.ry LeftHand2.rz</td>
<td width="128" valign="top">LeftShoulder1.rx LeftShoulder1.ry LeftShoulder1.rz</td>
<td width="169" valign="top"></td>
</tr>
<tr>
<td width="162" valign="top"><strong>RightFoot</strong></td>
<td width="153" valign="top"></td>
<td width="128" valign="top"></td>
<td width="169" valign="top"></td>
</tr>
<tr>
<td width="162" valign="top">IkHandle_RightFoot.pvx IkHandle_RightFoot.pvy IkHandle_RightFoot.pvz</td>
<td width="153" valign="top">RightFoot2.rx RightFoot2.ry RightFoot2.rz</td>
<td width="128" valign="top"></td>
<td width="169" valign="top"></td>
</tr>
<tr>
<td width="162" valign="top"></td>
<td width="153" valign="top">RightFoot_ctrl1.tx RightFoot_ctrl1.ty RightFoot_ctrl1.tz</td>
<td width="128" valign="top">RightFoot_ctrl1.rx RightFoot_ctrl1.ry RightFoot_ctrl1.rz</td>
<td width="169" valign="top">RightFoot_ctrl2.rx RightFoot_ctrl2.ry RightFoot_ctrl2.rz</td>
</tr>
<tr>
<td width="162" valign="top"><strong>RightHand</strong></td>
<td width="153" valign="top"></td>
<td width="128" valign="top"></td>
<td width="169" valign="top"></td>
</tr>
<tr>
<td width="162" valign="top">IkHandle_RightHand.pvx IkHandle_RightHand.pvy IkHandle_RightHand.pvz</td>
<td width="153" valign="top">RightHand_ctrl1.rx RightHand_ctrl1.ry RightHand_ctrl1.rz</td>
<td width="128" valign="top">RightHand_ctrl2.rx RightHand_ctrl2.ry RightHand_ctrl2.rz</td>
<td width="169" valign="top">RightHand_ctrl3.rx RightHand_ctrl3.ry RightHand_ctrl3.rz</td>
</tr>
<tr>
<td width="162" valign="top"></td>
<td width="153" valign="top">RightHand_ctrl1.tx RightHand_ctrl1.ty RightHand_ctrl1.tz</td>
<td width="128" valign="top">RightHand2.rx RightHand2.ry RightHand2.r</td>
<td width="169" valign="top"></td>
</tr>
</tbody>
</table>
9 给豹子蒙皮</p>

<p>骨骼系统与控制系统创建完成后，可以进行蒙皮操作。豹子的蒙皮可以使用Smooth Bind方式，蒙皮后进行相应的绘制权重工作，具体方法与三毛角色创建中相同，在此不再重复。</p>

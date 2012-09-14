---
layout: post
title: 第四章第七节 动作与表情的结合
categories:
- Maya
tags:
- combine
- emote
- Maya
- 开始maya吧
- 第四章
published: true
comments: true
---
<p><!--more--></p>

<p><a href="http://hivan.me/2008/03/20/begin-maya.html" target="_blank">回章目录选择</a></p>

<p><a href="http://hivan.me/2008/03/20/fourth-charactor-design.html" target="_blank">回节目录选择</a></p>

<p><h5>本节概述</h5>
本节通过实例讲解如何将角色的表情动画与身体动画合成的方法，注意参照第二章中关于变形次序的讲解。
<h5>制作三毛读书的动画</h5>
在角色动画中，表情动画是相对独立制作的，可以单独制作后添加到身体动画中。表情与语言表达的关键帧不需要重复设置，只需要将表情动作出现的时间调整准确即可。这样制作身体动画和表情动画可以同时进行，最后进行合成，可以提高工作效率。</p>

<p>实例教程
<h6>1 完成三毛的身体动画</h6>
打开4.7_Reading_1.mb文件，这是一个三毛读书的动画片段。三毛为了学习文化知识，利用休息时间找来一本书，独自坐在长凳上，准备从读书识字开始，如图4.7.1所示。</p>

<p><a title="image001" href="http://www.flickr.com/photos/95019520@N00/2347280311/" target="_blank"><img src="http://farm3.static.flickr.com/3001/2347280311_5a5db9cd04.jpg" border="0" alt="image001" /></a>图4.7.1</p>

<p>播放这段动画，可以看到在场景中三毛从坐在长凳上开始，双手通过IK的作用拿起放在长凳上的书本，慢慢将书本拿到眼前。如图4.7.2所示。</p>

<p><a title="image003" href="http://www.flickr.com/photos/95019520@N00/2347279785/" target="_blank"><img src="http://farm3.static.flickr.com/3128/2347279785_580e01939e.jpg" border="0" alt="image003" /></a>图4.7.2</p>

<p>三毛拿起书本以后，身体的动作基本结束，三毛开始进行朗读，这时就需要将表情动画加入其中，首先倒入表情制作文件，选择主菜单File&gt;Import选择第三章制作的口形动画的文件，将其导入当前场景，移动至适当位置，如图4.7.3所示。</p>

<p>注意 在物体级别（Object Mode）缩放口形模型的大小，不会影响变形效果。</p>

<p><a title="image005" href="http://www.flickr.com/photos/95019520@N00/2347283853/" target="_blank"><img src="http://farm3.static.flickr.com/3050/2347283853_bce3be5ece.jpg" border="0" alt="image005" /></a>图4.7.3
<h6>2 将导入的口形模型与身体的头部模型建立混合形状变形（Blendshape）</h6>
倒入文件中，Blendshape的目标模型All带有动画信息，我们将通过它与当前三毛的头部模型制作Blendshape达到动画效果。</p>

<p>首先，需要将角色恢复Bindpose状态。将时间回复到绑定默认状态。进入Animation模块，选择主菜单Modify&gt;Evaluate Nodes&gt;Ignore All取消全部控制工具的作用，选择三毛的CenterRoot关节后选择主菜单Animation&gt;Skin&gt;Go to Bind Pose恢复绑定初始状态。如图4.7.4所示。</p>

<p><a title="image007" href="http://www.flickr.com/photos/95019520@N00/2347283401/" target="_blank"><img src="http://farm3.static.flickr.com/3288/2347283401_6f67e639c2.jpg" border="0" alt="image007" /></a>图4.7.4</p>

<p>选择All头部模型，按住Shift键增加选择当前三毛头部模型，如图4.7.5所示。</p>

<p><a title="image009" href="http://www.flickr.com/photos/95019520@N00/2347283001/" target="_blank"><img src="http://farm3.static.flickr.com/3247/2347283001_eda46804cf.jpg" border="0" alt="image009" /></a>图4.7.5</p>

<p>选择主菜单Deform&gt;Create Blend Shape添加二者之间的Blend Shape。选择All模型，在右侧ChannelBox中的OUTPUTS中将All项的数值设为1，这样当前三毛的头部变形受All模型的完全控制。如图4.7.6所示。</p>

<p><a title="image011" href="http://www.flickr.com/photos/95019520@N00/2348111898/" target="_blank"><img src="http://farm3.static.flickr.com/2239/2348111898_659b6f0c43.jpg" border="0" alt="image011" /></a>图4.7.6
<h6>3 调整混合变形（BlendShape）的变形次序</h6>
选择主菜单Modify&gt;Evaluate Nodes&gt;Evaluate All恢复全部控制工具的作用。播放动画，可以发现当前三毛的头部跟随All模型一起做表情运动，但并不跟随骨骼运动，如图4.7.7所示。</p>

<p><a title="image013" href="http://www.flickr.com/photos/95019520@N00/2348111738/" target="_blank"><img src="http://farm3.static.flickr.com/2347/2348111738_7fc9757981.jpg" border="0" alt="image013" /></a>图4.7.7</p>

<p>这是在因为当前三毛头部模型的设置记录堆栈中，BlendShape排在骨骼之后，骨骼并不是没有起作用，而是骨骼起作用后，被BlendShape的作用覆盖了，最后的结果只能看到BlendShape的效果。解决的办法是将它们的先后顺序颠倒过来即可。</p>

<p>选择三毛头部模型，在模型上RMB（鼠标右键）&gt;Inputs&gt;All Inputs弹出设置窗口，如图4.7.8所示。</p>

<p><a title="image015" href="http://www.flickr.com/photos/95019520@N00/2347281983/" target="_blank"><img src="http://farm3.static.flickr.com/3258/2347281983_fb5720cf58.jpg" border="0" alt="image015" /></a>图4.7.8</p>

<p>可以看到，BlendShape的变形作用位于所有变形作用的最上面，所以三毛头部的最终变形结果是由BlendShape决定的。使用MMB（鼠标中键）按住Blend Shape(blendShape1)项，将其拖动到堆栈的最后，如图4.7.9所示。</p>

<p><a title="image017" href="http://www.flickr.com/photos/95019520@N00/2348111080/" target="_blank"><img src="http://farm3.static.flickr.com/2003/2348111080_e9b6102d5c.jpg" border="0" alt="image017" /></a>图4.7.9</p>

<p>这时三毛的头部立刻回到了身体上，说明骨骼动画的作用在BlendShape之后了。如图4.7.10所示。</p>

<p><a title="image019" href="http://www.flickr.com/photos/95019520@N00/2347281527/" target="_blank"><img src="http://farm3.static.flickr.com/3173/2347281527_c3482949fb.jpg" border="0" alt="image019" /></a></p>

<p>图4.7.10
<h6>4 表情动画于身体动作的匹配</h6>
播放动画，三毛的表情动画与身体动画同时进行，我们希望的是三毛在拿起书本后开始阅读，因此需要调整表情动画开始的时间。</p>

<p>在Character选择栏中选择Sanmao角色集，我们发现三毛的身体动画结束的时间是46帧，这就意味着表情动画在46帧以后开始即可，这里我们将设定从第50帧开始。</p>

<p>在倒入模型时，被倒入的场景中的角色集也一同倒入。在Character选择栏中选择zhonghua_sanmao&gt;face子角色集，这里记录了表情动画的时间信息。选择主菜单Window&gt;Animation Editors&gt;Dope Sheet打开设置窗口，可以看到表情动画是从第一帧开始的，如图4.7.11所示。</p>

<p><a title="image021" href="http://www.flickr.com/photos/95019520@N00/2348110302/" target="_blank"><img src="http://farm3.static.flickr.com/2187/2348110302_59c4d1a171.jpg" border="0" alt="image021" /></a>图4.7.11</p>

<p>选择全部时间标记，使用移动工具，按住MMB（鼠标中键）将标记向右拖动直至起始帧位于50帧为止，如图4.7.12所示</p>

<p><a title="image023" href="http://www.flickr.com/photos/95019520@N00/2348109922/" target="_blank"><img src="http://farm3.static.flickr.com/3037/2348109922_701071fee0.jpg" border="0" alt="image023" /></a>图4.7.12</p>

<p>这时再播放动画，动作顺序表现正常，三毛拿起书本后认真的进行学习：中华人民共和国。</p>

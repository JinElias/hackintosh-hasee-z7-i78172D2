BIOS此处摘录原作者文章,以及bios文件,以供参考

作者：诺小板的诺
链接：https://www.zhihu.com/question/37007270/answer/141872424
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

**这两年来询问的小白太多了，在此郑重声明：此回答和BIOS文件没有任何技术支持，仅供折腾党自己折腾，刷黑或不能启动一律不答疑！！！有疑虑不要刷！！**
<img src="https://pic1.zhimg.com/50/v2-cb2020dd596c97a3632482dc7a33c19a_720w.jpg?source=1940ef5c" data-rawwidth="959" data-rawheight="577" data-size="normal" data-caption="" class="origin_image zh-lightbox-thumb" width="959" data-original="https://picx1.zhimg.com/v2-cb2020dd596c97a3632482dc7a33c19a_r.jpg?source=1940ef5c"/>
Z7D2（P650SE） 通过改BIOS测试NVME启动通过。原厂BIOS只能作为从盘使用无法引导。NVME设备必须插在主板下方标注了SSD的M2接口上，运行于PCI-E
2.0 x4速度下。 另外一个M2接口依然可以使用SATA协议的M2 SSD，两个SSD可以一起工作。也就是说支持NVME协议的M2口只有一个，而SATA协议两个M2都支持。

分享下自己修改的BIOS文件链接: https://pan.baidu.com/s/1mjsJPI4
密码: 7szs

**型号为P6xxSE的主板**支持，包括神舟z7 地球人T5等一系列机型

**请注意！！刷BIOS前请确认自己有一定的计算机运维知识！**

**请再次注意：仔细检查自己的笔记本主板型号是不是P6xxSE！神舟Z7有很多不同主板型号，请勿混淆！有知友因为看错型号导致刷黑返厂。**

**另请注意，此BIOS只支持UEFI启动，不理解这句话的意思请不要刷。**

**还有就是我这里改BIOS只解决NVME引导的问题，就是说使用原厂BIOS能够识别NVME SSD的情况下，刷我的BIOS才有意义，因为原厂BIOS只能把NVME
SSD作为仓储盘使用，无法在上面引导系统。如果你本来就系统里识别不了，那么刷完我的BIOS还是识别不了的。**

刷入方法：制作一个DOS启动盘，把BIOS文件传入。然后在BIOS里关闭UEFI启动，使用传统CSM模式启动到U盘里的DOS。

在BIOS文件夹中执行step1.bat，等待几秒系统会重新启动，再次来到DOS下。

这一次执行step2.bat，开始刷入BIOS和EC。等待两分钟后刷新完成电脑会关闭。此时按电源键开机就可以进入新BIOS了。重新把启动模式改为UEFI即可使用NVME固态启动系统。

改BIOS参考教程：
[神舟战神Z7D2(P655SE)改BIOS强上NVME固态硬盘_笔记本吧_百度贴吧](https://tieba.baidu.com/p/4790179566)
[【教程】自制解锁bios，加slic，改logo和添加序列号_准系统吧_百度贴吧](https://tieba.baidu.com/p/4936939406)
[[Guide] How to get full NVMe support for all Systems with an AMI UEFI BIOS](https://winraid.level1techs.com/t/howto-get-full-nvme-support-for-all-systems-with-an-ami-uefi-bios/30901)

如果你的主板和我不一样但又想NVME引导支持和设置解锁，可以参考以上教程。

20170920更新：
使用新NVME启动模块，或许能支持更多型号SSD。 本主板BIOS文件是可以解锁CPU TDP的，可以在BIOS设置里修改CPU Power
Limit来设置。但是有朋友反映显卡还是有功耗墙，可是我这里用功率表测量双烤可以达到190W以上。后来发现是因为我刷过第三方解锁TDP的VBIOS，但后经验证魔改VBIOS不支持新驱动和新版本win10，就不提供了。

20171017更新：
发现了给PremaMod BIOS增加NVME启动支持的方法，所以又改了一个PremaMod的版本，也上传到网盘了，喜欢的朋友们可以刷这个版本。\

20180810更新：
本人的Z7因为涂过液态金属，某天拆机清理的时候把液金吹到显存里去了，导致独显报废，每次开机等几秒钟就会蓝屏。整个本子已经放弃治疗回收掉了。现在换了台式，以后就没法再做实机测试了。BIOS不会再做改动更新了（其实也没啥好改的了）感谢大家关注，祝使用愉快。

其中评论区讨论到如果需要只能uefi启动,无法使用dos问题,应该切换至legacy boot,把uefi硬盘拔掉后就可以进入dos了
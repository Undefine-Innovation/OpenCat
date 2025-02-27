# OpenCat

OpenCat 是由 Petoi（未来可编程机器人宠物的制造商）开发的一款基于 Arduino 和 Raspberry Pi 的四足机器人宠物框架。

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/walk.gif?raw=true)

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/run.gif?raw=true)

受到波士顿动力公司的 Big Dog 和 Spot Mini 的启发，李荣忠博士于2016年在维克森林大学的宿舍开始了这个项目。经过一年的研发，他创立了 Petoi LLC，并投入所有资源来开发开源机器人。

该项目的目标是促进四足机器人研究、教育和工程开发的合作，推动敏捷且经济实惠的四足机器人宠物的发展，向大众普及STEM概念，并激励新人（包括许多孩子和成人）加入机器人AI革命，创造更多应用。

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/slope.gif?raw=true)

这个项目是一个复杂的四足机器人系统，适用于任何探索四足机器人的爱好者。我们希望与社区分享我们的设计和工作成果，并通过大规模生产降低硬件和软件成本。OpenCat 已部署在 Petoi 所有的仿生手掌大小、逼真的 [可爱机器猫 Nybble](https://www.petoi.com/collections/robots/products/petoi-nybble-robot-cat?utm_source=github&utm_medium=code&utm_campaign=nybble) 和高性能机器狗 [Bittle](https://www.petoi.com/collections/robots/products/petoi-bittle-robot-dog?utm_source=github&utm_medium=code&utm_campaign=bittle) 上。我们现在已经建立了生产线，可以将这些 [经济实惠的机器人套件和配件](https://www.petoi.com/store?utm_source=github&utm_medium=code&utm_campaign=store) 发送到全球各地。

此项目提供了一个基础的开源平台，用于创建惊人的可编程步态、运动和逆运动学四足机器人的部署，并通过基于块的编码/C/C++/Python 编程语言将模拟带到现实世界中。

我们的用户已部署了许多机器人/AI/IoT 应用程序：
- [具有自主移动和物体检测功能的机器人狗](https://www.petoi.com/blogs/blog/reid-graves-robotics-ai-applications-with-bittle-robot-dog-raspberry-pi)
- [使用 Petoi 开源四足机器人制作的 Raspberry Pi 机器人项目](https://www.petoi.com/blogs/blog/raspberry-pi-robotics-projects-with-petoi-open-source-quadruped-robots)
- [在我们的机器人上进行的 NVIDIA Issac 模拟和强化学习](https://www.youtube.com/playlist?list=PLHMFXft_rV6MWNGyofDzRhpatxZuUZMdg)
- [使用 Bittle 和 Raspberry Pi 开发视觉和激光雷达 SLAM](https://www.youtube.com/watch?v=uXpQUIF_Jyk&list=PLHMFXft_rV6MWNGyofDzRhpatxZuUZMdg&index=6)
- [使用 Petoi Bittle 和 Raspberry Pi 进行基于 Tiny 机器学习模型的模仿学习](https://www.learnwitharobot.com/p/imitation-learning-with-petoi-bittle)
- [使用 AWS 实现机器人车队的 IoT 自动化以提高工人安全](https://www.petoi.com/blogs/blog/aws-iot-robot-fleet-demo-with-petoi-bittle)
- [3D 打印配件](https://www.petoi.com/blogs/blog/petoi-bittle-bittle-x-robots-3d-printed-robot-accessories)
- 使用 OpenCat 构建自己的 [DIY 3D 打印机器人宠物](https://www.petoi.com/pages/3d-printed-robot-dog-robot-cat)

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/stand.gif?raw=true)

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/NybbleBalance.gif?raw=true)

我们成功地为这两个迷你机器人套件进行了众筹，并已向世界各地发货数千个单位。

通过我们的 [定制 Arduino Uno 板](https://www.petoi.com/products/nyboard-customized-arduino-board) 和 [高性能伺服器](https://www.petoi.com/products/quadruped-robot-dog-bittle-servo-set)，协调所有本能和复杂动作（行走、跑步、跳跃、后空翻），你可以安装各种传感器和摄像头来引入感知能力，并通过有线或无线连接安装 Raspberry Pi 或其他 AI 芯片（如 Nvidia Jetson Nano）来注入人工智能能力。

请参阅 [Petoi 常见问题解答](https://www.petoi.com/pages/faq?utm_source=github&utm_medium=code&utm_campaign=faq) 获取更多信息。

此外，请查看 [所有 OpenCat 和 Petoi 机器人用户的展示](https://www.petoi.camp/forum/showcase)。

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/ball.gif?raw=true)

## 设置过程：

OpenCat 软件适用于 Nybble 和 Bittle，由基于 ATmega328P 的 NyBoard 控制。更详细的文档可以在 [Petoi 文档中心](https://docs.petoi.com) 查找。

配置板子：

1. 下载仓库并解压。移除文件夹名称中的 **-main**（或其他分支名称）后缀。

2. 打开文件 OpenCat.ino，选择你的机器人和板子版本。
```cpp
#define BITTLE    //Petoi 9 DOF 机器人狗：头部1个 + 腿部8个
//#define NYBBLE  //Petoi 11 DOF 机器人猫：头部2个 + 尾巴1个 + 腿部8个

//#define NyBoard_V0_1
//#define NyBoard_V0_2
#define NyBoard_V1_0
//#define NyBoard_V1_1
```

3. 注释掉 ```#define MAIN_SKETCH``` 以便将其代码切换到板子配置模式。上传代码并按照串口提示操作。
```cpp
// #define MAIN_SKETCH
```

4. 如果激活 ```#define AUTO_INIT```，程序将自动设置而无需提示。它不会重置关节偏移，但会校准 IMU。这只是我们生产线上方便的一个选项。

5. 将 USB 编程器插到 NyBoard 上，如果在 Arduino -> 工具 -> 端口下找不到 USB 端口，请安装驱动。

6. 在 Arduino IDE 的左上角点击上传按钮（->）。

7. 打开 Arduino IDE 的串口监视器。你可以在工具栏找到按钮，或者在 IDE 的右上角找到。

将串口监视器设置为**无行尾**和**115200**波特率。
串口提示：
```
重置关节偏移？(Y/n)
Y
```

如果你想要将所有关节偏移重置为0，请输入 'Y' 并按回车键。

程序将执行重置，然后更新静态内存中的常量和本能技能。

8. IMU（惯性测量单元）校准。

串口提示：
```
校准 IMU？(Y/n)：
Y
```
如果你从未校准过 IMU 或者想重新校准，请输入 'Y' 并按回车键。

将机器人平放在桌子上，不要触碰它。机器人会发出六次长鸣声以给你足够的时间。然后它会读取数百个传感器数据并保存偏移值。当校准完成时，它会发出蜂鸣声。

当串口监视器显示 "Ready!" 时，你可以关闭串口监视器进行下一步。

9. 取消注释 ```#define MAIN_SKETCH``` 使其生效。这次代码变为主要功能的正常程序。上传代码。
```cpp
#define MAIN_SKETCH
```
当串口监视器显示 "Ready!" 时，机器人准备好接收你的下一个指令。

10. 如果你从未校准过关节偏移或在第2步中重置过偏移值，你需要校准它们。如果启动机器人时一侧朝上，它会自动进入校准状态以便安装腿。否则，它将进入正常的休息状态。

11. 你可以直接使用串口监视器进行校准。或者插入蓝牙适配器，使用 Petoi 应用程序（Android/iOS）进行更友好的界面。移动应用程序可在以下链接获取：

* iOS：[App Store](https://apps.apple.com/us/app/petoi/id1581548095)
* Android：[Google Play](https://play.google.com/store/apps/details?id=com.petoi.petoiapp)

你可以参考用户手册中的校准部分（https://bittle.petoi.com/6-calibration）和 Petoi 应用指南（https://docs.petoi.com/app-guide）。

12. 你可以使用红外遥控器或其他应用程序（如 Petoi 应用程序、Python、串口监视器等）来与机器人互动（https://bittle.petoi.com/7-play-with-bittle）。

关于更新：
* 给此仓库加星以接收及时的通知。
* 访问 www.petoi.com 并 [订阅我们的官方新闻通讯](https://www.petoi.com/pages/subscribe-petoi-newsletter) 以获取项目公告。我们还在 [petoi.camp](https://www.petoi.com/forum) 上举办了一个论坛。
* 在 [Twitter](https://twitter.com/petoicamp)、[Instagram](https://www.instagram.com/petoicamp/)、[Facebook](https://www.facebook.com/PetoiCamp/)、[LinkedIn](https://www.linkedin.com/company/33449768/admin/dashboard/) 和 [YouTube 频道](https://www.youtube.com/c/rongzhongli) 关注我们，获取有趣的视频和社区活动。

![](https://github.com/PetoiCamp/NonCodeFiles/blob/master/gif/backflip.gif?raw=true)

## 资源：
* [用户制作的高级教程](https://www.youtube.com/playlist?list=PLHMFXft_rV6MWNGyofDzRhpatxZuUZMdg)
* [用户评论、开箱和演示](https://www.youtube.com/playlist?list=PLHMFXft_rV6PSS3Qu5yQ-0iPW-ohu1sM3)
* [用户展示的 OpenCat 机器人](https://www.petoi.com/pages/petoi-open-source-extensions-user-demos-and-hacks)
* [OpenCat 机器人画廊](https://www.petoi.com/pages/robot-pet-gallery)

OpenCat 机器人已被用于 K12 学校和大学的机器人教育，以教授学生有关 STEM、编程和机器人技术的知识：
- [机器人教育展示](https://www.petoi.com/blogs/blog/tagged/showcase+education)
- [STEM 与机器人课程及教学编码与机器人的资源](https://www.petoi.com/pages/resources-curriculum-stem-coding-robot)
- [机器人竞赛](https://www.petoi.com/blogs/blog/robot-competitions-with-petoi)
- [Petoi 机器人比赛](https://www.petoi.com/blogs/blog/petoi-spring-2024-robotics-contest-winners)

[OpenCat 的旧仓库](https://github.com/PetoiCamp/OpenCat-Old) 包含大量冗余的图像日志，并且已经过时，不再更新。

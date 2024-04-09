# Unity Drone Controller

<p align="center"><img src="images/dji.gif"/></p>

The idea behind this project is to share a set-up for robotics simulation in Unity. 
At the time of this writing, this is simply a Unity-based drone controller—in particular a DJI F450 controller written in C#—which can be controlled
by any joystick you'd like; although, it's been only tested with a PS4 controller (it's pretty easy to set up a different one).

Keep in mind it's a very basic implementation, inspired by other people, in which you can control the drone's altitude and orientation with the joystick sticks.
Feel free to improve it!

本项目旨在开源分享一套通过Unity实现的机器人模拟设置。可以通过手柄控制无人机的飞行高度和旋转等姿态。
截至本文完成之时，本项目只是一个基于unity的无人机控制器，特别是用 C# 编写的 DJI F450 控制器，可以通过任意手柄控制；
不过因成本有限目前仅使用 PS4 控制器进行了测试（设置不同的控制器非常容易）。

需要特别注明的是，本项目仅仅是一个坐在巨人肩膀上的浅尝辄止的尝试。

## Requirements

To start running this project you need to fulfil a few steps.
Firstly, you've got to have Unity installed (obviously), and secondly, you should download the `Art` for the models.
There are only two models in the scene, the DJI F450 drone and the ground to collide with.

运行本项目之前你需要完成以下几步操作：
1. 安装unity（bushi
2. 下载“Art”，内含无人机建模（只有两个，DJI F450和大地模型）

### DJI F450 Drone

The model was downloaded from [here][3DWarehouse DJI F450] (thanks Matheus Monteiro).
However, there are some caveats to use the model directly.
If you import either Collada or SketchUp files, the model won't be complete. 
So I fixed it and exported a Unity package based on a FBX file. Download it from this [link][F450 Unity package].

模型下载自 [here][3DWarehouse DJI F450] ，感谢 Matheus Monteiro。

注意事项：单独导入Collada或SketchUp文件时，模型会不太完整。

所以我进行了修复，导出了一个.FBX的unity包。点击[这里][F450 Unity package]进行下载。

![DJI F450 Image]

### Ground

The ground is basically a 2D `GameObject` (a plane) with some texture on it.
Be sure to download the materials and the texture folders from [here][Ground Material/Textures].
You can place both `Material/` and `Textures/` folders within `Art/Ground` for instance.
Thanks [Indie Pixel] for the cool textures.

大地模型简单来说就是一个2D的"GameObject"，一个带点纹理的平面
所以一定要下载材质和纹理，可以点击 [这里][Ground Material/Textures]下载
可以把“Material/”和“Textures/”文件夹都放在“Art/Ground”里面
感谢[Indie Pixel] 提供牛逼的纹理。

## PS4 Controller

The PS4 controller is connected directly by pairing it with a computer.
Once you've confirmed that the OS has recognized the device you just need to install the Unity Package called "Input System".
It can be installed via the package manager in Unity.

PS4手柄控制器是直接配对到了电脑上的。
一旦确认了电脑和手柄配对完毕后，你需要安装“Input System”的unity包，你可以在package manager里安装它。

![New Input System Image]

The configuration for the drone inputs can be found this [directory][Drone Inputs].

无人机输入的配置文件在这里：[directory][Drone Inputs].

## Future work

There are a few things that can be done based on this project.

1. Improve the physics of the drone.
2. Integrate Unity with ROS and implement algorithms to automatically control the drone (e.g. hovering).
3. Add a camera view to the GoPro Hero 4.
4. Create a more realistic scene around the model to make a better simulation.

基于本项目，未来可以做到:
1. 改善无人机的物理模型。
2. 将Unity与ROS集成并实现算法来自动控制无人机（例如悬停）。
3. 添加无人机自带摄像头的视角
4. 优化场景建模，使仿真看起来更加真实

<!-- Images -->
[DJI F450 Image]: images/dji-f450.png
[New Input System Image]: images/new-input-system.png

<!-- Internal links -->
[Drone Inputs]: drone_controller/Assets/F450_Controller/Input/F450_Inputs.inputactions

<!-- External links -->
[Indie Pixel]: https://www.youtube.com/channel/UC7P6olyswpgJlElZA6RXUNQ
[F450 Unity package]: bit.ly/3qasto4
[Ground Material/Textures]: https://bit.ly/2ImVLyU
[3DWarehouse DJI F450]: https://3dwarehouse.sketchup.com/model/c69f18fa-06b0-4074-bdf5-e383c0772c44/DJI-F450-Quadcopter

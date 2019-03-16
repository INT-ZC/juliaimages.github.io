# 开始: 安装并测试您的安装

大多数用户会想从 Images 包开始，它包含了他多数（但不是全部）的 JuliaImages 基础功能。

## 安装

通过 [package manager](https://docs.julialang.org/en/v1/stdlib/Pkg/) 进行安装,

```julia
(v1.0) pkg> add Images
```

这同时会安装许多依赖项。

Images（可能加上其他一些包）或许就是所有你需要用来操作图片编程的。但是，大多数用户会想要多做一两步来确定您可以载入并显示图片。

## 载入您的第一张图片

在测试想法或者仅仅是跟随着文档操作的时候，有一些可以用来作业的图片会是很有用的。[测试图片](https://github.com/JuliaImages/TestImages.jl)包为您提供了许多“标准图像”。如果您还没有安装它的话，使用 `pkg> add TestImages`。

要载入这个包当中的一张图片，使用：

```julia
using TestImages
img = testimage("mandrill")
```

如果这是您第一次在 Julia 当中操作图片，这些命令很可能会建议您安装几个其他与您的平台相关的包；您大体上应该接受这些建议，除非您有其他的理由来选择一个替代方案。

为了载入您的本地图片，您应该使用 [FileIO包](https://github.com/JuliaIO/FileIO.jl)：

```julia
using FileIO
img = load("myphoto.png")
```

这应该会为您载入图片，同时也可能建议您安装与您平台相关的一个输入/输出包。

## 显示图片

在操作图片时，能看着他们显然是非常有帮助的。如果您配合 [Juno](http://junolab.org/) 或者 [IJulia](https://github.com/JuliaLang/IJulia.jl) 使用 Julia，图片应当会自动显示。

![IJulia](assets/ijulia.png)

使用 Julia 命令行界面（REPL）的用户可以安装 [ImageView](https://github.com/timholy/ImageView.jl) 包：

```julia
using TestImages, Images, ImageView
img = testimage("mandrill")
imshow(img)
```

`ImageView` 包含交互特性（平移/缩放、对比度调整、播放电影、标签、等等），即使是图形环境用户也可能会对它感兴趣。

## 故障排除

读取、写入图片以及图形操作，包含与其他外部软件库的交互。偶尔，安装这些库时可能会出现问题。如果您在执行上述步骤当中时遇到任何问题，请参考 [安装故障排除](@ref) 页面来获取更多信息

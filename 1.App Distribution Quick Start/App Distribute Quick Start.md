#APP-Distribution-Quick-Start(快速上手app开发及上架)

翻译，GO~知识是人类进步的阶梯

>本文适用于刚准备学iOS开发的小白

## 关于本文

主要是为了让你快速上手代码签名和配置一个运行到设备上且最终上架到App Store、Apple TV App store或者Mac App Store的app。在这几种情况下，你的app必须是配置证书并成功签名了的，1.通过Xcode对app做早起的测试，2.真机运行，3.使用了苹果提供的核心服务功能，如：iCloud storage，Game Center，and In-App Purchase

<img src="./1.0.png" alt="图1.0" title="图1.0" width="700"/>

本文教你在开发应用时通用的Xcode工作流程，你将会学到这些内容，1.如何在Xcode中添加Apple ID，2.在Xcode中创建证书并配置对应文件，3.验证访问你的开发者账户，4.真机调试，5.给app添加功能配置对应证书文件。你还将学到经验，例如备份你的签名身份。

## 另请参阅

本文是App Distribution Guide（app开发上架指南）的前奏，App Distribution Guide一文全面覆盖了开发所有阶段和可选可配置的工作流程，例如发布你的Mac应用但是不上架到Mac App Store。阅读App Distribution Guide，你将全面掌握配置文件、发布应用、解决遇到的问题，当然你得继续阅读本文，遇到不懂的专业词汇，请参见术语表（附件）。

## 准备工作

接下来的一切内容如果没有特别声明的地方，均适用于各大平台（iOS，tvOS，watchOS，Mac）

前提条件：

 + 一台Mac电脑，最好已经装有Xcode 7.1
 + 为了最好的体验效果，安装最新的OS X系统和Xcode
 + 用Xcode创建一个没有任务错误、正常运行的项目

另外，你可以选择加入苹果开发者计划，这样就可以使用苹果各大平台提供的功能服务。如果你不加入开发者计划，你给你的app添加的官方功能服务就受限制了，不过最终，你必须加入开发者计划才能向商店发布你的应用。

## 安装最新的Xcode

Xcode是苹果集成的开发工具（IDE），是你开发应用的主要工具。它包含源代码编辑器、图形界面编辑器、及很多其它的特性。Xcode简化了证书配置和代码签名过程，在开发阶段中，你不用离开Xcode。在后续的发布阶段，你会用到Xcode和其它工具将应用提交测试和发布到应用商店

想装最新的Xcode，前往Mac App Store。

## 创建Xcode工程

如果你没有现成的可运行无误的Xcode工程项目，你可以创建一个简单的应用用来在本文中学习代码签名和配置应用

创建应用步骤

1. 打开Xcode

2. 选择File > New > Project,或者在“Welcome to Xcode”面板中点击“Create a new Xcode project”

3. 在你想要创建的平台选项下选择“Application”,从对应的模板列表中选择一个，然后点击“Next”

    例如，创建一个iOS空窗口应用，选择“Single View Application”，如果要创建Mac应用，选择“OS X”的“Cocoa Application”

<img src="./1.1.png" alt="图1.1" title="图1.1" width="700"/>

4. 在出现的对话框中，填写Product Name和Company Identifier。

    Company Identifier应该以反向DNS格式来填写，如果你没有公司标识，就填写 `com.example.你的名字` ，等以后有了，再更改掉。d对话框中其它的内容需要现在就完成，下面的截图展示了创建iOS应用的填写，对于tvOS、watch OS和Mac应用，选项大同小异。
5. 在Language弹出框中选择一个编程语言
6. 点击“Next”

    会有一个对话框让你选择在哪儿保存当前的工程文件
7. 为工程文件的保存指定一个位置，可以选择取消选中“Create git repository on”，然后点击“Create”
    对于iOS应用，一个新的窗口出现了，类似于下图：

<img src="./1.2.png" alt="图1.2" title="图1.2" width="700"/>

## 购买开发者计划

如果你将发布应用上架到商店或者使用TestFlight进行测试，你最需要加入苹果开发者计划或者加入一个已经购买了开发者计划的组织。

购买开发者计划，请前往 [Apple Developer Program Enrollment](https://developer.apple.com/programs/enroll//)，按照指示操作。

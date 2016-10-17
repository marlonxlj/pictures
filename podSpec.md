##pod Spec 为自己的项目添加pod管理功能.
###前言：
  上一篇文章中提到，因为自己在操作的时候遇到很多坑，所在在此做一个记录，同样也希望可以帮到在这个操作上遇到坑的人。
  本文将采用配图和加文字的方式，以最直观的方式呈现操作细节。如果文中有错误的地方，请大家指出以便即时做出调整。
###一、首先在自己的github中添加新的管理目录
####1.进入github账号管理中心，创建管理目录。
  以上过程请参考下图：
   
  ![图片1](/Users/x/Desktop/未命名文件夹/1.png)
  
  ![图片1](/Users/x/Desktop/未命名文件夹/2.png)
  
  ![图片1](/Users/x/Desktop/未命名文件夹/3.png)

####2.上述创建目录完成，接下来做上传代码至github仓库。在此将按照空仓库的方式，在终端进行上传。操作的命令请参数github官网信息

 ![图片1](/Users/x/Desktop/未命名文件夹/4.png)
 
> ``echo "# XLJSegScrollView" >> README.md``
> ``git init``
> ``git add README.md``
> ``git commit -m "first commit"``
> ``git remote add origin https://github.com/marlonxlj/XLJSegScrollView.git``
> ``git push -u origin master``

####请参考下图:
打开终端切换到本地工程的目录下面;
![图片1](/Users/x/Desktop/未命名文件夹/6.png)
![图片1](/Users/x/Desktop/未命名文件夹/7.png)

###二、创建pod Spec文件
根据上面的步骤操作完成，github仓库中有了你上传的代码。接下来要做的就是创建pod spec 文件，同样终端操作。pod 里面有一些命令，不在此做介绍，具体的使用方法：pod --help查看所有的命令。
>`` pod spec create XLJSegScrollView ``
>``其中XLJSegScrollView.podspec 这个命令可以自行定义``

###三、配置spec文件
创建完成生会生成``XLJSegScrollView.podspec``这个文件。
可以使用vim 方式打开，或使用工具打开这个文件进行配置。

    #
    #  Be sure to run `pod spec lint XLJSegScrollView.podspec' to ensure this is a
    #  valid spec and to remove all comments including this before submitting the spec.
    #
    #  To learn more about Podspec attributes see http://docs.cocoapods.org/specification.html
    #  To see working Podspecs in the CocoaPods repo see https://github.com/CocoaPods/Specs/
    #
    
    Pod::Spec.new do |s|
    
      # ―――  Spec Metadata  ―――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  These will help people to find your library, and whilst it
      #  can feel like a chore to fill in it's definitely to your advantage. The
      #  summary should be tweet-length, and the description more in depth.
      #
    
      # ---- Spec 元数据-----------
      s.name         = "XLJSegScrollView" #这里的名字会跟pod search 中的名字一样，和AFNetworking的名字一样
      s.version      = "0.0.1" #版本号一定要和push tag的版本号一至
      s.summary      = "快速实现标题和下划线一起滚动的功能" #这里的描述不要和description描述相同，否则发报警告
    
      # This description is used to generate tags and improve search results.
      #   * Think: What does it do? Why did you write it? What is the focus?
      #   * Try to keep it short, snappy and to the point.
      #   * Write the description between the DESC delimiters below.
      #   * Finally, don't worry about the indent, CocoaPods strips it!
    
      # 这个描述用来生成标签和改善搜索结果
      s.description  = "标题内容滚动的封装，可快速实现功能模块。" #描述信息
    
      # 主页地址
      s.homepage     = "https://github.com/marlonxlj/XLJSegScrollView" #github仓库的目录
      # s.screenshots  = "www.example.com/screenshots_1.gif", "www.example.com/screenshots_2.gif"
    
    
      # ―――  Spec License  ――――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  Licensing your code is important. See http://choosealicense.com for more info.
      #  CocoaPods will detect a license file if there is a named LICENSE*
      #  Popular ones are 'MIT', 'BSD' and 'Apache License, Version 2.0'.
      #
    
      # s.license      = "MIT (example)"
      # s.license      = { :type => "MIT", :file => "FILE_LICENSE" }
      # -- Spec 授权协议----
      s.license      = { :type => "MIT", :file => "LICENSE" }
    
    
      # ――― Author Metadata  ――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  Specify the authors of the library, with email addresses. Email addresses
      #  of the authors are extracted from the SCM log. E.g. $ git log. CocoaPods also
      #  accepts just a name if you'd rather not provide an email address.
      #
      #  Specify a social_media_url where others can refer to, for example a twitter
      #  profile URL.
      #
    
      # 作者信息
      s.author             = { "marlonxlj" => "marlonxlj@163.com" }
      # Or just: s.author    = "marlonxlj"
      # s.authors            = { "marlonxlj" => "" }
      # s.social_media_url   = "http://twitter.com/marlonxlj"
    
      # ――― Platform Specifics ――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  If this Pod runs only on iOS or OS X, then specify the platform and
      #  the deployment target. You can optionally include the target after the platform.
      #
    
      # s.platform     = :ios
      # 平台信息
      s.platform     = :ios, "7.0"
    
      #  When using multiple platforms
      # s.ios.deployment_target = "5.0"
      # s.osx.deployment_target = "10.7"
      # s.watchos.deployment_target = "2.0"
      # s.tvos.deployment_target = "9.0"
    
    
      # ――― Source Location ―――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  Specify the location from where the source should be retrieved.
      #  Supports git, hg, bzr, svn and HTTP.
      #
      # -- 资源在github的位置 ---
      s.source       = { :git => "https://github.com/marlonxlj/XLJSegScrollView.git", :tag => s.version }
    
    
      # ――― Source Code ―――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  CocoaPods is smart about how it includes source code. For source files
      #  giving a folder will include any swift, h, m, mm, c & cpp files.
      #  For header files it will include any header in the folder.
      #  Not including the public_header_files will make all headers public.
      #
      # --源代码位置---
      s.source_files  = "Classes", "XLJSegScrollView/Classes/XlJSegScrollviews/**/*.{h,m}"
      # s.exclude_files = "Classes/Exclude"
    
      # s.public_header_files = "Classes/**/*.h"
    
    
      # ――― Resources ―――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  A list of resources included with the Pod. These are copied into the
      #  target bundle with a build phase script. Anything else will be cleaned.
      #  You can preserve files from being cleaned, please don't preserve
      #  non-essential files like tests, examples and documentation.
      #
      # -- 资源,一般较少用---
      # s.resource  = "icon.png"
      # s.resources = "Resources/*.png"
    
      # s.preserve_paths = "FilesToSave", "MoreFilesToSave"
    
    
      # ――― Project Linking ―――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  Link your library with frameworks, or libraries. Libraries do not include
      #  the lib prefix of their name.
      #
    
      # ---项目链接---
      # 一般是framework和library等
      # s.framework  = "SomeFramework"
      # s.frameworks = "SomeFramework", "AnotherFramework"
    
      # s.library   = "iconv"
      # s.libraries = "iconv", "xml2"
    
    
      # ――― Project Settings ――――――――――――――――――――――――――――――――――――――――――――――――――――――――― #
      #
      #  If your library depends on compiler flags you can set them in the xcconfig hash
      #  where they will only apply to your library. If you depend on other Podspecs
      #  you can include multiple dependencies to ensure it works.
    
      # ----项目依赖设置----
      # 是否为ARC
      s.requires_arc = true
    
      # s.xcconfig = { "HEADER_SEARCH_PATHS" => "$(SDKROOT)/usr/include/libxml2" }
      # 项目依赖其它的第三方库
      # s.dependency "JSONKit", "~> 1.4"
    
    end


###四、上传到pod服务器
####上面的步骤做完了，就是对本地的`XLJSegScrollView.podspec `进行正确性验证。如下图:

####命令:`pod spec lint --verbose`
![图片1](/Users/x/Desktop/未命名文件夹/8.png)

###错误原因是没有在pod服务器中添加版本号信息.
##很重要##
给pod添加tag信息，及版本号信息:

`git tag 0.0.1`

`git push --tag`
![图片1](/Users/x/Desktop/未命名文件夹/9.png)
###五、验证pod功能添加是否成功
`pod search XLJSegScrollView`

`pod trunk push`

####当出现下面这个错误的时候，心里就像出现了好多好多的马，因为在`pod spec lint`的时候都是成功。在google了很多后，得到一个信息那就是等，耐心的等，为此我重复的等了40分钟后成功上传。
`[!]There was an error pushing a new version to trunk: getaddrinfo: nodename nor servname provided, or not known
`
![图片1](/Users/x/Desktop/未命名文件夹/10.png)
####网络不好的情况下，请翻....,在不知重复了多少次后总算成功了。

![图片1](/Users/x/Desktop/未命名文件夹/11.png)

![图片1](/Users/x/Desktop/未命名文件夹/12.png)


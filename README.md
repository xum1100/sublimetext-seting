# SublimeText3及其常用插件的安装与使用 #
## 一. SulblimeText3下载安装 ##

* [官网](http://www.sublimetext.com/)
* [绿色破解版](http://www.w3cfuns.com/tools.php?mod=regex "前端工具库")

## 二. 安装Package Control ##

　1. 复制对应版本的[python代码](https://packagecontrol.io/installation)<br>
　```
　import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
　```
　2. 打开sublime,通过*ctrl + `* 或 *View > Show Console*打开控制台，将1中的python代码复制过去并回车;<br>
　3. 通过*Preferences*查看菜单中出现*Package Control*说明安装成功。

## 三. 常用插件的安装与使用 ##

### 常用插件 ###
* Emmet 代码快速补全
* HTML/CSS/JS Prettify 代码格式美化
* BracketHighlighter 标签高亮配对提示
* SideBarEnhancements 侧边栏，浏览器预览
* View in Browser 浏览器预览

### 插件安装 ###

###### 常规安装 ######

* 通过`Preferences > Package Control`或*ctrl + shift + p*打开_Package Control_搜索框；
* 输入`Install Package`回车；
* 在弹出框中输入插件名称（例如Emmet）回车等待插件安装成功；
* 通过`Preferences > Package Setting`查看菜单中是否存在上门安装插件的名称，若有表示该插件安装成功。

###### _NodeJs_安装(HTML/CSS/JS Prettify插件运行前提) ######

* 没有安装_NodeJs_或路径设置不一致时，在sublime编辑页面单击鼠标右键`HTML/CSS/JS Prettify > Prettify Code` 或_Ctrl + Shift + H_插件异常并提示安装配置_NodeJs_；
![warning](https://www.github.com/xum1100/images-file/raw/master/sublime/sb-nodejs.png)
* 下载[NodeJs](http://nodejs.cn/ "中文官网") / [NodeJs](https://nodejs.org/en/ "英文官网")并安装；
* `Window + R > cmd`打开计算机控制台，输入`node -v`回车，显示版本号表示_NodeJs_安装成功；
![success](https://www.github.com/xum1100/images-file/raw/master/nodejs-setting/node-ok.jpg)
* 打开sublime单击鼠标右键`HTML/CSS/JS Prettify > Set node Path`设置_NodeJs_安装路径；<br>
```
"node_path": {
    "windows": "D:/NodeJs/安装路径/node.exe",
    "linux": "/usr/bin/nodejs",
    "osx": "/usr/local/bin/node"
  }
```

###### 插件BracketHighlighter ######

* 在ST中用_Package Control_安装_BracketHighlighter_;
* 安装完成后，打开`Preferences -> package settings -> Bracket Highlighter -> Bracket Settings – User`,然后添加如下代码;<br>
```
{
    "bracket_styles": {
        "default": {
            "icon": "dot",
            // "color": "entity.name.class",
            "color": "brackethighlighter.default",
            "style": "highlight"
        },

        "unmatched": {
            "icon": "question",
            "color": "brackethighlighter.unmatched",
            "style": "highlight"
        },
        "curly": {
            "icon": "curly_bracket",
            "color": "brackethighlighter.curly",
            "style": "highlight"
        },
        "round": {
            "icon": "round_bracket",
            "color": "brackethighlighter.round",
            "style": "highlight"
        },
        "square": {
            "icon": "square_bracket",
            "color": "brackethighlighter.square",
            "style": "highlight"
        },
        "angle": {
            "icon": "angle_bracket",
            "color": "brackethighlighter.angle",
            "style": "highlight"
        },
        "tag": {
            "icon": "tag",
            "color": "brackethighlighter.tag",
            "style": "highlight"
        },
        "single_quote": {
            "icon": "single_quote",
            "color": "brackethighlighter.quote",
            "style": "highlight"
        },
        "double_quote": {
            "icon": "double_quote",
            "color": "brackethighlighter.quote",
            "style": "highlight"
        },
        "regex": {
            "icon": "regex",
            "color": "brackethighlighter.quote",
            "style": "outline"
        }
    }
}
```
###### 插件SideBarEnhancements ######
* 在ST中用_Package Control_安装_SideBarEnhancements_;
* 安装完成后打开`preferences > package setting > side bar > Key Building-User`，添加如下代码。按F1~F5分别在firefox，chrome，IE，safari，opera浏览器预览效果，当然你也可以自己定义喜欢的快捷键，最后注意代码中的浏览器路径要以自己电脑里的文件路径为准；
```
[
       /*{ "keys": ["alt+f12"],
            "command": "side_bar_open_in_browser",
            "args":{"paths":[], "type":"production", "browser":""}
        },*/
          { "keys": ["ctrl+shift+c"], "command": "copy_path" },
          //chrome
    { "keys": ["f1"], "command": "side_bar_files_open_with",
            "args": {
                "paths": [],
                "application": "C://Program Files (x86)//Google//Chrome//Application//chrome.exe",
                "extensions":".*"
            }
     },
    //firefox
    { "keys": ["f2"], "command": "side_bar_files_open_with",
             "args": {
                "paths": [],
                "application": "E://软件//Firefox//firefox.exe",
                "extensions":".*" //匹配任何文件类型
            }
    },
    //ie
     { "keys": ["f3"], "command": "side_bar_files_open_with",
             "args": {
                "paths": [],
                "application": "C://Program Files//Internet Explorer//iexplore.exe",
                "extensions":".*"
            }
    },
    ]
```

## sublime常用快捷键 ##

####### 编辑类 ######

* `Ctrl + Enter` 光标所在行向下插入新行；
* `Ctrl + Shift + Enter` 光标所在行向上插入新行；
* `Tab` 向右缩进;
* `Shift+Tab` 向左缩进;
* `Ctrl+Z` 撤销;
* `Ctrl + J` 将下一行或鼠标选中的多行合并到光标所在行；
* `Ctrl + Shift + K` 删除光标所在整行；
* `Ctrl + K + K` 从光标处开始删除代码至行尾;
* `Ctrl + /` 单行注释，注释光标所在行，也可鼠标选中多行实现多行注释；
* `Ctrl + Shift + /` 多行注释，注释从光标所在行开始，与光标所在行起始位置标签配对的闭合标签所在行结束；也可选中多行再多行注释；

###### 选择类 ######

* `Ctrl + Shift + [` 折叠选中代码；
* `Ctrl + Shift + ]` 展开选中代码；
*  `Ctrl + K + 0` 展开所有折叠代码；

###### 显示类 ######
 
* _Ctrl + `_ 打开控制台
* `Ctrl + K + B` 开启/关闭侧边栏
* `F11` 全屏
* `Shift+F11` 免打扰模式
* `Alt + Shift + 1`窗口分屏，默认1屏（非小键盘的数字1）
* `Alt + Shift + 2`左右分屏-2列
* `Alt + Shift + 3`左右分屏-3列
* `Alt + Shift + 4`左右分屏-4列
* `Alt + Shift + 5`等分4屏
* `Alt + Shift + 8`垂直分屏-2列
* `Alt + Shift + 9`垂直分屏-3列

###### 搜索类 ######

* `Ctrl + Shift + P` 打开命令框。场景栗子：打开命名框，输入关键字，调用sublime text或插件的功能，例如使用package安装插件
* `Ctrl + F` 打开底部搜索框，查找关键字
* `Ctrl + Shift + F` 指定文件内查找替换
* `Ctrl + P` 打开搜索框。举个栗子：1、输入当前项目中的文件名，快速搜索文件，2、输入@和关键字，查找文件中函数名，3、输入：和数字，跳转到文件中该行代码，4、输入#和关键字，查找变量名
* `Ctrl + G` 打开搜索框，自动带：，输入数字跳转到该行代码。举个栗子：在页面代码比较长的文件中快速定位
* `Ctrl + R` 打开搜索框，自动带@，输入关键字，查找文件中的函数名。举个栗子：在函数较多的页面快速查找某个函数
* `Ctrl + ：` 打开搜索框，自动带#，输入关键字，查找文件中的变量名、属性名等
* `Esc` 退出光标多行选择，退出搜索框，命令框等。


## 参考资料 ##
* [前端开发环境搭建](http://yangxiaofu.com/2015/11/02/%E5%89%8D%E7%AB%AF%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA/)
* [Sublime Text 3 常用插件以及安装方法](https://www.douban.com/note/474507021/)
* [sublime text 3 扩展插件SideBarEnhancements用法教程–使用浏览器快捷预览网页](http://www.tuicool.com/articles/36FNJbv)
* 

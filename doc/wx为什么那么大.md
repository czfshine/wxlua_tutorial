有的同学觉得wxlua很大，想说能不能给它弄小一点，我的答案是可以。

wxlua下有什么
=============
编译过wxlua的人知道在cmake中有一个选项为
	```wxWidgets_ALL_COMPONENTS_28=gl;stc;richtext;aui;xrc;qa;media;net;xml;
html;adv;core;base```
用来设置wxlua生成所需要的库。其中我列举几个较重要的，
如果你的项目不需要这种功能，可以去掉，减小体积。：

*stc模块，全称StyledTextCtrl，一个文本编辑控件，可以设置行号，代码高亮，代码折叠等等，


*xrc模块 用来读取界面布局文件（后缀xrc），这种文件是用所见即所得的工具（如 wxFormBuilder）生成的。

*aui模块 这个模块用来做类似例程中auidemo类似的界面，这个我找不到词语来描述。

*media 模块用来播放各种媒体（声音，视频等）。

*net 模块 用来网络访问的，如果你的项目

*richtext 包含通用富文本控件的功能。（我没用过），看例子好像和RTF文本一样。

*http 简单的HTML渲染器和其他HTML呈现包含在这个库,以及 wxHtmlHelpController , wxBestHelpController 和 wxHtmlListBox 。 


通常在发布前按需要重新编译一下wxlua，可以减少一些体积。

为wxlua加壳压缩
==================
wxlua编译后主要的是一个5M左右的wx.dll，使用ASpack等工具，可以压缩到30%～40%，而且不影响调用。


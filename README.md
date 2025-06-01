# Mp4Toolbox_For_Dolby_digital
## Star History

<a href="https://www.star-history.com/#Basyaact/mp4toolbox&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Basyaact/mp4toolbox&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Basyaact/mp4toolbox&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Basyaact/mp4toolbox&type=Date" />
 </picture>
</a>
#### 介绍
专注于MP4文件处理与Dolby Digital音频编码的开源工具箱，提供高效、易用的杜比音视频处理功能。

#### 软件架构
目前只支持Mac Intel/Silicon和Linux x64/Arm64

环境变量里必须要有mp4muxer和mp4demuxer工具，这个工具箱只是简化流程而已，工具已上传至仓库，请git clone,并随时准备git pull。

#### 先将mp4muxer和mp4demuxer加入环境变量

1.编辑 .bash_profile 或 .zshrc（根据使用的 shell）
```
vi ~/.bash_profile   # 对于 bash 用户
# 或
vi ~/.zshrc           # 对于 zsh 用户
```

2.将路径添加到 PATH 环境变量,在配置文件中，找到 PATH 变量，添加你的工具所在的绝对路径并写在配置文件的最后一行。比如像这样：
在vi工具中，按i进入编辑模式并在最后一行输入：
`export PATH="/path/to/mp4muxer:$PATH"`
`export PATH="/path/to/mp4demuxer:$PATH"`
输入完成后按ESC并输入:wq（写入并退出命令)

3.让配置文件生效

```
source ~/.bash_profile  # 对于 bash 用户
# 或
source ~/.zshrc         # 对于 zsh 用户
```
就可安装入环境变量，同理对于mp4deAndmuxer也可用。

#### 安装工具箱教程

0.  `git clone https://gitee.com/mrturn_1/mp4-toolbox_-for_-dolby_digital.git`
1.  `cd mp4-toolbox_-for_-dolby_digital` （到脚本目录下）
2.  `chmod +x mp4deAndmuxer.sh` (赋予执行权限)
3.  `sudo cp mp4deAndmuxer.sh /usr/local/bin/mp4deAndmuxer` (添加至全局环境变量)

#### 使用说明

# ① 交互式
./mp4deAndmuxer.sh

# ② 命令行
./mp4deAndmuxer.sh demux -i in.mp4 -o demux_dir -t "0-5.2,4-"
./mp4deAndmuxer.sh mux   -o out.mp4 \
                       -a audio.ec3:eng \
                       -v video.h264:23.976 \
                       --dv-profile 5 --overwrite

#### 更新日志
25/03/05:  
发布第一个版本v0.1.0  
  
25/04/05:  
发布第二个版本v0.1.1:  
   1）增加 -h|--help 全局及子命令帮助. 
   2）智能切换至用户默认 Shell（bash/zsh）. 
   3）run_cmd 使用原生调用，无 eval，减少启动子进程. 

（UTC+8)09:50:04:  
 发布第三个版本v0.2.0:  
    1)修复了不能粘贴的bug. 
    2)修复了选择崩溃的错误. 
  
（UTC+8)09:56:04:  
 发布第四个版本v0.4.10(其实已经大大小小修改了二十多次). 
    1)修复了脚本启动死循环问题. 
    2)DEMUX/MUX若无参数则交互式提示文件路径. 
    3)让脚本仅兼容.mp4视频文件(.h264, .h265(HEVC)编码),音频支持 .aac, .wav, .mp3, .ec3, .ac3, .ogg。  

（UTC+8)10:56:04:  
    发布第四个版本v1.0.0(稳定版本)：  
    1)添加新功能：让MUX选项增加三个可选择的杜比视界参数：dv-profile, dv-bl-compatible-id, hvc1flag。  
    2)改进了一些功能，让交互体验友好一点。  
    3)增加了运行脚本的速度，每个参数都会进入线程预先准备执行，提高输出速度。  
    4)第一个稳定版本，目前为止任何功能都没有错误或bug。  

#### 参与贡献
808Melo(Basya). 
欢迎提出issues,有能力可以Pull Request来改进脚本！  
1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request
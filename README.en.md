# Mp4Toolbox_For_Dolby_digital

#### Introduction
An open-source toolbox focused on MP4 file processing and Dolby Digital audio encoding, providing efficient and user-friendly Dolby audio and video processing features.

#### Architecture
Currently only supports Mac Intel/Silicon and Linux x64/Arm64.

You must have the mp4muxer and mp4demuxer tools in your environment variables. This toolbox only simplifies the workflow. The tools have been uploaded to the repository. Please git clone and be ready to git pull at any time.

#### Add mp4muxer and mp4demuxer to Environment Variables

1. Edit .bash_profile or .zshrc (depending on your shell)
```
vi ~/.bash_profile   # For bash users
# or
vi ~/.zshrc          # For zsh users
```

2. Add the path to the PATH environment variable. In the config file, find the PATH variable, add the absolute path to your tools, and write it at the end of the file. For example:
In vi, press i to enter insert mode and enter the following at the last line:
`export PATH="/path/to/mp4muxer:$PATH"`
`export PATH="/path/to/mp4demuxer:$PATH"`
After entering, press ESC and type :wq to save and exit.

3. Make the config file effective

```
source ~/.bash_profile  # For bash users
# or
source ~/.zshrc         # For zsh users
```
Now the tools are added to the environment variable. Similarly, you can do this for mp4deAndmuxer.

#### Toolbox Installation Guide

0.  `git clone https://gitee.com/mrturn_1/mp4-toolbox_-for_-dolby_digital.git`
1.  `cd mp4-toolbox_-for_-dolby_digital` (go to the script directory)
2.  `chmod +x mp4deAndmuxer.sh` (grant execute permission)
3.  `sudo cp mp4deAndmuxer.sh /usr/local/bin/mp4deAndmuxer` (add to global environment variable)

#### Usage

# ① Interactive
./mp4deAndmuxer.sh

# ② Command Line
./mp4deAndmuxer.sh demux -i in.mp4 -o demux_dir -t "0-5.2,4-"
./mp4deAndmuxer.sh mux   -o out.mp4 \
                       -a audio.ec3:eng \
                       -v video.h264:23.976 \
                       --dv-profile 5 --overwrite

#### Changelog
25/03/05:  
First release v0.1.0  
  
25/04/05:  
Second release v0.1.1:  
   1) Added -h|--help for global and subcommand help. 
   2) Smartly switches to user's default shell (bash/zsh). 
   3) run_cmd uses native calls, no eval, reducing subprocesses. 

(UTC+8)09:50:04:  
 Third release v0.2.0:  
    1) Fixed bug where pasting was not possible. 
    2) Fixed crash error when making selections. 
  
(UTC+8)09:56:04:  
 Fourth release v0.4.10 (actually, there have been more than 20 minor changes). 
    1) Fixed script startup infinite loop issue. 
    2) If DEMUX/MUX has no parameters, interactively prompts for file path. 
    3) Script now only supports .mp4 video files (.h264, .h265(HEVC) encoding), audio supports .aac, .wav, .mp3, .ec3, .ac3, .ogg.  

(UTC+8)10:56:04:  
    Fourth release v1.0.0 (stable version):  
    1) Added new feature: MUX options now have three selectable Dolby Vision parameters: dv-profile, dv-bl-compatible-id, hvc1flag.  
    2) Improved some features for a more user-friendly interactive experience.  
    3) Increased script running speed, each parameter is pre-processed in a thread to improve output speed.  
    4) First stable version, so far no features have any errors or bugs.  

#### Contributing
808Melo(Basya).  
Issues are welcome, and you can submit Pull Requests to improve the script!  
1.  Fork this repository
2.  Create a Feat_xxx branch
3.  Commit your code
4.  Create a Pull Request
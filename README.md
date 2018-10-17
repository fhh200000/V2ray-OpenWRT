# V2ray-OpenWRT  
Compiled V2ray Binaries for OpenWRT(ipk file)  
为OpenWRT编译的V2Ray二进制文件（ipk格式）  
Source merged from an "Outdated" Lede firmware  
源代码从一份“过时”的Lede固件处合并  
https://github.com/coolsnowwolf/lede/pull/331  
#-----------------Versions------------------  
For soft routers please visit x86-64 branch.  
软路由请移步X86-64分支。
MT7621 or other mipsel-24kc platforms please visit mipsel-24kc branch.
MT7621或者其他mipsel-24kc平台请移步mipsel-24kc分支。
(Not recommended for installation on a real router due to the low performance)
（因为超乎预期的低性能，不推荐在硬件路由器上使用）
#--------------Installations----------------  
1.Install V2ray,V2ray Pro and the Depencies  
1.安装V2ray,V2ray Pro和依赖  
Note the package dnsmasq-full would make a conflict with the current dnsmasq,so run the following commands:  
注意依赖包dnsmasq-full会与现存项目dnsmasq冲突，所以请运行以下命令：  
opkg remove dnsmasq  
opkg install dnsmasq-full  
2.Because OpenWRT's ip command isn't in its correct place so a link is required:  
2.因为OpenWRT的ip命令不在其正确的位置上，所以我们需要一个链接：  
which ip  
ln -s YourIPPathFromWhich(which中显示的地址) /usr/bin/ip  
3.Generate V2ray profile manually by using:  
3.通过以下命令手动生成V2ray配置文件：  
cd /etc/v2ray  
lua gen_config.lua  
cp TheGeneratedProfile(上一步生成的配置文件) ./  
4.Enable the LuCi V2ray-Pro server  
4.启动图形化V2Ray-Pro服务器  
service v2raypro start  
5.Further settings in LuCi interface  
5.在LuCi界面中完善设置  

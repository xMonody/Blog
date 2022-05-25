# <center>编译ffmpeg
# 安装Msys2以及依赖
```bash
pacman -S mingw-w64-x86_64-nasm mingw-w64-x86_64-yasm mingw-w64-x86_64-cmake base-devel mingw-w64-x86_64-toolchain
```
##依赖
libfmx官网：  git clone https://github.com/lu-zero/mfx_dispatch.git
libx264官网： git clone https://code.videolan.org/videolan/x264.git
libx265官网   wget http://ftp.videolan.org/pub/videolan/x265/x265_3.2.tar.gz
fdk-aac官网： git clone https://github.com/mstorsjo/fdk-aac.git
libfaac官网： git clone https://github.com/Kiennh/libfaac.git
libmp3lame： https://sourceforge.net/projects/lame/files/lame/3.100/
##Msys2编译
 如果是linux平台交叉编译需要指定运行平台目标平台编译器 --cross-prefix=x86_64-w64-mingw32- --arch=x86_64 --target-os=mingw32
 linux平台不用启用禁用下面的依赖 --extra-cflags=-DLIBTWOLAME_STATIC --extra-cxxflags= --extra-ldexeflags= --extra-ldexeflags=-static-libgcc  --disable-lzma --disable-zlib --disable-bzlib 

```bash
./configure --prefix=D://ffmpeg --pkg-config-flags=--static --enable-gpl --enable-version3 --enable-shared --enable-static --enable-sdl2 --enable-libx264 --enable-libx265 --enable-libmp3lame --enable-libfdk-aac --enable-libmfx --enable-encoder=h264_qsv --enable-decoder=h264_qsv --enable-nonfree --enable-libvpx --enable-encoder=libvpx_vp8 --enable-encoder=libvpx_vp9 --enable-decoder=vp8 --enable-decoder=vp9 --enable-parser=vp8 --enable-parser=vp9 --extra-cflags=-DLIBTWOLAME_STATIC --extra-cxxflags= --extra-ldexeflags= --extra-ldexeflags=-static-libgcc  --disable-lzma --disable-zlib --disable-bzlib
```
## rtmp支持
```bash
--pkg-config-flags=--static --enable-gpl --enable-version3 --enable-shared --enable-static --enable-sdl2 --enable-libx264 --enable-libx265  --enable-parser=libx264 --enable-decoder=libx264 --enable-demuxer=libx264 --enable-encoder=libx264 --enable-muxer=libx264 --enable-parser=libx265 --enable-decoder=libx265 --enable-demuxer=libx265 --enable-encoder=libx265 --enable-muxer=libx265 --enable-libmp3lame --enable-libfdk-aac --enable-libmfx --enable-encoder=h264_qsv --enable-decoder=h264_qsv --enable-nonfree --enable-libvpx --enable-encoder=libvpx_vp8 --enable-encoder=libvpx_vp9 --enable-decoder=vp8 --enable-decoder=vp9 --enable-parser=vp8 --enable-parser=vp9 --enable-protocol=rtmp --enable-demuxer=rtmp --enable-muxer=rtmp --enable-protocol=rtsp --enable-demuxer=rtsp --enable-muxer=rtsp --enable-demuxer=flv --enable-muxer=flv --enable-muxer=mp4 --enable-demuxer=mp4 --enable-gcrypt --enable-gmp --enable-openssl --extra-cflags=-DLIBTWOLAME_STATIC --extra-cxxflags= --extra-ldexeflags= --extra-ldexeflags=-static-libgcc --enable-lzma --enable-zlib --enable-bzlib
```
##linux平台编译
```bash
./configure --prefix=/usr/local/ffmpeg ---pkg-config-flags=--static -enable-gpl --enable-version3 --enable-shared --enable-static --enable-sdl2 --enable-libx264 --enable-libx265 --enable-libmp3lame --enable-libfdk-aac --enable-libmfx --enable-encoder=h264_qsv --enable-decoder=h264_qsv --enable-nonfree --enable-libvpx --enable-encoder=libvpx_vp8 --enable-encoder=libvpx_vp9 --enable-decoder=vp8 --enable-decoder=vp9 --enable-parser=vp8 --enable-parser=vp9 --enable-lzma --enable-zlib --enable-bzlib
```
emji表情包
cpu 🧠👽︎👽
电池 🔋
内存 💿📀
硬盘 💻
联网 📡📞🛰
充电 🔌
日历 🗓︎
时间 🕙️
音量 🔔
亮度 💡
温度 🌡
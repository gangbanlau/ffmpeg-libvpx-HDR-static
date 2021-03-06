# ffmpeg-libvpx-HDR-static
A script to build a static binary of FFmpeg optimised for libvpx (HDR 10bit) encoding.

As part of some work producing some developer documentation for the webm team at Google we came to the conclusion that getting a stable, known build of FFmpeg with libvpx in place was non-trivial.

This script was developed on a GCP Centos7 n1-standard-4 Virtual Machine. It was then modified to support debian too, and run on a a GCP Debian n4-standard-4 VM.

By default it grabs a recent, defined and stable release of FFmpeg and libvpx, and the latest releases of many of the other elements that are useful in decoding a source video. The script can be modified at the top to force it to compile the very latest (or any other specified) version of FFmpeg or libvpx. See the comments in the script for more information on this.

It builds a standalone static version of ffmpeg optimised for your chipset and for 10-bit HDR encoding with libvpx. 

This ffmpeg can be distributed to other machines of similar architecture, and simply executed. 

It has been tested on Centos 7 and Ubuntu 16.04, and on Debian 9 Linux variants. Please let us know if you have success with it on other architectures.

# Execution 

This has been tested on Centos7 and Debian GNU/Linux 9 (stretch)

```{r, engine='bash', count_lines}
$ curl https://raw.githubusercontent.com/id3as/ffmpeg-libvpx-HDR-static/master/build_static_ffmpeg_centos-debian.sh > ffmpeg-build-script.sh
$ chmod 766 ffmpeg-build-script.sh
$ ./ffmpeg-build-script.sh
```

Takes about 25 mins to build on the tested machines.

On many architectures you can replace the last line with this to make the build considerably faster:

```{r, engine='bash', count_lines}
MAKEOPTS=-j4 ffmpeg-build-script.sh
```
But we don't consider that to be tested widely enough to clearly define which environments will universally support it. Might be worth a test on your own architecture.

# About

While the script should ‘just work’ and is offered ‘as-is’ and unsupported to the community the team at [www.id3as.co.uk](www.id3as.co.uk) will be monitoring GitHub and if we can help with any issues we will try to find some time to improve the script, so please do feed back on GitHub.

[![image alt text](https://static.wixstatic.com/media/b1006e_f523c081c6f448dd91e45e46eea54a86~mv2.png?dn=Screen+Shot+2018-01-17+at+10.25.15.png)](http://id3as.co.uk/active)


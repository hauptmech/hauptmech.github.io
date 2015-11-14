---
layout: post
title: Android Studio 1.4.1, Android NDK r10, gradle-experimental
---

As a newb to android, java, and gradle I had trouble figuring out how to best
setup the NDK. There have been a lot of changes to the whole android system over the last year and the integration of the NDK into gradle is still in process.

Here's what worked for me...

1) Use the NDK integrated with Android Studio.
    I went through a bunch of iterations on this. First I installed the NDK via my
    distro, archlinux. Then I installed via the download from google. Finally installed
    via the Android SDK Manager. This final approach seems to be the preferred method.

2) Use gradle-experimental.
    I resisted using this initially but I've found that it works fine and I'll
    be in good position when the android guys make the switch.

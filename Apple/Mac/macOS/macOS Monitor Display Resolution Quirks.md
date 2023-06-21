---
created: 2023-06-20
updated: 2023-06-21
---

Many people have written a lot of things about how monitor display resolutions and UI scaling works with [[macOS]]. This comment from [r/mac](https://old.reddit.com/r/mac/comments/vtl7nk/is_4k_scaling_for_external_monitors_unbereable/if8mk1c/) perfectly describes the situation.

>The problem basically comes down to this. macOS supports only two sizes for its UI, "1x" and "2x" (with 1x typically being used for pre-Retina [[Mac|Macs]] and 2x being used for Retina Macs). Apple did this because when they went to Retina displays on Macs, they used displays that were exactly 2x the resolution in each dimension as their previous displays, so a 2x UI mode let them keep things the same physical size as before.
>
>So, for instance, a 27" iMac display used to be 2560x1440. Now a 27" iMac or Studio Display is 5120x2880, and uses the 2x UI mode (so everything is the same physical size it was on the 1440p screens). So what happens if you get a 3840x2160 27" display?
>
>At native resolution, 3840x2160 @ 1x will make everything significantly smaller than on a 27" iMac, so you may find it hard to read. (This would be less of a problem on a 32" display, though, since the display itself is larger.) In the 2x mode, you'll get the same real estate as a 1920x1080 display, so everything will be much larger.
>
>As a workaround, Apple does let you run "scaled" resolutions. So what you can do is run at 5120x2880 (5K) using the 2x mode, and have macOS scale it down to 4K. This lets you have the same screen real estate as a 27" iMac, and it will still be clearer than a 1440p display, but it won't be as sharp as a real 5K display. More importantly, because you're running at a non-native resolution, this isn't ideal for work that may require pixel precision like graphic design.
>
>As for performance, it kind of depends on your Mac. Running at 5K scaled does require slightly more GPU power than running at native 4K. If you're using something from the past few years with an Apple Silicon chip or a discrete GPU it probably won't be an issue. I've used an Intel 13" MBP with a Studio Display though and it can definitely drop some frames and make the fans spin up.

I'll add a note about DPI/PPI:

The [[macOS]] UI was originally designed to be displayed on monitors that were around 110ppi (pixels per inch). In the mid 2010s [[Apple]] released "retina" displays for their machines, doubling the PPI to ~220ppi, which were literally 2x the resolution in both horizontal el and vertical directions. A 2560*1440 iMac display was now 5120x2880.

But because all of the UI was designed for the 110ppi displays, although they rendered content at full resolution, the UI was scaled to look like the older non-retina resolution. As a result everything looked sharper and had more clarity, but the UI wasn't tiny.

Because [[macOS]] only supports either 110ppi or 220ppi displays properly, if you are using a display with a different ppi (eg a 27" 4K display has PPI of 163. Great for Windows, not great for macOS) you will likely need to use a scaled UI. This means there will be some performance impact - and the text/details won't be as crisp as they could be.[^1]

Simple example:
You have a 27" 4K (3840*2160) display. To get the best picture quality with proper UI size, you want to use the "Looks like 1440p" display setting. macOS will render your image at 5K resolution and then scale it all down by 1/2x to the 1440p resolution, and it will then scale this to the 4K resolution.

Because of the extra scaling involved, there is a performance hit because the GPU works harder and the text won't look as crisp as possible because 1440p doesn't scale perfectly to 4K - it's got fractional scaling.

[^1]: https://bjango.com/articles/macexternaldisplays2/
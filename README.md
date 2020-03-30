# surgical-mask-clip
A 3D printable clip to improve the comfort of wearing a surgical mask for a long time.

![](https://raw.githubusercontent.com/pmotch/surgical-mask-clip/master/readme_assets/surgical-mask-clip-single-300px.jpg)![](https://raw.githubusercontent.com/pmotch/surgical-mask-clip/master/readme_assets/surgical-mask-clip-video-original.gif)![](https://raw.githubusercontent.com/pmotch/surgical-mask-clip/master/readme_assets/surgical-mask-clip-printing-300px.jpg)

# Why
COVID-19 caused a shortage of [surgical masks (face masks)](https://www.fda.gov/medical-devices/personal-protective-equipment-infection-control/n95-respirators-and-surgical-masks-face-masks) ([archive.org link](https://web.archive.org/web/20200325214258/https://www.fda.gov/medical-devices/personal-protective-equipment-infection-control/n95-respirators-and-surgical-masks-face-masks)) and hospitals are having a hard time replenishing their supplies. Our [local hospital said they're running low on masks](https://www.courierpress.com/story/news/2020/03/18/coronavirus-deaconess-ask-public-provide-medical-face-masks/2865273001/) ([archive.org link](https://web.archive.org/web/20200326225658/https://www.courierpress.com/story/news/2020/03/18/coronavirus-deaconess-ask-public-provide-medical-face-masks/2865273001/)) and asked the community to [make some](https://www.deaconess.com/How-to-make-a-Face-Mask) ([archive.org link](https://web.archive.org/web/20200327003117/https://www.deaconess.com/How-to-make-a-Face-Mask)). My wife sews, so [she made a bunch](https://raw.githubusercontent.com/pmotch/surgical-mask-clip/master/readme_assets/sewn_masks.jpg).

Then I saw pictures on reddit showing what happens when someone wears a surgical mask for a long time -- it's not good. I wondered if I could create a clip that could make wearing them more comfortable behind the ears, so I gave it a shot.

I 3D printed a few different sized prototypes and included them when she delivered the masks to the hospital. The person who accepted the donation liked the idea, took it to the hospital executive committee, and they said they wanted 200 more of the largest prototype I had!

This project is that successful prototype.

# Files

Descriptions of the files in this project:

## `surgical_mask_clip.blend`

This is the Blender project file. The final object is a joined object from other primitive objects cylinders, rings, etc. You can definitely get back to those in version control.

## `surgical_mask_clip.stl`

The exported STL file that you can use to import into your slicer software; in my case I used PrusaSlicer. I used the Blender addon "Mesh: 3D-Printer Toolbox" to export it.

## `surgical_mask_clip-single.3mf`

The PrusaSlicer file for printing one clip.

![surgical_mask_clip-single.3mf](https://raw.githubusercontent.com/pmotch/surgical-mask-clip/master/readme_assets/sugical_mask_clip-single_g-code_screenshot.png)

## `surgical_mask_clip-single_0.2mm_PLA_MK3S_29m.gcode`

G-code file ready to put on an SD card and print a single clip to your Prusa i3 MK3S.

## `surgical_mask_clip-multiple.3mf`

The PrusaSlicer file for printing as many clips as one can reasonably fit on the build plate and still be able to safely remove them. 18 in this case.

![surgical_mask_clip-multiple.3mf](https://raw.githubusercontent.com/pmotch/surgical-mask-clip/master/readme_assets/sugical_mask_clip-multiple_g-code_screenshot.png)

## `sugical_mask_clip-multiple_0.2mm_PLA_MK3S_8h42m.gcode`

G-code file ready to put on an SD card and print 18 clips to your Prusa i3 MK3S.

## `default_scene.blend`

A handy blank build plate object in Blender in case you want to start from scratch with your own modeling.

# Design stuff

Here's a list that I thought about for the design:

- Dimensions XYZ: ~130mm, ~28mm, ~10mm.
- PLA bends well, yet rigid enough.
- Arc of the bend holds around the neck, but isn't a perfect fit allowing some tension.
- Thickness allows enough surface area over the skin to be comfortable, yet not use too much filament.
- More infill makes it more rigid. 100% infill is best I found.
- Easy to wash.
- [Minwoo Choi](https://www.prusaprinters.org/social/52530-minwoo-choi)'s design [on PrusaPrinter](https://www.prusaprinters.org/prints/25999-mask-connection-clips) was a validating design and has some evidence of adoption (very nice!), but after comparing this design, the edges needed beveling, the sizes were too small, and the hooks were a little too narrow for users to easily slip in the elastic bands.

# Blender settings

Useful Blender settings I used:

- See various articles on how to get Blender prepared for 3D Print modeling. It's not by default, so you'll want to do that.
- The model is in millimeters.
- The "Floor" included in the model is of the dimensions of the Prusa i3 MK3 build plate
- Enable in addons "Mesh: 3D-Print Toolbox". It's used to export the STL and check for 3D printing modeling problems.

# Printer and slicer settings

This project is a perfect fit for the Prusa i3 MK3S, but many people will find a way to make this work on their printer. Here's some printer and PrusaSlicer settings I used:

- 0.4mm nozzle
- 100% infill (say yes to the infill pattern suggestion)
- 0.20 QUALITY
- PLA works. I'm sure other materials will work too, but unsure how rigid they'll be.

Note: other settings can be seen if you open the `.3ds` files in PrusaSlicer.

# Mass printing right away

If you want to set up a farm and print hundreds or thousands of these immediately without any modifications, do this:

1. Get a Prusa i3 MK3S printer and set it up with a spool of PLA
2. Put the `sugical_mask_clip-multiple_0.2mm_PLA_MK3S_8h42m.gcode` file on the SD card (your own or the one that came with the printer)
3. Turn on the printer, select this file from the SD card and print!

It's 8 hours and 42 mins for 18 clips. If you modify the .3ds file to use 15% infill the time drops to ~6 hours.

# Feedback, changes, and contact

Please share any feedback you have. Good and bad!

If you're familiar with GitHub, issues work great.

If you're on PrusaPrinters, [leave a comment in the project](https://www.prusaprinters.org/prints/27357-surgical-mask-clip/comments). If you have success with it, let me know here too!

Feel free to directly contact me as well:
- [dan.cundiff [at] gmail.com](mailto:dan.cundiff@gmail.com)
- DM @ https://twitter.com/pmotch

# FAQ

## Is this limited to just the Prusa i3 MK3S 3D printer?

This project is ready to go on the Prusa i3 MK3S printer, but one could take all the files (except for the G-code ones) and use them on any different printer.

The `Floor` object in the Blender file is the dimensions of the Prusa i3 MK3S, but that isn't important if you're just exporting the `Clip` to an STL - it's just useful when modeling on this specific printer. The G-code files are specific to the Prusa i3 MK3S, but you can take the `.3ds` files and generate your own G-code exports.

## Why use git and GitHub to store these project files?

Git / GitHub is something I'm familiar with, and I noticed some people using git for version controlling 3D stuff. It's also nice using GitHub to host the documentation and files. Works good enough. You can also find this project on PrusaPrinters print hosting site: https://www.prusaprinters.org/prints/27357-surgical-mask-clip

## Why choose Creative Commons Attribution 4.0 International as the license?

I'm familiar with software licenses (MIT, Apache 2, GPL, etc), but after having a look, it seems like CC licenses are common on 3D model things.

## Why didn't you use git-lfs?

I looked into it because it feels odd committing binary-ish like assets, but it seemed like the files are small enough to not justify LFS. I'm willing to change that if someone says it's a good idea.

## Why did you choose Blender to model your 3D print?

Several reasons:
- I'm new to 3D printing and had to pick something
- Blender isn't perfect for 3D printing, but it's good enough
- Blender is free (the CAD options looked seemed to be not free)
- Blender can be used for a lot of other things, so learning that made sense

## Your 3D models aren't precise. Why?

I agree. I haven't learned all the tricks in Blender to make alignment of things perfect, but the tolerances when you 3D print them aren't perceptible nor do they jeopardize the structural integrity it seems. I do like precision though, so if you can make it better, I welcome pull requests!

## Is it sanitizable?

I'm unsure. That said, the successful Prusa face shield project has some information on various disinfection tests performed on their 3D printed face shield: https://help.prusa3d.com/en/article/prusa-face-shield-disinfection_125457

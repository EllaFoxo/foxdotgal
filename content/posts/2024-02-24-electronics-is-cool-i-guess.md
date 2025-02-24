---
date: "2025-02-24T13:12:02+01:00"
title: "Electronics is cool, I guess"
description: "On learning a new skill, I have (almost) no idea what I'm doing"
toc: false
tocOpen: false
isStarred: false
tags:
  - Electronics
  - 3D Printing
---

Since around 2019, I've been dead-set on learning the skills that 10 year old me once dreamed of figuring out. Back then, I imagined being able to do so much cool stuff. I never quite got the hang of until I was late into my twentys. Life always got in the way, and those aspirations had to be put aside.

In 2020, Blender's UI took a huge leap forward, and I was finally able to take my first steps into 3D modeling. I sunk my teeth into the sculpting tools, and the Unity game engine, intent on creating VRChat avatars to represent myself during the pandemic. That was a crazy time. In 2022, I returned to 3D printing, having the urge to turn some of those models into physical objects that I could hold in my hand. But as amazing as it is, Blender absolutely sucks for hard surface modeling - especially when it comes to dimensional accuracy.

So there was a brick wall ahead of me. It was CAD.

There was FreeCAD. I do not like FreeCAD. It is in a perpectual state of not being quite there. One day, I hope I can enjoy it, but as of now, the engine gets in the way. There are too many obtuse errors that, as a newbie, are nigh impossible to decipher. I tried OpenSCAD, and the math really hit me hard. It is cool! But it is not for me. Eventually I had to forfeit my desire to use open source tools, and pick something up with a shallower learning curve. In 2023, that was Autodesk Fusion.

I despise Autodesk as a company, just as much as artists do with Adobe. Their licensing model is hostile, and the sofware crashes as frequently as Photoshop does. On a couple of accounts, my entire Fusion library got completely corrupted. I'm taking regular offline backups now, and I do not trust their cloud saves. But you know what, I finally got over that learning curve, and I couldn't be happier. There is a lot I still don't know, like surface modeling, but eh. I'll take a win when I can get one.

## Cracking the Skill of Electronics

Usually when I am learning a new skill, I need a project that lets me sink my teeth into it. Something that I'm allowed to fail on, or ask for help with if I get stuck. But it's also a place to practice, and this has been no different for electronics.

When Prusa announced the Prusa XL in 2021, the headline feature for me was the load cell in the toolhead. It lets it figure out the Z homing position, and build a bicubic mesh of the bed, all by tapping the nozzle to the build plate. It took ages before the printer eventually hit the market, but the load cell 'just worked', and Z offsets were a thing of the past. I wanted it, but I don't have Prusa XL money. And it wasn't fully open source. Prusa have been dropping the ball when it comes to open source commitment. For a company that founded itself on the very principle, it sure is disappointing. Plus the software had no way of working with Klipper in its current state. At least it could be studied, since that bit was open source<sup>[[1]](#footnotes)</sup>. I wanted a load cell Z probe in Klipper, but I wasn't really in a position to make it happen at the time.

Fast forward to early 2024, and we _still_ didn't have load cell Z probes in Klipper. It was so frustrating! People always had talks of doing this, but nothing surfaced in those 3 years. Something had to be done. It was about this time I became aware of the work by [Gareth Farrington](https://github.com/garethky). The mad lad took Prusa's Nextruder from an XL unit, and [slapped that thing onto a Voron](https://www.youtube.com/watch?v=ATdIHIhHrec). He was reverse engineering Prusa's load cell code to work with Klipper. The chicken and egg problem of hardware vs. software first, was solved. It looked so goofy, this Frankenstein's Prusa-Voron machine, but it worked. If it works, it ain't stupid.

That lead me to see a problem that I wanted to solve. I am, by all accounts, terrible at math. I'm glad the software was a solved problem, and Gareth's done a remarkable job at it. But for hardware? A project for me to apply myself in electronics, finally! We got chatting, and eventually formed a group to make this happen.

When I've described my thought process to people, I've said it's like a box-ticking exercise. You can try to tick the boxes you know exist, but for the ones you don't - you have to uncover them through learning. Did you add that ground plane? Are you keeping analog traces well clear of power supply routing, to avoid inteference? You have to ask the right questions and read _lots_ of datasheets. The more boxes you discover and tick, the better your design becomes, and so does your understanding.

Then there's the tooling. There is no best or worst EDA program; there is _your_ EDA program. For me, [KiCAD](https://www.kicad.org) has been a breath of fresh air to use. Even at a beginner level, KiCAD feels like it's the perfect tool for the job. That's not to say it's perfect, but it's definitely up there in terms of quality. At no point do I feel I'm being held back, or the interface is getting in the way; it simply doesn't. I love it.

## Where to go from here?

There is a lot about electronics design on this project I have learned, but I still consider myself quite the newbie, and that's okay! I recognise my own limits. I don't fully trust my own schematics or board layouts yet, which means I'm leaning on peer reviews to help push this thing into production.

This week, I'll be at the electronics bench, soldering up the first batch of 20 beta units for a closed beta. I've been away from home for a bit, but I can't wait to get back into the hobby room. There's a shipment of PCBs sitting on my desk at the office, just waiting to be soldered. I'm excited!

After this project is concluded, I will likely turn my head towards toolhead PCB integration. Meaning, you won't need a separate board to handle all the ADC stuff. After that? Who knows. I'll need another project to sink my teeth into before I learn anything new here.

### Footnotes

**[1]** In most part. Their machine learning model and data for bed squish isn't open source.

# TargetPointInside
I made a 3D model of my local Target.

## Motivation
After playing around with [Target's Cartwheel app](https://itunes.apple.com/us/app/cartwheel-by-target/id659563061?mt=8), I discovered a very neat 3D render of my local target. These renders can be found under My List -> My Store. Poking around in my iPhone's system files, I tried to see if I could pull the model directly. Unfortuanely all I found were svg, lua, and zip files. The zip doesn't extract, and the meta.lua file is unreadble. These files may contain information about how the final render is suppposed to look (Eg. heights of the model). Instead I worked to recreate the render using only the SVG file.

## Process
1. **Extract** the SVG file from an iOS system running the Cartwheel App after the local store has been cached.
`/var/mobile/Containers/Data/Application/<AppString>/Library/Caches/com.pointinside.images/<ImageString>.svg`
2. Edit the **SVG** file, stripping away any tags which contain aisle numbers, departments, icons, etc.  
This can be done with a basic text editor.
3. Convert the **SVG** to **PNG**  
[http://svgtopng.com](http://svgtopng.com)
4. Convert the **PNG** to **STL**.  
I took two different conversions, one with a slightly higher tolerance than the other to keep additional details.  
[http://selva3d.com](http://selva3d.com)
5. Import into 3D authoring tool to merge the two **STL** files together, and for further processing, forming a **SKP** file.  
I used SketchUp with the SketchUp STL extension and scaled them by hand. I created two separate layers in hopes that the model’s intersection would not cause any issues.

## Afterward
I plan on cleaning up the SKP file and parsing it through [JanusVR](http://janusvr.com) via [SketchUp2Room](https://github.com/lisa-lionheart/sketchup2room).  
I will also research the other surrounding files to see if there is a more direct way to pull the 3D model from the source instead of recreating it. All I know is that it is using some underlying OpenGL api.  
All models used are copyright [Point Inside](http://www.pointinside.com). This project is purely done for educational purposes only.

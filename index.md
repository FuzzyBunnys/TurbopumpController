## Turbopump Controller

So to get the whole fusor working, I need to generate a vacuum, and to generate a vauum I need some pumps. In particular I need a turbopump and a backing pump. I have both, but only the backing pump is working. The turbopump needs a controller, and those are expensive so I've decided to build my own!


### The PCB
#### First Attempts 
I've built many PCB's before, but this is the first time I've done a 4-layer board. The circuit is based on John Futter's (From the fusor.net forums) design, the only real modification I made was to add an LCD screen, a Raspberry Pi Pico, and some buttons. Joe Gayo on the fusor.net forum very kindly pointed me to the following [video](https://www.youtube.com/watch?v=ySuUZEjARPY) about proper PCB grounding. While it's long, it's very worth it. The whole PCB was laid out in [KiCad](https://www.kicad.org/), and I commissioned a little chibi bunny drawing from a great [artist](https://twitter.com/courtelizbth) on twitter. A few revisions were necessary to deal with some layout errors, but I soldered up the board and began testing. The files for the most recent complete revision are available on my [GitHub repository](https://github.com/FuzzyBunnys/TurbopumpController/tree/main/Turbopump%20Controller). I used [JLPCB](https://jlcpcb.com/) for the boards simply because their quote was the cheapest. 
![Soldered PCB](https://raw.githubusercontent.com/FuzzyBunnys/TurbopumpController/gh-pages/IMG_2115.JPG) If you want to examine the [schematics and PCB](https://kicanvas.org/?github=https%3A%2F%2Fgithub.com%2FFuzzyBunnys%2FTurbopumpController%2Ftree%2Fmain%2FTurbopump%2520Controller) immediately you can use the wonderful [KiCanvas tool](https://kicanvas.org/home/) that was put together by [Stargirl](https://twitter.com/theavalkyrie). 
#### Second Revisions
Returning to this project after over a year away revealed some problems. My skills have continued to develop and I can see mistakes and poor practice in the schematics and PCB design. To begin, I've started to re-work the schematics for legibility. You can see the improvement in the schematic layout for the microcontroller quite quickly with the two photos below. 
![New Schematic](https://raw.githubusercontent.com/FuzzyBunnys/TurbopumpController/gh-pages/signal-2023-12-18-092529_002.png)  
The New Schematic  
![Old Schematic](https://raw.githubusercontent.com/FuzzyBunnys/TurbopumpController/gh-pages/signal-2023-12-18-092559_002.png)  
The Old Schematic
### The Program
I wanted to use this project as an excuse to pick up another new language, [Ada](https://en.wikipedia.org/wiki/Ada_(programming_language)), I've been curious about it for awhile largely because of it's safety features. Handily a bunch of people have been doing a bunch of work to get it running on the RP 2040, which powers the Raspberry Pi Pico that I have on the PCB. I'm also really interested in using [SPARK](https://en.wikipedia.org/wiki/SPARK_(programming_language)) which is a [formal method](https://en.wikipedia.org/wiki/Formal_methods). It's a powerful tool that lets you prove properties about your program which is important if you want it to be safe and reliable.

Step one in the programming section is to get connected to the Raspberry Pi Pico so that we can put stuff on it. To do that we're going to use [OpenOCD](https://openocd.org/doc-release/html/About.html#What-is-OpenOCD_003f). This is a program that lets us do On Chip Debugging, Jeremy G's [tutorial](https://www.youtube.com/watch?v=g3sGKoLafew) on YouTube was a huge help and I basically followed it step for step. I've had to work through a bunch of tutorials on Ada, and relative to other languages, there isn't a lot on the internet. [Maciej Sobczak's series](http://www.inspirel.com/articles/Ada_On_Cortex.html) is excellent for microcontroller programming, [Paul Jerret's talk](https://archive.fosdem.org/2022/schedule/event/ada_outsiders_guide/) was a nice quick overview, as was [Jean Pierre Rosen's](https://www.youtube.com/watch?v=V-WK6Iaqlns), finally the [AdaCore website](https://learn.adacore.com/courses/Ada_For_The_Embedded_C_Developer/chapters/02_Perspective.html) has some excellent documentation. SPARK is a subset of the Ada language that lets you prove some properties about your program. As simply as possible, you have a specification and a program, and SPARK lets you check that there's a correspondence between your program and your specification. I found the following [talk](https://www.youtube.com/watch?v=97G1V2U8Drk) very helpful as an introduction into how this works.  
```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```



## Turbopump Controller

So to get the whole fusor working, I need to generate a vacuum, and to generate a vauum I need some pumps. In particular I need a turbopump and a backing pump. I have both, but only the backing pump is working. The turbopump needs a controller, and those are expensive so I've decided to build my own!


### The PCB
I've built many PCB's before, but this is the first time I've done a 4-layer board. The circuit is based on John Futter's (From the fusor.net forums) design, the only real modification I made was to add an LCD screen, a Raspberry Pi Pico, and some buttons. Joe Gayo on the fusor.net forum very kindly pointed me to the following [video](https://www.youtube.com/watch?v=ySuUZEjARPY) about proper PCB grounding. While it's long, it's very worth it. The whole PCB was laid out in [KiCad](https://www.kicad.org/), and I commissioned a little chibi bunny drawing from a great [artist](https://twitter.com/courtelizbth) on twitter. A few revisions were necessary to deal with some layout errors, but it's all soldered up now and the files are available on my GitHub repository. I used [JLPCB](https://jlcpcb.com/) for the boards simply because their quote was the cheapest. I should note that until I've finished writing the code and got everything up and running you shouldn't trust the board. There might be some undiscovered errors.  
![Soldered PCB](https://raw.githubusercontent.com/FuzzyBunnys/TurbopumpController/gh-pages/IMG_2115.JPG)


### The Program
I wanted to use this project as an excuse to pick up another new language, [Ada](https://en.wikipedia.org/wiki/Ada_(programming_language)), I've been curious about it for awhile largely because of it's safety features. Handily a bunch of people have been doing a bunch of work to get it running on the RP 2040, which powers the Raspberry Pi Pico that I have on the PCB. I'm also really interested in using [SPARK](https://en.wikipedia.org/wiki/SPARK_(programming_language)) which is a [formal method](https://en.wikipedia.org/wiki/Formal_methods). It's a powerful tool that lets you prove properties about your program which is important if you want it to be safe and reliable. 
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



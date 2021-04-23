2021-04-19

- st1s14phr datasheet vs EVB design
  - breakout? actually build it? ... or is design sufficient for now?
  - kicad at least maybe?
- compare power supplies for iMX boards
-> CE post (basic design vs design for EMC (Scott Williams))
  - simulation possible?

  2021-04-19T23:19:16
  - i feel like i need to recognise that im not a professional design engineer - and so understanding the minute details is probably not important - knowing the high level and functionality is "good enough"; you have enough to focus on without getting too deep into the weeks in more subjects - so enjoy HW, and ask questions when you need it. But right now; MIC, CoAP, Vue, etc are all much more important for you to know

2021-04-22T21:36:33
- the S19Y02 EVB uses an ST1S14 buck converter
  - it is wired up in an interesting way
  - there is a lot in there for EMC compliance I think
    - i can't share this design of course, but I can start from scratch - the datasheet and build up a design, using the CE forum for help and direction (like scott williams) and compare it as i go along
    - this is probably the best way to learn anyway
- ST1S14 Datasheet : https://www.st.com/resource/en/datasheet/st1s14.pdf
  - one open question i am grappling with here is the diference between signal and power ground
    - [When Grounds Are Separated](https://www.analog.com/en/analog-dialogue/raqs/raq-issue-159.html#)
    - though robert had a blog post on this as well (saying not to split) [Ground in PCB Layout - Separate or Not Separate? (with Rick Hartley)](https://www.youtube.com/watch?v=vALt6Sd9vlY)
    - the impact of the fast switching is significant i should think
- Other places to learn Buck Converter - Contextual Electronfs Power Swap : https://contextualelectronics.com/courses/power-swap/
  - can refer to this in my opening build log
    Clubman's Buildlog
    need to update https://forum.contextualelectronics.com/t/introduction-clubmanplus850-robert-colvin/3344
      - "confessions of a rusty engineer"
      - make electronics book for kids now vs dick smith in my day - when a bread board WAS a breadboard!
        cover image: https://www.amazon.com/Dick-Smiths-Fun-into-Electronics/dp/0959508007
  - course would require Journeyman membership ($59 for a month)
- CE apparently had a project once called "BenchBudEE" - which is open to apprentice level
  - https://contextualelectronics.com/courses/the-benchbudee/
  - this doesnt appear to be on the courses page
  - github page: https://github.com/ContextualElectronics/BenchBudEE
  - this is a bit like Dave Jones lab supply project I was looking at on YouTube
  - someones attempt: https://rheingoldheavy.com/contextual-electronics-benchbuddee/
    - discusses noise

- a post on CE forum talking about [PCB Design Overall Best Practices?](https://forum.contextualelectronics.com/t/pcb-design-overall-best-practices/2953)
  - scott williams was talking in this post

- was looking into the common mode choke in the design (which is there for common mode noise)
  - what is common mode noise though?!
    - an from NXP: [System Design and Layout Techniques for Noise Reduction in MCU-Based Systems](https://www.nxp.com/docs/en/application-note/AN1259.pdf) discusses common mode noise
  - [reduced conducted emi in buck converter](https://www.ti.com/lit/an/snva886/snva886.pdf?ts=1618909881773&ref_url=https%253A%252F%252Fwww.google.com%252F)
  - [Understanding EMI and mitigating noise in DC/DC converters](https://training.ti.com/understanding-emi-and-mitigating-noise-dcdc-converters)

- since i can't use the s19y02 design directly, maybe i can use the imx6rex design?
  https://www.imx6rex.com/wp-content/uploads/2016/04/iMX6-Rex-Development-Baseboard-Schematic.pdf
-

- [KiCad PCB design: power supply pcb layout](https://www.youtube.com/watch?v=UrTwvjs2YQE)
- before i start a build log on CE though, i might want to have something to show? although an opening introduction to the project isnt a bad thing?
  - start documenting here first perhaps...

2021-04-22T22:13:13
- pinged forum update on shipping from Taiwan to US for $4.99

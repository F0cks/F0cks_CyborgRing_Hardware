# F0cks_CyborgRing_Hardware

I have created my own hardware and software of **Zach Fredin** [zakqwy](https://github.com/zakqwy) Cyborg ring. This code can only be used with [my Cyborg ring hardware](https://github.com/F0cks/F0cks_CyborgRing_Hardware). <br />
You can find more information on my blog : [blog.f0cks.net/projects/Cyborg-ring](https://blog.f0cks.net/projects/Cyborg-ring/).


### Prerequisites

* You will need **avrdude** to flash the ring.
* A programmer like the **USBasp** (with some modifications to adapt the connector).
* **Arduino IDE** if you want to modify and rebuild the code. 

### Programming

You need to change **fuses** to switch internal oscillator from 8MHz to 6.4MHz :
```
avrdude -c usbasp  -p t85 -U flash:w:cyborg_ring_software.ino.hex -B 400
```
You can use the provided .hex file or create your own by rebuilding **cyborg_ring_software.ino** with **Arduino IDE**.
```
avrdude -c usbasp  -p t85 -U lfuse:w:0x43:m -U hfuse:w:0xdf:m -U efuse:w:0xff:m   -B 400
```

## Authors

* **Geoffrey Enjolras** - [F0cks](https://github.com/F0cks)

## License

In agreement with **Zach Fredin**, this code is released under the terms of the Creative Commons Attribution-ShareAlike 4.0 license, available here: http://creativecommons.org/licenses/by-sa/4.0/.
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>

## Acknowledgments

Completely inspired by **Zach Fredin** [zakqwy](https://github.com/zakqwy).

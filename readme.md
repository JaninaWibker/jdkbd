<img src="./jdkbd_logo.svg" width="384px" alt="Jade keyboard (based on crkbd)" />

The Jade keyboard is a split 40% ortholinear mechanical keyboard (*that's a lot of words*) which
(optionally) has a thinkpad trackpoint attachment on the right half.

**TODO**: add pictures here

The whole project is based on the [corne keyboard](https://github.com/foostan/crkbd) by foostan but
has undergone many modifications. Still, a lot of work has been saved duo to the previous works done
by foostan (*thanks a lot*).

The main differences between the corne and the jade are that:
- corne has 4 less keys (44 vs 48; jade has a bottom row and thumb cluster while the corne only has
  a thumb cluster)
- corne is (depending on the model) reversible; the jade uses kailh hot-swap sockets which are also
  supported by the corne-cherry version (which is also not reversible)
- corne has more case options available, the jade currently only has "pcb case"

## Getting the jade

the current method to getting a jade keyboard is letting it be manufactured by jlcpcb, pcbway or a
different pcb manufacturer. There are not kits available.

> Almost all pcb manufacturers have a minimum order quantity of 5pc; getting 5 times the pieces you
> need might still be cheaper than some other keyboard kits and you can possibly resell them.

The keyboard comes in 3 different parts: the pcb, the bottom plate and the top plate.

## Building and needed components

You mainly need kailh hot-swap sockets, screws, LEDs and ProMicro's

The full list can be found [here](/components.md) along with some cost estimates.

Build instructions can be found [here](/build-instructions.md).

## Modifying the jade

The jade was designed in [KiCad](https://https://kicad-pcb.org/) and uses some of
[foostan's footprints / symbols](https://github.com/foostan/kbd) for custom keyboards.

These should be directly available when cloning the repo **with submodules**. This can be done by
using

```sh
git clone --recursive [url]
```

when cloning the repo initially or later on using

```sh
git submodule update --init --recursive
```

A few beginner mistakes I made / faced are:
- not working with eeschema and jumping straight into pcbnew (the pcb designer)
- not caring about aligning things to the grid (KiCad really likes it's grid)

When using KiCad 5.1.6 the pick and place file (also called .pos file) might be incorrect. Using
later versions will probably fix this as well as prior versions as this is a bug that was introduced
while fixing another bug.

Incase you are using KiCad 5.1.6 the error is easy to correct: the x-coordinate in the (csv) file is
simply flipped. Just flip it back and you are fine.

If you are using JLCPCB for manufacturing you can use their preview while ordering to check that everything
is alright. 

> Modifying the PCB can require also modifying the bottom- and top-plate.

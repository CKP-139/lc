- started with `solid` color, got to orange
- wanted to make `layer` on top on half of screen, switched to `diff` of `osc` instead to get a color gradient over the solid (try `color` on `osc`?)
- added `kaleid` to change the shape
- changed parameters on the `osc` to make it switch between two values, added `ease` and it started to flash really fast between the two
- adding `bpm = 0.001` works but is clunky, adding `fast` on lilith's suggestion worked better
- added `shape` on top with `diff`, changing its side count with an `ease`
- used a `mask` to put a `voronoi` inside the shape to create a cool pattern
- used `rotate` with the same `fast` and `ease` settings as the shape to make the voronoi rotate - opposite of the shape modulation

```js
bpm = 120

solid(1,0.5,0.2)
	.diff(osc([-1,1].fast(0.001).ease('easeInOutCubic'))).kaleid(5)
	.diff(shape([2.5,9].fast(0.1).ease('easeInOutCubic'),0.3,0.1)
		.mask(voronoi(10,.5,.4).rotate([0,-5].fast(0.1).ease('easeInOutCubic'))))
.out(o0)
```

- hmm can you have a variable for the ease? maybe
- Nope
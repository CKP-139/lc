# p5.live Group Project
with Daphne, we created this:
```js
let libs = ['https://unpkg.com/hydra-synth', 'includes/libs/hydra-synth.js']
let hydra = new Hydra()
hydra.setResolution(window.innerWidth*2, window.innerHeight*2) // retina res

bpm = 138

osc( [0.5,1].ease('linear'))
.blend(noise(10, 5),0.5)
.mask(shape(4, (0.01, ()=> 0.2 + a.fft[4]),1)
.kaleid(40)
.mult(osc(1, 1).modulate(osc(5).rotate(1.4,1),3))
.color(1,8,3)
.diff(gradient([1,0,1]))
.luma(1.2,0.05, (5, ()=> 2 + a.fft[3]))
.scale(0.6, ()=> 0.9 + a.fft[3])
.diff(o0))// o0
.modulateRepeatX(osc(1),2,({time}) => Math.sin(time) * 3)
.scroll(0.2,0.2,-0.2,-0.3)
.diff(osc(200,10,5))
.mask(
	shape([3,6].fast(0.25).ease('easeInOutCubic'),0.3,.1)
	.repeat([5,10].fast(0.125).ease('easeInOutCubic'), [5,5].fast(0.0625).ease('easeInOutCubic'))
	.scroll(  () => mouse.x / width,() => -mouse.y / height)
	.scroll(0.2,0.5,0.1,0.2)
)
.blend(
	osc(0,0,3).add(solid(0,0,1).diff(gradient(0)))
)

.out(o0)// o1
```

We started with a patch taken from the hydra demo website that had a `shape` mapped to an `fft` that looked cool.

After that, we set that patch on top of an `osc` so that it wasn't just on a black background.

I added the `ease`-based `shape` `mask` from my own Hydra project last week on top of this pattern, and added some interactive elements using the `scroll` function and mapping to `mouse` input from the Hydra functions website. 

It was a bit limited, so I also made it `scroll` on its own without input as well. After that, I made it `repeat` in both directions and also made that change over time.

Daphne added the `bpm` to set the speed once we chose a song, and then we used `fast` to change the speed of different easing functions to match how fast they were to the music.

We had some issues trying to get it to change colors using `color`, which I think was because of everything on top running through a `diff`? not sure... but we eventually added a `blend` at the end with an `osc`, `solid` color and `gradient` for the colored elements
# Percussion Patch - [Rattler](https://strudel.cc/#Lyoga3AgcGVyY3Vzc2lvbiBwYXRjaCAtIHJhdHRsZXIgKi8Kc2V0Y3BtKDQwKQokOiBzKCJiZCBzZCIpLmJhbmsoIjxyb2xhbmR0cjgwOCByb2xhbmR0cjkwOT4iKQokOiBzKCJiZCIpLmJhbmsoInJvbGFuZHRyODA4IikKJDogcygifiByaW0hMTUgfiE0IikuYmFuaygicm9sYW5kdHI4MDgiKS5jdXRvZmYoc2luZS5tdWwoMzAwMCkuc3ViKDE1MCkpLnB1bmNoY2FyZCgp)
```javascript
/* kp percussion patch - rattler */
setcpm(40)
$: s("bd sd").bank("<rolandtr808 rolandtr909>")
$: s("bd").bank("rolandtr808")
$: s("~ rim!15 ~!4").bank("rolandtr808").cutoff(sine.mul(3000).sub(150)).punchcard()
```

# Documentation
- started with low tempo bass and snare
- selected roland tr808 bank
- added 20x fast rim hits
    - wanted variations in it, so added a sine cutoff to change the sound of it over each cycle
    - tried different multiplying values to change the amplitude of the curve
    - finally, subtracted 150 so that it would fall off a bit more near the end
- decided i wanted more variation in the backbeat
- introduced a second soundbank (roland tr909) and variation between them
- added another tr808 bass hit to trigger every cycle, because the tr909 on its own wasn't punchy enough
- removed the first rim hit so that they wouldn't overlap with the kick hit (sort of manual duck)
- removed the last few rim hits as well to suggest a stronger falloff
- added visualization using punchcard \:D
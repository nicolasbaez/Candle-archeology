# Candle-archeology
mindblowing destiny

![buh](https://github.com/nicolasbaez/Candle-archeology/blob/main/xp038.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = -1.5;
draw = (_) => {
  h = w / 2;
  rotateX(k);
  rotateY(k / 2);
  fill(0, h, h, 9);
  beginShape();
  for (i = 0; i < 3; i += 0.1)
    for (j = 0; j < 6; j += 0.1) {
      r = w * noise(i, j, k) * cos(k);
      vertex(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
  endShape();
  if (k == -1.5) saveGif("xp038.gif", 600, { delay: 0, units: "frames" });
  k += map(cos(k), 0, 1, 0.05, 0.001);
};

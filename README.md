# mad006
basic modulated space loop

![mad006](https://github.com/nicolasbaez/mad006/blob/master/mad006.gif)

```processing
float dAngle=18;
float j=0;
float n=16;
void setup() {
  size(512, 256);
  background(255);
  noStroke();
  fill(0);
}
void draw() {
  background(255);
  translate(width/2, height/2);
  for (float i=j; i<=j+360; i+=dAngle) {
    for (float k=0; k<=n; k++) {
      float r=height*map(k, 0, n, 0, 1);
      float x=r*cos(radians(i+map(k, 0, 8, 0, 360)));
      float y=r*sin(radians(i+map(k, 0, 8, 0, 360)));
      float w=map(k, 0, n, 1, 8);
      rect(x, y, w, w);
    }
  }
  j++;
  if (j<=360) {
    saveFrame("gif/mad006-######.png");
  }
}
```

# Report 2-1
## 컴퓨터 공학과 남현지

```

void setup(){
  size(800, 300);
  textSize(128);
}
int i, a=1;
void draw(){
  fill(255);
  background(165,102,255);
  if(keyPressed)
    a=key-'0';
  text("andong", i=i+a, 200);
  if(i>800) i=0;
}

```

# Report 2-1
## 컴퓨터공학과 남현지

```
void setup() {
  size(800, 300);
  textSize(128);
}
int i, dir=1, sp=1;
void draw() {
  fill(255);
  background(0, 0, 255);
  text("andong", i, 200);
  if (i>width-128/2*7) dir=-1;
  if (i<0) dir=1;
  i = i+dir*sp;
  if (keyPressed)
    sp = key - '0';
}
```
### 리포트 소감
* 교수님 프로세싱 배울수록 재미있는 것 같아요.
* 어려운 부분도 있지만 더 열심히 배우겠습니다.
* 재밌게 가르쳐주셔서 감사합니다.
* [markdown 언어](https://gist.github.com/ihoneymon/652be052a0727ad59601)

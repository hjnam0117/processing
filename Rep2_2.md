# Report 2-2
## 컴퓨터공학과 남현지

```
PFont f;
void setup() {
  size(800, 300);
  f = createFont("굴림", 64);
  textFont(f);
}
int i, a=1;
void draw() {
  fill(0);
  background(0, 255, 0);
  text("안동대 컴공 사랑합니다", 60, i=i+a);
  if (i > height) i=0;
  if (keyPressed)
    a = key - '0';
}

```
### 리포트 소감
* 프로세싱 많이 해볼수록 점점 더 익숙해지는 것 같아요.
* 교수님 앞으로 프로세싱 더 열심히 공부하겠습니다.
* [markdown 언어](https://gist.github.com/ihoneymon/652be052a0727ad59601)

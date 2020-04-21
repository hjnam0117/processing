# Report
## 안동대학교 컴퓨터공학과
### 20190703 남현지

### [1. 화면에 원이 위에서 아래로 내려오는 코드](https://cafe.naver.com/graphicscafe/260)

```
void setup() { // 한번 실행
  size(500, 500); // 화면 가로 세로 크기
}

int h; // 타원 y좌표 나타내는 정수형 변수 선언

void draw() { // 반복 실행
  background(0); // 검은색으로 배경 지우기
  fill(0, 255, 0); // 타원의 색 초록색으로 설정
  ellipse(250, h++, 100, 100); // 위에서 아래로 내려오는 타원 그리기
  if (h > height) h = 0; // 아래에 도착하면 위에서 다시 시작
}

```

### [2. 위아래로 왔다 갔다하는 배너를 만드는 코드](https://cafe.naver.com/graphicscafe/266)

```
PFont f; // 한글 나타내기 위해 폰트 f 선언

void setup() { //한번 실행 
  size(800, 400); // 화면 가로 세로 크기
  f = createFont("굴림", 64); // 글씨체와 글씨 크기 설정한 폰트 생성
  textFont(f); // 사용할 텍스트폰트 선언
}

int i, dir = 1, a = 1; // 정수 변수

void draw() { // 반복 실행
  fill(0); // 글씨 검은색으로
  background(255, 255, 0); // 노란색 배경
  text("안동대 컴퓨터 공학과", 60, i); // 문자 출력
  if (i > height) dir = -1; // 아래에 도착하면 위로 올라가게함
  if (i < 60) dir = 1; // 위에 도착하면 아래로 내려가게함
  i = i + dir*a; // dir은 a의 부호를 나타내며 i는 a만큼 증가 또는 감소
  if (keyPressed) // 키보드 0, 1,..., 9에 따라 속도 조절
    a = key - '0'; // 0, 1, 2,..., 9가 됨
}
```

### [3. Processing Examples (Math-Sine)](https://processing.org/examples/sine.html)

```
float diameter; // 원의 지름 나타내는 데 필요한 실수형 변수 선언
float angle = 0; // 각도 나타내는 실수형 변수 선언

void setup() { // 한번 실행
  size(640, 360); // 화면 가로 세로 크기
  diameter = height - 10; // 원의 지름 최소 10으로 설정하기 위해 변수 초기화
  noStroke(); // 원의 테두리 선 제거
}

void draw() { // 반복 실행
  
  background(255, 255, 0); // 노란색 배경

  float d1 = 10 + (sin(angle) * diameter/2) + diameter/2; // 첫번째 원의 지름 나타내는 실수형 변수 선언 후 초기화
  float d2 = 10 + (sin(angle + PI/2) * diameter/2) + diameter/2; // sin 값에 의해 원의 지름은 항상 10부터 height 사이의 값
  float d3 = 10 + (sin(angle + PI) * diameter/2) + diameter/2; // 원의 지름의 값에 따라 원이 커졌다가 작아지는 과정 반복
  
  fill(255,0,0); // 원의 색 빨간색으로
  ellipse(0, height/2, d1, d1); // 지름이 d1인 원 화면 왼쪽 중간에 그리기
  fill(127); // 원의 색 회색으로
  ellipse(width/2, height/2, d2, d2); // 지름이 d2인 원 화면 가운데 중간에 그리기
  fill(0,0,255); // 원의 색 파란색으로
  ellipse(width, height/2, d3, d3); // 지름이 d3인 원 화면 오른쪽 중간에 그리기
  
  angle += 0.05; // 각도 0.05씩 더해지며 더하는 수로 속도 조절
}

```

###[4. Processing Tutorials – 나의 도형 만들기(곰돌이)](https://cafe.naver.com/graphicscafe/269)

```
void setup() { // 한번 실행
  size(500, 500); // 화면 가로 세로 크기
}

void draw() { // 반복 실행
  translate(mouseX, mouseY); // 마우스 위치로 이동
  fill(255, 255, 0); // 원 노란색으로
  strokeWeight(1.5); // 원 테두리 선 두께 1.5로
  ellipse(-30, -50, 35, 35); // 귀를 나타내는 원 그리기
  ellipse(+30, -50, 35, 35); // 귀를 나타내는 원 그리기

  fill(255); // 원 흰색으로
  strokeWeight(1.5); // 원 테두리 선 두께 1.5로
  ellipse(-30, -45, 15, 15); // 귀를 나타내는 원 그리기
  ellipse(+30, -45, 15, 15); // 귀를 나타내는 원 그리기

  fill(255, 255, 0); // 타원 노란색으로
  strokeWeight(1.5); // 타원 테두리 선 두께 1.5로
  ellipse(0, -10, 90, 75); // 얼굴을 나타내는 타원 그리기

  fill(255); // 원 흰색으로
  strokeWeight(1); // 원 테두리 선 두께 1로
  ellipse(-20, -15, 12, 12); // 눈을 나타내는 원 그리기
  ellipse(+20, -15, 12, 12); // 눈을 나타내는 원 그리기

  fill(0); // 원 검은색으로
  strokeWeight(1); // 원 테두리 선 두께 1로
  ellipse(-20, -15, 5, 5); // 눈동자를 나타내는 원 그리기
  ellipse(+20, -15, 5, 5); // 눈동자를 나타내는 원 그리기

  fill(0); // 타원 검은색으로
  strokeWeight(1.5); // 타원 테두리 선 두께 1.5로
  ellipse(0, 0, 12, 7); // 코를 나타내는 타원 그리기

  noFill(); // 호의 채우기 색 없음
  strokeWeight(1.5); // 호 테두리 선 두께 1.5로
  arc(-8, 0, 15, 15, 0, PI); // 입을 나타내는 중심각 180도인 호 그리기
  arc(8, 0, 15, 15, 0, PI); // 입을 나타내는 중심각 180도인 호 그리기
}

```

### [5. PGraphics - Create Graphics](https://processing.org/examples/creategraphics.html)

```
PGraphics pg; // PGraphics 객체 pg 선언

void setup() { // 한번 실행
  size(640, 360); // 화면 가로 세로 크기
  pg = createGraphics(400, 100); // PGraphics 클래스에서 객체 생성
}

void draw() { // 반복 실행
  fill(255, 50); // 사각형의 색은 흰색, 투명도 50으로
  rect(0, 0, width, height); // 화면의 크기와 같아 배경으로 사용된 사각형 그리기
  fill(0); // 원의 색 검은색으로
  noStroke(); // 원의 테두리 색 없음
  ellipse(mouseX, mouseY, 30, 30); // 원 그리기
  
  pg.beginDraw(); // 그리기 준비
  pg.background(0, 255, 0); // 초록색 배경
  pg.fill(255, 0, 255); // 원의 색 보라색으로
  pg.stroke(255, 0, 255); // 원의 테두리 색 보라색으로
  pg.ellipse(mouseX-120, mouseY-60, 30, 30); // 원 그리기
  pg.endDraw(); // 그리기 완료
  
  image(pg, 120, 60); // 객체 이용해 이미지로 나타내서 그리기
  
  pg.beginDraw(); // 그리기 준비
  pg.background(0, 0, 255); // 파란색 배경
  pg.fill(255, 255, 0); // 원의 색 노란색으로
  pg.stroke(255, 255, 0); // 원의 테두리 색 노란색으로
  pg.ellipse(mouseX-120, mouseY-60, 30, 30); // 원 그리기
  pg.endDraw(); // 그리기 완료
  
  image(pg, 120, 160); // 객체 이용해 이미지로 나타내서 그리기
}

```

# MCS-Engine
Mini html5 Canvas Sprite game Engine  
used : http://nupa.xyz/p/fts/game.html

---
## Sprite()
### field
- Setting
  - id
  - tag  
    - player - 키보드연결  
    - background - 카메라로 이동되지 않음
  - width
  - height
  - moveSpeed - 이동속도
- Switch
  - gravity - 중력가속도
  - static - 충돌시 밀려남
  - collision - 충돌감지
- State
  - x
  - y
  - ax - 가속도
  - ay
  - crash - 충돌상태
  - jump - 점프상태
  - state - 방향상태

### method
- start( callback )  
  draw() 가 호출될 때 callback 호출  

- update( callback )  
  0.01초마다 callback 호출  

- renderer( callback )  
  프레임마다 callback 호출  

- onCrash( callback( direction, target ) )  
  - 충돌시 callback 호출  
  - direction - 충돌한 방향  
  - target - 충돌한 물체


- emitCrash( direction, target )  
  충돌이벤트를 발생시킴  

- animate( img, width, height, state{} , frame, collider[])   
  스프라이트의 애니메이션을 설정한다.  
  - img - Image() 오브젝트
  - width, height - 프레임 한 장의 크기
  - state = { left, leftRun, leftJump, right, rightRun, rightJump }  
    해당 상태의 라인 번호
  - frame - 상태 하나의 프레임 개수
  - collider - 충돌범위보다 더 크게 그리기 [위,오른쪽,아래,왼쪽]


- draw( x, y )  
  해당 좌표에 그리기를 시작함

- dead()  
  그리기 중단

- onDead( callback )  
  그리기가 중단되었을 때 callback 호출

- setInterval( callback, time )  
  그리기가 중단되었을 때 자동으로 interval 해제

- remove( string )  
  기본 설정을 삭제( starts, updates, renderers, crashes, deads, intervals )

---
## Camera
### field
  - x
  - y
  - target - 카메라의 기준이 되는 sprite 지정  
  - marginX, marginY - 카메라 자동이동 보정

### method
  - set( x, y ) - 해당 좌표로 카메라 이동

---

## BGM

---

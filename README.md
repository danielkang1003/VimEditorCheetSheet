Vim Editor Cheet Sheet
=========
Vim Editor Download: https://www.vim.org/download.php
***
## Purpose
---------

- 마우스를 사용하지 않고 키보드 내에서 일반모드, 입력모드 그리고 비주얼 모드를 넘나들며 모든 일을 처리할 수 있어 시간 단축에 매우 유용할 것으로 보이는 매력적인 Vim
하지만 다양한 명령어와 입력어들을 까먹지 않고 Git에서 관리하여 잊어버린 내용도 찾아서 사용할 수 있도록 하기위해
김왼손의 왼손코딩 채널에서 배운 Vim의 입력어 및 다양한 명령어를  작성해나갈 계획입니다.

- 아래 작성된 내용은 **김왼손의 왼손코딩**님의 강의와 몇몇 블로그에서 보고 배워서 작성되었습니다.

---------
## Get Started
> ### 1. 실행 저장 종료: 
 - 실행: 다운로드 받은 Vim을 실행
      + 콜론( : )을 입력하면 Vim 에디터의 아래칸에 : 가 보이고 이후에 종료와 저장 명령을 주면 된다.
 - **종료: :q**
      + (저장되지 않은 부분이 있다면 바로 종료가 되지 않습니다)
 - 강제종료: :q!
 - **저장: :w**
 - 저장 및 종료 : :wq
 - 강제 저장 및 종료: :wq!
      + ! 는 Vim에서 강제라는 의미를 가지고 있음

> ### 2. 이동하기:
 - 방향키도 가능하지만 영문키 이동 기능이 Vim에디터 기능의 가장 큰 장점이다. 되도록 영문키를 잘 활용하도록 노력하자.
 - 오래된 에디터여서 마우스도 없고 키보드에 방향키도 없을 때 만들어졌다고 한다.
  
 - __상하좌우 한칸씩 이동__: Shift를 누른 상태가 아닌 __H, J, K, L (H는 왼쪽, L은 오른쪽, J는 아래, K는 위)__
 - **꿀팁**: 오퍼레이터 펜딩 모드(Operator Pending Mode) 숫자를 상하좌우 이동 명령 전에 입력해주면 입력해준 숫자칸 만큼 이동을 한다.
     +  ex) 3 + j : 3칸 아래로 커서가 움직임 ( + 더하기 키는 입력하지 않아도 된다.)
- __단어 단위로 커서 이동__:
> - w (단어의 시작 위치 또는 문장 부호의 첫 글자에서 멈춤)
> - b ( w와 같은데 방향이 다름. 문장 부호나 단어의 시작위치로 이동을 하는데 역방향 (왼쪽) 으로 이동함)
> - e (단어의 시작이 아닌 단어의 끝으로 이동)
>      +   ex) Ama Et Fac Vis 가 있고 w를 누르면 A에서 시작하여 E F V 으로 이동
>      +   ex) Ama Et Fac Vis 가 있고 e를 누르면 A에서 a로 이동을 시작하고 t c s로 이동
>      +   ex) Ama Et Fac Vis 가 있고 Vis의 s에 커서가 있으면, V로 이동을 시작하고 F E A로 이동
     + 문제는 사용하다 보면 짧은 단어가 많아 너무 자주 멈춤. 문맥에 맞는 단어를 인식해서 이동하는 기능 즉 공백 단위로 이동하는 방법이 있음
     대문자 W B E를 사용하면 됨
> -  W (w와 기능은 같지만 코딩을 예로 들자면 void BFS(int n){ 에서 W를 사용하면 BFS(int을 한 문장으로 인식하여서 v B n으로 이동을 한다
> -  B 와 E 도 위와 같이 문장을 공백단위로 이동하므로 같이 적용하면 된다.

- __문장 단위로 이동__:
     +  행의 맨 앞으로 이동: 0
     +  행의 맨 뒤로 이동: $
     +  행의 맨 앞에서 다음에 커서를 위치 (즉, 공백을 제외한 가장 첫번째 글자로 이동) : ^

- __같은 줄에서 문자로 뛰는 방법:__
     +  f + 내가 찾아가고 싶은 숫자 또는 문자 입력. 가장 처음 나온 문자를 찾아감 (Operator Pending Mode)
     +  f를 누르고 입력값을 주고 나서 ';'__(정방향)__ 를 눌러주면 같은 단어 또는 숫자를 문장이 끝날 때 까지 찾아줌. ','__(역방향)__ 를 누르면 역방향으로 찾아감
     +  t + 내가 찾아가고 싶은 숫자 또는 문자 입력. 입력한 값을 찾아서 커서를 그 단어 또는 숫자의 앞으로 위치. ';' 또는 ',' 적용 가능

- __화면 스크롤 하기:__
     + CTRL + y or e : 한줄씩 위 아래로 스크롤 가능 ( y : 위로, e : 아래로)
     + CTRL + u or d : 반 페이지씩 위 아래로 스크롤 가능 ( u : 위로, e : 아래로)

- __문서의 첫과 끝 또는 특정 행으로 이동:__
     + gg : 문서의 제일 처음으로 이동
     + 대문자 G : 문서의 가장 마지막으로 이동
     + : (콜론) 입력후 행(줄) 넘버 = 특정 행(줄)으로 이동
     + 응용 실습: 기존에 윈도우에서 전체 선택을 하려면 CTRL + A를 하면 선택이 가능했으나, Vim에서는 다른 방법을 사용한다.
     gg를 눌러서 문서의 가장 처음으로 이동을 한 후에 V(대문자)를 눌러서 한줄을 선택. 이후에 G (대문자)를 누르면 전체 음영처리가 된다
     

> ### 3. 단어 검색하기:
  - / (슬래시) 를 누르고, '찾기를 원하는 값' 입력. 입력한 값을 찾고 나서 여러개가 나온다면 N__(역방향)__ 과 n__(정방향)__ 으로 탐색기능을 사용 가능 ex) /main 을 입력하면 됨
  - 찾고 싶은 단어에 커서를 두고 * (*single asterisks*) 를 눌러도 같은 방식으로 적용 됨. N, n 사용 가능. # 또한 사용 가능 역방향 탐색

  - **꿀팁**: 입력후 음영 처리 된 값에서 벗어나고 싶다면 / 를 누르고 asdf (asdf를 보통 코딩에서 사용하지 않으므로) 하면 빠져나올 수 있다.



> ### 4. 입력하기:
- a, i, o, r 이 있음
     + a를 누르면 커서가 위치한 곳의 다음 문자에 입력이 가능함.
     + i를 누르면 현재 커서 위치의 앞에서부터 문자 입력이 가능함.
     + o는 Open line으로 밑으로 한 줄이 생기고 입력이 가능함.
     + r은 Replace 기능으로 현재 커서 위치에서 character만 바꾸어주고 입력모드에서 탈출함.
          + 대문자 A I O 도 입력으로 가능.
          + A는 행의 가장 마지막으로 이동하여 입력이 가능하도록 함
          + I는 행의 가장 앞으로 이동하여 입력이 가능하도록 함
          + O는 위로 한줄을 추가해주고 입력이 가능하도록 함
          + __꿀팁__: 입력모드에서 나오려면 ESC키도 가능하지만, __CTRL + [__ (대괄호) 를 입력해주면 빠져 나올 수 있음. 또 오류 수정을 위해 입력모드에서 타이포를 없애려면 **CTRL + h**를 눌러주면 backspace를 누르지 않아도 됨



> ### 5. 삭제하기 (Vim에서는 삭제라고 하기 보다는 잘라내기로 보는 게 맞다):
- x : 현재 자리의 문자 하나씩 삭제
- dd : 문장 전체 한줄 삭제
- D : 대문자 D는 현재 커서의 위치부터 문장의 끝까지 삭제
- J : 밑에 줄 전체를 위 줄로 당겨줌. (스페이스가 한칸 생성 됨)
- dj도 사용 가능하다.

> ### 6. 붙여넣기:
- p: 위에서 dd 또는 D로 삭제(잘라내기)한 문자 또는 문장을 붙여 넣을 수 있다. (잘라낸 문자 또는 문장은 레지스터라는 곳에 저장이 됨)
- 대문자 P 와 p 모두 가능한데, 대문자 P는 위 칸에 붙여넣기 소문자 p는 아래칸에 붙여넣기
- y + y: y를 한번 누르면 오퍼레 펜딩 모드로 들어가지는데 y를 한번 더 누르면 현재  한줄이 복사가 됨. 이후 p를 연속 사용하면 계속 붙여넣기 가능
- Y 도 한줄 복사 기능


> ### 7. 작업 취소하기, 다시 실행하기, 이전 명령어 반복하기:
- Undo Redo의 기능임. 윈도우에서 CTRL + z(실행 취소, Undo), CTRL + SHITF + z 또는 CTRL + y (실행 취소 복원, Redo)로 워드에서 많이 사용했었던 기능
- 문서를 열었을 때부터 지금까지의 모든 작업 (몇개가 되든 끝까지 모두 취소도 가능! 참 대단한 에디터)을 취소할 수 있다 
- u : 실행 취소 (Undo) 윈도우에서 CTRL + z의 기능
- CTRL + r : 다시 실행 (Redo) 윈도우에서 CTRL + SHIFT + z 기능
- .(마침표) : 바로 이전에 했던 동작을 그대로 반복해줌 ex) 문장을 dd로 삭제를 했다면 .을 누르면 계속 삭제를 해줌

> ### 8. 비주얼 모드에서 시각적으로 블록을 선택 복사 삭제하기:
- v : 일반 비주얼 모드로 진입 가능하게 해주는 명령어. char 단위로 이동 가능 이후 hjkl로 커서를 움직여주면 블록이 형성되서 드래그한 것처럼 만들어줌
- V : 비주얼 라인 모드. 대문자 V는 소문자 v와 다르게 한줄 단위로 드래그 처리 ( 현재 칸이 위치한 행에서 행단위로 이동하며 블록 지정)
- CTRL + v : 비주얼 블록 모드. 여태까지 드래그한 것과 다르게 (뭐라고 설명하는게 맞는 설명일지 모르겠음. 한번 사용해보고 몸으로 체득하기 권장)
- 응용 : gg + V + G : gg : 문서의 처음으로 이동  -> 비주얼 라인모드로 진입 -> 문서의 끝으로 이동. 즉 문서 전체 선택이 가능해짐. 윈도우의 CTRL + A와 같은 기능

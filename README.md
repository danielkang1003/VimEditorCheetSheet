VimEditorCheetSheet
=========
Vim Editor Download: https://www.vim.org/download.php
***
## Purpose
---------

- 마우스를 사용하지 않고 키보드 내에서 모든 입력을 처리할 수 있어 시간 단축에 매우 유용할 것으로 보이는 매력적인 Vim
하지만 다양한 명령어와 입력어들을 까먹지 않고 Git에서 관리하여 잊어버린 내용도 찾아서 사용할 수 있도록 하기위해
직접 터득한 Vim의 입력어 및 다양한 명령어를  작성해나갈 계획입니다.

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
 - **꿀팁**: 오퍼레이션 펜딩 모드(Operator Pending Mode) 숫자를 상하좌우 이동 명령 전에 입력해주면 입력해준 숫자칸 만큼 이동을 한다.
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


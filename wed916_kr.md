# Minecraft Education 커맨드 + MakeCode 블록코딩 수업  
## 숫자로 갑옷거치대 조종하기
## 오늘의 수업 목표
오늘은 Minecraft Education에서 커맨드의 기능을 알아보고,  
MakeCode에서 **블록을 직접 가져와 갑옷거치대를 움직이는 프로그램**을 만들어봅니다.
이 README의 MakeCode 예제는 일반 JavaScript 설명이 아니라  
MakeCode에서 실제 블록 모양으로 보이도록 `blocks` 형식으로 작성되어 있습니다.  이렇게 떠버리는 현상이 위에 사진처럼있습니다 해결이 필요합니다
---
# 1. 오늘 만들 프로그램
채팅창에 숫자를 입력하면 `Grumm`이라는 갑옷거치대가 움직입니다.
| 채팅 입력 | 기능 |
|---|---|
| 1 | 갑옷거치대 소환 |
| 2 | X+ 방향으로 이동 |
| 3 | X- 방향으로 이동 |
| 4 | Z+ 방향으로 이동 |
| 5 | Z- 방향으로 이동 |
| 6 | 위로 이동 |
| 7 | 아래로 이동 |
---
# 2. MakeCode에서 사용할 블록
MakeCode의 **플레이어(PLAYER)** 메뉴에서  
`다음 채팅명령어를 입력하면` 블록을 가져옵니다.
```blocks
player.onChat("1", function () {
})
```
그 안에 **다음 채팅 명령 실행** 블록을 넣습니다.
```blocks
player.onChat("1", function () {
    player.runChatCommand("say hello")
})
```
오늘은 이 구조를 사용해서 갑옷거치대를 조종합니다.
---
# 3. 1번 — 갑옷거치대 소환하기
## 기능
채팅창에 `1`을 입력하면 내 옆에 `Grumm`이라는 갑옷거치대가 생깁니다.
## 만들 블록
```blocks
player.onChat("1", function () {
    player.runChatCommand("summon " + "armor_stand " + "~-2 ~ ~ " + "0 0 " + "default " + "Grumm")
})
```
## 완성되는 커맨드
```mcfunction
summon armor_stand ~-2 ~ ~ 0 0 default Grumm
```
## 실행
채팅창에 입력합니다.
```text
1
```
---
# 4. 2번 — X+ 방향으로 이동하기
## 기능
채팅창에 `2`를 입력하면 `Grumm`이 X+ 방향으로 1칸 이동합니다.
## 만들 블록
```blocks
player.onChat("2", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~1 ~ ~")
})
```
## 완성되는 커맨드
```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~1 ~ ~
```
## 실행
```text
2
```
---
# 5. 3번 — X- 방향으로 이동하기
## 기능
채팅창에 `3`을 입력하면 `Grumm`이 X- 방향으로 1칸 이동합니다.
## 만들 블록
```blocks
player.onChat("3", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~-1 ~ ~")
})
```
## 완성되는 커맨드
```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~-1 ~ ~
```
## 실행
```text
3
```
---
# 6. 4번 — Z+ 방향으로 이동하기
## 기능
채팅창에 `4`를 입력하면 `Grumm`이 Z+ 방향으로 1칸 이동합니다.
## 만들 블록
```blocks
player.onChat("4", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~ ~1")
})
```
## 완성되는 커맨드
```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~ ~1
```
## 실행
```text
4
```
---
# 7. 5번 — Z- 방향으로 이동하기
## 기능
채팅창에 `5`를 입력하면 `Grumm`이 Z- 방향으로 1칸 이동합니다.
## 만들 블록
```blocks
player.onChat("5", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~ ~-1")
})
```
## 완성되는 커맨드
```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~ ~-1
```
## 실행
```text
5
```
---
# 8. 6번 — 위로 이동하기
## 기능
채팅창에 `6`을 입력하면 `Grumm`이 위로 1칸 올라갑니다.
## 만들 블록
```blocks
player.onChat("6", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~1 ~")
})
```
## 완성되는 커맨드
```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~1 ~
```
## 실행
```text
6
```
---
# 9. 7번 — 아래로 이동하기
## 기능
채팅창에 `7`을 입력하면 `Grumm`이 아래로 1칸 내려갑니다.
## 만들 블록
```blocks
player.onChat("7", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~-1 ~")
})
```
## 완성되는 커맨드
```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~-1 ~
```
## 실행
```text
7
```
---
# 10. 전체 블록 코드
아래 코드를 MakeCode README에 넣으면 `blocks` 코드블록으로 표시됩니다.
```blocks
player.onChat("1", function () {
    player.runChatCommand("summon " + "armor_stand " + "~-2 ~ ~ " + "0 0 " + "default " + "Grumm")
})
player.onChat("2", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~1 ~ ~")
})
player.onChat("3", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~-1 ~ ~")
})
player.onChat("4", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~ ~1")
})
player.onChat("5", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~ ~-1")
})
player.onChat("6", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~1 ~")
})
player.onChat("7", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~-1 ~")
})
```
---
# 11. 실습 미션
## 미션 1 — Grumm을 5칸 이동시키기
채팅창에 아래처럼 입력합니다.
```text
2
2
2
2
2
```
---
## 미션 2 — Grumm을 위로 3칸 올리기
```text
6
6
6
```
---
## 미션 3 — 네모 모양으로 움직이기
```text
2
2
2
4
4
4
3
3
3
5
5
5
```
---
## 미션 4 — 목표 지점으로 이동시키기
선생님이 정한 목표 블록 위로 `Grumm`을 이동시켜 봅니다.
사용 가능한 숫자:
```text
2, 3, 4, 5, 6, 7
```
---
# 12. 도전 미션 1 — 한 번에 5칸 이동하기
## 기능
채팅창에 `8`을 입력하면 `Grumm`이 X+ 방향으로 한 번에 5칸 이동합니다.
```blocks
player.onChat("8", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~5 ~ ~")
})
```
## 실행
```text
8
```
---
# 13. 도전 미션 2 — 다시 내 근처로 불러오기
## 기능
채팅창에 `9`를 입력하면 `Grumm`을 내 근처로 다시 불러옵니다.
```blocks
player.onChat("9", function () {
    player.runChatCommand("tp " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~2")
})
```
## 실행
```text
9
```
---
# 14. 오늘 배운 개념
## 채팅 명령어
채팅창에 특정 숫자를 입력하면 코드가 실행됩니다.
```blocks
player.onChat("1", function () {
})
```
---
## 명령어 실행
MakeCode 블록 안에서 Minecraft 명령어를 실행합니다.
```blocks
player.onChat("1", function () {
    player.runChatCommand("say " + "hello")
})
```
---
## 문자열 연결
여러 글자를 하나의 명령어로 이어 붙입니다.
```blocks
player.onChat("1", function () {
    player.runChatCommand("Hello" + "World")
})
```
`"Hello"`와 `"World"`를 연결하면 `HelloWorld`가 됩니다.
오늘은 이 연결 블록을 사용해서 긴 커맨드를 여러 조각으로 나누어 만들었습니다.
---
## 좌표
Minecraft에서는 위치를 X, Y, Z로 나타냅니다.
```text
X = 좌우 방향
Y = 위아래 높이
Z = 앞뒤 방향
```
---
# 15. 좌표 기억하기
```text
~1 ~ ~  = X+ 방향으로 1칸
~-1 ~ ~ = X- 방향으로 1칸
~ ~1 ~  = 위로 1칸
~ ~-1 ~ = 아래로 1칸
~ ~ ~1  = Z+ 방향으로 1칸
~ ~ ~-1 = Z- 방향으로 1칸
```
---
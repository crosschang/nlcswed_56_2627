# Minecraft Education MakeCode 수업 - 숫자로 갑옷거치대 조종하기

### @explicitHints true

이 튜토리얼은 **Minecraft Education의 Code Builder + Microsoft MakeCode 블록 편집기 전용**입니다.

채팅창에 숫자를 입력해 `Grumm`이라는 갑옷거치대를 소환하고 X, Y, Z 방향으로 움직여 봅니다.

```template
//
```

## 1. Minecraft Education 준비하기

Minecraft Education에서 새 월드를 만들고 **치트 활성화(Activate Cheats)** 를 켭니다.

월드에 들어간 뒤 키보드의 **C 키**를 눌러 **Code Builder**를 열고 **Microsoft MakeCode**를 선택합니다.

새 프로젝트를 만든 뒤 **블록(Blocks)** 화면에서 시작합니다.

이번 수업에서는 다음 두 종류의 블록을 사용합니다.

- **플레이어(Player)** → 채팅 명령을 입력하면
- **고급(Advanced)** → 게임 명령 실행

MakeCode에서 실행하는 Minecraft 명령어에는 앞의 `/`를 적지 않습니다.

---

## 2. 채팅 1 - 갑옷거치대 소환하기

채팅창에 `1`을 입력했을 때 플레이어 옆에 이름이 `Grumm`인 갑옷거치대를 소환합니다.

**플레이어**에서 `다음 채팅명령어를 입력하면` 블록을 가져오고, 안쪽에 **고급**의 게임 명령 실행 블록을 넣어 보세요.

```blocks
player.onChat("1", function () {
    player.execute("summon " + "armor_stand " + "~-2 ~ ~ " + "0 0 " + "default " + "Grumm")
})
```

완성되는 Minecraft 명령어는 `summon armor_stand ~-2 ~ ~ 0 0 default Grumm` 입니다.

Minecraft 화면으로 돌아가 채팅창에 `1`을 입력해 실행해 보세요.

---

## 3. 채팅 2 - X+ 방향으로 이동하기

채팅창에 `2`를 입력하면 `Grumm`을 **X+ 방향으로 1칸** 이동시킵니다.

명령어를 여러 문자열 조각으로 나누어 블록으로 연결해 보세요.

```blocks
player.onChat("2", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~1 ~ ~")
})
```

완성되는 Minecraft 명령어는 `execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~` 입니다.

Minecraft 채팅창에 `2`를 입력해서 이동을 확인합니다.

---

## 4. 채팅 3 - X- 방향으로 이동하기

이번에는 채팅창에 `3`을 입력하면 `Grumm`을 **X- 방향으로 1칸** 이동시킵니다.

앞 단계와 비교하면서 마지막 상대좌표만 바꿔 보세요.

```blocks
player.onChat("3", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~-1 ~ ~")
})
```

`~1 ~ ~`이 X+ 방향이라면 `~-1 ~ ~`은 X- 방향입니다.

---

## 5. 채팅 4와 5 - Z축으로 이동하기

이제 X축이 아니라 **Z축**으로 움직여 봅니다.

`4`는 Z+ 방향, `5`는 Z- 방향입니다.

```blocks
player.onChat("4", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~ ~1")
})

player.onChat("5", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~ ~-1")
})
```

Minecraft에서 `4`와 `5`를 각각 입력해 움직이는 방향을 비교해 보세요.

---

## 6. 채팅 6과 7 - 위아래로 이동하기

Minecraft의 **Y축은 높이**를 나타냅니다.

`6`을 입력하면 위로 1칸, `7`을 입력하면 아래로 1칸 이동하도록 만들어 봅니다.

```blocks
player.onChat("6", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~1 ~")
})

player.onChat("7", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~-1 ~")
})
```

이제 숫자 `2`부터 `7`까지를 이용하면 갑옷거치대를 3차원 공간에서 움직일 수 있습니다.

---

## 7. 좌표 규칙 확인하기

상대좌표 `~`는 현재 위치를 기준으로 움직인다는 뜻입니다.

다음 규칙을 기억해 보세요.

- `~1 ~ ~` → X+ 방향으로 1칸
- `~-1 ~ ~` → X- 방향으로 1칸
- `~ ~1 ~` → 위로 1칸
- `~ ~-1 ~` → 아래로 1칸
- `~ ~ ~1` → Z+ 방향으로 1칸
- `~ ~ ~-1` → Z- 방향으로 1칸

아래 블록을 보면서 X, Y, Z 중 어느 숫자가 바뀌는지 확인해 보세요.

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})
```

---

## 8. 도전 - 한 번에 5칸 이동하기

지금까지는 한 번 실행할 때 1칸씩 이동했습니다.

채팅창에 `8`을 입력했을 때 X+ 방향으로 **5칸** 이동하도록 직접 수정해 보세요.

```blocks
player.onChat("8", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~5 ~ ~")
})
```

힌트: `~1 ~ ~`에서 숫자 `1`을 `5`로 바꾸면 됩니다.

---

## 9. 도전 - Grumm을 플레이어 근처로 불러오기

갑옷거치대가 너무 멀리 이동했다면 채팅창에 `9`를 입력해서 다시 플레이어 근처로 불러옵니다.

`player.execute()`는 현재 플레이어 위치를 기준으로 게임 명령을 실행하므로 `~ ~ ~2`는 플레이어 기준 상대좌표가 됩니다.

```blocks
player.onChat("9", function () {
    player.execute("tp " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~2")
})
```

Minecraft 채팅창에 `9`를 입력하고 `Grumm`이 플레이어 근처로 이동하는지 확인해 보세요.

---

## 10. 실습 미션 - 네모 그리기

지금까지 만든 숫자 명령을 이용해 `Grumm`을 네모 모양으로 움직여 봅니다.

다음 순서로 Minecraft 채팅창에 입력하세요.

`2 → 2 → 2 → 4 → 4 → 4 → 3 → 3 → 3 → 5 → 5 → 5`

각 숫자가 어떤 좌표를 변경하는지 생각하면서 움직임을 관찰합니다.

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})

player.onChat("4", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~1")
})

player.onChat("3", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~-1 ~ ~")
})

player.onChat("5", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~-1")
})
```

---

## 11. 커맨드를 블록으로 분해해 보기

Minecraft 커맨드는 한 줄의 텍스트지만 MakeCode에서는 여러 문자열 블록으로 나누어 조립할 수 있습니다.

예를 들어 소환 명령은 다음 구조로 나눌 수 있습니다.

`소환 명령 + 엔티티 + 좌표 + 회전값 + 이벤트 + 이름`

```blocks
player.onChat("1", function () {
    player.execute("summon " + "armor_stand " + "~-2 ~ ~ " + "0 0 " + "default " + "Grumm")
})
```

이 방식으로 긴 커맨드의 각 부분이 어떤 역할을 하는지 블록을 옮겨 보면서 확인할 수 있습니다.

---

## 12. 최종 코드 확인하기

마지막으로 지금까지 만든 숫자 명령을 한 번에 확인합니다.

```blocks
player.onChat("1", function () {
    player.execute("summon " + "armor_stand " + "~-2 ~ ~ " + "0 0 " + "default " + "Grumm")
})

player.onChat("2", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~1 ~ ~")
})

player.onChat("3", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~-1 ~ ~")
})

player.onChat("4", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~ ~1")
})

player.onChat("5", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~ ~-1")
})

player.onChat("6", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~1 ~")
})

player.onChat("7", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~ ~-1 ~")
})

player.onChat("8", function () {
    player.execute("execute " + "as @e[type=armor_stand,name=Grumm] " + "at @s " + "run tp @s " + "~5 ~ ~")
})

player.onChat("9", function () {
    player.execute("tp " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~2")
})
```

완성했습니다!

이제 Minecraft Education에서 채팅창에 `1`부터 `9`까지 입력하면서 직접 테스트해 보세요.

# 숫자로 갑옷거치대 조종하기

### @explicitHints true

Minecraft Education의 Code Builder와 MakeCode를 사용하여 채팅 숫자로 갑옷거치대를 움직여 봅시다.

## 1. 갑옷거치대 소환

||player:플레이어||에서 **채팅 명령어** 블록을 사용합니다. 채팅 명령을 `1`로 바꾸고, 안에 Minecraft 명령 실행 블록을 넣으세요.

```blocks
player.onChat("1", function () {
    player.execute("summon armor_stand ~-2 ~ ~ 0 0 default Grumm")
})
```

Minecraft로 돌아가 채팅창에 `1`을 입력해 보세요. 이름이 `Grumm`인 갑옷거치대가 플레이어 옆에 소환됩니다.

## 2. X+ 방향으로 이동

채팅 명령 `2`를 만들고 `Grumm`을 X+ 방향으로 1칸 이동시킵니다.

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})
```

Minecraft 채팅창에 `2`를 입력해 움직임을 확인하세요.

## 3. X- 방향으로 이동

이번에는 채팅 명령 `3`을 만들고 X- 방향으로 1칸 이동시킵니다.

```blocks
player.onChat("3", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~-1 ~ ~")
})
```

`~1 ~ ~`과 `~-1 ~ ~`의 차이를 확인하세요.

## 4. Z+ 방향으로 이동

채팅 명령 `4`를 만들고 Z+ 방향으로 1칸 이동시킵니다.

```blocks
player.onChat("4", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~1")
})
```

Minecraft 채팅창에 `4`를 입력하세요.

## 5. Z- 방향으로 이동

채팅 명령 `5`를 만들고 Z- 방향으로 1칸 이동시킵니다.

```blocks
player.onChat("5", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~-1")
})
```

Minecraft 채팅창에 `5`를 입력하세요.

## 6. 위로 이동

Y축은 Minecraft의 높이입니다. 채팅 명령 `6`을 만들고 위로 1칸 이동시킵니다.

```blocks
player.onChat("6", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~1 ~")
})
```

Minecraft 채팅창에 `6`을 입력하세요.

## 7. 아래로 이동

채팅 명령 `7`을 만들고 아래로 1칸 이동시킵니다.

```blocks
player.onChat("7", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~-1 ~")
})
```

Minecraft 채팅창에 `7`을 입력하세요.

## 8. 좌표 규칙 확인

지금까지 사용한 상대좌표를 확인합니다.

- `~1 ~ ~` : X+ 1칸
- `~-1 ~ ~` : X- 1칸
- `~ ~1 ~` : 위로 1칸
- `~ ~-1 ~` : 아래로 1칸
- `~ ~ ~1` : Z+ 1칸
- `~ ~ ~-1` : Z- 1칸

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})
```

## 9. 도전 - 한 번에 5칸 이동

채팅 명령 `8`을 만들고 X+ 방향으로 한 번에 5칸 이동시켜 보세요.

```blocks
player.onChat("8", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~5 ~ ~")
})
```

`~1`을 `~5`로 바꾸면 이동 거리가 달라집니다.

## 10. 도전 - 플레이어 근처로 불러오기

채팅 명령 `9`를 입력하면 `Grumm`을 플레이어 근처로 다시 불러옵니다.

```blocks
player.onChat("9", function () {
    player.execute("tp @e[type=armor_stand,name=Grumm] ~ ~ ~2")
})
```

Minecraft 채팅창에 `9`를 입력하세요.

## 11. 네모 모양으로 움직이기

이제 숫자 명령을 이용해 `Grumm`을 네모 모양으로 움직여 보세요.

`2 → 2 → 2 → 4 → 4 → 4 → 3 → 3 → 3 → 5 → 5 → 5`

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})
player.onChat("3", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~-1 ~ ~")
})
player.onChat("4", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~1")
})
player.onChat("5", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~-1")
})
```

## 12. 완성

잘했습니다! 이제 숫자 `1`부터 `9`까지를 이용하여 갑옷거치대를 직접 조종할 수 있습니다.

Minecraft 커맨드의 **X, Y, Z 상대좌표**와 MakeCode의 **채팅 명령 블록**을 함께 사용해 보았습니다.

```blocks
player.onChat("1", function () {
    player.execute("summon armor_stand ~-2 ~ ~ 0 0 default Grumm")
})
```

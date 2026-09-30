# 숫자로 갑옷거치대 조종하기

```template
//
```

## 1. 갑옷거치대 소환하기

||player:플레이어||에서 **다음 채팅명령어를 입력하면** 블록을 가져와 명령어를 `1`로 바꾸세요. 그 안에 **다음 치트키 실행** 블록을 넣고 갑옷거치대 소환 명령어를 입력합니다.

```blocks
player.onChat("1", function () {
    player.execute("summon armor_stand ~-2 ~ ~ 0 0 default Grumm")
})
```

## 2. X+ 방향으로 이동하기

새로운 ||player:다음 채팅명령어를 입력하면|| 블록을 가져와 `2`로 바꾸세요. `Grumm`을 X+ 방향으로 1칸 이동시키는 명령어를 넣습니다.

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})
```

## 3. X- 방향으로 이동하기

채팅 명령어 `3`을 만들고 `Grumm`을 X- 방향으로 1칸 이동시켜 보세요.

```blocks
player.onChat("3", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~-1 ~ ~")
})
```

## 4. Z+ 방향으로 이동하기

채팅 명령어 `4`를 만들고 `Grumm`을 Z+ 방향으로 1칸 이동시켜 보세요.

```blocks
player.onChat("4", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~1")
})
```

## 5. Z- 방향으로 이동하기

채팅 명령어 `5`를 만들고 `Grumm`을 Z- 방향으로 1칸 이동시켜 보세요.

```blocks
player.onChat("5", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~ ~-1")
})
```

## 6. 위로 이동하기

Y축은 Minecraft의 높이입니다. 채팅 명령어 `6`을 만들고 `Grumm`을 위로 1칸 이동시켜 보세요.

```blocks
player.onChat("6", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~1 ~")
})
```

## 7. 아래로 이동하기

채팅 명령어 `7`을 만들고 `Grumm`을 아래로 1칸 이동시켜 보세요.

```blocks
player.onChat("7", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~ ~-1 ~")
})
```

## 8. 좌표 확인하기

지금까지 만든 블록을 이용해 상대좌표를 확인하세요. `~1 ~ ~`은 X+, `~-1 ~ ~`은 X-, `~ ~1 ~`은 위, `~ ~-1 ~`은 아래, `~ ~ ~1`은 Z+, `~ ~ ~-1`은 Z- 방향입니다.

```blocks
player.onChat("2", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~1 ~ ~")
})
```

## 9. 도전 - 한 번에 5칸 이동하기

채팅 명령어 `8`을 만들고 X+ 방향으로 한 번에 5칸 이동하도록 숫자를 바꿔 보세요.

```blocks
player.onChat("8", function () {
    player.execute("execute as @e[type=armor_stand,name=Grumm] at @s run tp @s ~5 ~ ~")
})
```

## 10. 도전 - 플레이어 근처로 불러오기

채팅 명령어 `9`를 만들고 멀리 이동한 `Grumm`을 플레이어 근처로 다시 불러오세요.

```blocks
player.onChat("9", function () {
    player.execute("tp @e[type=armor_stand,name=Grumm] ~ ~ ~2")
})
```

## 11. 네모 모양으로 움직이기

Minecraft 채팅창에서 `2 → 2 → 2 → 4 → 4 → 4 → 3 → 3 → 3 → 5 → 5 → 5` 순서로 입력해 `Grumm`을 네모 모양으로 움직여 보세요.

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

잘했습니다! 이제 Minecraft 채팅창에서 `1`부터 `9`까지 입력하면서 갑옷거치대를 직접 조종해 보세요. 오늘은 MakeCode의 채팅 명령 블록과 Minecraft의 X, Y, Z 상대좌표를 함께 사용했습니다.

```blocks
player.onChat("1", function () {
    player.execute("summon armor_stand ~-2 ~ ~ 0 0 default Grumm")
})
```

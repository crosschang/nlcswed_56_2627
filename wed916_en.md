# Minecraft Education Command + MakeCode Block Coding Lesson  
## Controlling an Armor Stand with Numbers

## Today’s Lesson Goal

Today, we will learn how commands work in Minecraft Education,  
and then use **MakeCode blocks** to create a program that moves an armor stand.

The MakeCode examples in this README are not just regular JavaScript examples.  
They are written in the `blocks` format so that MakeCode can display them as real block shapes.

---

# 1. What We Will Make Today

When you type a number in the chat, an armor stand named `Grumm` will move.

| Chat Input | Function |
|---|---|
| 1 | Summon the armor stand |
| 2 | Move in the X+ direction |
| 3 | Move in the X- direction |
| 4 | Move in the Z+ direction |
| 5 | Move in the Z- direction |
| 6 | Move upward |
| 7 | Move downward |

---

# 2. Blocks We Will Use in MakeCode

In MakeCode, open the **PLAYER** menu.  
Then drag out the `on chat command` block.

```blocks
player.onChat("1", function () {
})
```

Inside that block, add the **run chat command** block.

```blocks
player.onChat("1", function () {
    player.runChatCommand("say hello")
})
```

Today, we will use this structure to control the armor stand.

---

# 3. Number 1 — Summon the Armor Stand

## Function

When you type `1` in the chat, an armor stand named `Grumm` will appear next to you.

## Blocks to Make

```blocks
player.onChat("1", function () {
    player.runChatCommand("summon " + "armor_stand " + "~-2 ~ ~ " + "0 0 " + "default " + "Grumm")
})
```

## Completed Command

```mcfunction
summon armor_stand ~-2 ~ ~ 0 0 default Grumm
```

## Run

Type this in the Minecraft chat:

```text
1
```

---

# 4. Number 2 — Move in the X+ Direction

## Function

When you type `2` in the chat, `Grumm` moves 1 block in the X+ direction.

## Blocks to Make

```blocks
player.onChat("2", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~1 ~ ~")
})
```

## Completed Command

```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~1 ~ ~
```

## Run

```text
2
```

---

# 5. Number 3 — Move in the X- Direction

## Function

When you type `3` in the chat, `Grumm` moves 1 block in the X- direction.

## Blocks to Make

```blocks
player.onChat("3", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~-1 ~ ~")
})
```

## Completed Command

```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~-1 ~ ~
```

## Run

```text
3
```

---

# 6. Number 4 — Move in the Z+ Direction

## Function

When you type `4` in the chat, `Grumm` moves 1 block in the Z+ direction.

## Blocks to Make

```blocks
player.onChat("4", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~ ~1")
})
```

## Completed Command

```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~ ~1
```

## Run

```text
4
```

---

# 7. Number 5 — Move in the Z- Direction

## Function

When you type `5` in the chat, `Grumm` moves 1 block in the Z- direction.

## Blocks to Make

```blocks
player.onChat("5", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~ ~-1")
})
```

## Completed Command

```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~ ~-1
```

## Run

```text
5
```

---

# 8. Number 6 — Move Upward

## Function

When you type `6` in the chat, `Grumm` moves up by 1 block.

## Blocks to Make

```blocks
player.onChat("6", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~1 ~")
})
```

## Completed Command

```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~1 ~
```

## Run

```text
6
```

---

# 9. Number 7 — Move Downward

## Function

When you type `7` in the chat, `Grumm` moves down by 1 block.

## Blocks to Make

```blocks
player.onChat("7", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~ ~-1 ~")
})
```

## Completed Command

```mcfunction
execute @e[type=armor_stand,name=Grumm] ~ ~ ~ tp @s ~ ~-1 ~
```

## Run

```text
7
```

---

# 10. Full Block Code

Add the code below to your MakeCode README so it can be displayed as `blocks`.

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

# 11. Practice Missions

## Mission 1 — Move Grumm 5 Blocks

Type the following in the chat:

```text
2
2
2
2
2
```

---

## Mission 2 — Move Grumm Up 3 Blocks

```text
6
6
6
```

---

## Mission 3 — Move in a Square Shape

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

## Mission 4 — Move to the Target Point

Move `Grumm` to the target block chosen by the teacher.

You can use these numbers:

```text
2, 3, 4, 5, 6, 7
```

---

# 12. Challenge Mission 1 — Move 5 Blocks at Once

## Function

When you type `8` in the chat, `Grumm` moves 5 blocks in the X+ direction at once.

```blocks
player.onChat("8", function () {
    player.runChatCommand("execute " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~ " + "tp " + "@s " + "~5 ~ ~")
})
```

## Run

```text
8
```

---

# 13. Challenge Mission 2 — Bring Grumm Back Near You

## Function

When you type `9` in the chat, `Grumm` comes back near you.

```blocks
player.onChat("9", function () {
    player.runChatCommand("tp " + "@e[type=armor_stand,name=Grumm] " + "~ ~ ~2")
})
```

## Run

```text
9
```

---

# 14. Coding Concepts We Learned Today

## Chat Command

When you type a specific number in the chat, the code runs.

```blocks
player.onChat("1", function () {
})
```

---

## Run Chat Command

This block runs a Minecraft command inside MakeCode.

```blocks
player.onChat("1", function () {
    player.runChatCommand("say " + "hello")
})
```

---

## String Joining

We can join several pieces of text into one command.

```blocks
player.onChat("1", function () {
    player.runChatCommand("Hello" + "World")
})
```

`"Hello"` and `"World"` become `HelloWorld`.

Today, we used the join block to build long commands using smaller text pieces.

---

## Coordinates

Minecraft uses X, Y, and Z to show positions.

```text
X = left and right
Y = up and down
Z = forward and backward
```

---

# 15. Remember the Coordinates

```text
~1 ~ ~  = move 1 block in the X+ direction
~-1 ~ ~ = move 1 block in the X- direction

~ ~1 ~  = move up 1 block
~ ~-1 ~ = move down 1 block

~ ~ ~1  = move 1 block in the Z+ direction
~ ~ ~-1 = move 1 block in the Z- direction
```

---

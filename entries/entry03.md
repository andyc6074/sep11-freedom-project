# Entry 3
##### 2/9/23

## Background

I was working on the first proytype game from the tutoral then tinker with it. After that I start look up new tutoral to follow along and under stand what going on.The webpage of phaser is https://phaser.io/tutorials/making-your-first-phaser-3-game/part1.

## Progress

Last time we left of building the platforma and starting to make th eplayer control. Now we are working on the rest of the player control as well as adding a point system in the game.

```js 
function collectStar (player, star)
 {
     star.disableBody(true, true);
     score += 10;
    scoreText.setText('Score: ' + score);
 }
 // this code is just the starting code that check if the star are working and counting points.
```
After I set up the point system, I add a bombs so there can be a game over. After I finsh I let other play test and see what can make it better.

```js
function hitBomb (player, bomb)
    {
        this.physics.pause();

        player.setTint(0xff0000);

        player.anims.play('turn');

        gameOver = true;
    }
```
After I complete the tutorial and tinker around for a bit, I start look for other tutorial to follow and code. I try to look for any thing Rpg related. Then I came along a tutorial call "How to Create a Turn-Based RPG in Phaser 3" from Lyubomira Popova. -https://gamedevacademy.org/     how-to-create-a-turn-based-rpg-game-in-phaser-3-part-1/

## Skills
What I had learn is to organnize my time and tinker more when I'm learning new things. Try to explan diffent genre to see/ plan what are you going to make.

## what I plan on learning next
 Since I was planing to make an Rpg, I looking working on that. For small thing I want to know how to make different movemnts, Ai or NPC, and mabye know how to make sprite sheet. and any extra on the side.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
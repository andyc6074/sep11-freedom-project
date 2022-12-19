# Entry 2
##### 12/16/22

### Background
 After chosing our tool we were task to tinker and learn our tool. The first thing I did was to study on their webform first to get used to the feeling of how it works. Teh webpage of phaser is https://phaser.io/tutorials/making-your-first-phaser-3-game/part1.

### Context
 In the webpage there is a tutoral on the basic of creating a new game using the tools givin. It help you get strated and learn how what are some tool you can use trough steps.

To start with I learn how to to set up the frame work of the game we are working on. While It is mosty self explanitory,I still tinker with some of the code to see what will change what and what is nessary to function at is base.
```js
var config = {
    type: Phaser.AUTO,
    width: 800,
    height: 600,
    scene: {
        preload: preload,
        create: create,
        update: update
    }
};

var game = new Phaser.Game(config);

function preload ()
{
}

function create ()
{
}

function update ()
{
}
```
This part is simmilar to the a tool I use in the past call Aframe where you put your assect in a part so you can call it later for it to be use. You put the assest in the preload function. After seting up the frame of the game I created the back groud as the tutariol instruced me to. You will have to into the create function in order for it to show up. I add it to the setting and see what it can do to get a idea on How I can use it my self.
```js
function create ()
{
    this.add.image(400, 300, 'sky');
    this.add.image(400, 300, 'star');
    
    platforms = this.physics.add.staticGroup();

    platforms.create(400, 568, 'ground').setScale(2).refreshBody();

    platforms.create(600, 400, 'ground');
    platforms.create(50, 250, 'ground');
    platforms.create(750, 220, 'ground');
}
```
Later I add Physics to those platform, and the player model/control.

### Skills
What I had learn is to organnize my time and tinker more when I'm learning new things. I learn not to push every on the last day as it can cause alot fo stress and tiker more can help you rlearn more that the tutuial didn't tell you.





[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
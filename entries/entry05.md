# Entry 5
##### 4/21/23


## Background Information


My group members(Chin and Ulysses) and I were working on our freedom project Mvp. Since we had a rough start in the beginning, we have a bit of a late start. However, That doesn't mean we can't recover.


## Mvp Progress (My Tasks)


### The Beginning


We want to start with the basics: the player, movement, and the map.


Chin created the map using Tiled which came out fine, however when Chin tried to implement it into code it did not work. So he reached out to Ulysses and me. I say ok I will try to work on the map while you work on the movement for now.


After some tinkering and trying to figure out how to put in the map.Json, I couldn't get it to work as well.


### Player animation


So I notify Chin, then decide to work on the player animation instead. I looked for Sprite and came across a site that has a gallery of different things you can download. The site is called https://itch.io/io and the sprite I got from https://penzilla.itch.io/hooded-protagonist.


``` js
this. load.spritesheet('player','assets/robePlayer.png',{ frameWidth: 32, frameHeight: 32 });//this load in the sprite sheet for the animation. As you can see above, The frame height and frameWidth, define the size of the frame.


        this.anims.create({
            key: 'idle',
            frames: this.anims.generateFrameNumbers('player', {
            frames: [ 8,0,1, 9 ]}),//You would have to use frames like how you would in a grid.
            frameRate: 1.5,
            repeat: -1
        });
        this.anims.create({
            key: 'left',//this is the key you would use to call the animation for the movement.
            frames: this.anims.generateFrameNumbers('player',
            {frames: [ 16,17,18,19]}),
            frameRate: 0.5,
            repeat: -1
        });
        this.anims.create({//you don't need a new animation for the left and right, you can later flip the animation later.
            key: 'right',
            frames: this.anims.generateFrameNumbers('player',
            {frames: [ 16,17,18,19]}),
            frameRate: 0.5,
            repeat: -1
        });
```
### HeathBar Prototype
I thought if we are going to make a game we gotta have a health bar. So I went to grab a Sprite from itch.io again.(https://adwitr.itch.io/pixel-health-bar-asset-pack) There was a slight problem when I downloaded the file, I realized that it was a .rar and I don't know how to open it. So I went on to Slack to ask on the GitHub channel, and thankfully someone replied and helped out. Now that over I open the var file and select the heath bar I want to use.


When I realized there was no part to the health bar, and I am not quite how to split the image by using code alone, I decided the next best thing is to use an art program called Krita (https://krita.org/en/), I then split them up into different part, then imported them back into My ide.


Since we don't have any that will make the player get hit nor did I realize how to connect it to one button I would have a lot of buttons such as the one below.
```js
testheal = this.input.keyboard.addKey(Phaser.Input.Keyboard.KeyCodes.U);


if (Phaser.Input.Keyboard.JustDown (test heal)){
        heath = this.add.image(75, 0, 'heathempty');
    }  
```
![alt text](https://lh3.googleusercontent.com/cGVCUWcAxdzsmfG6esMfinmhy0NFlCHrHy9BNsMVef8YOK7GAMsn_-N7LRsV_bUDxb5az-ykEjrWg0ndWSTFJgzhp9DIQ4SOO8kn8Ajh)


![alt text](https://lh3.googleusercontent.com/Hr4w2UQ87FSJ7Yh8x4sq4SWLlManghjRym33AKALhSGyeL1OcEA2sLIDRFcq731pifRVYPEtrH6jp7E4h9QB57O9BQZMfL7m-mCA35wzGg).


### HeathBar
I soon realized how you can connect them together. You would have to create a new variable to keep track of how many times the player was hit so it will look like this.
```js
var playerHit = 0


if (playerHit == 0){
        heath0hit.visible = true;
        heath0hit.setScrollFactor(0);
    }
    else if (playerHit == 1){
        heath0hit.visible = false;
        heath = this.add.image(75, 0, 'heathempty');
        let heath1hit = this.add.image(75, 12.5, 'heath1hit');
    }
```
We soon will talk about how to increase the playerHit via contact.


### enemies Prototype
In the beginning, we just put zones that don't have any texture, as enemies so we can test the other function. In order to see the zones, will have to turn the debug to true.
```js
debug: true // set to true to view zones
```
### Contact
we need to create a function outside of the create function.
```js
onMeetEnemy: function(player, zone) {
        // we move the zone to some other location
        zone.x = Phaser.Math.RND.between(0, this.physics.world.bounds.width);
        zone.y = Phaser.Math.RND.between(0, this.physics.world.bounds.height);
        playerHit+=1// this is for the heathbar variable mentioned before
        this.cameras.main.flash(500)
    },
```  


### enemies
Since we can't keep using the zones, we will have to use sprites, however, that came with it own problem as zone can't have texture, so we will have to import the sprite and add them to the scene along with changing all the code so it can work with the sprites instead of the zones.


### Enemies Following
We need to have the enemies follow us. However, we didn't quite know how to do that so when we went only to search for an answer. There were many, however, everyone did work out so well, so I decided to take a small slice of each of them and tinker with them in my code till it worked out. So what we got is.
```js
enemyFollows: function () {
        this.physics.moveToObject(this.enemy, this.player, 75);
    },
```
## Challenges
There was one challenge with the contact function when I was trying to make the game. When I was trying to input the sprites, The library did not function as well, so I tried to look for answers online yet nothing they had was doing anything. So I head on to Slack for some help. Luckily, someone answered and, together, she solved the problem, after many trials and errors.

There was some moment where the code did not work on a single Html so I restored it to make a js file along with a .json file I found online.

## Takeaway
*If you help, don't be afraid to ask on Slack.




[Previous](entry04.md) | [Next](entry06.md)


[Home](../README.md)


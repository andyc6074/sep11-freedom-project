# Entry 5
##### 4/21/23

## Background Information

Me and my group member(Chin and Ulysses) were working on our freedom project Mvp. Since we had a rough start in the begining, we have a bit of a late start. However That doesn't mean we can't recover. 

## Mvp Progress (My Tasks)

### The Begining

We want to start by the basic:the player, movemnet, and the map.

Chin has create main using Tiled which cap out fine, however when Chin try to implement in to code it does not work. So he reach out to Ulysses and me. I say ok I will try to work on the the may while your work on the movment for now.

After some tinkering and try out how to figure out how to put in the map.Json, I couldn't get it to work as well. 

### Player animation

So I notify Chin, then decide to work on the player animation instead. I look for sprite and came across and site that have gallery of differnt things you can download. The site is call https://itch.io/io and the sprite I got from https://penzilla.itch.io/hooded-protagonist. 

```js
this.load.spritesheet('player','assets/robePlayer.png',{ frameWidth: 32, frameHeight: 32 });//this load in the spreite sheet for the animation. As you can see aboved, The frameHeight and frameWidth, these define the size of the frame.

        this.anims.create({
            key: 'idle',
            frames: this.anims.generateFrameNumbers('player', { 
            frames: [ 8,0,1, 9 ]}),//You would have to use frame like how you would in a grid.
            frameRate: 1.5,
            repeat: -1
        });
        this.anims.create({
            key: 'left',//this is the key you would use to call the anims for the movement.
            frames: this.anims.generateFrameNumbers('player', 
            {frames: [ 16,17,18,19]}),
            frameRate: 0.5,
            repeat: -1
        });
        this.anims.create({//you dont need a new animation for the left and right, you can later filp the animation later.
            key: 'right',
            frames: this.anims.generateFrameNumbers('player', 
            {frames: [ 16,17,18,19]}),
            frameRate: 0.5,
            repeat: -1
        });
```
### HeathBar Protype 
I thought if we are going to make a game we gotha have a heath bar. So I went to grab a Sprite from itch.io again.(https://adwitr.itch.io/pixel-health-bar-asset-pack) The was a slight proublem when I open download the file, I realized that is was a .rar and I don;t know how to open it. So I went on to slack to to ask on the github channel, and thankfuly someone replied and help out. Now that over with I open the var file and selected the heath bar I want to use. 

When I realized there was no part to the heath bar, and I am not quite how to split the img by using code along, I decide the next best thing is to use an art program call Krita (https://krita.org/en/), I then split them up into diffent part, then imported them back into My ide. 

shince we dont have a any that will make the player get hit nor did I realized how to connect it to one button I would have a lot of button such as the one below.
```js
testheal = this.input.keyboard.addKey(Phaser.Input.Keyboard.KeyCodes.U);

if (Phaser.Input.Keyboard.JustDown (testheal)){
        heath = this.add.image(75, 0, 'heathempty');
    }  
```
![alt text](https://lh3.googleusercontent.com/cGVCUWcAxdzsmfG6esMfinmhy0NFlCHrHy9BNsMVef8YOK7GAMsn_-N7LRsV_bUDxb5az-ykEjrWg0ndWSTFJgzhp9DIQ4SOO8kn8Ajh)

![alt text](https://lh3.googleusercontent.com/Hr4w2UQ87FSJ7Yh8x4sq4SWLlManghjRym33AKALhSGyeL1OcEA2sLIDRFcq731pifRVYPEtrH6jp7E4h9QB57O9BQZMfL7m-mCA35wzGg).

### HeathBar 
I soon relizse how you can connect them together. You would have to create a new varivle to keep trake of how many time the player was hit so it will lokk like this.
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

### enemies Protype
In the begining we just put zone that don't have any texture, as enemies so we can test the other function. In order to see the the zones, will will have to turn the debug to true. 
```js
debug: true // set to true to view zones
```
### Contact 
we need to create an a function outside ofthe create function.
```js
onMeetEnemy: function(player, zone) {
        // we move the zone to some other location
        zone.x = Phaser.Math.RND.between(0, this.physics.world.bounds.width);
        zone.y = Phaser.Math.RND.between(0, this.physics.world.bounds.height);
        playerHit+=1// this it for the heathmbar varible mention before
        this.cameras.main.flash(500)
    },
```  

### enemies
Shince we can't keep using the zones, we will have to use sprites, howevery that came with it own prouble as zone can't have texture, so we will have to inport the sprtie and add them to the scene along with changing all the code so it can work with the sprites instead of the zones.

### Enemies Folowing
We need to have the enemies follow us. However we didn't quite know how to do that so when went only so search for an answer. The was many however every they did work out so well, so I decide to take small of of each of them and tinker with them in my code till it work out. SO what we got is.
```js
enemyFollows: function () {
        this.physics.moveToObject(this.enemy, this.player, 75);
    },
```
## Challanges 

## Takeaway
*If your help don't be afaid to ask on slack.


[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
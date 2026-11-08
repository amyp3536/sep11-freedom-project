# Tool Learning Log

## Tool: **Phaser**

## Project: **SEP11 Freedom Project**

---

### 10/23/26:
I discovered the examples Phaser provided with its 2D games. I discovered the use of JavaScript and has features that develop characters, animation, movement, and background. For instance the code below shows how to code a background.

```js
function preload ()
{
    this.load.image('sky', 'assets/sky.png');
    this.load.image('ground', 'assets/platform.png');
    this.load.image('star', 'assets/star.png');
    this.load.image('bomb', 'assets/bomb.png');
    this.load.spritesheet('dude', 
        'assets/dude.png',
        { frameWidth: 32, frameHeight: 48 }
    );
}
```

### 11/03/26:
I went to phaser, read and stared tinkering with given code and changed things to really understand what it is and what each thing does. The code below shows what I have tinkerd. I changed numbers and scaling. 

```js
<!DOCTYPE html>
<html>
<head>
    <script src="https://cdn.jsdelivr.net/npm/phaser@3.85.2/dist/phaser-arcade-physics.min.js"></script>
</head>
<body>

    <script>
    class Example extends Phaser.Scene
    {
        preload ()
        {
            this.load.setBaseURL('https://cdn.phaserfiles.com/v385');

            this.load.image('sky', 'assets/skies/space3.png');
            this.load.image('logo', 'assets/sprites/phaser3-logo.png');
            this.load.image('red', 'assets/particles/red.png');
        }

        create ()
        {
            this.add.image(400, 300, 'sky');

            const particles = this.add.particles(0, 0, 'red', {
                speed: 100,
                scale: { start: 1, end: 0 },
                blendMode: 'ADD'
            });

            const logo = this.physics.add.image(400, 100, 'logo');

            logo.setVelocity(100, 200);
            logo.setBounce(1, 1);
            logo.setCollideWorldBounds(true);

            particles.startFollow(logo);
        }
    }

    const config = {
        type: Phaser.AUTO,
        width: 800,
        height: 600,
        scene: Example,
        physics: {
            default: 'arcade',
            arcade: {
                gravity: { y: 200 }
            }
        }
    };

    const game = new Phaser.Game(config);
    </script>

</body>
</html>
```


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->

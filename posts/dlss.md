<h1><center>NVIDIA DLSS</center></h1>

## Graphics vs. Performance

Video games have always struggled in the compromise between **graphics** and **performance**. Let’s start by discussing the pros and cons of prioritizing graphics versus prioritizing performance and establish some terminology along the way.

### Prioritizing Graphics 

![Connor's Ultra Realistic Textures](/assets/dlss/connor.jpg)

<sub><center><em>Connor from Detroit: Become Human (2018), note the realistic textures of his suit and tie</em></center></sub>

The prettier a game looks, the more difficult it is for the **graphics processing unit (or GPU)** to render a game at a high **frame rate** and **resolution**. Frame rate, or **frames per second (FPS)**, is the number of images per second that the GPU can send to a **display**, such as a computer monitor or television. The more images per second, the smoother the experience for the player. **Resolution** is the number of distinct pixels on a display. The more pixels there are the clearer the display looks, but as a result high frame rate becomes much more difficult to achieve for the GPU.

If a game strictly prioritizes graphics the GPU might not be able to render the game quickly enough. This can make the display look more like a PowerPoint than a live, interactive experience. Observe below how choppy 15 FPS looks compared to 30 FPS and especially 60 FPS. Could you imagine playing a video game or watching a movie that looked like it was stuttering the whole time?

<center>
    <details>
        <summary>Click to view the difference between 15 FPS, 30 FPS and 60 FPS</summary>
        <p>
            <p align="center">
                <img src="/assets/dlss/frames_per_second.gif" />
            </p>
        <center><sub>15 FPS isn't very smooth. The human eye starts to perceive motion at about 10-12 FPS!</sub><sup>1</sup></center>
        </p>
    </details>  
</center>
<br>

### Prioritizing Performance

Conversely, you can make a game perform excellently by decreasing the complexity of the images that need to be rendered to play the game.

<p align="center">
  <img src="/assets/dlss/dusk.gif" />
</p>

<sub><center><em>DUSK (2018) rendering at 60 FPS, note the simple repeating rock and lava textures</em></center></sub>

DUSK is a great example of this, choosing a retro aesthetic reminiscent of the earliest 3D first-person shooter games, [DOOM](https://en.wikipedia.org/wiki/Doom_(1993_video_game)) in particular. This decrease in visual quality simultaneously allows the game to achieve near-flawless performance on lower-end GPUs for fantastically fast and smooth gameplay.

<p align="center">
  <img src="/assets/dlss/doom_eternal.gif" />
</p>

<sub><center><em>Doom Eternal (2020) rendering at 60 FPS, note the light eminating from the fire and the sword</em></center></sub>

Doom Eternal has a similar visual style to DUSK, but opts for ultra-realistic textures and lighting effects. The game can still achieve the
performance of DUSK, but you'll need a GPU with [some serious horsepower](https://www.nvidia.com/en-us/geforce/graphics-cards/30-series/rtx-3080/) to do it...

### Summarizing Graphics vs. Performance

If a game prioritize graphics, but sacrifices too much performance, the game might look pretty but will likely be frustrating to play. If a game prioritizes performance, but sacrifices too much in graphics, the game will risk not being visually engaging enough for the player. In the worst case the game's immersiveness<sup>2</sup> will also be lost. 

For decades graphics and performance have been a trade-off where many delicate compromises have to be made to create a quality product. What if video game developers could easily have both high performance and ultra-realistic graphics without requiring insane GPU power to do so? NVIDIA DLSS proposes an incredibly interesting solution.

## What is NVIDIA DLSS?

**NVIDIA DLSS**, short for deep-learning super sampling, is a way to use machine learning to decrease the looks vs. performance trade-off. It works like this.

1. yo
2. yo
3. yo
4. The game is now displaying at a high resolution, while the GPU is still rendering at a lower resolution, offering huge performance gains.

### Pros of DLSS

The whole reason DLSS is so revolutionary is that it can offer substantial performance gains, especially for lower-end hardware. This kind of technology would be particularly exciting for consoles like the Xbox, PlayStation and Nintendo Switch where performance is limited due to cost and form factor. Consoles have to sacrifice a hvusgfdusfbsdufb.

### Cons of DLSS

Although DLSS is exciting and potentially revolutionary, it is an experimental project that only works on a small subset of PC games and only for modern NVIDIA GPUs, so no consoles or AMD GPUs yet.

The biggest issue of the current implementation of DLSS is that the upscaled images can have noticeable issues compared to simply rendering the image at native resolution. 

![Death Stranding Waterfall](/assets/dlss/death_stranding_waterfall.gif)

<sub><center><em>Death Stranding (2020) rendering at 4K resolution, note the details lost in waterfall due to DLSS<sup>3</sup></em></center></sub>

But DLSS is still *very close* to the original, and it's running at *a minimum of 30 FPS higher*. That's why DLSS is so impressive to me. If we're already seeing solid upscaling and substantial performance gains in its experimental phase imagine what it will be more capable of as its machine learning algorithms improve!

## Sources

[1](https://books.google.com/books?id=jzbUUL0xJAEC&pg=PA24#v=onepage&q&f=false)

[2](https://www.merriam-webster.com/dictionary/immersive)

[3](https://youtu.be/5I-1kivNAtc?t=205)

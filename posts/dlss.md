<h1><center>NVIDIA DLSS</center></h1>

## Graphics vs. Performance

![Pong](/assets/dlss/pong.png)

<sub><center><em>One of the earliest arcade games Pong (1972). The graphics aren't much to talk about these days...</em></center></sub>

![Pong](/assets/dlss/forza_lambo.jpg)

<sub><center><em>A Lamborghini rendered in Forza Motorsport 7 (2017). No, that is not a real Lamborghini...</em></center></sub>

Video games have always struggled in the compromise between **graphics** and **performance**. Let’s start by discussing the pros and cons of prioritizing graphics versus prioritizing performance and establish some terminology along the way.

### Prioritizing Graphics 

![Connor's Ultra Realistic Textures](/assets/dlss/connor.jpg)

<sub><center><em>Connor from Detroit: Become Human (2018), note the realistic textures of his suit and tie</em></center></sub>

The prettier a game looks, the more difficult it is for the **graphics processing unit** (or **GPU**) to render the game at a high **frame rate** and **resolution**. Frame rate, or **frames per second (FPS)**, is the number of images per second that the GPU can send to a **display**, such as a computer monitor or television. The more images per second, the smoother the experience for the player. **Resolution** is the number of distinct pixels on a display. The more pixels there are the clearer the display looks, but as a result images become more complicated to render. This means higher frame rates become much more difficult to achieve for the GPU.

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

DUSK is a great modern example of this, choosing a retro aesthetic reminiscent of the earliest 3D first-person shooter games, [DOOM](https://en.wikipedia.org/wiki/Doom_(1993_video_game)) in particular. This decrease in visual quality simultaneously allows the game to achieve near-flawless performance on lower-end GPUs for fantastically fast and smooth gameplay.

<p align="center">
  <img src="/assets/dlss/doom_eternal.gif" />
</p>

<sub><center><em>Doom Eternal (2020) rendering at 60 FPS, note the light eminating from the fire and the sword</em></center></sub>

Doom Eternal has a similar visual and gameplay style as DUSK but opts for ultra-realistic textures and lighting effects. The game can still achieve the performance of DUSK, but you'll need a GPU with [some serious horsepower](https://www.nvidia.com/en-us/geforce/graphics-cards/30-series/rtx-3080/) to do it...

### Summarizing Graphics vs. Performance

If a game prioritize graphics, but sacrifices too much performance, the game might look pretty but will likely be frustrating to play. If a game prioritizes performance, but sacrifices too much in graphics, the game will risk not being visually engaging enough for the player. In the worst case the game's immersiveness<sup>2</sup> will also be lost. 

For decades graphics and performance have been a trade-off where many delicate compromises have to be made to create a quality video game. What if video game developers could easily have both high performance and ultra-realistic graphics without requiring insane GPU power to do so? NVIDIA DLSS proposes an incredibly interesting solution.

## What is NVIDIA DLSS?

![DLSS Architecture](/assets/dlss/dlss_architecture.png)

<sub><center><em>A diagram of the DLSS Architecture<sup>3</sup></em></center></sub>

**NVIDIA DLSS**, short for **deep learning super sampling**, is a way to use **machine learning** (letting a computer teach itself to improve at a task with minimal input from humans) to decrease the looks vs. performance trade-off. Here's the complex step-by-step breakdown of how it works:

1. Several ultra-high resolution 16K images are uploaded to an NVIDIA DGX AI supercomputer. This computer is an **AI training** computer, and will compare images rendered with DLSS algorithms to these original ultra-high resolution images.
2. The DGX computer renders the game at a resolution much lower than the desired final resolution.
2. An AI network called a convolutional autoencoder, "takes the low resolution current frame, and the high resolution previous frame, to determine on a pixel-by-pixel basis how to generate a higher quality current frame."<sup>3</sup>
3. **Motion vectors**, images that track the change between two frames, are also rendered. These help DLSS guess what the next frame is going to look like. For example, motion vectors could be used recognize the direction the player is moving and render the next frame accordingly.
4. The DGX supercomputer then compares the DLSS image to the original image and sees how close it got.
5. Steps 2 through 5 are repeated thousands of times until DLSS images are consistently close enough to the original image. At this point the **AI model** for the game is complete. An **AI model** is just an algorithm that has been successfully trained to recognize patterns. In this case, the pattern involves what the game looks like (common color palettes and textures), accurate motion vectors to guess what the next frame will look like and so much more!
6. This AI model is then put into the GPU **drivers**, software that tells hardware how to communicate with a computer. This means that all kinds of NVIDIA RTX GPUs can now use this model to render games!
7. The user enables DLSS in their supported game of choice. The game will now displaying at a high resolution while the GPU is rendering the game at a lower resolution, offering huge performance gains.

Basically, a supercomputer teaches itself to take low quality images of a game and make them higher quality. What it learns is then put into the end user's GPUs, which allows any RTX NVIDIA GPU to render the game at a low resolution but display the game at a high resolution. Better graphics AND better performance have now been achieved simultaneously!

### Pros of DLSS

![Wolfenstein Youngblood 4K Performance Benchmarks](/assets/dlss/wolfenstein_dlss_performance.png)

<sub><center><em>Wolfenstein Youngblood (2020) 4K benchmarks. Literally double the performance!<sup>3</sup></em></center></sub>

The whole reason DLSS is so revolutionary is that it can offer substantial performance gains, especially for lower-end hardware. This kind of technology would be particularly exciting for consoles like the Xbox, PlayStation and Nintendo Switch. These consoles have to sacrifice a lot of performance and graphics capability to keep them cheap. 

DLSS allowing GPUs to run at a lower resolution to achieve the same results also means that GPUs could run at

### Cons of DLSS

Although DLSS is exciting and potentially revolutionary, it is an experimental project that currently only works on a small subset of PC games and only for modern NVIDIA RTX GPUs, so no consoles or AMD GPUs are supported yet... or maybe ever.

The biggest issue of the current implementation of DLSS is that the upscaled images can have noticeable issues compared to simply rendering the image at native resolution. 

![Death Stranding Waterfall](/assets/dlss/death_stranding_waterfall.gif)

<sub><center><em>Death Stranding (2020) rendering at 4K resolution, note the details lost in waterfall due to DLSS<sup>4</sup></em></center></sub>

But DLSS is still *very close* to the natively rendered image, and it's running at *a minimum of 30 FPS higher*. That's why DLSS is so impressive to me. If we're already seeing solid upscaling and substantial performance gains in its experimental phase imagine what it will be more capable of as the machine learning algorithms improve!

## Closing Remarks

DLSS is without a doubt the most exciting development in closing the gap between graphics and performance in the past decade. It's an ingenious way to "cheat" for high performance by rendering at a lower resolution and using AI models to upscale it live to a higher resolution. This gives gamers the best of both worlds: the performance of lower resolution and the appearance of higher resolution. I can't wait to see how DLSS improves or even inspires a competing system with greatercompatible  yet better system!

## Sources

[1](https://books.google.com/books?id=jzbUUL0xJAEC&pg=PA24#v=onepage&q&f=false)

[2](https://www.merriam-webster.com/dictionary/immersive)

[3](https://www.nvidia.com/en-us/geforce/news/nvidia-dlss-2-0-a-big-leap-in-ai-rendering/)

[4](https://youtu.be/5I-1kivNAtc?t=205)

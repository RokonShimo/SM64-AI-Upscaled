# Wait, this isn't what AI Upscaled means?
> ##RokonShimo

A texture pack for [sm64ex](sm64pc.info)  
For use with a vanilla US rom

## The Idea  
> What happens when I tell a neural network to rewrite Super Mario 64 from memory?  
The neural network in question was GPT-2, specifically the version found [here.](https://colab.research.google.com/drive/1VLG8e7YSEwypxU-noRNhsv5dW4NfTGce)  
I gave it the full list of text from the game, throwing in a little extra from Super Mario 64 DS for good measure, and let it generate what it thought was reasonable-sounding text from the game. I then cherry-picked my favourite lines it came out with and inserted them in place of the text from the game. Some of them I put in thematically-appropriate places, others I threw in with reckless abandon.  
And then I did the only thing more dangerous than having an idea:

I had another idea. 

## The Mistake  
> What if I told *another* neural network to generate paintings based on what GPT-2 thinks the courses are called?  
Said neural network turned out to be [VQGAN+CLIP.](https://colab.research.google.com/drive/1wkF67ThUz37T2_oPIuSwuO4e_-0vjaLs?usp=sharing)  
I told it to generate paintings based on the names I'd chosen for each course. But while searching for the painting textures in the files, I found several other textures that directly related to Stars. Those, I generated using the new names of their respective stars, applying transparency manually where applicable since CLIP could not. In some cases, I gave it the original texture as a base, or a goal.

Guess what happens next.

## The Collapse  
> Why stop there? Why not retexture things in levels? Why not retexture entities?

I intentionally limited myself to textures such as Swoop's Wings or the maps of Hazy Maze Cave, since I wasn't sure what would happen if I tried anything else. Generally, I either told CLIP to generate something taken from GPT-2's work or my own description of what the texture is. While the general technique remains the same, I do edit some textures to better match the original, as well as continuing to manually remove backgrounds. For some animated textures such as coins, I used different versions of the same image.
I now have an Alpha Build.

## The End
> Why am I limiting myself to the original resolution? This thing supports way larger textures.

> VQGAN and CLIP work surprisingly well for making sure textures mesh well with themselves... I can do tiling textures!

> I can do every texture in the game!

> I'm not going to be able to rest until I've done that, am I?

> ***Chaos.***

For most of the finer textures, I gave VQGAN+CLIP the original texture to upscale to 4x resolution, as well as my best guess at what the texture actually is. To make it loop (close to) properly, I shifted the output by a little bit in each direction and put it back through VQGAN for a couple of iterations, creating a coherent transition.  
A 4x upscale was chosen because that was the scale at which I had generated most of the preexisting images, in order to not put VQGAN under too much strain. Downscaling to the original resolution had sacrificed a lot of finer detail that I really liked.

I was still editing textures to be transparent manually, using [*paint.net.*](getpaint.net) As you can imagine, this was tedious and imprecise. I looked for a neural network that supported transparent images... no dice.

Course by painstaking course, I edited every image file to 

To generate Skyboxes at the desired resolution would take more memory than Colaboratory could provide, so a fourth neural network would have to be employed.

Some textures, such as the intro background, I decided to remake myself. 

And there we have it. Super Mario 64, as reimagined by three neural networks and one very tired fox.

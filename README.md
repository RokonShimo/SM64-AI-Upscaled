# Wait, this isn't what AI Upscaled means?
> RokonShimo

A texture pack and translation patch for Render96ex 
For use with a vanilla US rom

Play at own risk. Not suitable for children.
Don't say I didn't warn you about: Body Horror, Realistic Eyes, Seizure Hazards, Trypophobia, Master Chaos knows what else

## How To Use
- Install Render96ex using [sm64pcBuilder2](https://sm64pc.info).
- Apply Credits.patch while compiling the game to change the names in the credits. (It does not credit the people who contributed to this, that's further down)
- Install your chosen texture pack using the glowing button after compiling the game.
	- Jiggly Wiggly's Super Dash.zip: The full package for maximum fever dreamage.
	- Jiggly Wiggly's Super Hyphen.zip: Leaves all textures relating to fonts unchanged, for COWARDS who want to be able to read the text easily.
	- Jiggly Wiggly's Super Stroll.zip: An unintrusive texture pack that's easier on the eyes. I don't even remember what's in this but it should be mostly normal.
	- Something might happen if you combine Hyphen and Stroll.
- Copy the contents of the Texts folder to where your files are stored. 
- After loading the game, change your language to "Mario Party: The Muppets" through the pause menu.

## The Question  
> What happens when I tell a neural network to rewrite Super Mario 64 from memory? 
 
The neural network in question was GPT-2, specifically the version found [here.](https://colab.research.google.com/drive/1VLG8e7YSEwypxU-noRNhsv5dW4NfTGce)  
I gave it the full list of text from the game, throwing in a little extra from Super Mario 64 DS for good measure, and let it generate what it thought was reasonable-sounding text from the game. I then cherry-picked my favourite lines it came out with and inserted them in place of the text from the game. Some of them I put in thematically-appropriate places, others I threw in with reckless abandon.  
And then I did the only thing more dangerous than having an idea:

I had another idea. 

## The Mistake  
> What if I told *another* neural network to generate paintings based on what GPT-2 thinks the courses are called?  

Said neural network turned out to be [VQGAN+CLIP](https://colab.research.google.com/drive/1wkF67ThUz37T2_oPIuSwuO4e_-0vjaLs?usp=sharing).
I told it to generate paintings based on the names I'd chosen for each course. But while searching for the painting textures in the files, I found several other textures that directly related to Stars. Those, I generated using the new names of their respective stars, applying transparency manually where applicable since CLIP could not. In some cases, I gave it the original texture as a base, or a goal.

Guess what happens next.

## The Collapse  
> Why stop there? Why not retexture things in levels? Why not retexture entities?

I intentionally limited myself to textures such as Swoop's Wings or the maps of Hazy Maze Cave, since I wasn't sure what would happen if I tried anything else. Generally, I either told CLIP to generate something taken from GPT-2's work or my own description of what I thought the texture was. While the general technique remains the same, I do edit some textures to better match the original, as well as continuing to manually remove backgrounds. For some animated textures such as coins, I used different versions of the same image.
I now have an Alpha Build.

## The End
> Why am I limiting myself to the original resolution? This thing supports way larger textures.

> VQGAN and CLIP work surprisingly well for making sure textures mesh well with themselves... I can do tiling textures!

> I can do every texture in the game!

> I'm not going to be able to rest until I've done that, am I?

> ***Chaos.***

For some textures, I gave VQGAN+CLIP the original texture to upscale to 4x resolution, as well as a description of the texture. To make it loop (close to) properly, I shifted the output by a little bit in each direction and put it back through VQGAN for a couple of iterations, creating a coherent transition. However, my method was anything but consistent. For most textures, I performed a simple manual operation.

A 4x upscale was chosen because that was the scale at which I had generated most of the preexisting images, in order to not put VQGAN under too much strain. Downscaling to the original resolution had sacrificed a lot of finer detail that I really liked.

I was still editing textures to be transparent manually, using [*paint.net.*](https://getpaint.net) As you can imagine, this was tedious and imprecise. I looked for a neural network that supported transparent images... no dice.

Course by course, entity by entity, I steadily transformed texture after texture until the pack was complete.

Since the skybox textures were so much larger than any other texture in the game, trying to generate them at 4x upscale would completely kill CLIP. Therefore, they are only 2x resolution. Even this was difficult for CLIP to generate.

The name "Jiggly Wiggly's Super Dash" was generated by a separate instance of GPT-2, given a list of Mario, Zelda and Kirby games rather than a list of lines from Super Mario 64. The name of the "Language" file, "Mario Party: The Muppets", is a rejected alternative.

Some textures, such as the title screen background, I decided to do personally as I didn't trust CLIP to do them justice. You'll be able to tell which.

The voice in the intro cutscene was generated using [uberduck.ai](https://uberduck.ai). The voice in the ending cutscene is mine (once I do it).

Credits font generated by VQGAN+CLIP, all other ui fonts from [Deep Script 2](https://ai.fabi.design/). Some textures used in cutscenes feature Lucida Calligraphy or [linja pona](http://musilili.net/linja-pona/).
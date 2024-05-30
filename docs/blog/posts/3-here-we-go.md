---
date: 2024-05-30
authors:
  - tealingg
---

# Here We Go!

Hi there! Sorry about the lack of posts concerning Apollo. I've been trying to find the perfect way to implement Apollo's ideas, and it's been a bumpy road...

<!-- more -->

## Context

When I originally envisioned Apollo, I wanted to make it super easy to write custom, modular extensions that anybody could create and distribute.

An example of this would be having 200cc as its own extension, and Wiimmfi patches being their own extension, with the user being able to choose which extensions to load.

This turned out a tricky task, however, as you will read...

## 1: The Payload

The original envision of Apollo was going to be similar to that of [MKW-SP](https://github.com/mkw-sp/mkw-sp "Take me there!")'s, with a payload loaded in memory which does all of the patching etc.

So there I was, I'd made a payload which loads itself statically in memory, I read it from the SD card in the launcher, and, long story short, I successfully managed to run code outside of the launcher which references in-game memory. Brilliant!

With the success of loading the payload into memory, I then set on the task of creating a sample extension which I could test the loading and running of code.

When I tried it, it didn't work. After a long and daunting debugging session, I realised it was because I was **dynamically** loading the extension into memory, but the extension was built **statically**.

The implications? Basically any instruction that requires relative addresses didn't work. And that meant this was a no-go.

Oh dear. Where can we go from this?

## 2: Anyone Can Do It!

After my original plan of dynamically loading extensions failed, I felt defeated. My whole vision of Apollo being easy, modular and friendly seemed pointless.

At this point, my mind briefly thought of doing something similar to that of MKW-SP and [Pulsar](https://github.com/MelgMKW/Pulsar), where a base template is provided, and any modifications to this base can be made by forking the template, and writing your own static modifications.

But this method of modding was far from what I was planning to do.

## 3: What Now?

With the failure of my extensions and the reluctance to use a template, I considered dropping the project altogether.

I stopped working on Apollo to consider if it was even worth its creation. I couldn't think of any other way to create Apollo in its initial envisionment.

I was just about to give up when I remembered...

## 4: The Saviour of Apollo

There does in fact exist a way to use extensions dynamically! What a relief!

After almost giving up on Apollo, I remembered seeing months ago a GitHub repository which did some form of patching on games, but I couldn't remember what it was.

Then, just by chance, I stumbled upon [BrainSlug](https://github.com/Chadderz121/brainslug-wii "Take me there!")! Now I remembered!

If you've never heard of BrainSlug before, its whole idealogy is almost identical to Apollo's: Having dynamically loaded extensions which can modify the game's functions. How brilliant!

Now, thanks to my rediscovery of BrainSlug, I'm going to redirect my attention back to that of extensions for Apollo.

## Thank you

I would love to say a massive thank you to:

 - [The (now abandoned) MKW-SP Project](https://github.com/mkw-sp): for creating MKW-SP, which initially sparked my interest in creating Apollo, and for creating the mkw.re Ghidra repository, which has helped massively in my understanding of how MKW works.
 - [Melg](https://github.com/MelgMKW): for creating Pulsar. Pulsar is what caused me to actually begin to create Apollo, after I saw what could really be done in the modern modding community.
 - [Chadderz](https://github.com/Chadderz121): for creating BrainSlug, which helped revive my ambition to create Apollo, and of which a lot of code will be heavily inspired from.
 - You! For reading these blogposts, even if it is months to come in the future. It really does mean a lot that somebody has shown even a hint of interest towards Apollo.

Once again, I hope to bring some good news again soon.

\- tealingg ❤️
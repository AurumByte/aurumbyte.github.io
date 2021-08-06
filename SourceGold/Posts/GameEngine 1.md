# Making a 2D Game Engine.... (and other stuff)

#### -- 6th August 2021

*I made a game engine*

Take a moment to let that sink in. Not many people can say *I made a game engine*. It actually was relatively simple and I learned a lot of the supposed "magic" that goes behind it as well. I'm not gonna keep you waiting for long though... so let's get into them juicy details.

### So yeah, a Game Engine

I recently joined Discord, somewhere around May (after I got into Game Development in Unity, but that's another story) where I joined the [Brackeys Discord Server](https://discord.com/channels/243005537342586880/401076241861443587). Turns out there are a lot of people in that server with the same interests as me. I found a ton new projects ([There's even a list on languages developed by people on that server](https://github.com/salty-sweet/TLoDLiBSsf)) some of which included game engines that people made.

When I started out in Unity, I just couldn't get any external editors to provide code completion to the Unity API (I was a beginner, so code completion was a must). I tried 5 different editors/IDEs, watched a ton of tutorials on how to fix the issue, tried suggestions and basically spent days trying to get Unity API code completion up and running (I tried Bolt during this phase but it didn't feel the same).

Then, as I was hanging out in that server one day, It struck me... there were multiple people who made game engines in the server, why not just make a simple one for my uses? The engines from that server kinda provided that small drive to make my engine, the biggest inspiration being [FastJ by lucasstarz](https://github.com/fastjengine/FastJ) as it was made using only the Java standard libraraies. I initially wanted to make the engine using LWJGL (OpenGL bindings for Java), but as I got into it, The engine just wouldn't work after a point of progression because my computer just couldn't render it. So, after about 5 (very exhausting) rewrites, I decided to just use the standard libs to render the graphics in my engine.

After about 2 weeks, here we are, a basic engine framework complete. My engine (named SypherEngine) as of this post supports

 - Basic Game Framework (Game Loop, Window Rendering, etc.)
 - Image rendering
 - ImageTiles (Sprites) with which you can setup basic sprite animations
 - Alpha blending and z-indexing for Images and Sprites
 - Drawing of basic shapes
 - Lighting
 - Shadows
 - GameObjects (a full Entity Component System hasn't been set up yet.. but that will be for a later date)

I'll definitely be working on this for a while, as I want to develop Games, but Unity is a pain, and I don't think my computer can handle Unreal...

### Other Stuff that went on 

 I dropped C++ after a while, it got a bit "difficult" to work with, but that hole for a performant systems language still lingered... so after a while, I went searching and found Rust, a language that was very fast, has a great build system, memory safety and a great community. Best of all, There was a Rust plugin for IntelliJ! So now i could develop both Rust and Java from the same IDE. It was perfect for me and now I'm a (budding) Rustacean!

Second update, after getting nowhere with the compiler for Crypt, and learning a bit of Rust, I decided to rewrite the entire compiler in Rust using LLVM as a backend because what better way to learn than to rush headlong into projects... so after a cup of Rust, we'll see where this get me. So expect an update soon.

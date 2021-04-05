# Creating Cylvre - The steps I took to create a JVM Programming Language

#### -- 8 Feb 2021 

![](https://github.com/SivAxis/SivAxis.github.io/blob/main/images/Always%20need%20new%20programming%20languages%20(freeCodeCamp).png)

*images not showing? Click [here](https://github.com/SivAxis/SivAxis.github.io/blob/main/Posts/Creating%20Cylvre.md) to read this in its repo*

This language is currently on [Github](https://github.com/Cylvre-Language/Cylvre).

Every programmer dreams of creating a programming language. The topic ``programming-language`` on GitHub yields 3600+ results, and only about 500 languages are in the mainstream (both Modern and Historic) with the rest being either unmaintained or toy languages. Most of us have just taken a subset of an existing language and made a compiler for it. Some of us have contributed to a language we like to use. Some of us have taken one step further and a language and its compiler from scratch. 

The greatest thing about open source is that if developers are unhappy or unsatisfied with what they see... They build their own solution. So, here is my journey on creating my solution for the whirlpool of programming languages that I was unsatisfied with. This is the story of the creation of **Cylvre** - The JVM Language.

## Driving force - What led me to create a language

First of all, why **Cylvre**? Well, I wanted a name that would stand for something. Something that was unique and described my language well. After, lots of renaming, I finally settled on Cylvre (pronounced Silver) which stands for **Cy**ber **L**anguage for **V**irtual **R**untime **E**nvironments. Cylvre, was going to be like Kotlin and (in the future) be deployed to various platforms, but for now I settled with Cylvre because... well... it was snazzy and had pretty much **zero** Google searches related to it.

It is May 2020, and we are smack in the middle of a "crisis". Time frees up and I decide to brush up on my coding skills because... why not? and also because I hadn't touched code for like 6 months or so. Back then, I was die-hard C++ fan. I just started to "revise" on C++ and learn the more advanced topics when I hit a road block. Pointers. Yes, they might be useful for someone who is perfect at managing computer memory, or has a lot of experience with low-level computer stuff. But, it wasn't for me and so, I started looking for the ideal language for the beginner.

So now you are probably thinking, "Wait, so you quit using C++ just because you couldn't get the hang of pointers?" and I see why you may think that. Pointers in C++ are easy enough to get with enough practice. Also, I didn't **quit** using C++, I just stopped using it as a main language. I saw lots of flaws with C++ even though it was a beautiful language, and it slowly started to get harder to write C++ code and also to read it. Obviously, I stumbled on Python and immediately moved on. The thought of indentation didn't really appeal to me (no offense to Python fans). So, then I realized that there is no single language that combines extreme simplicity like Python and power like C++ (Safety was also added to the core principles of my language later) and hence I started the work of creating **Cylvre**.

## Design Phase

The first couple of months were all for designing the syntax of Cylvre. The final syntax of the language was completely different, but those changes were from necessity rather than aesthetics. Next was the platform to deploy it to. After several websites, and a bunch of research, it came down to two options: LLVM and the JVM. 

I wanted LLVM due to its speed and ability to convert into binaries but eventually chose the JVM due to its clear specifications and the use of the Java standard library. This came at a price, to learn Java. Although Kotlin was also an option, I chose to use Java to create my language. Kotlin has all these nice features and it is very concise, but sometimes I had a hard time reading Kotlin code. No offense to people who love Kotlin, but sometimes, there is a learning curve that comes with the conciseness that Kotlin offers.

Kotlin was the idol (and soon to be competitor) for Cylvre. Null Safety, Conciseness and exotic use of operators were ideas taken from Kotlin, for which I should give credit. JetBrains created an amazing language, but it just didn't sit right with me. 

The aim of my language was to provide an extremely beginner-friendly, safe and powerful language without sacrificing conciseness.

In the near future, I plan on implementing the ``match`` statement form Scala, the language from which I also took some other ideas.

## Implementataion

Finally, after designing the language, it was time to implement the compiler. I did some research and decided to use ANTLR for the lexing and parsing of my language.
Why did I choose ANTLR? Well, I was capable of writing a good lexer, but my parser... not so much. ANTLR provided fairly performant lexer/parser with the listener/visitor system so that it would be easy to generate JVM bytecode.

For the compiler itself, I searched website after website reading compiler theories, browsing compiler models and code through Github when I finally found the perfect model to write my compiler with. It was the compiler from this repository: [JakubDsiworski/Enkel-JVM-language](https://github.com/JakubDziworski/Enkel-JVM-language).
Yes, the code hasn't been updated for almost 6 years now but it was perfect. No compilcated IR Builders, Launchers and other stuff that could overwhelm a teen. Just three sections: Nodes, Visitors, ByteCode Generators. 

So, with the compiler as a reference, I started building my compiler. I got my compiler nearly done but it started giving some very weird errors and I eventually had to scrap it (Compiler 1 scrapped). I started on the second one, and almost got it finished. It was time for testing. My spirits were high when it all started to go rapidly downhill. All I had to do was to add the bytecode generator for the ``main()`` function but got some NPEs, a developer's worst nightmare. I got it working upto a simple ``Hello World`` program, but every other test put out thousands of Null Pointer Exceptions. Every NPE I fixed resulted in 5 more NPEs being thrown. Compiler 2 was scrapped.

![](https://github.com/SivAxis/SivAxis.github.io/blob/main/images/99%20little%20bugs%20meme.png)

At this point I was getting disheartened and frustrated. I was trying to find a way to build a compiler that works and that's when it hit me, The Eureka moment.
I quickly pull up my computer, cloned the repository I mentioned earlier, and started hacking away. I wanted this compiler to be as close to the original reference as possible.

Soon, as in a couple of weeks, I got Compiler 3 up and running. I faced some NPEs but eventually got the compiler up and running and... IT WORKED! For a developer, nothing beats the feeling of using a working piece of software he/she created. Although there were many problems, Compiler 3 could successfully compile and run basic printing, variable declaration, loops, basic conditionals etc. The biggest problem was that Compiler 3 still couldn't reference Java API. But for me... If it works (somewhat) It Works!... right?


## Conclusion

So far, I know that I have got enough features running to make it a small, functional language. Its not complete yet... and will be subjected to lots of changes but the final product will be to provide a great and powerful language that is easy from the user's perspective. Sure, I may be slightly inexperienced for such a project but this is a long term project. I've learned a lot through this project and I'm determined to bring it to light, no matter what.

*This is my first post! Give a star to [this repository](https://github.com/SivAxis/SivAxis.github.io) if you liked it!*

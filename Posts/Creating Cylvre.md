# Creating Cylvre - The JVM Language

We have all gone through this before. The itch of knowing what a programming language's internals look like. The topic ``programming-language`` yields 3600+ results, and only about 500 languages are in the mainstream (both Modern and Historic) with the rest being either unmaintained or toy languages. Most of us have just taken a subset of an existing language and made a compiler for it. Some of us have contributed to a language we like to use. Some of us have taken one step further and a language and its compiler from scratch. The greatest thing about open source is that if developers are unhappy or unsatisfied with what they see... They build their own solution. So, here is my journey on creating my solution for the whirlpool of programming languages that I was unsatisfied with. This is the story of the creation of **Cylvre** - The JVM Language.

## Driving force - What led me to create a language

It is May 2020, and we are smack in the middle of a "crisis". Time gets freed up and I decide to brush up on my coding skills because... why not? and also because I hadn't touched code for like 6 months or so. Back then, I was die-hard C++ fan. I just started to "revise" on C++ and learn the more advanced topics when I hit a road block, I couldn't grasp pointers no matter how much I tried. So, I started looking for the ideal language for the beginner.

So now you are probably thinking, "Wait, so you quit using C++ just because you couldn't get the hang of pointers?" and I see why you may think that. Pointers in C++ are easy enough to get with enough practice. Also, I didn't **quit** using C++, I just stopped using it as a main language. I saw lots of flaws with C++ even though it was a beautiful language, and it slowly started to get harder to write C++ code and also to read it. Obviously, I stumbled on Python and immediately moved on. The thought of indentation didn't really appeal to me (no offense to Python fans). So, then I realized that there is no single language that combines extreme simplicity like Python and power like C++ (Safety was also added to the core principles of my language later) and hence I started the work of creating **Cylvre**.

## Design Phase

The first couple months were all for designing the syntax of Cylvre. The final syntax of the language was completely different, but those changes were from necessity rather than aesthetics.


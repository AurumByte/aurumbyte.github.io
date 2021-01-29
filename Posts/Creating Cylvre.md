# Creating Cylvre - The JVM Language

We have all gone through this before. The itch of knowing what a programming language's internals look like. The topic ``programming-language`` yields 3600+ results, and only about 500 languages are in the mainstream (both Modern and Historic) with the rest being either unmaintained or toy languages. Most of us have just taken a subset of an existing language and made a compiler for it. Some of us have contributed to a language we like to use. Some of us have taken one step further and a language and its compiler from scratch. The greatest thing about open source is that if developers are unhappy or unsatisfied with what they see... They build their own solution. So, here is my journey on creating my solution for the whirlpool of programming languages that I was unsatisfied with. This is the story of the creation of **Cylvre** - The JVM Language.

## Driving force - What led me to create a language

It is May 2020, and we are smack in the middle of a "crisis". Time gets freed up and I decide to brush up on my coding skills because... why not? and also because I hadn't touched code for like 6 months or so. Back then, I was die-hard C++ fan. I just started to "revise" on C++ and learn the more advanced topics when I hit a road block, I couldn't grasp pointers no matter how much I tried. So, I started looking for the ideal language for the beginner.

So now you are probably thinking, "Wait, so you quit using C++ just because you couldn't get the hang of pointers?" and I see why you may think that. Pointers in C++ are easy enough to get with enough practice. Also, I didn't **quit** using C++, I just stopped using it as a main language. I saw lots of flaws with C++ even though it was a beautiful language, and it slowly started to get harder to write C++ code and also to read it. Obviously, I stumbled on Python and immediately moved on. The thought of indentation didn't really appeal to me (no offense to Python fans). So, then I realized that there is no single language that combines extreme simplicity like Python and power like C++ (Safety was also added to the core principles of my language later) and hence I started the work of creating **Cylvre**.

## Design Phase

The first couple months were all for designing the syntax of Cylvre. The final syntax of the language was completely different, but those changes were from necessity rather than aesthetics. Next was the platform to deploy it to. After several websites, and a bunch of research, it came down to two options: LLVM and the JVM. I wanted LLVM due to its speed and ability to convert into binaries but eventually chose the JVM due to its clear specifications and the use of the Java standard library. This came at a price, to learn Java. Although Kotlin was also an option, I chose to use Java to create my language. Kotlin has all these nice features and it is very concise, but sometimes I had a hard time reading Kotlin code. No offense to people who love Kotlin, but sometimes, there is a learning curve that comes with the conciseness that Kotlin offers.

The aim of my language was to provide an extremely beginner-friendly, safe and powerfull language without sacrificing conciseness.

## Implementataion

Finally, after designing the language, it was time to implement the compiler. I did some research and decided to use ANTLR for the lexing and parsing of my language.
Why did I choose ANTLR? Well, I was capable of writing a good lexer, but my parser... not so much. ANTLR provided fairly performant lexer/parser with the listener/visitor system so that it would be easy to generate JVM bytecode.

For the compiler itself, I searched website after website reading compiler theories, browsing compiler models and code through Github when I finally found the perfect model to write my compiler with. It was the compiler from this repository: [JakubDsiworski/Enkel-JVM-language](https://github.com/JakubDziworski/Enkel-JVM-language).
Yes, the code hasn't been updated for almost 6 years now but it was perfect. No compilcated IR Builders, Launchers and other stuff that could overwhelm a teen. Just three sections: Nodes, Visitors, ByteCode Generators. 

So, with the compiler as a reference, I started building the compiler. I got the compiler nearly done but it started giving some very weird errors and I eventually had to scrap it (Compiler 1 scrapped). I started on the second one, and almost got it finished. It was time for testing. My spirits were high when it all started to go rapidly downhill. All I had to do was to add the bytecode generator for the ``main()`` function but got some NPEs, a developer's worst nightmare. I got it working upto a simple ``Hello World`` program, but every other test put out thousands of Null Pointer Exceptions. Every NPE I fixed resulted in 5 more NPEs being thrown. Compiler 2 was scrapped.

At this point I was getting disheartened and frustrated. I was trying to find a way to build a compiler that works and that's when it hit me, The Eureka moment.
I quickly pull up my computer, cloned the repository I mentioned earlier, and started hacking away. I wanted this compiler to be as close to the original as possible.
Soon, as in a couple of weeks, I got Compiler 3 up and running. I faced some NPEs but eventually got the compiler up and running and... IT WORKED! For a developer, nothing beats the feeling of using a working piece of software he/she created. Although there were many problems, Compiler 3 could successfully compile and run basic printing, variable declaration, loops, basic conditionals etc. The biggest problem was that Compiler 3 still couldn't reference Java API. But for me... If it works (somewhat) It Works!


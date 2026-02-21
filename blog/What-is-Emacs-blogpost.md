
# Table of Contents

1.  [Emacs or Vim? The question that fooled the world.](#orgb6df351)
2.  [Why people mention Vim and Emacs in the same context.](#org8a7dee8)
3.  [What is Emacs *not*](#org175cc6c)
4.  [So What is Emacs?](#orgde537dd)
    1.  [The Keyboard](#orgb5b87ba)
5.  [Outline](#org33170bd)
    1.  [So You're in the market for a new Text Editor.](#org52e1cba)
        1.  [The Benefits of Vim or Emacs if you *are* looking to switch](#orgab5e6d3)
    2.  [First: Change the keybindings.](#orgd4432cc)
        1.  [Default Keybinding Problems](#orgc57d62c)
        2.  [So change them.](#org176fe8c)
        3.  [Distributions](#orgeb74f7d)
        4.  [Plugins vs Packages.](#org3131919)
        5.  [Use Vim.](#org918ea03)
    3.  [Emacs and Vim are not the same.](#orgaee7203)
        1.  [Emacs is not a text editor](#org90ddabb)
        2.  [Emacs is not an IDE.](#orgd954de5)
        3.  [Emacs is a tool for those with a certain philosophy about how to interact with a computer.](#orge2775a0)
    4.  [What even is Emacs](#orgf2c26bd)
        1.  [Elisp Interpreter](#org7d92545)
        2.  [Why is using an interpreter as a text editor advantageous?](#org1d3b5f3)
        3.  [Why](#orgf38502f)



<a id="orgb6df351"></a>

# Emacs or Vim? The question that fooled the world.

Its quite possible that the first time you head of Emacs, it was being compared to Vim. In fairness to those discussions, they *do* have things in common, which we'll get to later.


<a id="org8a7dee8"></a>

# Why people mention Vim and Emacs in the same context.

1.  They've never used either. Not really anyway.

1.  Why using Vim to explain Emacs actually works, if used to disprove the converse.

    Weren't expecting a throwback to Discrete Math were ya?
    
    Thats P -> Q
    
    \begin{equation}
    P \rightarrow Q
    \end{equation}
    
    and
    
    \begin{equation}
    Q \rightarrow P
    \end{equation}
    
    Or something like that anyway.
    
    The point is. Emacs can do anything Vim can do. Vim cannot do anything Emacs can do.


<a id="org175cc6c"></a>

# What is Emacs *not*

Emacs is *not* a text editor. Oh it'll edit text just fine. Mostly. But nobody set out to create a text editor one day and popped out Emacs as a result.
Emacs is also *not* and IDE. The Integrated Development Environment is a wonderful thing. Everything you need for language X, right there in one program. But as we all learn after a few years, **nobody** only uses one language. Config files. Scripts: large and small. Making a website, only to learn that somehow the world wide web is running on string and duct tape.


<a id="orgde537dd"></a>

# So What is Emacs?

Forget about the fact that Emacs can edit text. That is a side-effect at best. Its not even particularly good at doing so.

To understand Emacs, its probably easiest to start from the beginning. Once upon a time, before the internet, there was one programmer, and he made a window. The type everyone makes right before they learn that GUI programming is hard. This guy decided that in *his* window. The stuff on it would be left as an exercise to the reader. I'm somewhat joking, but not by much.

He wrote some C code that would do the basics, and then everyone else could make their own stuff to put into it. He even let their stuff work together.

Still, it was hard for everybody to program such a thing. So the first thing they made was a text editor, so they didn't have to go somewhere else to type.

Next, they realized that while they were programming this window, there were some things they ended up doing **a lot**. So they made some functions to do those things for them, and gave them names.

Eventally, typing in those names became the thing they were doing a lot. Remembering the names was a chore, typeing with -'s instead of spaces was awkward. They saw where this was going. They decided the way to do the least work was to bind functions to individual keys. But, by this time, they already had hundreds of little helper functions. There simply wasn't enough room for all of them!


<a id="orgb5b87ba"></a>

## The Keyboard

So they invented the key chord. Yes, like on a guitar. Back then they were using the [Space Cadet Keyboard](https://en.wikipedia.org/wiki/Space-cadet_keyboard#/media/File:Space-cadet.jpg), which had the modifier keys:

-   Control
-   Meta (Alt equivalent)
-   Super (Windows key, Command key equivalent)
-   Hyper

And the Shift keys:

-   Shift
-   Greek
-   Top (referring to the character on the top of the letter on the key)

Thats right, 7 modifier keys. 7! = 5040 combinations of modifier keys.

There were 50 keys on the keyboard they could modify (26 letter keys + 10 number keys + 14 punctuation/math symbol keys.

5040 \* 50 = 252,000 possible combinations of modifiers + a letter that could mean different things.

While incredibly versatile, it was also a bit unwieldy. 252 thousand different choices was *too* many. "Was this function Control-Hyper-Meta + S? or Control-Super-Meta + S?"

While Emacs still supports Hyper and Super keys, and indeed some users still use them, most keys have been bound to Control and Meta. But 2 modifier keys is only what

So 

Emacs is a LISP interpreter. Thats the engin


<a id="org33170bd"></a>

# Outline


<a id="org52e1cba"></a>

## So You're in the market for a new Text Editor.

If you have 0 problems with your current experience, it makes no sense to switch, no matter which target you're switching to.


<a id="orgab5e6d3"></a>

### The Benefits of Vim or Emacs if you *are* looking to switch

1.  Permanent Residence.

    Vim and Emacs are free. They're Open Source. They both run on damn near everything. I run a 2014 Macbook Air in 2026, and I still love it. Chrome uses too much RAM, but other than that I have everything I want. But VSCode doesn't work on my Operating System after an update. Can you download an Older Version of VSCode? Possibly. But its not transparent, and ant any point they might decide to make a breaking API change, or what have you, and suddenly you can't install plugins anymore. While this is largely my fault, giving complete control of your ability to use the environment you practice your profession in to Microsoft seems&#x2026;unwise in the long term. I'm not a conspiracy theorist, I don't think they're "out to get you." I just think they won't always care if you're a casualty in whatever the next move they make in, because it covers the *majority* of their users.

2.  The ability to get better for the rest of your life.

    If you're just starting out, use an IDE. Learn to code. See if you like it.
    
    If you're starting a *career*, though, you might want to think a little deeper about the trade-offs you're making by doing so.
    
    1.  Learning IDES
    
        IDE's are great. I learned on one. Or rather, I learned on a bunch. Which is sort of the problem. There are great IDE's, but they're built for languages, not all of programming.
        
        Recently (okay maybe for a while now), the best IDEs have been subscription services. I have nothing against those models inherently. The problem is, if you stop paying, you can't work the way you're used to. You can't just buy it once and use it forever.
        
        The other problem is they're easy to learn, but hard to master. I love a good learning curve, but in my opinion IDE's gently lift you up to the middle, then dump you in no man's land, and you're looking around for the next feature that will make your life easier, but you can't see the path. Not from inside the IDE anyway. Not when you need the tool. Not when you would remember it being helpful and solving a problem. So you go to the menu, read all the options, and click on the one that seems like maybe it'll do what you want. You sigh in relief. But you're not really sure what happened. Not really sure what that menu option can be used for. It doesn't give you the function its running. It doesn't enumerate use cases. You're just supposed to know that when what you want is a Aardvark Fourier Transform Anomaly Set, this is the button to click.
        
        And they keybindings. God the keybindings. I'm sure there's a way to change them somehow. Probably in one of dozens of config file languages you've never had to write in before. That you can't reasonably access from anywhere but the 'Edit Keybindings' button 2 nested menus deep because its buried so deep in the filesystem. But I'll allow that for most, its possible. But the philosophy behind their layout? Almost completely opque. There are no "categories" because they just use Control-Shift-<x> whenever Control-<x> was already taken. And Alt-<x> whenever&#x2026;well I don't really know. When does it make sense to use alt instead?
    
    2.  The difference in Vim (and Emacs)
    
        In Vim, you can always learn a way to do something better. There is no doubt in my mind that every vim user has functions they don't know about just waiting to be discovered.
        
        The question is&#x2026;why? Why is there so much functionality they haven't discovered yet? Shouldn't it be eager to make itself known? Well, yes and no. Vim is great. I use it every day. But there's a gaping hole in Vim's interface, and that comes in the form of "Ex Commands". The ones that start with `:`. Which is where most of Vim's user-friendliness falls apart. What happened to modality? What happened to being able to do things you want in a series of keypresses, each with discrete meaning, that can be chained together to become incredibly powerful??
        
        You make moving the cursor to the end of a word one key. the beginning of the next another. You make inserting text before the current character one key, and after it another. But to do anything beyond the normal mode keyset, you're suddenly typing out commands like you're on the terminal, except even those have the benefit of being legible.
        
        The Terminal holds vim back. You're locked into a font, a font size, dealing with colors based on whatever standard your terminal application supports. To send output from one thing to another you have to use pipes to send it line by line, or to files where you have to pick a name, location, extension, that you're probably going to use again, yet have to remember.

3.  


<a id="orgd4432cc"></a>

## First: Change the keybindings.


<a id="orgc57d62c"></a>

### Default Keybinding Problems

The default emacs keybindings are hot garbage. They're probably hard to learn. I wouldn't know, as I didn't really try for more than a day. The **real** problem with emacs keybindings is they hurt. Yes, that's right. Using the default keybindings for Emacs will feel uncomfortable because it literally is hurting your wrists, hands, and fingers. "Emacs pinky" is an understatement. If they wanted to be more accurate, they should have called it "Emacs RSI."


<a id="org176fe8c"></a>

### So change them.

One of the best parts about emacs is the ability to change *anything* within it. Many have done this already. Emacs is both Free and open source. (You can both see the code and do anything you want with it, even sell it.)


<a id="orgeb74f7d"></a>

### Distributions

[Spacemacs](https://www.spacemacs.org/) and [Doom Emacs](https://github.com/doomemacs/doomemacs) are the two most popular distributions of emacs that implement every feature of Vim. Technically, they do this using [the Evil package](https://github.com/emacs-evil/evil), which stands for ****E****​xtensible **VI** ****L****​ayer. This makes the text-editing features of emacs just like Vim. (Though advanced users may prefer to use emacs methods to do advanced things. They really are easier)

1.  Spacemacs

    If you're just starting out, go with spacemacs. It's a wonderful distribution that, while a little on the heavy side, doesn't force you to seek out packages for every functionality you could want.
    
    Its keybindings are discoverable, as when you press the spacebar in normal mode, every keybinding and keybinding tree is listed in a nice little popup.
    
    Prefixing your google searches with "spacemacs how to " is suprisingly reliable given the size of the project compared to base emacs. Unlike doom emacs where it seems like you would either have to figure out if doom is changing something, or set your own keybinds, which for an emacs package can mean anything from 10 to 100s of keybindings. Personally, I want my keybindings the way I want them, but am happy to use someone else's philosophy as a jumping off point to add to if it is suitable. Spacemacs fits that criteria.
    
    Doom Emacs is lighter, but you're going to have to do the research to decide what to add to it. I have not used Doom Emacs, but I have looked into it and decided it wasn't for me until I probably had a few years into the emacs ecosystem.


<a id="org3131919"></a>

### Plugins vs Packages.

Vim has plugins. Emacs has packages.

Vim plugins **can** interact with each other. Emacs packages are **built** to interact. It is assumed that someone will want to modify what your code is doing from their outside code, and as a result every package is built with support for that. There is barely an option not to allow it, since Emacs uses a global namespace for functions. Any function of any Elisp code you've installed can be called from anywhere at any time.

Vim plugins are great. But they extend Vim, not **your** Vim.


<a id="org918ea03"></a>

### Use Vim.

Yes, thats right. You should use Vim inside of Emacs. Well, not actual vim of course. Though that is possible. 


<a id="orgaee7203"></a>

## Emacs and Vim are not the same.


<a id="org90ddabb"></a>

### Emacs is not a text editor


<a id="orgd954de5"></a>

### Emacs is not an IDE.


<a id="orge2775a0"></a>

### Emacs is a tool for those with a certain philosophy about how to interact with a computer.


<a id="orgf2c26bd"></a>

## What even is Emacs


<a id="org7d92545"></a>

### Elisp Interpreter

1.  What is Elisp?

2.  What are the advantages of Elisp?

3.  Why Elisp instead of another, more widespread language?

    All Elisp code works the way it was intended to in Emacs. While it is no doubt a disadvantage that nobody is familiar with it ahead of time, any elisp code can be copy-pasted and run in seconds. You don't need to worry about running it in the right place. You don't have to worry about namespaces, or certain packages interfering with one another. Any function from org mode will be org-function-name in everybody who ever write Elisp's code.

4.  Why hasn't Emacs made the transition to a more modern language like Neovim has?

    For one, I'm not a fan of Lua. Indexes starting at 1 was a silly decision, and so is using it.
    
    Elisp, all things considered, holds up pretty well to modern languages. Its interpreted, so everything can be inspected at runtime. Its Dynamic, which means you dont have to worry about what type a variable has. But it **does** have types. Most things, admittedly, are lists. But you essentially have duck-typing


<a id="org1d3b5f3"></a>

### Why is using an interpreter as a text editor advantageous?

1.  First-class support. For everything.

    1.  Buffers, Windows, and Frames.
    
    2.  Creating your own functions
    
        1.  Stand on the shoulders of giants.
        
            1.  Linus Torvalds (creator of Linux and Git)
            
            2.  Donald Knuth (author of The Art of Computer Programming, creator of TeX, Turing Award winner)
            
            3.  Guido von Rossum (Creator of Python)
            
            4.  James Gosling (Creator of Java)
            
            5.  Peter Norvig (Director of Research and Search Quality at Google)
        
        2.  
    
    3.  
    
    4.  Keybindings
    
    5.  Alterations
    
        No need to compile. No need to shut down and restart. I haven't restarted emacs since a week after I started using it. I've altered it countless times since then.
    
    6.  


<a id="orgf38502f"></a>

### Why


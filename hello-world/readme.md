#HELLO WORLD


Thanks to the petcat utility supplied with VICE emulator package, one can easily write C64 Basic programs on his favorite text editor on a 'modern' computer and run on the emulator. Let's see how.

###Step 1 - Setup
Assuming you already have VICE installed and runninig on your system. All you had to do is to copy petcat into system path. You can find petcat in VICE folder. Just go to `Vice/tools/` locate `petcat` and copy it to some place define in your system path. I my case, I have copied it to `/usr/local/bin`. This is a good place to put **local** installs on Unix like system. (e.g. OSX)

###Step 2 - Prepare your code

Fire up your favorite text editor and write down the following code. This is the ""Hello World"" incarnation written in C64 Basic.

```basic
10 print "hello world  ";
20 goto 10
```

Save the file as **hello-world.bas**. Now it is time to petcat magic.

###Step 3 - Petcat magic

Petcat magically tokenize text input and creates the basic data, to be placed in C64  memory. This data is saved in a **prg** file. All you have to do is to type in `petcat -w2 -o hello-world.prg hello-world.bas` **hello-world.prg** file will be created in the same folder.

for details and other uses of petcat you can always type in `petcat -help` 

###Step 4 - Run it, finally
Just go to the folder you created the prg. Double click on it and enjoy. Ok, I know, watching some letters flowing through the screen is not so fun. But may be you can do something better. 
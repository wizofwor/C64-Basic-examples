#HELLO WORLD


Thanks to the petcat utility supplied with VICE emulator package, one can easily write C64 Basic programs on his favorite text editor on a 'modern' computer and run on the emulator. Let's see how.

###Step 1 - Setup
Assuming you already have VICE installed and runninig on your system. All you had to do is to copy petcat into system path. You can find petcat in VICE folder. Just go to `Vice\tools\` locate `petcat` and copy it to some place define in your system path. I my case, I have copied it to `/usr/local/bin`. This is a good place to put **local** installs on Unix like system. (e.g. OSX)

###Step 2 - Prepare your code

Fire up your favorite text editor and wire following code.

```basic
10 print "hello world  ";
20 goto 10```
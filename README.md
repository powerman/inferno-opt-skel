This project is example, which can be used as template to start new /opt project for OS Inferno.

Dependencies:
  * http://code.google.com/p/inferno-opt-mkfiles/
  * http://code.google.com/p/inferno-contrib-tap/ (only for tests)
  * http://code.google.com/p/inferno-contrib-logger/ (example dependency for example command :))
  * http://www.methods.co.nz/asciidoc/ (converter from asciidoc markup to other formats)
  * http://powerman.name/asciidoc/ (asciidoc 9man backend for converting into Inferno man pages)

Actually all these dependencies are optional:
  * mkfiles project can be just copied to ./mkfiles/ subdir in your project to avoid dependency on external project
  * tap module needed only for testing; you can use another modules, but this one is cool because it allow you to run tests using `prove` command in host os (standard testing tool for Perl)
  * logger is just an example dependency, nothing more
  * asciidoc needed only if you like to generate Inferno man pages from simple .txt source

You can build this project using these commands both from host os and inside emu (except `prove`, which works only in host os):

```
mk all
mk install

mk test
prove -r

mk clean
mk nuke
```

When this project installed in `/opt/skel` and your /opt is correctly set up (http://code.google.com/p/inferno-opt-setup/) you can also:

```
$ emu
; examplecmd
Hello from ExampleLib->init()
user.warn: Dec  6 05:04:40 examplecmd[158]: Hello from ExampleCmd->init()
user.err: Dec  6 05:04:40 examplecmd[158]: Hello from ExampleCmd->init()
; man examplecmd
EXAMPLECMD(1)                                       EXAMPLECMD(1)

NAME
     examplecmd - Example command in /opt skeleton project
…
; man examplelib
EXAMPLELIB(2)                                       EXAMPLELIB(2)

NAME
     examplelib - Example library in /opt skeleton project
…
```
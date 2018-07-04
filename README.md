# Rerun if changed

*Wojciech Adam Koszek super duper process restarter*

`rerun-if-changed` starts the application and moniors the source code files in
parallel.
It uses a standard shell commands, requires no extensions or complex
dependencies.
It's designed to be simple to install and simple to run.
Competitive tools might be smarter, faster and more effecient, but this
tool will likely give you less headpain.

If the source code files change, `rerun-if-changed` restarts the
application.  This script was created for technologies such as Golang,
Node.js or Ruby Sinatra framework.

In the cases supported right now, the application which is started runs in the foreground.
If your application spins and goes into the background, you must ask it not
to do so.

# Quickstart

Assuming your app is in `app.rb`, and you'd normally run it as:

	ruby app.rb

you run `rerun-if-changed` as:

	./rerun-if-changed 'ruby app.rb' '*.rb'

It means that `rerun-if-changed` will run `ruby app` and monitor all `.rb`
files.
If any of them change, `rerun-if-changed` will send a SIGTERM to `ruby app`
already spun and wait a little wait for it to finish.
Afterwards, it'll start `ruby app` again.

As opposed to `*.rb` you can pass anything you'd usually pass to `ls`.
This tool uses `ls` internally, in fact.

# Author

- Wojciech Adam Koszek, [wojciech@koszek.com](mailto:wojciech@koszek.com)
- [http://www.koszek.com](http://www.koszek.com)

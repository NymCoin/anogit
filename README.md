These are some basic tools for using git in an anonymous way.

Please note that these tools only do very basic anonymisation: it is up to you to configure the essentials.

In other words, ensure you have the following setup first:

 * A strong SSH key used ONLY for this repo
 * A secure development box
 * An anonymous connection to the git provider of your choice over tor, I2P or similar

You should also ensure there is nothing obvious in your actual code that identifies you personally.

Use sensible precautions and do a git diff before running a commit - review it for obvious signs of your
real identity.

To use the tools, clone the repo and set your path variable appropriately:

```
cd ~
git clone http://git.psii2pdloxelodts.onion/Womed1969/anogit.git
export PATH=$HOME/anogit:$PATH
```

Once you have done this, use the tools to run commits and pushes instead of invoking git directly.

Your commits will all be set to "John Doe" with each commit taking place seconds
after the unix epoch time.

When pushing to a remote repo (such as github, or better: git.psi.i2p) you should
schedule your pushes rather than pushing manually. To assist with this, you should
run the provided anogit-setup-cron tool.

anogit-setup-cron will generate a script to push your changes on a random delay of
up to 24 hours - it is recommended that you set this in a daily cron job, but you may also
simply invoke it manually.

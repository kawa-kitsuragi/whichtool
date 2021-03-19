# whichtool
 Which tool from the Society for Internet Blaseball Research is right for your needs?

Accepting PRs - contact `@Kawa#7680` in `#projects` in [SIBR](https://discord.sibr.dev) for help or questions, and check out the issue tracker for braindumps.

This is being built using the [Sugarcube](https://www.motoslave.net/sugarcube/2/docs/#introduction) story format; refer to that link for most syntax questions. Github Pages should auto-compile changes from WhichTool.twee into WhichTool.html then push [here](https://kawa-kitsuragi.github.io/whichtool/); refer to [Em LazerWalker's excellent blog on the subject](https://blog.lazerwalker.com/azure,/game/dev/2020/01/16/a-modern-developers-workflow-for-twine.html) for more info on how that works.

## Adding your own tools
Create a new `.twee` file in the `src` directory, titled after your tool. Start it with:

```
:: YourToolName
```

It is easiest if this line (the name of the passage) doesn't have spaces, and Kawa is generally preferring for this name to be in [UpperCamelCase](https://en.wikipedia.org/wiki/Camel_case).

Then add content about your tool:
* a link to it
* useful notes and documentation about it
* who you are
* where people can report bugs and discuss it
* its source code, if you're making that public
* places to support you such as Patreon and Ko-Fi, if you'd like

If you're comfortable with Twee, you can also edit `main.twee` to lead to a link to a passage called `YourToolName` - if not, just ask Kawa, either by an @-mention in `#projects` or opening an Issue here. 

Currently existing tool makers are welcome to edit their own tools' .twee files as well! 

### An arbitrary style note
I'm trying to demarcate Discord channel names using the `.channel` style; you can wrap a channel like so:
```
@@.channel;#channel-name-here@@
```
If you have AutoHotKey, you can use the script in this repo - `+ch` will 'autocorrect' to `@@.channel;#@@`, ready to be edited accordingly.

# whichtool
 Which tool from the Society for Internet Blaseball Research is right for your needs?

Accepting PRs - contact `@Kawa#7680` in `#projects` in [SIBR](https://discord.sibr.dev) for help or questions, and check out the issue tracker for braindumps.

This is being built using the [Sugarcube](https://www.motoslave.net/sugarcube/2/docs/#introduction) story format; refer to that link for most syntax questions. Github Pages should auto-compile changes from the `src` directory into WhichTool.html then push [here](https://whichtool.sibr.dev); refer to [Em LazerWalker's excellent blog on the subject](https://blog.lazerwalker.com/azure,/game/dev/2020/01/16/a-modern-developers-workflow-for-twine.html) for more info on how that works.

## Adding your own tools
Create a new `.twee` file in the `src\tools` directory, titled after your tool. Here's a format to follow:

```
:: YourToolName

[[This tool|https://whatever.sibr.dev]] does {things and stuff.} {Here's some notes on how to use it.}

It's made by {this user!} The source code is [[here|https://github.com/me/mytool]]. 

If you'd like, you can also [[send {this user} a Ko-Fi|https://ko-fi.com/me]].

<<include WhereToDiscuss>>
```

The first line *must* start with the double colon `::` and then a short word or phrase. It is easiest if this phrase (the name of the passage) doesn't have spaces, and Kawa is generally preferring for this name to be in [UpperCamelCase](https://en.wikipedia.org/wiki/Camel_case).

Remove `{curly braces}` and fill them with text. Keep the `[[double square braces]]` in that format - those will make links; left of the `|` pipe is the text, that links to the site on the right. Be sure to include the full site name (with the `https://`!) You're of course not required to use precisely this format, or necessarily share your source or support links - do what feels right for your tool. 

The final line auto-includes boilerplate on where to discuss issues for your project. It should default to the main `#📽-Projects` channel in "🙌 Getting Involved". If you have your own 💼 Major Projects channel, you'll need an extra line - `<<set $discussion_channel to "my-channel">>` before the `include`. (Kawa can help with some of the subtleties of variable flagging in Twine.)

If you're comfortable with Twee, you can also edit `main.twee` to lead to a link to a passage called `YourToolName` where your tool should go in the main flow. It's okay if you're not comfortable with editing the main flow - submit a pull request anyway, and Kawa will help make that happen!

If you have questions, just ask Kawa, either by an @-mention in `#projects` or opening an Issue here. 

Currently existing tool makers are welcome to edit their own tools' .twee files as well! 

### An arbitrary style note
Kawa demarcates Discord channel names using the `.channel` style; you can wrap a channel like so:
```
@@.channel;#channel-name-here@@
```
If you have AutoHotKey, you can use the script in this repo - `+ch` will 'autocorrect' to `@@.channel;#@@`, ready to be edited accordingly.

## Local Testing
Install [Tweego](https://www.motoslave.net/tweego/) then in a command line
`tweego src -o WhichTool.html --head=headers.html`
and test WhichTool.html in your favorite browser.

Yo can also do 
`tweego -w src -o WhichTool.html --head=headers.html`
and have the HTML auto-recompile each time you save anything in `src`.

Kawa requests that HTML changes be discarded before pushing to main, to not interfere with Github Actions doing the same thing during its build process.

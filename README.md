
# This package will allow you to use embed color names in pycord or discord.py


To get started, create a command that will send an embed. 
In the `color=` set color equal to `colorcoder(color)` where `color` is the name of the color you wish to send the embed with.
 
 
 For example:

```
@client.command(description='Sends a Customized Embed to the specified channel')
async def embed(ctx, title, description, *, channel : discord.TextChannel = None, color = None):


  if color == None:
      color = "default"

  em = discord.Embed(
      title=title, 
     description=description, 
      color = (colorcoder(color)))

  if channel is None:
      await ctx.respond(embeds=[em])
  else:
      await channel.send(embeds=[em])
      await ctx.respond(f'Embed Sent to #{channel}', ephemeral=True)
```

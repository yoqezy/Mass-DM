import discord, os,json,random,colorama

from discord.ext import commands

import requests

import time

import asyncio

client = commands.Bot(command_prefix="$", self_bot=True)

client.remove_command('help')

@client.event

async def on_ready():

  print("on")

@client.command()

async def dmall(ctx, *, msg: str):

 await ctx.message.delete()

 for channel in client.private_channels:

  try:

   await channel.send(f"{msg}")

   print(f'Sent {msg}')

  except:

   pass

token = "YOUR TOKEN"

client.run(token, bot=False)

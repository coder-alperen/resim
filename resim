import discord
from discord.ext import commands
import os
import random
import requests

img_files=os.listdir("C:/Users/Casper/Desktop/code/kodland_python/denemeler/images")
intents = discord.Intents.default()
intents.message_content = True

def get_duck_image_url():    
    url = 'https://random.dog/woof.json'
    res = requests.get(url)
    data = res.json()
    return data['url']

bot = commands.Bot(command_prefix='*', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} olarak giriş yaptık')

@bot.command('dog')
async def dog(ctx):
    image_url = get_duck_image_url()
    await ctx.send(image_url)

@bot.command()
async def mem(ctx):
    img_file=random.choice(img_files)
    with open(f'C:/Users/Casper/Desktop/code/kodland_python/denemeler/images/{img_file}', 'rb') as f:
        picture = discord.File(f)
    await ctx.send(file=picture)

bot.run("")

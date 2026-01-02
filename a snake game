import random
import pygame
import time
from pygame.locals import *
pygame.init()
screen = pygame.display.set_mode((1800,1000))
pygame.display.set_caption("Game")
color=(255,0,0)
colorw=(0,255,0)
colors=(0,0,255)
clock=pygame.time.Clock()
def food():
    foodx=(random.randint(1000,1600)//50)*50
    foody=(random.randint(0,800)//50)*50
    return(foodx,foody)
foodx,foody=food()
snakex=(random.randint(0,1600)//50)*50
snakey=(random.randint(0,800)//50)*50
up=False
down=False
right=False
left=True
snlist=[]
snlist.append((snakex,snakey))
snlen=1
rect2=pygame.draw.rect(screen,colorw,(snakex,snakey,50,50))
def Done(msg,size):
       fontobj=pygame.font.SysFont("freesans", size)
       msgobj=fontobj.render(msg,False,colors)
       screen.blit(msgobj,(500,500))
       print("hello")
while True:
    screen.fill((0,0,0))
    for event in pygame.event.get():
        if event.type==KEYDOWN:
            if event.key==K_DOWN:
                up=False
                right=False
                left=False
                down=True
            if event.key==K_UP:
                down=False
                right=False
                left=False
                up=True
            if event.key==K_RIGHT:
                up=False
                right=False
                down=False
                right=True
            if event.key==K_LEFT:
                up=False
                right=False
                down=False
                left=True
        if event.type==QUIT:
            pygame.quit()
            exit()
    if up==True:
        snakey=snakey-50
    if down==True:
        snakey=snakey+50
    if right==True:
        snakex=snakex+50
    if left==True:
        snakex=snakex-50
    if (snakex,snakey) in snlist:
        break
    snlist.insert(0,(snakex,snakey))    
    rect1=pygame.draw.rect(screen,color,(foodx,foody,50,50))
    head=pygame.draw.rect(screen,colors,(snlist[0][0],snlist[0][1],50,50))
    if rect1.colliderect(head):
        snlist.insert(0,(foodx,foody))
        snlen=snlen+1
        foodx,foody=food()
    if snlen<len(snlist):
        snlist.pop()
    i=0
    for seg in snlist:
        if i==0:
            pygame.draw.rect(screen,colors,(seg[0],seg[1],50,50))
            i=1
            
        else:
            pygame.draw.rect(screen,colorw,(seg[0],seg[1],50,50))

    if snakex>1800-50 or snakex<0:
        break
    if snakey>1000-50 or snakey<0:
        break
    clock.tick(15)
    pygame.display.update()
    
        
        
        

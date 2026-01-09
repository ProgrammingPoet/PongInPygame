import pygame
import random
pygame.init()#initialisation
WINDOW = pygame.display.set_mode((600,600))#window resolution
CLOCK = pygame.time.Clock()#initialising fps functionalilty
PONG=[300,300]
BOTTOM_PADDLE=[180,580]
TOP_PADDLE=[180,10]
PONGVELOCITYX=0
PONGVELOCITYY=0 
while PONGVELOCITYX==0 or PONGVELOCITYY==0:#make sure the ball has velocity
    PONGVELOCITYX=random.randint(-1, 1)*8
    PONGVELOCITYY=random.randint(-1, 1)*3


#game loop
RENDERING=True
while RENDERING==True:

    WINDOW.fill((0, 0, 0))#clear the screen black

    KEYDATA = pygame.key.get_pressed()#stores all pressed keys


    if KEYDATA[pygame.K_LEFT]==True:#left key held down
        BOTTOM_PADDLE[0]=BOTTOM_PADDLE[0]-15
    
    if KEYDATA[pygame.K_RIGHT]==True:#right key held down
        BOTTOM_PADDLE[0]=BOTTOM_PADDLE[0]+15

    if KEYDATA[pygame.K_z]==True:#z key held down
        TOP_PADDLE[0]=TOP_PADDLE[0]-15
    
    if KEYDATA[pygame.K_x]==True:#x key held down
        TOP_PADDLE[0]=TOP_PADDLE[0]+15

    


    PONG[1]=PONG[1]+PONGVELOCITYY#pong vertical displacement
    PONG[0]=PONG[0]+PONGVELOCITYX#pong horizontal displacement

    BOTTOM_PADDLE_RECT=pygame.Rect(BOTTOM_PADDLE[0],BOTTOM_PADDLE[1],100,10)#bottom paddle loading and drawing
    pygame.draw.rect(WINDOW, (0,0,255),BOTTOM_PADDLE_RECT)#bottom paddle rendering

    TOP_PADDLE_RECT=pygame.Rect(TOP_PADDLE[0],TOP_PADDLE[1],100,10)# top paddle loading and drawing
    pygame.draw.rect(WINDOW, (0,0,255),TOP_PADDLE_RECT)#bottom paddle rendering


    PONG_BALL=pygame.Rect(PONG[0],PONG[1],10,10)#pong loading and drawing
    pygame.draw.rect(WINDOW, (255, 255, 255),PONG_BALL)#pong rendering




    CLOCK.tick(60)#FPS lock

    LEFT_BORDER=pygame.Rect(0,0,10,600)#left border loading and drawing
    pygame.draw.rect(WINDOW, (0,255, 0),LEFT_BORDER)#left border rendering
    RIGHT_BORDER=pygame.Rect(590,0,10,600)#right border loading and drawing
    pygame.draw.rect(WINDOW, (0, 255, 0),RIGHT_BORDER)#right border rendering
    TOP_BORDER=pygame.Rect(0,0,600,10)#top border loading and drawing
    pygame.draw.rect(WINDOW, (255, 0, 0),TOP_BORDER)#top border rendering
    BOTTOM_BORDER=pygame.Rect(0,590,600,10)#bottom border loading and drawing
    pygame.draw.rect(WINDOW, (255,0, 0),BOTTOM_BORDER)#bottom border rendering


    if PONG_BALL.colliderect(BOTTOM_PADDLE_RECT):#bottom paddle collision detection
        PONGVELOCITYY=-PONGVELOCITYY

    if PONG_BALL.colliderect(TOP_PADDLE_RECT):#top paddle collision detection
        PONGVELOCITYY=-PONGVELOCITYY
    

    if PONG_BALL.colliderect(LEFT_BORDER) or PONG_BALL.colliderect(RIGHT_BORDER):#left and right border collision detection
        PONGVELOCITYX=-PONGVELOCITYX
    if PONG_BALL.colliderect(TOP_BORDER) or PONG_BALL.colliderect(BOTTOM_BORDER):#top and bottom border collision detection
        PONGVELOCITYY=-PONGVELOCITYY

       


    for event in pygame.event.get():#checks for inputs
        #quit from x button functionality
        if event.type == pygame.QUIT:
            RENDERING = False

    pygame.display.update()#rendering the final image

pygame.quit()

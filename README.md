# yixinyixi12


import pygame  
import random

# 定义颜色  
BLACK = (0, 0, 0)  
WHITE = (255, 255, 255)  
GREEN = (0, 255, 0)  
RED = (255, 0, 0)

# 初始化 Pygame  
pygame.init()

# 设置窗口大小  
screen_width = 800  
screen_height = 600  
screen = pygame.display.set_mode((screen_width, screen_height))

# 设置窗口标题  
pygame.display.set_caption("Rabbit and Turtle Game")

# 创建兔子和乌龟对象  
rabbit = pygame.Rect(screen_width // 2 - 100, screen_height // 2 - 100, 100, 100)  
turtle = pygame.Rect(100, 100, 100, 100)

# 创建时钟对象  
clock = pygame.time.Clock()

# 游戏循环  
while True:  
    # 处理事件  
    for event in pygame.event.get():  
        if event.type == pygame.QUIT:  
            pygame.quit()  
            quit()  
        elif event.type == pygame.KEYDOWN:  
            if event.key == pygame.K_LEFT:  
                rabbit.left(100)  
            elif event.key == pygame.K_RIGHT:  
                rabbit.right(100)  
            elif event.key == pygame.K_UP:  
                turtle.up()  
            elif event.key == pygame.K_DOWN:  
                turtle.down()

    # 更新兔子和乌龟的位置  
    rabbit.move(0, -100)  
    turtle.move(0, 100)

    # 绘制背景  
    screen.fill(WHITE)

    # 绘制兔子和乌龟  
    pygame.draw.rect(screen, GREEN, rabbit)  
    pygame.draw.rect(screen, RED, turtle)

    # 更新屏幕  
    pygame.display.update()

    # 控制游戏帧率  
    clock.tick(30)  

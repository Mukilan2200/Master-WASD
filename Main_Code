import pygame
import time

pygame.init()

SCREEN_WIDTH = 800
SCREEN_HEIGHT = 600

screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))

player = pygame.Rect((300, 250, 50, 50))

show_error_message = False


pygame.display.set_caption("Mastering WASD")

run = True
while run:
    screen.fill((0, 0, 0))


    
    pygame.draw.rect(screen, (255, 0, 0), player)
    key = pygame.key.get_pressed()
    if key[pygame.K_a] == True:
        player.move_ip(-1, 0 )
    elif key[pygame.K_d] == True:
        player.move_ip(1, 0 )
    elif key[pygame.K_w] == True:
        player.move_ip(0, -1)
    elif key[pygame.K_s] == True:
        player.move_ip(0, 1)
    
    if player.left < 0 or player.right > SCREEN_WIDTH or player.top < 0 or player.bottom > SCREEN_HEIGHT:
        font = pygame.font.SysFont(None, 60)
        text = font.render("Out of Bounds!!!", True, (255, 255, 255))
        font_two = pygame.font.SysFont(None, 40)
        text_two = font_two.render("Wait for Sprite to Recenter", True, (255, 255, 255))
        text_rect = text_two.get_rect(center=(SCREEN_WIDTH // 2+30, SCREEN_HEIGHT // 2))
        text_rect_two = text.get_rect(center=(SCREEN_WIDTH // 2, SCREEN_HEIGHT // 2+50))
        screen.blit(text, text_rect)
        screen.blit(text_two, text_rect_two)
        pygame.display.update()

        player.center = (SCREEN_WIDTH // 2, SCREEN_HEIGHT // 2)
        time.sleep(1)


    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            run = False
        if event.type == pygame.KEYDOWN:
            if event.key in (pygame.K_UP, pygame.K_DOWN, pygame.K_LEFT, pygame.K_RIGHT):
                text_three = font.render("Stop Using Arrow Keys!!!", True, (255, 255, 255))
                text_rect_three = text_three.get_rect(center=(SCREEN_WIDTH // 2, SCREEN_HEIGHT // 2))
                show_error_message = True
        if event.type == pygame.KEYUP:
            if event.key in (pygame.K_UP, pygame.K_DOWN, pygame.K_LEFT, pygame.K_RIGHT):
                text_three = font.render("Stop Using Arrow Keys!!!", True, (255, 255, 255))
                text_rect_three = text_three.get_rect(center=(SCREEN_WIDTH // 2, SCREEN_HEIGHT // 2))
                show_error_message = False
    
    if show_error_message:
        screen.blit(text_three, text_rect_three)
        
    pygame.display.update()

    

    
pygame.quit()

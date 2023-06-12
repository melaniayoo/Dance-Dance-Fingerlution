import pygame
from gpiozero import Button, LED
import RPi.GPIO as GPIO
from time import sleep
import random
import math
import sys

pygame.init()

btn_sound1 = Button(17)
led_sound1 = LED(4)

btn_sound2 = Button(22)
led_sound2 = LED(27)

btn_sound3 = Button(10)
led_sound3 = LED(9)

btn_sound4 = Button(6)
led_sound4 = LED(5)

sound1 = pygame.mixer.Sound("/home/melaniayoo/gpio-music-box/samples/sound1 (1).wav")
sound2 = pygame.mixer.Sound("/home/melaniayoo/gpio-music-box/samples/sound2 (1).wav")
sound3 = pygame.mixer.Sound("/home/melaniayoo/gpio-music-box/samples/sound3 (1).wav")
sound4 = pygame.mixer.Sound("/home/melaniayoo/gpio-music-box/samples/sound4 (1).wav")
losing_sound = pygame.mixer.Sound("/home/melaniayoo/gpio-music-box/samples/losing.wav")
winning_sound = pygame.mixer.Sound("/home/melaniayoo/gpio-music-box/samples/winning.wav")

touched_order = []

def pressed1():
    touched_order.append(1)
    led_sound1.on()
    sound1.play()

def pressed2():
    touched_order.append(2)
    led_sound2.on()
    sound2.play()

def pressed3():
    touched_order.append(3)
    led_sound3.on()
    sound3.play()

def pressed4():
    touched_order.append(4)
    led_sound4.on()
    sound4.play()

btn_sound1.when_pressed = pressed1
btn_sound1.when_released = led_sound1.off

btn_sound2.when_pressed = pressed2
btn_sound2.when_released = led_sound2.off

btn_sound3.when_pressed = pressed3
btn_sound3.when_released = led_sound3.off

btn_sound4.when_pressed = pressed4
btn_sound4.when_released = led_sound4.off

def button1():
    led_sound1.on()
    sleep(0.5)
    led_sound1.off()
    sleep(0.5)

def button2():
    led_sound2.on()
    sleep(0.5)
    led_sound2.off()
    sleep(0.5)

def button3():
    led_sound3.on()
    sleep(0.5)
    led_sound3.off()
    sleep(0.5)

def button4():
    led_sound4.on()
    sleep(0.5)
    led_sound4.off()
    sleep(0.5)

def all_buttons():
    sleep(0.5)
    led_sound1.on()
    led_sound2.on()
    led_sound3.on()
    led_sound4.on()
    sleep(0.2)
    led_sound1.off()
    led_sound2.off()
    led_sound3.off()
    led_sound4.off()
    sleep(0.2)
    led_sound1.on()
    led_sound2.on()
    led_sound3.on()
    led_sound4.on()
    sleep(0.2)
    led_sound1.off()
    led_sound2.off()
    led_sound3.off()
    led_sound4.off()
    sleep(0.2)
    led_sound1.on()
    led_sound2.on()
    led_sound3.on()
    led_sound4.on()
    sleep(0.2)
    led_sound1.off()
    led_sound2.off()
    led_sound3.off()
    led_sound4.off()
    sleep(0.2)
    led_sound1.on()
    led_sound2.on()
    led_sound3.on()
    led_sound4.on()
    sleep(0.2)
    led_sound1.off()
    led_sound2.off()
    led_sound3.off()
    led_sound4.off()
    sleep(0.2)
    led_sound1.on()
    led_sound2.on()
    led_sound3.on()
    led_sound4.on()
    sleep(0.2)
    led_sound1.off()
    led_sound2.off()
    led_sound3.off()
    led_sound4.off()
    sleep(0.2)
    led_sound1.on()
    led_sound2.on()
    led_sound3.on()
    led_sound4.on()
    sleep(0.2)
    led_sound1.off()
    led_sound2.off()
    led_sound3.off()
    led_sound4.off()
    sleep(0.5)

array = []
level = 0
for x in range(4):
    array.append(random.randint(1,4))
print(array)

def check_sequence():
    if touched_order == array:
        array.append(random.randint(1,4))
        return True
    else:
        return False
first_time = True
while True:
    if first_time == True:
        first_time = False
        for x in array:
            if x == 1:
                button1()
            elif x == 2:
                button2()
            elif x == 3:
                button3()
            elif x == 4:
                button4()

    for i in range(len(touched_order)):
        if touched_order[i] != array[i]:
            print("You lost")
            losing_sound.play()
            sys.exit()

    if touched_order == array:
        print("You passed")
        winning_sound.play()
        level += 1
        array = []
        for x in range(level+4):
            array.append(random.randint(1,4))
        first_time=True
        touched_order = []
        all_buttons()
        sleep(2)


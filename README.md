#!/usr/bin/python
import RPi.GPIO as GPIO
import time
import requests
import subprocess
import os

GPIO.setmode(GPIO.BCM)

GPIO.setup(21, GPIO.IN, pull_up_down=GPIO.PUD_UP)

while True:
	    input_state = GPIO.input(21)
	    if input_state == False:
                  os.system("curl -X POST https://maker.ifttt.com/trigger/button_pressed/with/key/cEc2_PLQP53PmxE3vLQhpy")
                  print('')
                  os.system("curl -X POST https://maker.ifttt.com/trigger/hulp/with/key/cEc2_PLQP53PmxE3vLQhpy")
                  print('Hulp komt eraan')
                  execfile("hulpoled.py")
		  # import hulpoled
                  time.sleep(4.0)

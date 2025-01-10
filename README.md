# python-openbci

![Python versions](https://img.shields.io/pypi/pyversions/icon_font_to_png.svg)

Optimized Python Library for OpenBCI Cython.

Basic usage:

```python
ffps = Fps()
ffps.tic()

def handle_sample(sample):
   ffps.steptoc()

   print( f"Estimated frames per second: {ffps.fps} - Sample: {sample.channel_data[0]} ")


if __name__ == '__main__':

   fs = 250.0

   board = OpenBCIBoard()
   board.print_register_settings()
   board.get_radio_channel_number()
   print(f'OpenBCI connected to radio channel {board.radio_channel_number}')

   board.start_streaming(handle_sample)

   #print('Closing up everything....')
   board.checktimer.cancel()

   
   board.disconnect()
```

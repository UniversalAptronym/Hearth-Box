## __Optional: Overclocking__

If you are using a Raspberry Pi 4 or 5, you can do something called "overclocking" your Pi to improve performance. This means that your Pi will temporarily run faster for short periods of time when needed, such as when you give it a big file to transfer. This increases the heat your Pi generates above the threshold at which it could run safely forever, but below the threshold at which it would immediately be damaged. 

If you have a cooling fan (which you should if you followed the instructions), are conservative with how much you overclock your Pi (which the settings below are), and don't live somewhere extremely hot, this is perfectly safe. 

The below is for the Raspberry Pi 5.
```
sudo nano /boot/firmware/config.txt
```

```
arm_freq=2800
gpu_freq=700
over_voltage=3

usb_max_current_enable=1

dtparam=fan_temp0=45000
dtparam=fan_temp0_hyst=6000
dtparam=fan_temp0_speed=165
dtparam=fan_temp1=52000
dtparam=fan_temp1_hyst=6000
dtparam=fan_temp1_speed=190
dtparam=fan_temp2=57000
dtparam=fan_temp2_hyst=6000
dtparam=fan_temp2_speed=215
dtparam=fan_temp3=61000
dtparam=fan_temp3_hyst=6000
dtparam=fan_temp3_speed=255```

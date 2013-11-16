maestro.py
==========

This Python class supports Pololu's Maestro servo controller over USB serial. Great with Raspberry Pi. The class includes methods to control servos (position, speed, acceleration), read servo position, and start/stop Maestro scripts.  See Pololu's on-line documentation to understand the full capabilities of this nifty micro-controller.

Pololu's Maestro Windows installer sets up the Maestro Control Center, used to configure, test and program the controller.  Be sure the Maestro is configured for "USB Dual Port" serial mode.  I believe the controller is setup fine by default, so it isn't necessary to use the Control Center application.

You'll need to have the 'pyserial' Python module installed to use maestro.py.

For Linux, download pyserial-2.6.tar.gz from http://sourceforge.net/projects/pyserial/files/pyserial/ and then install

    tar –zxf pyserial-2.6.tar.gz
    cd pyserial-2.6
    sudo python setup.py install


Example usage:

    import maestro.py
    servo = maestro.Controller()
    servo.setAccel(1,4)      #set servo 1 acceleration to 4
    servo.setTarget(1,6000)  #set servo to move to center position
    servo.close

## PID Controller

To control the car steering angle using the PID controller and to keep the car with in the road. The PID controller comprises of Proportional, Integral and derivative components. 

### P
The P controller will give output proportional to the Cross Track Error (CTE) based on the proportional gain (Kp) configured. This is a simplest controller one can design with minimal component (P alone). 

If we increase the proportional gain of the controller, the stability of the system decreases. It produces oscillations and never become settled to the set point. It might not be suitable for the continuous control systems.

### I
The integral term of the controller accumulated the previous errors of the system and tries to produce control variable based on that. It is used to remove the offset produced overtime due to the memory effect of the P component. The Integral gain (Ki) be given as small as 0.0001 as the accumulated error value gets larger by time.

### D
The derivative component of PID gives output based on the difference between the current CTE and previous CTE. The derivative component plays a key role in making the system stable. The CV can be damped quickly to setpoint if we could correctly configure the D gain (Kd). Also the D controller can not be used alone since it relies on the difference between past value and present value, if there is no change in error, it would simply output 0. It will affect the stability of the system.

---

### Tuning the controller

I chose PID controller since it is simple to implement and have good overall system stability. 

I tuned the PID values manually experimenting with trial and error method.
I started with changing the P gain of the controller. Once the system started to critically oscillate (without damping), I started to increase the D gain by steps of 0.05. The D gain helped to damp the oscillations and bring the CV to set point.
I didn't change the I gain until the car was going off track in second sharp bend. The I gain helped to regain control over the car.

Finally after experimenting with various values, I  settled with the following parameters for the Kp, Ki and Kd gains.

| Parameter | Gain |
----|----
|Kp | 0.05 |
|Ki | 0.008 |
|Kd | 5.0 |




 




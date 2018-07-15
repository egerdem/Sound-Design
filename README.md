Some Notes 
•	After drawing, there is only a one pair of swooshing sound. To continue, click the message :
            
	Reynolds number automatically recalculated if you change and hit this message.
You can also switch to “random swooshing model” if you do not want to initate the swooshes manually :
           
•	I could not complete the hitting of swords, but you can manually hit them with the blue bang.  Or you can use “random hit”
•	Because of some timing incompatiblity, I disabled the draw “speed” control. You can still see it inside the “draw_run” object, unconnected.
•	Speed at the tip of the sword is calculated (pd Reynolds) with v = 2* π * L * w where,
L =sword length and w = angular velocity
If you think you are rotating the sword 360 degrees in half seconds, it would be 120 rpm. 120 rpm = 2 Hz which may be the second argument of the above message (“freq. of swooshing”)


Objects
Draw_run : Execute drawing sound with a proper timing command (vline)   
	Draw_a : Users drawing model
	Draw_b : Opponents drawing model (I made them slightly different to follow easily)
		Swordd  : Model of the sword with some band pass filters
		Sword : Another sword model for different opponent, I did not used at the final model.
	Swosh_env : Includes necessary vline object 
Pd Reynolds : Calculates the Reynolds number. If Re<50000 , no swoosh sound. (Reynolds number is 2000 for internal flow (pipe, closed duct etc. but it is 50000 for external flow like sword or air flow over plate etc)
Pd swing:
	Swosh_run_a : Execute swooshing sound with a proper timing command (vline) for user
	Swosh_run_b : Execute swooshing sound with a proper timing command (vline) for enemy.
		Swosh : Swoosh model, few bandpass filters and oscillator
		Swosh_env_a/b : Timing of swoosh for user/enemy
	Pd fighttimer : Delays the opponents move (random 100 -500ms or 400-800ms): the second swoosh sound that you hear
I did not know that "message"s are not visible on graph on parent. Did not have time to fix the appearance
Hit : Model of hitting sound, it also have a ping metallic sound to represent the actual reverberation of the sword if there is an impact. (swordping ~)


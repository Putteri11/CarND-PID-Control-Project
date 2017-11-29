# Reflections

Here I will discuss the reflection topics listed in the rubric.

## Describe the effect each of the P, I, D components had in your implementation.

### P

When the coefficient `Kp` was increased, the vehicle turned more aggressively when it was driving in a turn, but also it would oscillate more whenever it did do a turn. This is pretty much what I expected to happen based on what I know about the coefficient in theory. 

### I

Based on my understanding of the component´ I kept the coefficient `Ki` small (at most `0.01`) throughout the project. When I did increase it, the vehicle would overshoot when it tried to correct itself while driving in a turn, but it wouldn't oscillate that much afterwards (although this overshooting process would happen multiple times while driving in a turn). 

I didn't understand this behaviour at first, but then I realized that this overshooting must happen in order to reduce the error `i_error` close zero again, since it is calculated as a sum of all the previous CTEs.

### D

As I expected based on my understanding of this component, when the coefficient `Kd` was increased, the vehicle would oscillate less and would usually converge to drive in the middle of the road. However, if the coefficient was increased too much, the vehicle would start to wobble around the middle of the road. My guess for why this happens is that the time steps in the simulator are quite coarse, so when this coefficient is too large, the vehicle moves to direction of the middle of the road a little bit too much in one time step and doesn't (literally) have time to correct itself in between, so it has to move in the direction of the middle again.

## Describe how the final hyperparameters were chosen.

I chose the parameters with manual tuning, because I found it was quicker to just do that instead of trying implement twiddle (or other similar) algortihm, since the simulation platform is so much different to what it was in the lesson. I managed to find reasonnably good parameters because I understood what each of the components should do, so I could adjust them accordingly, but fine tuning the paramteres could definitely make the vehicle's driving quite a bit smoother.




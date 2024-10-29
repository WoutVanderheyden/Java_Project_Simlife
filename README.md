# ObjectOrientedProgramming_Java_Simlife
In this project called simlife we ask you to implement
  (i.e., formally specify, implement, and unit test) a basic program
  simulating the evolution of species of point-like creatures.

**Here is a description of what this program does.**
  At each generation, a fixed number (in the demo, 1000) of creatures is spawned
    in a central square whose area is 1/4 of the simulation field.
    More precisely, each new creature is assigned a random position in that central square
    as well as a random orientation within the set of 8 cardinal directions
    {E, NE, N, NW, W, SW, S, SE}. Using vectors, the same set is represented as follows
    {(1,0), (1,-1), (0, -1), (-1, -1), (-1, 0), (-1, 1), (0,1), (1,1)}.
  By default, the program continuously computes and displays how each creature moves in the simulation field.
    
      At each tick, each creature of kind B (blue creatures) moves according to its orientation, only if the target position has no creature in it.
        In that case the target position is computed as TARGET = CURRENT + ORIENTATION.
        If the target position is not free, the creature does not move but its orientation is randomly (50%) turned clockwise or counterclockwise.
        For example, a blue creature that cannot move and that is pointing in
        the N orientation will either be pointing NE or NW at the end of the current tick.
        Once a creature reaches one of borders of the simulation field, it will remain stationary from then on.
      Creatures of kind A (red creatures) have a similar behavior with a crucial difference.
        The target position of each creature of kind A is computed as TARGET = CURRENT + ORIENTATION + DRIFT.
        The last summand DRIFT is a cardinal direction that is solely determined by the chromosome (in fact a list of integers)
        that the creature carries.
        Similar to creatures of kind B, if a creature of kind A has not moved, its orientation is randomly (50%) turned clockwise or counterclockwise.
 
  When the user presses the space bar, the program analyses which creatures “survived”, which we define as having reached
    the south-east ninth of the simulation field, in order to spawn the next generation of creatures.
    
      The proportion A/(A + B) of creatures of kind A in the next generation is the same as the proportion A/(A + B)
        of creatures of kind A,B that survive.
      Each new creature of kind A is assigned a chromosome c determined by looking at the parent generation.
        Specifically, c is the result of crossing over (combining) 2 chromosomes from the parent generation of creatures of kind A,
        and maybe applying a random mutation to that.
    
  After pressing the space bar several times,
    we see that more and more creatures of kind A survive. In fact no blue creatures remain at the end of the demo.
    Indeed, the proportion A/B tends to grow over time because
    creatures of kind A that survive are the only ones to pass their genetic information and this
    information correlates with the probability of survival.

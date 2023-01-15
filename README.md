# AI-FlappyBird

Description:
Flappy bird game with a NEAT AI that produces generations of offsprings that will learn itself how to play the game by increasing and decreasing its fitness value based on the desirability of the action.


Demo:


https://user-images.githubusercontent.com/70008295/212560994-b9afe383-dfb4-4f72-b6e5-dbe7321343f8.mp4


NEUROEVOLUTION OF AUGMENTING TOPOLOGIES (NEAT) AI to Flappy Bird:
The NEAT AI emphasizes the use of Neural Evolution (NE) which uses artificial evolution of neural networks to optimize reinforcement of learning tasks. In order to generate good neural networks, we need good inputs. Good inputs mean valuable information that the AI needs to know in order to pass on to the next offsprings. For our flappy bird game, good inputs include the position of the bird, top pipe, and bottom pipe. Our outputs will be the response to the inputs which would be the bird jumping in order to climb up and down its position.
For our NEAT AI, we also need to set the population size. The population size refers to the population of the neural networks that we will start with in each geneartion. For example, if the population size is 100 for the flappy bird game, then we will have 100 birds, or neural networks, that will the play the game. We will select the best birds out of the 100 birds and mutate them, breed them, and create another set of 100 birds (neural networks) that will play for the next generation.
The next question that would naturally come out is how do we define "best" birds? To answer this question, the NEAT AI came up with fitness functions which are ways to calculate whether the birds acted in a desirable fashion or not. In the flappy bird game, the best way would be to compare which  bird went furthest without crashing on the pipe. 

If the bird crashes, we would decrease the fitness value of that bird

'''
if(pipe.collide(bird, win)):
                    ge[x].fitness -= 1
                    birds.pop(x)
                    nets.pop(x)
                    ge.pop(x)
'''

If a new pipe is generated, it indicates that the bird successfully passed the previous one

'''
if add_pipe:
            score += 1
            for g in ge:
                g.fitness += 5
            pipes.append(Pipe(600))
'''

The birds with the higher fitness values will be selected to be breaded and mutated to create the 100 offsprings for the next generation.



Reference:
https://nn.cs.utexas.edu/downloads/papers/stanley.cec02.pdf
https://neat-python.readthedocs.io/en/latest/config_file.html
https://www.youtube.com/watch?v=MPFWsRjDmnU

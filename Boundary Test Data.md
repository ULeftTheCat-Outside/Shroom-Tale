# Boundary Test Data

Health: \-1, 0, 101

Health: the character’s health meter bounds  
\----------------------------------------------------  
| Boundary Input | Why It’s a Boundary              |  
|----------------|----------------------------------|  
| \-1            | Cant have a negative health      |  
| 0             | at 0 the game should end/ have the player restart|  
| 101           | Can’t have more than health allows |

| Boundary Input | Test Data Example |

\--------------------------------------

| \-1          | player HP \= \-1     |

| 0           | player HP \= 0      |

| 101         | player HP \= 101    |

*  What SHOULD the game do?  
  * The game should end when the health reaches 0\.  
* What would break if the game handled this incorrectly?  
  * The player won’t die and be immortal.

| Boundary Input | Test Data | Expected Outcome |

\-------------------------------------------------

| \-1      | HP \= \-1      | should not be able to do that. |

| 0       | HP \= 0      | End the game and make player restart  |

| 101      | HP \= 101  | Should not have that. Have a cap at 100   |

Timers; \-1, 0, 61  
Timer : for timed challenges. Cant go beyond the set timer.  
\----------------------------------------------------  
| Boundary Input | Why It’s a Boundary              |  
|----------------|----------------------------------|  
| \-1           | can’t go beyond the time lotted    |  
| 0           | At 0 the challenge should end       |  
| 1           | should act as should and count down with the challenge going|  
 

| Boundary Input | Test Data Example |

\---------------------------------------

| \-1          | Timer hits \-1    |

| 0           | timer hits 0     |

| 1           | timer hits 1     |

*  What SHOULD the game do?  
  * Timer should END at 0 and not go beyond that.  
* What would break if the game handled this incorrectly?  
  * The challenge wouldn’t end

| Boundary Input | Test Data | Expected Outcome |

\-------------------------------------------------

| \-1  | timer hits \-1     | shouldn’t happen                  |

|  0  | timer hits 0      | ends challenge                    |

|  1  | timer hits 1      | keep counting down till reaches 0 |

Collision checks  
Collision checks: To make sure the character should get hit when collided with enemy  
\----------------------------------------------------  
| Boundary Input | Why It’s a Boundary              |  
|----------------|----------------------------------|  
| overlapping pixels  | should take damage           |  
| few pixels away from player mesh | no damage       |

| Boundary Input | Test Data Example |  
\---------------------------------------  
| overlapping pixels   |  |  
| few pixels away from player mesh   | the sword away from player |

*  What SHOULD the game do?  
  * When pixels of the enemy overlap with the character’s pixels then the player should take damage.  
* What would break if the game handled this incorrectly?  
  * The player might not get damaged or get randomly damaged.

| Boundary Input | Test Data | Expected Outcome |

\-------------------------------------------------

| overlapping pixels | enemy sword overlapping character mesh |    take damage              |

|  few pixels away from player mesh  | the sword away from player      | dont take damage                |

* Which logic point feels most fragile?  
  * timer  
* What will I need to watch out for when coding this?  
  * collison  
* Which boundary case surprised me?  
  * health


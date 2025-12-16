Testing Plan — 

1\. Overview  
This document compiles User Stories, Boundary test, and how to test the features they want. It will go over the requirements, purposes, test cases, and what the expected results are to be. We will work with 3 User Stories: getting games to run on Ps5, having more challenging bosses, and changing the battle difficulty.

\---

2\. User Stories and Acceptance Criteria

User Story 1: As a Ps5 player, I want to be able to play on ps, so that I can play as comfortably as possible.

\- Acceptance Criterion 1: The game is able  to be downloaded on Ps5.

    \- Requirement(s):Let the game run on Ps5.  
    \- Purpose: so that Ps5 players can play on Ps5.  
    \- Test Case:  
        a) Feature:There be an icon on Ps5 and clicking on it will activate the game  
        b) Test: Click on the game and see if it runs without crashing.  
        c) Expected Result / Behavior: The app opens and the game runs.  
        d) Automation Candidate: Yes, Start program and if it fails then log the incident.

\- Acceptance Criterion 2 The game responds to Ps controller inputs.  
    \- Requirement(s): Let the game support the Ps5 controller.  
    \- Purpose: If the game is to run on Ps5 the controller input needs to be accepted.  
    \- Test Case:   
        a) Feature: Ps5 controller inputs added  
        b) Test: click triangle to dodge, circle accept quests, square block, x jump, and use the joysticks to move around.  
        c) Expected Result / Behavior: when clicking buttons they should act according to the movement set it is assigned to.  
        d) Automation Candidate: no, needs human input.

User Story 2: As a hardcore player, I want there to be more challenging bosses, so I can challenge myself.

\- Acceptance Criterion 1 : After defeating the boss in the story they can revisit and select a difficult level causing them to send them to the battle ground and have the boss respawn.

    \- Requirement(s): Reload boss with changeable difficulty levels.  
    \- Purpose: To satisfy the people that like to refight bosses.  
    \- Test Case:   
        a) Feature: get to refight bosses at a specific location  
        b) Test: go back to the boss area and see if you can challenge them again and change the difficulty level.  
        c) Expected Result / Behavior: when lowering/raising difficulty the amount of damage the boss deals and the health bar lowers/raises.  
        d) Automation Candidate: no, need human input.

\- Acceptance Criterion 2: When selecting challenging bosses to up their health bar, increase their attack and add in new attack sequences to be less predictable and harder to counter.

    \- Requirement(s): new boss attack sequence, bigger health bar, increase attack damage  
    \- Purpose: to be less predictable and harder to defeat  
    \- Test Case:  
        a) Feature: new boss attack sequence, bigger health bar  
        b) Test: have someone fight the boss at a higher difficulty than normal  
        c) Expected Result / Behavior: new boss attack sequence, bigger damage taken when hit, and bigger hp  
        d) Automation Candidate: no, need human input.

User Story 3: As a casual player, I want to be able to change the difficulty level of enemies, so I don’t feel frustrated when battling. 

\- Acceptance Criterion 1 Put an option in the menu to change the difficulty.  
    \- Requirement(s): add an option to change difficulty in the menu.  
    \- Purpose: for the casual players that aren’t that good at fighting that much  
    \- Test Case:  
        a) Feature: a button in the menu to change the difficulty   
        b) Test: go into the menu and change the overworld difficulty  
        c) Expected Result / Behavior: the overworld should get easier or harder depending on the difficulty selected.  
        d) Automation Candidate: no, need human input

\- Acceptance Criterion 2 :  When the enemies attack it does less damage, slower, and has a lower health bar.

    \- Requirement(s): change the enemies damage, health bar, and movement speed.  
    \- Purpose: that when you decrease the difficulty you can see how it changed.  
    \- Test Case:  
        a) Feature:change the enemies stats  
        b) Test: when you lower the difficulty the enemies should noticeably become slower, deal less damage, and have smaller health bars.  
        c) Expected Result / Behavior: the enemies have become slower, deal less damage, and have smaller health bars  
        d) Automation Candidate: no, need human input.

\---

3\. Boundary and Edge Testing

Boundary / Edge 1:  health  
    \- Requirement(s): can’t go below 0 or above 101  
    \- Purpose: to not let the player be immortal.

    \- Test Case 1:  
        a) Upper Boundary: 101  
        b) Testing data used: \< 100- 1 , 100, 100 \+ 1 \>  
        c) Expected Result / Behavior:100-1 \= 99 take only 1 hp, 100+1 wont do anything, it should stay at 100\.  
        d) Automation Candidate: yes

    \- Test Case 2:  
        a) Lower Boundary: \-1  
        b) Testing data used: \< 0 \- 1 , 0, 0 \+ 1 \>  
        c) Expected Result / Behavior: 0-1 cant happen since the player should already be dead, 0 the play should die, 0+1 should happen since the player should be forced to restart  
        d) Automation Candidate: yes

Boundary / Edge 2:  timer  
    \- Requirement(s): make sure the challenge ends when it hits 0 and cant go beyond it.  
    \- Purpose: to make sure the time challenge is a time challenge

    \- Test Case 1:  
        a) Upper Boundary: 60  
        b) Testing data used: \< 60- 1 , 60, 60 \+ 1 \>  
        c) Expected Result / Behavior:60-1=59, 60 is when the challenge just started, 60+1 shouldn’t happen.  
        d) Automation Candidate: yes

    \- Test Case 2:  
        a) Lower Boundary: \-1  
        b) Testing data used: \< \-1 \- 1 , \-1, \-1 \+ 1 \>  
        c) Expected Result / Behavior:-1-1 should happen since the timer should end at 0, \-1 the challenge should be over, \-1+1 shouldn't happen.  
        d) Automation Candidate: yes

Boundary / Edge 3:  collision check  
    \- Requirement(s): check if pixels are overlapping or not  
    \- Purpose: to see if the player should take damage or not.

    \- Test Case 1:  
        a) Upper Boundary: enemies pixels overlap player’s pixels  
        b) Testing data used: \< player pixel location \- enemy pixel location, player pixel location, player pixel location \+ enemy pixel location \>  
        c) Expected Result / Behavior: if pixels overlap then player takes damage, if they dont then dont take damage.  
        d) Automation Candidate: no

    \- Test Case 2:  
        a) Lower Boundary: pixels not overlapping  
        b) Testing data used: close to player pixels, not close  
  c) Expected Result / Behavior: if they don’t overlap then no damage should be taken  
        d) Automation Candidate: no

\---

4\. Automated Test List  
Which tests were candidates for Automation?  Start game on Ps5 to see if crashes, all boundary tests except for if the pixels are overlapping  
For each candidate, which kind of automated testing is recommended:    
repetitive, rule-based, or high-volume?  
Start game: repetitive  
Boundary test: rule based
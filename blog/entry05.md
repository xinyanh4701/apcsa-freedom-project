# Entry 5
##### 5/6/24

### Progress

For this blog, I worked on the AI patrol for the most of of time doing the freedom project. On the other hand, Aron was working on reloading, weapon bobbing, and the med kit. For the AI patrol, I followed [Natty GameDev](https://www.youtube.com/watch?v=Mp8yFUKxldk&list=PLGUw8UNswJEOv8c5ZcoHarbON6mIEUFBC&index=6)'s AI patrol tutorial. Fortunately, the scripts didn't give me much issue. The reason the scripts weren't compiling correctly was because of the typos that I made. However, I did encountered conflict merges. When I tried to `git push`, Aron already pushed something meaning I had to `git pull` before I can push my changes. When I `git pull`, a merge conflict appears which I talked to Aron on discord about the merge conflict. We weren't sure what the merge conflict was, so we accept the incoming changes. This made my progress gone which took extra hours to get back the changes that I made.

Here's the code that makes the AI patrol:
```c#
public void PatrolCycle()
{
    //implement our patrol logic.
    if(enemy.Agent.remainingDistance < 0.2f)
    {
        waitTimer += Time.deltaTime;
        if(waitTimer > 3)
        {
            if(waypointIndex < enemy.path.waypoints.Count - 1)
                waypointIndex++;
            else
                waypointIndex = 0;
            enemy.Agent.SetDestination(enemy.path.waypoints[waypointIndex].position);
            waitTimer = 0;
        }

    }
}
```
For the second `if` condition, when the enemy waits for more than 3 seconds, the enemy will immediately go straight to the next destination point. Since the `waypoints` are numbered, the enemy would go to the next `waypoint` with the next number. When the enemy goes to the last `waypoint`, that is where the `else` condition comes in. The enemy will move to the first waypoint and this repeats continously until the enemy gets killed. The line, `enemy.Agent.SetDestination(enemy.path.waypoints[waypointIndex].position);` tells the enemy to go to the poisition of a specific `waypoint`. The `waitTimer` resets the time of the enemy standing on a `waypoint`.



#### Before
<p align="center">
<img src="img/apcsa-freedom-project-lighting-issue.png" width="70%">
</p>

https://github.com/xinyanh4701/apcsa-freedom-project/assets/91750651/528cfd33-e901-4c3c-93b4-8ddd254cb462



#### After
<p align="center">
<img src="img/apcsa-freedom-project-lighting-fixed.png" width="70%">
</p>


### Engineering Design Process (EDP)
Right now, my partner and I are on **stage5** of the EDP which is to *test and evaluate the prototype*. I also think that we are on **stage 6** of the EDP as well which is to *improve as needed*. My partner and I are still testing our creations to make sure there is no glitch. At this point, we are techincally beyond our MVP. Since we still have time for the Expo, I don't think we will be communicating our results any time soon.

### Skills

Skills-wise, I am improving on

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)

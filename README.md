# City Simulation

![Alt Text](city_sim_gif.gif)

## Overview
This simulation models a company hiring system where companies make hiring and firing decisions based on worker productivity and economic factors. Workers have varying productivity levels, and companies adjust wages and prices to optimize their workforce and profits.
### Algorithm
The main algorithm driving this simulation is the hiring system. Key points include:
#### Worker Productivity:
Each worker is initialized with a random productivity level between 20 and 30. Productivity diminishes as more workers are added to a company. This is handled in the diminishMargProd method in the Company superclass, where a worker’s productivity is reduced by their index number in the employee list.
#### Worker Value:
A worker’s value is calculated as:
worker value = productivity * employer’s product price
This value is used to determine hiring decisions.
#### Hiring and Firing:
Companies decide whether to hire additional workers by comparing the value of the employee with the highest index to the current hourlyWage. If the value exceeds the wage, the hiring flag is set to true; otherwise, it is false (checkWorkerProductivity() in Company).
Companies fire workers whose productivity falls below the hourlyWage (checkInval() and fireWorkers() in Company).
Companies adjust wages and product prices to manage hiring:
Lowering wages to afford new hires (setWage() in Company)
Raising product prices to balance hiring capacity (setPrice() in constructionCompany and deliveryCompany subclasses)
#### Worker Job Switching:
Workers evaluate companies offering higher wages in the checkJobs() method (Worker class). If another company offers more, they quit their current job and move to the higher-paying employer.
#### Supply and Demand Pricing:
Prices adjust dynamically based on demand. For example, a constructionCompany raises prices when client demand is high and lowers them when demand is low (setPrice() method).
### Known Bugs
Workers sometimes stop moving temporarily; this usually resolves itself automatically.
The real estate company’s building (brick building in the center) does not always display all workers who are home at nighttime.
### Contributors
Dolaniyi – debugging and collaboration
### Time Investment
I spent several hundred hours on this project and am very proud of the outcome. I hope you enjoy exploring it as much as I enjoyed building it!

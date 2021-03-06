# OOTD - Out Of The Dumps

Recently, there was a reddit article on how a person decided he had reached the lowest point in his life and what he did to get *Out Of The Dumps*.
Essentially, it was a post detailing all the things he did to get back on the horse.
It was mostly a motivational post that detailed how he kept track of all the things he did in his life. It spoke about how to build habbits and train oneself to become better at keeping them. It's not a new concept but it helped me do a lot better with my days.

Part of the process was keeping track of our daily habbits. The OP had mentioned that he kept a bullet journal that was colour coded where he tracked his daily activities and weather it kept up to his habbit forming guidelines. 

For example, if one targets to drink 4ltr of water daily, and managed to only consume 2 litres, he would record it under a red bullet etc.

The purpose of this project is to build a very simple tool that would help me to keep these tabs for myself through a mobile app. I have also procrastinated learning programming in Golang. I thought this project would be a great way to build a full-fledged microservice architectured project as the backend and a VERY simple android layout for the same in an attempt to learn the language a bit better than I know right now.

Now, I hate android development from the bottom of my soul from it's first incarnation of a ameobea some 7 million years ago but I truely hope this project will change my perception of it. So here goes!

[Here's a link to the original post!](https://www.reddit.com/r/getdisciplined/comments/9t0gqz/method_how_i_went_from_rock_bottom_to_disciplined/)

## High-level usage scenarion:
The user will have a list of mandatory fields such as sleep times, water consumed, workout, screen time, hourse wasted etc. Additionally, they can add any hobbies that they wish to pursure such as read, write, play bass etc. All these come with a configurable minimum and maximum limit. The user will be trusted with making these entries daily. Given this information, we will define Key Performance Index (KPI) that will give an overview of the daily data at a glance. A simple example KPI would be Workout vs. Water Consumed. The KPI will calculate how much water you consumed on days that you worked out vs. the days you didn't. If isn't in propertion, the KPI will indicate poor. The possibilities are endless! Apart from this, we will generate a weekly report on how your week has been. It will be a simple report that will let you see your week prgress at a glance and make better life decisions.

## Technologies I hope to use:
- Infrastructure: GCP Engines, docker, Kubernetes
- Database: Cassandra? Maybe Postgres, lets see. Depends on how relational I'm feeling :P
- Language: Pure Go
- Configuration Management Tool: Ansible
- Load Balencer/API Gateway: Nginx, what else?
- Android App: I've idea where to even start, will learn
- Would I need a message queue? Kafka, if so

## Highlevel Backend:
All microservices will be RESTful
- User Service: API's on users. Create, Update, Get etc on users as well as the tasks they wish to track
- Auth: Maintain simple auth tokens (JWT)
- History: Time sereis DB to track history of each activity on a daily Basis
- Activity: Add/delete/update activities and their limits, example, "drinkwater no less than 4ltrs per day", or "playbass no less that 20 minutes", "sleep for x hours"
- Insight: Visualise all this data for a user. This will have various KPI's and will help keep an overviwed track of everything.

## Possible enhancements:
- Add a configurable reminder service. Essentially, you can configure this to remind you to hit the gym, drink water, etc etc.
- Consolidate with Mi fit to auto-extract more relevant sleep cycles

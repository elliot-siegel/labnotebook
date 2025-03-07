<img width="189129387" alt="Screen Shot 2023-05-05 at 2 04 40 AM" src="https://user-images.githubusercontent.com/89604161/236387225-d58a367c-4a97-4f7c-b819-a044ff157efd.png">

<h1 align=”center”> 🤖🤖 Guard Robot (by Liulu Yue, Rongzi Xie, and Karen Mai) 🤖🤖🤖 </h1> 


<h3 align="left-center ">
Introduction 
</h3> 

<p>
For our team's COSI119a Autonomous Robotics Term Project, we wanted to tackle a challenge that was not too easy or not hard. All of our members have only recently learned ROS, so to create a fully demo-able project in 8 weeks sounded impossible. We started off having a few ideas: walking robot that follows an owner, robot that plays tag, and a pet robot that accompanies one. There were a lot of blockers for those ideas from limitation of what we know, tech equipments, time constraints, and mentor's concern that it will not be able to. We had to address issues like: 

In the end, we decided to work on a robot that guards an object and stop an intruder from invading a specified region. We pivoted from having one robot to having multiple robots so that they are boxing out the object that we are protecting. We tested a lot of design decisions where we wanted to see which method would give us the desired result with the most simple, least error prone, and high perfomring result.  

There were a lot of learnings throughout this project, and while even during the last days we were working to deploy code and continue to test as there is so much that we want to add.  
</p>


◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾
<h3 align="left-center ">
Proposal Breakdown 
</h3> 
<p>
As we will be approaching this project with an agile scrum methodology, we decided to take the time in developing our user stories, so that at the end of the week during our sprint review we know if we are keeping us on track with our project. After taking a review of the assignment due dates for other assignments of the class, we thought that having our own group based deadlines on Friday allows us to make these assignments achievable on time. Below is a brief outline of our weekly goals.
</p>

Here is a ⏰ timeline ⏳ , we thought were were going to be able to follow:
- March 3: Finish the Movie Script That Explains Story of Waht we want to do and Proposal Submission
- March 10: Figure out if tf can be done in gazebo
- March 17: Run multiple real robots
- March 24: Detect the object
- March 31: Aligning to be protecting it - circle or square like formation
- April 7: Detecting if something is coming at it
- April 14: Making the robot move to protect at the direction that the person is coming at it from 
- April 21: Testing
- April 28: Testing
- May 3: Stop writing code and work on creating a poster
- May 10 Continuing to prepare for the presentation

<img width="866" alt="Screen Shot 2023-05-05 at 2 09 55 AM" src="https://user-images.githubusercontent.com/89604161/236387884-c02bf777-ca33-4b76-8e44-d82aee0286e1.png">




Here is a timeline of what we actually did: 
- March 3: Finished all Drafting and Proposal - Submitted to get Feedback and Confirmation That it is Good To Go (Karen, LiuLu, Rongzi)
- March 10: Figure out if tf can be done in gazebo (Rongzi), Creating Github Repo (Karen), Drawing Diagrams (Liulu), Explore Gazebo Worlds - Get Assests and Understand Structure (Karen)
- March 17: Run multiple real robots on Gazebo (Karen), Created multi robot gazebo launch files (Karen), Explored different approaches for patrolling: circle around object, Fiducials, line following; decided to use line following as basic approach (whole team), Wrote Code on Patroling Line (Liulu), Create box world (Rongzi), Make Behavior Diagram (Karen)
- March 24: Continue to write code on patroling the line for multirobot (Liulu), Explored fiducials to integrate (Karen), Made better Gazebo world (Rongzi)
- March 31: Designed DFA for project (Liulu), Decide to let each robot patrolling along one line segment, Aligning to be protecting it - circle or square like formation
- April 7: Detecting if something is coming at it
- April 14: Making the robot move to protect at the direction that the person is coming at it from 
- April 21: Testing
- April 28: Testing
- May 3: Stop writing code and work on creating a poster
- May 10 Continuing to prepare for the presentation
<img width="876" alt="Screen Shot 2023-05-05 at 2 11 27 AM" src="https://user-images.githubusercontent.com/89604161/236388088-48d3e45f-4730-4905-a425-b9b0c724456b.png">






◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾◾


<h3 align="left-center ">
Preliminary ❓ Questions ❓ Answered 
</h3> 

<p>
To address blockers, we had to start asking ourselves questions and addressing issues like: 
</p>
  1. What are the major risky parts of your idea so you can test those out first?
  2. What robot(s) will you want to use?
  3. What props (blocks, walls, lights) will it need? 
  4. What extra capabilities, sensors, will your robot need? How you have verified that this is possibler?
  5. And many other questions.



<img width="869" alt="Screen Shot 2023-05-05 at 2 07 59 AM" src="https://user-images.githubusercontent.com/89604161/236387641-64ae5517-e94b-458e-96f5-45cf3b1a56e1.png">

<img width="871" alt="Screen Shot 2023-05-05 at 2 08 23 AM" src="https://user-images.githubusercontent.com/89604161/236387687-3db63abd-7a1f-4b99-bf9b-e0eb7919179b.png">

<img width="867" alt="Screen Shot 2023-05-05 at 2 08 38 AM" src="https://user-images.githubusercontent.com/89604161/236387702-5f45fd65-3292-486a-a432-63d087863e19.png">

<img width="860" alt="Screen Shot 2023-05-05 at 2 08 55 AM" src="https://user-images.githubusercontent.com/89604161/236387738-02f57a87-d7fc-4e17-86da-de20153979b9.png">


<img width="201" alt="Screen Shot 2023-05-05 at 1 59 55 AM" src="https://user-images.githubusercontent.com/89604161/236386699-5cd0786c-072b-4923-a3b7-9c81ec59f60d.png">

<img width="201" alt="Screen Shot 2023-05-05 at 2 00 16 AM" src="https://user-images.githubusercontent.com/89604161/236386744-9d3376ba-ccf9-47d9-aa38-146439e3abc5.png">

<img width="201" alt="Screen Shot 2023-05-05 at 2 01 08 AM" src="https://user-images.githubusercontent.com/89604161/236386843-1e1213ea-7d07-4572-9e42-21d70f66b5e5.png">

<img width="201" alt="Screen Shot 2023-05-05 at 2 01 36 AM" src="https://user-images.githubusercontent.com/89604161/236386897-4cd7db0a-76ce-4aaf-807e-4d2b731fed24.png">

👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻👩‍💻

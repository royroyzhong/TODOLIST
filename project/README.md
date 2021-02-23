# My Personal Project

## Todo list application 

#### What will the application do?  

 This todo list is **task management** designed to keep track of **day-to-day** events that makes it easy to stay organized and manage your life. Users can add an event to our task board and set an alert to remind the event. When users finished one task, they can cross the events, and the events will move to completed categoria. If users want to see the past event, they can find it on Completed. There are many ways to sort event. For example: by the due date, by created day, by priority, or by alphabetically. Users also can visualize the events in the calendar model, so they can easily see what things are coming up just by a glance. This application will automatically set the due day for an event if the event contains "due" in it, or users can manually set the due day.

#### Who will use it?
 This application fits for students if they don't want to miss any important day for the assignment and test, even some self-study plannings. Also, for the people who want to be self-organised, this application will best work for them.

#### Why is this project of interest to you?
 I am interested in the todo application because the all todo application which are published now, they are somehow not user-friendly. Some applications are not flexible to keep track of events, and some are not efficient, and some are not visually. Hence, I want to build an app that is friendly for users, efficient, and visualized. 
 
 ## User Stories
 
- As a user, I want to be able to add a task event to the task board, so that I can keep track of my event.
 
- As a user, I want to be able to remove a task event from the task board, so that I can remove a event when I finished it.
 
- As a user, I want to be able to set the due day of that event ahead, so that I can know see when will be the event is finished.

- As a user, I want to be able to set the due day manually, so that I can change the due day.

- As a user, I want to be able to sort the list of task, so that I can see the events are coming up in different order.

- As a user, I want to be able to see my completed task, so that I can see event in the past.

- As a user, I want to be able to save my to-do list to file.

- As a user, I want to be able to optionally load my to-do list from file when the program starts.

## Instructions for Grader:
- You can generate the first required event (add task to task board) by click the "Add" button. What you enter in the "Enter your task" box
will be added to the task board below.

- You can generate the second required event (add priority to a task) by select one of the task in the task board, then click "set priority"
button. Then you can click the "priority sort" button, which sort the task in the priority order.

- Note: All the tasks in JSON file do not set any priority, and the due day is the day that user create it. 
For example, if you click "load" button, it will load task with no priority and if today is Mar 16, then the due day is Mar 16.   



- You can generate the 3th required event (add due day to a task) by select one of the task in the task board, then choose the month and day.
After then, clicking "set due day" button will added due day for the task. Then you can click the "Due day sort" button, which sort the task
in the due day order.
 
- You can trigger my audio component by click the "save" or "load" button on the button. On the button screen, there are three buttons, the left one is "save" button.
the middle one is "load" button.

- You can save the state of my application by click the "save" button, which will save the current task board into JSON file.

- You can reload the state of my application by click the "load" button, which will load the tasks into task board.

 
## Phase 4: Task 2
-  Test and design a class that is robust.  You must have at least one method that throws a checked exception.  You must have one test for the case where the exception is expected and another where the exception is not expected.

- I added exception, invalid input and TaskBoard empty exception.

- On the TaskBoard class, I robust completedTask, sortByPriority, sortByAscOrder, and sortByDueDay method. The sortByPriority, sortByAscOrder, and sortByDueDay methods
were in the TaskBoard before, but now sortByPriority method is in RankingByPriority Class, sortByAscOrder is in RankingByArc Class, sortByDueDay is in RankingByDueDay Class.
RankingByPriority, RankingByArc, RankingByPriority extends Ranking, and the method name change to taskBoardSort.
And the completedTask method still in the TaskBoard class.

- For completedTask method, I make a if condition to check validation of the input, if it is valid, it will follow what it supposed to do. If not, it will
  throw a invalid input exception.
  
- For sortByPriority, sortByAscOrder, and sortByDueDay method, I added checking to see if the current TaskBoard is empty or not.
  If the taskBoard is empty, then throw emptyException.

## Phase 4: Task 3

- On the TodoScreenFront class, which lets User interact with the todo list. It was a dependence relation that from TodoScreenFront to TaskBoard, which is unnecessary. So, I design it.
For now, the TodoScreenFront will get the taskBoard from TodoOnScreenBack. By doing that, it will deceasing the level of coupling.

- On the TodoScreenFront class, there was a method class called playSound, which seems to does not belong here, it seems to belongs
    to TodoScreenBack class. I move it to TodoScreenBack class, so it will increase the level of cohesion by that. 
    
- On the Task class, I have a override method for compareTo, which seems do not belongs to this class. I removed it to RankingByArc class, which increases
the level of cohesion.

- On the taskBoard class, I have three methods to rank the tasks. It can apply to the open closed principle. So, I made an abstract class Ranking with an abstract method in  the ranking package. The three ranking method extends Ranking class, and 
override the taskBoardSort method.

Note: UML_Design_Diagram.pdf is the uml diagram
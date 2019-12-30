# User requirements

A complete list of user requirements that can be implemented. In the interest of time, not all functionality will be implemented.

## Primary user groups

### Persona 1

**Background**: Lisa Trevolta, aged 42, is a housewife with three kids, living in Singapore. She often wakes up early to prepare breakfast and fetch her kids of secondary school age to their school. During the day, she would either go grocery shopping at the nearby wet market, or spends the afternoon cleaning their house. She also attends Spanish classes every Tuesday and Thursday evening at downtown, during which she would prepare dinner in advance for her husband and kids.

**Motivation**: Lisa has always been using a physical planner to keep track of her schedule and expenses, but feels that it might be a little inconvenient carrying it around. The items of her grocery is detailed on that particular day, which makes consolidating the list a hassle prior to her grocery shopping. She also wants to be able to keep track of her regular commitments so that she remembers what to do during those times.

**Familiarity with technology**: Able to perform a Google search for groceries on her phone. Does not own a computer.

**Design requirements**:
+ Accessible on a phone screen, highly automated
+ Create seperate lists with recurring items (or tagged items)
+ Filter items of a specific tag
+ Add notes to individual items
+ Basic NLP to recognise different inputs, e.g. dates

### Persona 2

**Background**: Loh Chengyong is a year 1 university student studying Sociology in NUS. He loves gaming, currently hooked onto Overwatch and Borderlands 2. He stays in Raffles Hall and often goes out for late night supper and makes time to study between his classes at FASS. On weekends, he heads home to visit his parents and grandparents.

**Motivation**: Chengyong has not been coping too well with the academic stress. He wants something that can help him manage his assignment deadlines as well as his lessons in school, which can vary between one to three hours. He wants to be able to see all his assignments at a glance, sorted by date, tag and priority, to get an overview of his academic commitments.

**Familiarity with technology**: Very comfortable with the use of his laptop, uses it almost exclusively. No issues with using the internet.

**Design requirements**:
+ Create tasks with durations
+ Has a calendar and agenda view
+ Sorting and filter feature for tasks across lists
+ Recurring tasks

### Persona 3

**Background**: Stephanie works for HSBC as a financial consultant. She constantly keeps track of her schedule with clients and meets them at the comfort of their houses. On other days, she attends meetings at her office. Outside work, she is a foodie who loves visiting different parts of Singapore to try out food, and loves sharing her opinions on them.

**Motivation**: Stephanie wants to be able to stay on top of her schedule, by integrating her todo list and calendar. She wants to be able to keep track of her thoughts on food that she has tried before, and incrementally add more opinions on them as she tries different dishes.

**Familiarity with technology**: Highly proficient with technology, uses her phone and workstation often to schedule tasks.

**Design requirements**:
+ Has a calendar view to see availability
+ Create items with assigned timeslot
+ View past completed items within same view
+ Search functionality
+ Add notes to tasks
+ Automatically sync data between different devices
+ Possibly specify location of tasks, integration with navigation software
+ Optionally duplicate tasks

### Use cases

Use cases are textual descriptions of all the ways the user could interact with the system and show the steps that a user follows to perform a task. The use cases should address the stated requirements. Each use case describes scenarios of how users might interact with the system, but do not describe the internal workings of the system or how it will be implemented.

## Additional requirements

+ Login interface for different users
+ Multiplatform (phone and laptop, application can be designed to work on uniform, slender interface)
+ Auto-saves, uses atomic update to ensure date integrity across platforms

## Use case

### Create account

Users register for a user account with name, password and email. Upon account creation via email confirmation, an account is created for the user to login.

### Create task

Once logged in, the user will see their homepage with all tasks sorted chronologically. An empty text field on the top of the window prompts the user to select it, which opens a host of options for user to select.

1. The text field provides the space for the user to enter a one-liner task.
    + NLP is also provided for dates, priority, tags and notes as a one-liner comment.
2. Several buttons are available for additional information:
    - Datetime:
        + The todo prompts the user to specify start date and time. Start date defaults to the current date and is presented in a calendar view, with the year as a selectable button to change year. Time can also be specified using the round clock. If time is specified without the start date, the date is taken to be the current day.
        + If start date or time is selected, end date and time is also prompted.
        + Repeat options are also presented, with the ability to specify the end date of the repeat as well as the frequency with which it repeats (e.g. number of days), or the days on which they repeat (i.e. Monday to Friday).
    - Priority:
        + A dropdown menu to select the priority level is provided.
    - Tags:
        + A text field to type the tag is provided, with a dropdown list of the three most recent tag used.
    - Notes:
        + A multiline text field is provided for the user to add notes.
3. Upon pressing the confirmation button (or upon pressing enter), the task is created and immediately populated in the task list.
    + Alternatively, a cancel button is provided to cancel input, preferably far from the enter button at the bottom left.

Once created, the task is automatically saved.

### Edit task

The user selects the task on the list, and the same interface as task creation appears, the exception being the add button now transformed into a checkbox button, and the cancel button is accompanied with a delete task button.

### Search tasks

A search button is provided above the add task field, where a text field will appear and prompt the user to type. The header text to the left of the search field will indicate that it is a search rather than the default view.

### Filter tasks

A button to filter tasks by multiple criteria, including priority, tags, name and start datetime (or no date) is provided. Option to show completed tasks together with upcoming tasks, or separately.

### Sort tasks

A dropdown menu appears upon selecting the sort task button, which allows the user to sort singularly according to tag, priority, and chronologically. If the list of tasks in specific header extends beyond a set number of items, a view more button is provided at the end of the list to show more entries.

### Complete task

As simple as hitting the checkbox, and the task will disappear. A prompt is flashed on the top of the screen with an undo button in case the completion was made by accident.

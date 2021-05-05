2021-04-27T12:44:26
- talking with lennart johansson (re: notebook), he does something simillar to me with plain text and git! he might like what i want to build
- need to sync this with tim
- possible input in Personal Diary 2021-04-26

2021-05-02
- chatting with Daniel Kertby and sharing progress
  - Been a while! But I’m playing with a node.js/vue.js (wrapped in electron) UI using TinyMCE as the markdown WYSIWYG editor
  - I’m also trying local NLP to pick up tasks, todo’s etc from plain text and also guess where the note should be filed (using ML) - the underlying concept being similar to something like iTunes; notes inherently are not categorized (they they can be) - you use filters of metadata to create dynamic notebooks and notes can be in one or more notebooks (or views)
  - Lastly - bridging the analog/digital domain in two ways
1) using my Wacom bamboo which digitizes handwriting direct to svg
2) taking photos of post-it’s

The handwritten notes are parsed in an OCR library then NLP to extract keywords as metadata and fed into the same backend process
  - Some open questions
1. Storage (db; files; both)
2. UI/UX (how to get everything on the screen in one app!)
3. How to get something working with off the shelf components and the least amount of dev necessary! 😂

Of course, a tag on notes determines if the note should be synced or not; no sync is the default unless otherwise specified

  - The essential new parts are
- handwritten notes stay handwritten, but are searchable (to the extent your handwriting can be recognized)
- where there is doubt on auto parsing it’s held for review
- natural language can be used - so for example “must remember to pick up milk” can be detected

I feel like NONE of this is new; but no tool exists that does it...

To make the auto processing of handwritten notes easier abs more reliable I was working on a series of boxes on a note with each equating to a tag; coloring in the box applies the tag

Indeed. Having suffered with organization and note taking it’s a project for me of necessity - but also why I would rather reduce the development effort
I’m still drawn to git in the background for its file versioning - delta encoding and diff being powerful tools

I feel like we’ve come full circle - in the 70’s and 80’s you needed to really understand the HW and there was a skill in extracting performance and making awesome software on constrained devices
The 90’s/2000’s you had ample CPU and RAM and you really didn’t have to care about efficiency - Java is a good example or even our tendency to run so much production code on interpreted languages like JS and Python
IoT has meant that you need to be skilled in the HW again



2021-05-03T08:41:11
- did some drawings on the weekend which need to be imported

- problem with current solution
  - categorization is rigid based on folder structure (notes can't be in multiple "notebooks")
  - there is a lot of jumping around between notes
  - i create a note somewhere, say for a meeting, and that goes in the meetings folder (which is great)
    - in that note, i create a task, or AP, or whatever
    - imdone picks it up
      - imdone has way too much information, and way too many cards; It's cluttered and hard to work with (for me) - any task, to, resource, whatever is here - i want to see what is on the go now; and the next backlog items... small things/chores/interest/APs for a particular task, don't need to be there
      - imdone cards get large when you start adding more info, updates etc (basically to know where you were at in a task) which compounds the problem
      - imdone has to mess with the original file when you update the card (has its advantage, in that you see the diff in git and get timestamps; but downside is you can't write protect the file)
    - now, i create a folder to store the notes for that task (might be in a bigger collection which I incorrectly call EPICs at the moment (because thats imdone's way of aggregating multiple tasks))
    - and I work in that file when i work in the task.. or (as has happened with Tieto) i might work in the meeting notes where the task was created (and so the notes are attached directly to the task)
      - for small tasks, I work in the task?
      - for bigger tasks, that will be several sessions of work, i create a file and work there; when it gets too big i create a new file?
        - in this case, when i work on a task:
          - i have no idea where the original task is (missing the context of why it was created etc - and not finding the task makes it harder to update, though I can do that in the imdone interface)
          - i can't find the file where the notes are! i had this issue with meeting with Lennart last week; i could not find where i was taking notes for the meeting;
          - i might open a task in imdone (or find it on my postit)
            - where are the damn notes for it?
            - where am i up to?
            - what was the last thing I did?
            - why is it blocked?
            - what do I do next?
            - do i have open questions? do i need to chase people?
            - where is that resource/doc?
            - i know i solved this same problem once, for another customer... where did I do that?
            - this question has been asked 5 times now, maybe it would be good to dig a little deeper and write some new docs or a tutorial? (but i need to sync that with Tuva first)
            - hrmm, this is not really relevent to this case, but it's an interesting thing id like to learn and understand better
            - that solution i came up with on the weekend, and wrote on a napkin - where is that note? did it work?
            - now i've solved that problem, I have found 5 more things that need to be done
            - this problem is the same for 3 other customers, i better fix that
          - the notes i took when working will be needed for the next meeting, so i need a reference to it
          - i mailed someone and asked some questions, need to follow up
          - everything is in one file, and i have to scroll up and down when i take new notes...

    - i need to be able to work when im at the desk, and when im not... whatever "work" means; that might be actual work, a project, an interesting thought, inspiration or a chore..

  - high potential for things to get lost - for example, just little notes of things that I work on every now and again
    - When im away from the desk,
  - high potential for duplication of notes/tasks/todo's (since i don't know if i noted it down somewhere else - this might be more a process things more than anything else)
    - an example of this is using GraphQL for grabbing payloads; i made a note of this, then lost it and thought of it again - so i ended up with duplicates;
      - it's not a task, maybe a subtask to vicotee; but its also a training thing as well - but i didn't remember so i think i made a note on a postit as well over the weekend
    - if it ends up in the todo list, then i would see it, and clean it up; otherwise it gets lost and then duplicated
  - do i work in a single file for a task, or multiple tasks contributing to a single task? (does it matter?)
    - sometimes i do a LOT of work in a single file, and that works ok - i timestamp each section, commit etc; when it gets too big, i might want to start a new file - how do i name them so they stay chronological in the file-list? (otherwise it can be a pain to navigate)
    - after doing a lot of work, i decide that im going to do a major-writeup; for example this file was supposed to be a single note describing my problem with notetaking and task management, and a possible solution; instead i have started taking more notes - so because this is my latest work - i build on this; only it has the wrong name - and probably will be out of order in the file viewer (thats why i pre-append a date to the filename and i can fix this, by renaming this file, or moving the contents)
  - still rely on postit's to keep track of things
    - i have the kanban board, but i still have a stack of postit's with the Todo's on them (which is useful for when im not at my desk)
      - also useful for just "little" tasks; for example planning the weekend chores
  - when im away from the desk, i think about things; and if i get inspiration (for example Blog ideas) I will write them down on a post it; i might be thinking about other interesting things, so i look it up on chrome (now i have open tabs) - for example, the things i want to buy at Crema; i might see an interesting article i want to read, so i save it ... whatever! so now i come back to the desk and i have a bunch of postit's - its a lot of overhead to import, and really its things i just want to read ack again
    - what i want to do, is capture that inspiration and thought, then "stumble" on it again... or maybe chase it up
      - for example, TT electronics; i have an idea that the S19Y01 would be a good thing to be "MIC Ready"; since TT are unlikely to do that work I thought it would be a fun experiment; so i did some work, made some notes and contacted MkK; it's not a task yet (since MkK has not approved) so, where does it go? I capture the notes, then make a reminder to follow up
    - things to post to linkedin...
    - idle CPU states and idle loops! it was just interesting!
    - the video I watched on YouTube on how they film mirrors (a question i have had for ages, and found the answer to)... ok, thats just a personal diary thing! but you get the point

  - i am tending to keep documents open at the moment, as reminders of things to work on; for example
    - so i dont have to go looking for vicotee, those are open;
    - so i dont have to go looking, the "Open Tasks and Questions" for MIC are open still, so i can add and work (its buried in Training for some reason which might make sense, but its also not where i would go looking for it)

- on a workday
  - i want to get my coffee, sit down at my desk, open up my kanban board, and my calendar and plan my day - this might be written on a postit for easy reference?
  - i might receive inspiration of something to work with, just from memory - it might be on my kanban, but might not be high prio, but is interesting at the moment - but it might NOT be on my kanban and it's a project i am coming back to (maybe beer brewing... sourdough... something i haven't done for a while) ... or it's something thats just an inspiration thing (like S19Y01 tutorial) and I want to capture that (of course if i work with those things, it should become a task and over time i have things at the ready)
  - if I don't remember, I want to know exactly what the status of that task is; what i was doing, what i was thinking, and what i am doing next
  - since the last time i worked on a task, i might have made some notes/had an idea or thoughts that I want to try
- when im at my desk (but maybe not working, so doing a project, or training ... or whatever)
  - ...?
- when im away from my desk (maybe on a workday, or a weekend... or whatever)
  - i think about things, i do research, i read, i get inspiration... some of that

  - essentially; i want to plan my day and I want to be able to pick up any task, after no matter how long, and start working with minimal overhead. I want to be able to work on things, with minimal overhead
  - i want to be free to work on whatever, whenever... and not be slowed down, or feel i need to be at my desk (if i do some training whilst washing dishes... why not? make use of the time - or watch a preso when exercising... do it!)

- JUST THIS MINUTE (2021-05-03T10:16:21)
  - I am looking at a stack of post-it's from the weekend that need to be dealt with - they are inspiration, and ideas, and thoughts.... but where to put them?
  - I followed up the ping I got on CE forum regarding the bench setup and DSO Nano; I couldn't find it - there was some notes in the Personal Diary from some time ago, so now i make a new note in the personal diary for today, with reference to the CE forum post; which is just terrible and I will lose that data
  - another one is the blogs idea; I will create a task to capture that work, and ideas - planning; but there will be links to training and goals/job description
    - TCXN Goals -> MIC Goals -> MIC Commercial Goals (MIC Dev Goals related as well) -> My Goals
      - Scale MIC
        - Sales Material
        - Marketing
          - Directly to Customers
            - Blogs of functionality
          - Indirectly to Customers
            - Blogs...
        - Trainings to Existing/Potential Customer
        - Documentation (developer / Internal / customer... )
        - ... so where does the work I do on blogging really fit? if im not given the oportunity to do that work, there is no point in doing it!!
          - but i should at least capture the work better than I do on a postit..
  - I needed to install Brew; then wget - then get the docs for the SOM saved (and remember this is not attached to a task yet, so where do i put this? - i ended up putting in the daily diary
      - this was for the S19Y01 blog post idea
  - i am in the pricing model meeting, and hadn't done the prep at all (which came as a separate mail).... should prep for a meeting be a task?
  - i have fritzing open with a diagram for a blog idea; but that is not captured anywhere, so that diagram is not going to be easily found again
  - talking with Grant and Tim... where should that info go?!
  - ... what the above shows me is that _categorization_ is a huge problem; removing it would make life, much much much easier!

- creating tasks etc inside notes though is as good as I had hoped it would be! just needs to be expanded a wee bit to make it truly useful
  - i think the issue of task tracking and status can be solved by using '[ ]' markdown when a new sub-task is opened (or next step perhaps);
  - if you look at the note for Uplink Transform, then in that i write status updates all the time
    - can NLP detect a status update? -> have to be careful in knowing what is a status update, and what is just a note of something that was done (maybe much of what i put into that notes is not status update, its just an update)
    - [status] could be used, then the backend just finds all instances of [status] and can list them timestamped
    - the task can then link to the view of the tasks (since we are moving away from the concept of a single file - we instead have a collection of notes; and the entire task view is the collection of notes that makes up that task)
    - what i then need is UI/UX to show status updates (which should ideally be one per day worked - think agile/scrum): UI/UX to point me to next steps
    - use other metadata to denote the various things to track (some sort of tagging system) -> tied to UI/UX
    - maybe just show the latest status? (with an option to show more)

2021-05-04T08:23:45
- status of a task is _how would you describe it in a standup?_ a one sentence summary of progress, next steps, current status
- the current status might not be more than a sentence; but you may wish to see milestones of a task? maybe not a milestone as such - more a point in the task where something noteworthy was achieved, such that when reviewing the note, you can get a glimpse of the overall progress

2021-05-04T08:32:03
- open questions, thoughts, subtasks, etc - actionable items that may be attached to a task or set of notes; how to work with those?
  - lets imagine that I have a task,

- lets role play a day in the life - let's pick monday to start with, a work day:

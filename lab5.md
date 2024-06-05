Part 1: Debugging Scenario

Student: Hello TA, I am having issues with my program! For some reason my AutoGrader program called `grade.sh` has many errors. The symptom seems to be about `ClassNotFound` error message, can you help me? I've tried many different inputs but all of them seem to be failure-inducing inputs, nothing works!

![Screen Shot 2024-06-05 at 1 31 12 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/7eb8150e-bb51-4adc-97a7-882b46f7aff9)


TA: Hello student! Based on the error message, It seems your bug is about trying to find the lib file but is unable to find it, can you use the command `ls` in the terminal, while in the `list-examples-grader-main` working directory?

Student: Sure!

![Screen Shot 2024-06-05 at 1 15 29 AM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/04691416-7830-453e-a330-9f70137280ba)

TA: I think I see the issue here, there is no `lib` file in `list-examples-grader-main`, perhaps it is inside another file? Check all the directories in `list-examples-grader-main` to see if it is in there.

Student: I used `ls` on the directories, `student-submission` and `faulty-file`, and sure enough it was in `faulty-file`. But what do I do now?

![Screen Shot 2024-06-05 at 1 22 38 AM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/711bf87e-46ba-4360-8623-9d11389c0a2d)

TA: Now we have to move the `lib` file out of `faulty-file` and into `list-examples-grader-main` so your AutoGrader can use the `lib` file to work properly. To do this we will need to use the `mv` command, which goes like: `mv [options] <fdirectorypath> <destination>`. To move multiple files, you would have to write it like, `mv [options] <directorypath> <otherdirectorypath> <destination>`.

Student: Okay, so to move the file, `lib` from `faulty-file` to `list-examples-grader-main`, I will need to use the command, `mv ~/Desktop/CSE15L/list-examples-grader-main/faulty-file/lib ~/Desktop/CSE15L/list-examples-grader-main/lib`.

Directory before command:

![Screen Shot 2024-06-05 at 1 21 00 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/35bbd8a0-d2d0-45ff-994a-266d23c5ac83)

Execute command:

![Screen Shot 2024-06-05 at 1 21 19 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/b86f27d7-130a-4d30-a0c6-54f841433477)

Directory after command:

![Screen Shot 2024-06-05 at 1 21 33 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/00ce7205-e471-4cfb-b7bf-0be19cd2835e)

Student: Okay! All done, now my AutoGrader is working properly, thank you TA!


At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug
You should actually set up and run the scenario from your screenshots. It should involve at least a Java file and a bash script. Describing the bug should involve reading some output at the terminal resulting from running one or more commands. Design an error that produces more interesting output than a single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.

Part 2: Reflection

I had never thought I would learn so much from a 2 unit class. All the lab, lab reports, skill demos, and lecture notes had helped me with everything, in all my classes. Something I have learned from my lab experience in the second half of this quarter was all the bash scripting we did. Before this class I had no idea what bash scripting even was. Now im proud to say that after CSE15L I can confidently do the basics of bash scripting. Admittedly it is still confusing, and the strict punctuation (`if [[ 1 == 1 ]]`) seems a bit weird to me, but I do like being able to use bash script with my java codes.

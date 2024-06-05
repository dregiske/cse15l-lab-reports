Part 1: Debugging Scenario

Student: Hello TA, I am having issues with my program! For some reason my AutoGrader program called `grade.sh` has many errors. The symptom seems to be about `ClassNotFound` error message, can you help me? I've tried many different inputs but all of them seem to be failure-inducing inputs, nothing works!

![Screen Shot 2024-06-05 at 1 31 12 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/7eb8150e-bb51-4adc-97a7-882b46f7aff9)


TA: Hello student! Based on the error message, It seems your bug is about trying to find the lib file but is unable to find it, can you use the command `ls` in the terminal, while in the `list-examples-grader-main` working directory?

Student: Sure!

![Screen Shot 2024-06-05 at 1 15 29 AM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/04691416-7830-453e-a330-9f70137280ba)

TA: I think I see the issue here, there is no `lib` file in `list-examples-grader-main`, perhaps it is inside another file? Check all the directories in `list-examples-grader-main` to see if it is in there.

Student: I used `ls` on the directories, `student-submission` and `faulty-file`, and sure enough it was in `faulty-file`. But what do I do now?

![Screen Shot 2024-06-05 at 1 22 38 AM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/711bf87e-46ba-4360-8623-9d11389c0a2d)

TA: Now we have to move the `lib` file out of `faulty-file` and into `list-examples-grader-main` so your AutoGrader can use the `lib` file to work properly. To do this we will need to use the `mv` command, which goes like: 
`mv [options] <fdirectorypath> <destination>`.

Student: Okay, so to move the file, `lib` from `faulty-file` to `list-examples-grader-main`, I will need to use the command, `mv ~/Desktop/CSE15L/list-examples-grader-main/faulty-file/lib ~/Desktop/CSE15L/list-examples-grader-main/lib`.

Directory before command:

![Screen Shot 2024-06-05 at 1 21 00 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/35bbd8a0-d2d0-45ff-994a-266d23c5ac83)

Execute command:

![Screen Shot 2024-06-05 at 1 21 19 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/b86f27d7-130a-4d30-a0c6-54f841433477)

Directory after command:

![Screen Shot 2024-06-05 at 1 21 33 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/00ce7205-e471-4cfb-b7bf-0be19cd2835e)

Student: Okay! All done, but now my AutoGrader seems to have another issue with wrong feedback. When grading different student-submissions, my program tells the student that their java file compiled with no issues when it wasn't able to compile, and vise versa when their java file has issues. The symptom of this issue is that my program is giving the wrong error code. The failure-inducing input is all inputs, because this happens with all student-submissions.

(Wrong error feedback on the bottom, 3 lines above Time):

![Screen Shot 2024-06-05 at 1 40 49 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/80051220-d5b8-4bad-946b-f7febd3e1bac)

TA: I see, lets take a look at your `grade.sh`.

Student:

![Screen Shot 2024-06-05 at 1 43 08 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/3d539a7e-9332-48ee-ac02-ed74935cf836)

TA: I see the issue, the bug is that it returns the wrong error code. A java file only returns 0 when it successfully compiles, otherwise it will return a different number.

Student: So by using the error code, 1, I am telling the `if` statement to return an error in compiling when there is no error. I get it now.

TA: To fix this, you will need to edit your `grade.sh` to be `if [[ $? -eq 0 ]]` instead. To edit the file, you can use `nano grade.sh` or manually open the file yourself.

Student: I will fix it now.

![Screen Shot 2024-06-05 at 1 49 30 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/1ebca796-9d56-49a6-a59e-d26cf5bc59c1)

Executing `grade.sh` with changes:

![Screen Shot 2024-06-05 at 1 50 40 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/43659dc1-8ec1-4a17-8354-b09497aabb00)

Student: My `grade.sh` AutoGrader seems to be working properly now! Thank you TA.

Part 2: Reflection

I had never thought I would learn so much from a 2 unit class. All the lab, lab reports, skill demos, and lecture notes had helped me with everything, in all my classes. Something I have learned from my lab experience in the second half of this quarter was all the bash scripting we did. Before this class I had no idea what bash scripting even was. Now im proud to say that after CSE15L I can confidently do the basics of bash scripting. Admittedly it is still confusing, and the strict punctuation (`if [[ 1 == 1 ]]`) seems a bit weird to me, but I do like being able to use bash script with my java codes.

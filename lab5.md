Design a debugging scenario, and write your report as a conversation on Piazza (you don't need to make a post). It should have:

The original post from a student with a screenshot showing a symptom and a description of a guess at the bug/some sense of what the failure-inducing input is. (Don't actually make the post! Just write the content that would go in such a post).

Student: Hello TA, I am having issues with my java code! For some reason my AutoGrader program called `grade.sh` has many errors. The symptom seems to be about `ClassNotFound` error message, can you help me? I've tried many different inputs but all of them seem to be failure-inducing inputs.

![Screen Shot 2024-06-05 at 1 09 06 AM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/7f585943-807d-4e7c-a45b-056125a75b0a)


A response from a TA asking a leading question or suggesting a command to try (To be clear, you are mimicking a TA here.)
Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.

TA: Hello student! Based on the error message, It seems your program is trying to find the lib file but is unable to find it, can you use ls in the terminal in the `list-examples-grader-main` working directory?

Student:

![Screen Shot 2024-06-05 at 1 15 29 AM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/04691416-7830-453e-a330-9f70137280ba)


At the end, all the information needed about the setup including:
The file & directory structure needed
The contents of each file before fixing the bug
The full command line (or lines) you ran to trigger the bug
A description of what to edit to fix the bug
You should actually set up and run the scenario from your screenshots. It should involve at least a Java file and a bash script. Describing the bug should involve reading some output at the terminal resulting from running one or more commands. Design an error that produces more interesting output than a single message about a syntax or unbound identifier error – showcase some interesting wrong behavior! Feel free to set this up by cloning and breaking some existing code like the grading script or code from class, or by designing something of your own from scratch, etc.

Part 2: Reflection

I had never thought I would learn so much from a 2 unit class. All the lab, lab reports, skill demos, and lecture notes had helped me with everything, in all my classes. Something I have learned from my lab experience in the second half of this quarter was all the bash scripting we did. Before this class I had no idea what bash scripting even was. Now im proud to say that after CSE15L I can confidently do the basics of bash scripting. Admittedly it is still confusing, and the strict punctuation (`if [ 1 == 1 ]`) seems a bit weird to me, but I do like being able to use bash script with my java codes.

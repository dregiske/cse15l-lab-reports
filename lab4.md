Step 4: Login into ieng6

![Screen Shot 2024-05-22 at 2 31 14 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/41cc762a-04b3-4c03-b149-ea728c40a4d4)

Keys pressed: Opened a VS code terminal and typed, `ssh <space> agiske@ieng6.ucsd.edu <enter>`.

Summary: The ssh command followed by my email address allowed me to login to my ieng6 account.

Step 5:

![Screen Shot 2024-05-22 at 2 38 52 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/a47961eb-23ca-4172-b7c1-9b3a6acd3141)

Keys pressed: In the browser I `<ctrl + c>` the ssh url, then clicked my VS code open and `git <space> clone <space> <ctrl + v> <enter>` into the terminal.

Summary: By copying the ssh url and pasting it into the terminal with git clone it allowed me to clone my lab7 fork into VS code.

Step 6:

![Screen Shot 2024-05-22 at 4 05 00 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/43d4d6af-a557-4452-85a0-44a00f6b0f0e)

![Screen Shot 2024-05-22 at 2 43 13 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/aedcccef-7684-4dfe-8101-3deed20c6ca4)

Keys pressed: First, `cd <space> lab7 <enter>`, then `bash <space> test.sh <enter>`.

Summary: To run the tests in lab7, I first had to change my current working directory to `lab7` by using the `cd` command. Then I used `bash test.sh` to run the bash script that compiled and ran `ListExamplesTests.java` in one command line.

Step 7:

![Screen Shot 2024-05-22 at 3 01 39 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/e173ebdb-4f8b-4a4b-8d3e-966e982869a0)

Keys pressed: First `vim <space> ListExamples.java <enter>`. Scrolled down to the line that needed correction, then pressed `<left> <left> <left> <left> <left> <left> <left> <left> <left> <left> <left>` to place my cursor above the mistake, `<x>` to delete `1` and `<i> 2 <esc>` to insert a `2` in the same place. `:wq <enter>` to exit with saved changes.

Summary: To fix the failing test, I had to edit `ListExamples.java` with the `vim` command. After entering the editing tool, I navigated to the mistake in the code. Then after placing my cursor above the mistake, I used the command `x` to delete the mistake and `i` to type in the correction. To finish I used the command `:wq` which saved changes and exited.

Step 8:

![Screen Shot 2024-05-22 at 3 00 20 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/05c09d67-ab77-4cde-a929-cdfec7c33249)

Keys pressed: `bash <space> tesh.sh <enter>`.

Summary: To show that the code was fixed and the tests all pass I used `bash test.sh` again to run and compile `ListExamplesTests.java` which showed that all tests had passed.

Step 9:

![Screen Shot 2024-05-22 at 3 46 29 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/dfe4f118-22b5-4a3a-93c4-7d0ee242c298)

![Screen Shot 2024-05-22 at 3 47 43 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/0f240992-f185-4442-9320-4ef857e6f718)

![Screen Shot 2024-05-22 at 3 48 17 PM](https://github.com/dregiske/cse15l-lab-reports/assets/146780188/99963677-3241-4b3d-8aed-98fa4c35ddc5)

Keys pressed: First `git <space> add <space> ListExamples.java <enter>`, then `git <space> commit <space> -m <space> "lab report 4 done" <enter>`, then `git <space> push <space> origin <space> main <enter>`.

Summary: The `git add` command tells Github which files were changed and adds them to the staging area, I typed `ListExamples.java` with the command because that was the file I specifically changed. After I used `git commit -m "..."` which saves the changes made and I added a message saying lab report 4 is done. Lastly, I typed `git push origin main` to apply these changes to my Github, and now they can be seen in my Github.

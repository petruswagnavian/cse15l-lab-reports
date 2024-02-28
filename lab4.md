Peter Wang. CSE 15L. Lab Report 4.
---

On Vim.

---

Step 4: Log into ieng6
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/ab46dcc7-40ff-4ec9-9f5e-93a18ecc67fe)

Keys pressed: I typed `ssh pew017@ieng6.ucsd.edu`, and then pressed `<enter>`.

The command run is an `ssh` command that logs into the student `ieng6` account. Because I am set up to SSH using keys for `ieng6`, a password is not required. The `<enter>` keypress simply runs the command in bash.

Step 5: Clone your fork of the respository from your Github account (using the `SSH` URL)
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/b037022d-9856-4f26-bd05-aea634757cf1)

Keys pressed: I typed `git clone`, and then pasted in the `SSH` URL of the fork in my repository by pressing `<ctrl>+v`, and then pressed `<enter>`.

The command run is the `git clone` command that clones the repository specified. In this case, the `SSH` URL is specified, which clones the fork I created of the respository. `<ctrl>+v` pastes the URL in, and the `<enter>` keypress simply runs the command in bash.

Step 6: Run the tests, demonstrating that they fail
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/f1ce44e8-2803-4849-b8a9-cf565acb24fe)

Keys pressed: I typed `cd ` for the command to navigate to a directory, typed `l` and then pressed `<tab>` for the shortcut to autofill to `cd lab7/`, and then pressed `<enter>`. Then, I typed `bash `, and then `t`, and then pressed `<tab>` for the shortcut to autofill to `test.sh`, and then pressed `<enter>`.

The first command run is `cd lab7/` which simply navigates the working directory to the directory `lab7`. The `<enter>` keypress simply runs the command in bash. The second command is `bash test.sh`, which runs the bash file `test.sh`. the `<enter>` keypress simply runs the command in bash.

Step 7: Edit the code file to fix the failing test
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/96ec80bb-61da-4600-90ae-5e0d0a03c6fa)
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/d6497eee-e937-4030-b875-d2a126b6f95e)


Keys pressed: I typed `vim `, typed `Li` and then pressed `<tab>` for the shortcut to autofill to `vim ListExamples`, and then typed `.java` to finish the command: `vim ListExamples.java`. Then I pressed `<enter>`. In the text editor, I pressed `/` and then typed `index1`. Then I pressed `<enter>`, `n`, `n`, `n`, `n`, `n`, `n`, `n`, `n`, `n`. (pressed `n` 9 times). Then I pressed `l`, `l`, `l`, `l`, `l`. (pressed `l` 5 times). Then I pressed `r`, and then `2`. After the edit has been made, I typed `:wq`, and then pressed `<enter>`.

The first command run is `vim ListExamples.java`, which opens the file `ListExamples.java` in the text editor `vim`. This allows the user to edit the file from the command line. The typing of `/index1` is simply searching for all instances of where `index1` appears in the file. Pressing `n` nines times just goes through the instances, and I stop once the cursor jumps to the `index1` I want to edit. Pressing `l` five times moves the cursor over the `1` in `index1`. Pressing `r` and then `2` just replaces the `1` with `2`, so now the text was edited to `index2`. Typing `:wq` is the command to exit the text editor while also saving. Pressing the `<enter>` key runs the command and in this case closes the text edtior.

Step 8: Run the tests, demonstrating that they now succeed

Step 9: Commit and push the resulting change to your Github account

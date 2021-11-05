# Useful github practices, like pull requests and branch naming conventions

Github branches are incredibly useful tools. They allow you to branch off of your Master branch and add features, then simply merge your progress back into Master. The workflow looks something like this:
![Branches](http://jlord.us/git-it/assets/imgs/branches.png)

On github.com, you can create a new branch by clicking the dropdown that reads "Master", typing a branch name that isn't already in the list of branches, then click the button that reads "Create branch: NEW_BRANCH_NAME from Master". This creates a branch with the exact same code that Master had originally.

Now, if you open your terminal and pull in the most recent changes, you should see something indicating that you are pulling in a new branch. In order to switch to this branch, use *git checkout BRANCH_NAME*. This will allow you to make changes that are isolated to BRANCH_NAME, meaning that, when you push, Master is not affected at all.

This has many practical use cases in industry. For example, let's say a company is building a social media app. There are 3 teams: one responsible for developing the feed, one responsible for developing the user profile/settings functionality, and one responsible for creating the ability to add/view friends/other profiles. Within these teams, there are many smaller tasks divied up amongst the developers.

Let's say Sam is a lead developer on the profile/settings team. The profile team working under Sam has been very efficient, and has finished the profile screen. The settings team, however, is still trying to implement some functionality. Sam wants to push the finished profile screen to the remote repository, so the other lead developers can take a look and ensure everything works. However, he still has some broken settings code in his local repository that causes the app to crash.

If Sam had a separate branch for the profile screen and the settings screen, this problem would be completely averted. The profile team could push their changes to the profile branch, while the settings team could push their changes to the settings branch. Once the profile team is done, Sam could simply merge these changes into Master.

Sam decides to create this new branch, but doesn't know what to name it. There are a few different options Sam has. If Sam and the other developers have access to some centralized task management tool, for instance, a trello board, Sam could name the branch after the task that corresponds to the feature being developed. If there is no such task management system, Sam could simply name the branch after the feature that was developed, so for intance, user_profile_screen. Either way, it is important to name branches in a way that relates to the branch's purpose, rather than just naming it sams_code or something vague.

Anyway, let's say Sam had already named this branch user_profile_screen, performs the aforementioned merge. Now let's say the lead developer on the feed team finds that this new code isn't compatible with the already completed feed code. This causes the app to break, and every developer that pulled in Sam's changes would have a broken app. While it is possible for Sam or another developer to rebase to a previous commit, but on a large team, communicating this to all of the developers might be challenging.

This is where pull requests come in. Instead of directly merging into Master, Sam could create a pull request, where Sam details the changes made on the profile branch. This pull request asks the other developers for approval before merging the profile branch into Master. This ultimately allows the other developers to be notified of the merge before it occurs, and provides a way to for them to review Sam's code before allowing the merge to occur. Thus, the lead developer on the feed team could see that some of Sam's code isn't compatible with the feed code, and deny the pull request.

Hopefully this little narative helped provide some insight into the usefulness of branches and pull requests. They are widely used in industry, so it is a smart idea to become familiar with them now.
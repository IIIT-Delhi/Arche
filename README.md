# Arche

![rsz_1arche_logo_grayscale](https://cloud.githubusercontent.com/assets/20173739/23075475/a1edb11a-f562-11e6-90c0-eb11968a2fad.png)

**Arche** is an initiative to help newcomers contribute to open-source projects hosted on GitHub.

This README contains a step-by-step guide on how to contribute and aims to remove the hesitation present amongst newcomers. **Arche** follows common standard workflow guidelines that help maintain a project. The guidelines presented here are applicable for any general project. These guidelines however work with **Arche** itself.

Follow along to learn more!

## Before you start

Before we get started, it's better if we get on the same page. We request you to get familiar with basic Linux commands, so that it's easier for you to follow through.

A repository can be part of only 1 project. A project may have multiple repositories (by virtue of forking). Don't worry if you don't get this right now. Just remember this though.

We refer to the repository created on Github as the server repository. The server repository is the place where the original code resides, which is being used to run the application, or contains critical data, or something on the same lines. The local repository is (usually) a copy of the server repository but on your machine. Any changes you do to the local repository will not reflect in the server repository till you push them (more on this later). Remember,

> What happens on your machine, stays in your machine (unless you push it as well)

## Forking and Cloning

Forking and Cloning are the first steps required before working on any project.

Forking a project ensures that the original project isn't affected by any incorrect push you make. It's recommended practice to always fork a project and work on your copy of the project, instead of breaking the original project.

Cloning helps to create a local copy of the repository chosen so that you can work on it, make a few fixes and update the server repository by pushing your changes. To successfully fork and clone, follow these steps:

> Step 1

Head over to ``https://github.com/IIIT-Delhi/Arche`` and click on the fork button

![fork](https://cloud.githubusercontent.com/assets/20173739/22628529/59a828a6-ebfb-11e6-91d0-d2e8f9ea818d.png)

This will create a copy of ``Arche`` in your account. <br>
You should now have a copy of this project at ``https://github.com/``**yourUsername**``/Arche``
If you don't, then that means you weren't able to fork this project.

> Step 2

Since you have made a successful fork, it's time to contribute to the project as well. To do the same, you first and foremost need to clone it.

Fire up your terminal and change your directory to Desktop. After that, execute the command:

<pre>
git clone https://github.com/<b>yourUsername</b>/Arche.git
</pre>

![gitclone](https://cloud.githubusercontent.com/assets/20173739/22628542/b63b5e4e-ebfb-11e6-8bf9-187ac0d37eb8.png)

This should create a directory named ``Arche`` where you are currently working, which should be your Desktop.

Navigate into ``Arche`` and list the contents of the directory.
If you see a ``README.md`` file and a ``Website`` directory, you have successfully cloned a repository! Congrats! :smile:

## Remotes

Remotes are aliases or nicknames for locations to push and pull from.

The ``push`` command is used to send your changes to the target repository whereas the ``pull`` command is used to get the latest version/copy of the target repository.

Check the remotes listed for your local repository with the following command:
<pre>
git remote -v
</pre>

You should see something like this

![remote-v](https://cloud.githubusercontent.com/assets/20173739/22628551/f47eb098-ebfb-11e6-81a1-a220c8090d4f.png)

Now, we are going to add a new ``remote`` i.e. we will enable our local repository to sync up with another repository too rather than just ``origin``.

This another repository will be the original project sitting in the IIIT-Delhi namespace.

To add the IIIT-Delhi version of Arche to your local repository, follow these steps:

> Step 1

Add a new remote with the nickname ``upstream`` and the target location as ``https://github.com/IIIT-Delhi/Arche.git`` with the help of the command:

<pre>
git remote add upstream https://github.com/IIIT-Delhi/Arche.git
</pre>

> Step 2

Confirm the addition of the new remote by listing down all the remotes:

<pre>
git remote -v
</pre>

![upstream](https://cloud.githubusercontent.com/assets/20173739/22628566/52c54284-ebfc-11e6-8bd6-4c08b6620cee.png)

> Step 3

Finally, use the following command so that your local repository starts tracking the ``upstream`` remote:

<pre>
git fetch upstream
git branch -u upstream/master
</pre>

![1](https://cloud.githubusercontent.com/assets/20173739/24585755/aa98b458-17af-11e7-83fe-9749551452bd.png)


There is no direct way of syncing the forked repository (Origin) and the original repository (Upstream). Thus, your local repository acts as a bridge between the two. For syncing the origin and upstream, one can pull changes from upstream and push changes to origin.

## Branches

Very often, one needs to work on new features and builds that are not fully ready. For this, git has a feature called Branches. The default branch for every project is known as the ``master`` branch. The ``master`` branch is supposed to have a fully stable project. Hence, for working on experimental features, additional branches are created. While working on these additional branches, the ``master`` branch isn't affected at all.

For solving any issue or working on any feature, always create a new branch! The way to go about it as follows:

> Step 1

Create a new branch:

<pre>
git branch <b>yourUsername</b>
</pre>

The above command just creates a branch. It doesn't set it as the current working branch.

> Step 2

To work on your branch, issue the following command:

<pre>
git checkout <b>yourUsername</b>
</pre>

![2](https://cloud.githubusercontent.com/assets/20173739/24585784/14c0f3e0-17b0-11e7-8d45-8b6721b3146c.png)

The above command sets your current working branch as **yourUsername**.

> Remember: While solving an issue, always work on a new Branch. Contributions to the ``master`` branch will simply be rejected with a polite reminder.

## Adding & Committing Files

Now we shall finally make a contribution the repository. Please ensure that you have switched away from the ``master`` branch.

For contributing to any project one needs to either create new files or modify some existing files. To do the same, follow along:

> Step 1

Identify which issue you are going to work on. If you don't find one, then it's possible you are suggesting a feature enhancement. Be descriptive when creating an issue. We would recommend you to use **yourUsername** as the title of the Issue.

Make sure you wait for the issue to be assigned to you by a maintainer. It should look something like this:

![Step 1](https://cloud.githubusercontent.com/assets/20173739/23581668/1d30a0d0-013e-11e7-8a62-4e9098d79d60.png)

> Step 2

To contribute to the ``Arche`` project you should edit the ``index.html`` file inside the ``Website`` directory. Add your name as a list element to the file with the help of your text-editor.

![Step 2a](https://cloud.githubusercontent.com/assets/20173739/23581386/a99cc5ae-0138-11e7-87f6-a2f6d5477f5e.png)

Now, save the file and check if it reflects the changes locally by opening it in a browser to make sure your name is visible.

The HTML when opened in a Browser will show your name in the list:

![Step 2b](https://cloud.githubusercontent.com/assets/20173739/23581396/cf39701e-0138-11e7-97cb-1db78aefe1af.png)

> Step 3

After saving your file, execute the following:

<pre>
git status
</pre>

This will show you that the file you have created/modified is untracked.

> Step 4

To track this file, execute the following:

<pre>
git add Website/index.html
</pre>

![3](https://cloud.githubusercontent.com/assets/20173739/24585821/065986d6-17b1-11e7-8fd9-ddc92615b172.png)

All set. You are now ready to acknowledge, realize and tell the world what you have changed! :smile:

> Step 5

Now it's time to ``commit`` our changes so that we can ``push`` them ahead. For this, use the following command:

<pre>
git commit
</pre>

This basically associates a message with what you have changed in the project.

Ideally, one should commit per every logical change. Executing ``git commit`` will open your default editor to be used with git.
Ours is set up to be atom. Should you want to change yours from vim, checkout [this stackoverflow answer](http://stackoverflow.com/questions/2596805/how-do-i-make-git-use-the-editor-of-my-choice-for-commits).

On executing, your editor will open automatically with the following contents:

![4](https://cloud.githubusercontent.com/assets/20173739/23581513/7a9ea4ae-013b-11e7-9917-2545cbebebee.png)

### Committing Guidelines

Every Commit message should have the following 3 things:

      1)    Name of File Changed: Followed by a very short description.
    **Blank Line**
      2)    A short Description of the Things Achieved in 3-5 lines.
    **Blank Line**
      3)    Closes/Fixes ``issue_link``

      Note: Use Closes for issues that have been done for the sake of Enhancement
            Use Fixes for issues that have been done for the sake of Fixing a Bug

![4](https://cloud.githubusercontent.com/assets/20173739/24585851/87cf443a-17b1-11e7-93cd-9d1b2f19c212.png)

![5](https://cloud.githubusercontent.com/assets/20173739/24585856/cb7a9626-17b1-11e7-8e9f-c52101550c9c.png)

> Step 6

At this stage, you have committed this change but this hasn't been synced with both of your server repositories (origin and upstream)
This simply means that the changes you have made only exist in your local repository and not on Github!

To push these changes, use the following command:

<pre>
git push origin <b>yourUsername</b>
</pre>

This command pushes the changes you made to the the forked repository (origin).

**Note: Never Push to Upstream!**

![6](https://cloud.githubusercontent.com/assets/20173739/24585896/cbd040fc-17b2-11e7-9511-494cb787c66f.png)

Your forked repository will now look like this:

![7](https://cloud.githubusercontent.com/assets/20173739/24585905/071de3e4-17b3-11e7-8c76-6b5dfecb1d48.png)

## Submitting a Pull Request (PR)

After updating your personal copy with the changes you made, you would want to merge your changes in the actual project itself!

To accomplish this, follow these steps:

> Step 1

Simply Click ``Compare and Pull Request`` and you will be directed to this page:

![8](https://cloud.githubusercontent.com/assets/20173739/24585913/3fd0dfd4-17b3-11e7-9225-716888e5d6d8.png)

> Step 2

Click on ``Create Pull Request`` and you are done.

When your PR is merged by the maintainer, voila, you have successfully contributed to the ``Arche`` project!

Congratulations! You did it, you sexy beast! :smile:

## Final Steps

When your contribution has been accepted, notice that your contribution has been merged into the ``master`` branch of the original repository (Upstream).

The ``**yourUsername**`` branch doesn't even exist on Upstream anymore. Now, your local repository and the Upstream are **NOT** in sync.
The reason behind this is that the new ``README.md`` file exists on ``master`` branch of Upstream while it exists on ``**yourUsername**`` branch of the cloned repository.

``Please switch to your master branch on your local copy before proceeding.``

To update your cloned repository according to your Upstream, execute the following:

> Step 1

<pre>
git pull upstream master
</pre>

By doing this, your master branch in the cloned repository will pull changes from the Upstream and thus both of them will be in sync now.

For a similar reason, your fork (Origin) and the original repository (Upstream) will be out of sync.

> Step 2

To update your fork, execute the following:

<pre>
git push origin master
</pre>

It is important that the above 2 commands are done in the same order as given above i.e. pull first and push second.

# Fin.

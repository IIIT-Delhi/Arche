# Arche

![arche_logo_grayscale](https://cloud.githubusercontent.com/assets/20173739/22628324/ec307bb4-ebf7-11e6-9f33-0dcfc39c28c6.png)

## Forking & Cloning

Head over to ``https://github.com/IIIT-Delhi/Arche``
and Click on the Fork Button

![fork](https://cloud.githubusercontent.com/assets/20173739/22628529/59a828a6-ebfb-11e6-91d0-d2e8f9ea818d.png)

This will create a Copy of ``Arche`` into your account.
You now have a copy of this project at ``https://github.com/``**yourUsername**``/Arche``

Copy this link ``https://github.com/``**yourUsername**``/Arche.git``

Fire up your terminal and change directory to Desktop, Execute the following command,

``git clone https://github.com/``**yourUsername**``/Arche.git``

![gitclone](https://cloud.githubusercontent.com/assets/20173739/22628542/b63b5e4e-ebfb-11e6-8bf9-187ac0d37eb8.png)

This should create a folder named ``Arche`` on your Desktop. Change into ``Arche`` using the usual ``cd`` command on your terminal.

The Cloning Process does the following:

1) Creates a local copy (on your PC) of the Forked Project.

2) The Cloned Folder (local) is now set up to sync with the Online Hosted Forked Repository. Cloning does this automatically.

To confirm this, execute this command ``git remote -v``

You should see something like this,

![remote-v](https://cloud.githubusercontent.com/assets/20173739/22628551/f47eb098-ebfb-11e6-81a1-a220c8090d4f.png)

Basically, what this indicates is that you can sync your local copy and your forked copy via the keyword ``origin`` and via the commands ``push`` & ``pull``.

Now, we are gonna add a new ``remote`` i.e. we will enable our local copy to sync with another repository too rather than just ``origin``.
This another repository will be the original Project (not the forked one!)
To do this, Execute the following command.

``git remote add upstream https://github.com/IIIT-Delhi/Arche.git`` (Not **yourUsername** this time!)
Checking ``git remote -v`` now will show you both repositories that your local copy is able to sync with.

![upstream](https://cloud.githubusercontent.com/assets/20173739/22628566/52c54284-ebfc-11e6-8bd6-4c08b6620cee.png)

Finally, use the following command so that your local copy tracks the ``upstream``.

Execute this ``git branch -u upstream/master``

![track](https://cloud.githubusercontent.com/assets/20173739/22628626/263f2364-ebfd-11e6-9aae-f4cd514850d8.png)

This way, your cloned folder has 2 remotes now, one being the ``origin`` and the other being ``upstream``.
There is no direct way of syncing the Forked Repo (Origin) and the Original Repo (Upstream). Thus, the cloned repo acts as a bridge between the two. For syncing the origin and upstream, one can pull changes from upstream and push changes to origin.

## Branches

Git Supports Branches. The default branch for every project is known as the ``master`` branch. The ``master`` branch is supposed
to have a fully stable project. Hence, for working on Experimental features, additional branches are created. While working on these
additional branches, the ``master`` branch isn't affected.

To create a new branch, use this ``git branch experimental`` (Here, ``experimental`` is the branch name, This can be changed)
However, this does not take us to the new ``experimental`` branch, it just creates one. To work on this ``experimental`` branch,
use the following ``git checkout experimental``.

![branch](https://cloud.githubusercontent.com/assets/20173739/22628855/8311eb72-ec01-11e6-833b-1bfee9cbd05f.png)

Remember: While solving an issue, always work on a new Branch. Contributions from the ``master`` branch will simply be rejected with a polite reminder.

## Adding & Committing Files

Please switch to another branch before continuing. This is not to be done inside the master branch.

For Contributing, You would obviously want to create new files OR modify some existing files. Go ahead and do that in your cloned copy just like you would do with any other file normally.
For Example, I am creating the ``README.md`` file with the following contents on my text-editor atom inside the cloned ``Arch`` folder.


![readme](https://cloud.githubusercontent.com/assets/20173739/22628958/49d52098-ec03-11e6-9b05-d46e489317d2.png)

After saving your file, execute this ``git status``. Git will show you that the file you have created / modified is untracked.
To track this file, execute this ``git add README.md`` (Replace README.md with your **filename**)

![add](https://cloud.githubusercontent.com/assets/20173739/22628994/19483216-ec04-11e6-817e-33fbc01bd038.png)

All set, You are now ready to acknowledge, realize and tell the world what you have changed!!
For this, use ``git commit``. This basically associates a message with what you have changed in the project.

Ideally, one should commit per every logical change. Executing ``git commit`` will open your default editor to be used with git.
Mine is set up to be atom. On executing, your editor will open automatically with the following contents.

![commit](https://cloud.githubusercontent.com/assets/20173739/22629032/ced55a82-ec04-11e6-969a-30db6e188f1c.png)

### Committing Guidelines

Every Commit message should have the following 3 things:

      1)    Name of File Changed: Followed by a very short description.
    **Blank Line**
      2)    A short Description of the Things Achieved in 3-5 lines.
    **Blank Line**
      3)    Closes/Fixes ``issue_link``

      Note: Use Closes for issues that have been done for the sake of Enhancement
            Use Fixes for issues that have been done for the sake of Fixing a Bug

![com](https://cloud.githubusercontent.com/assets/20173739/22629141/9872f448-ec06-11e6-9805-b8d266ff4d0b.png)
![rt](https://cloud.githubusercontent.com/assets/20173739/22629151/c0305ef8-ec06-11e6-8dc0-7fda17071133.png)

At this stage, you have committed this change but this hasn't been synced with both of your remote online repos (Origin & Upstream)
This simply means that the changes you have made only exist in your local PC and not on github!

To push these changes, use the following command
``git push origin experimental``
This command pushes the changes you made to the the forked repository (Origin).
**Note: Never Push to Upstream!!**

![push](https://cloud.githubusercontent.com/assets/20173739/22629213/e7320136-ec07-11e6-8132-f53981bdd4ce.png)

Your forked Repository will now look like this

![pr](https://cloud.githubusercontent.com/assets/20173739/22629242/4d03f262-ec08-11e6-9bae-8169a0f41290.png)

## Submitting a PR (Pull Request)

Simply Click ``Compare and Pull Request``
You will be directed to this Page

![pr1](https://cloud.githubusercontent.com/assets/20173739/22629261/bbb06150-ec08-11e6-9488-b53eb76bb3bf.png)

Click on ``Create Pull Request`` and you are done.

When your PR is merged by the maintainer, voila, you have successfully contributed to the ``Arche`` Project.

## Final Steps
When your contribution has been accepted, Notice that your contribution has been merged into the ``master`` branch of the Original Repo (Upstream).
The ``experimental`` branch doesn't even exist on Upstream. Now, your cloned folder and the Upstream are NOT in sync.
(As the new README.md file exists on master branch of Upstream while it exists on experimental branch of cloned repository.)
To update your cloned folder according to your Upstream, execute the following:

``git pull upstream master``

By doing this, your master branch in the cloned repo will pull changes from the Upstream and thus both of them will be in Sync now.

For a similar reason, your fork (Origin) and the original repo (Upstream) will be out of sync.
To update your fork, execute the following:

``git push origin master``

It is important that the above 2 commands are done in the same order as given above i.e pull first and push second.

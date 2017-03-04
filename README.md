# Arche

![rsz_1arche_logo_grayscale](https://cloud.githubusercontent.com/assets/20173739/23075475/a1edb11a-f562-11e6-90c0-eb11968a2fad.png)

**Arche** (meaning ``beginning``) is an initiative to help newcomers contribute to open-source projects hosted on GitHub. **Arche** contains a Step-By-Step guide on how to contribute and aims to remove the hesitation present amongst newcomers. **Arche** follows common standard workflow guidelines that help maintain a project. The guidelines presented here are applicable for any general project. These guidelines however work with **Arche** itself. Follow along to learn more!!

## Forking & Cloning

Forking & Cloning are the first steps required before working on any Project.These Steps enable us to work on our copy of the project without affecting the original project. To successfully fork and clone, follow these steps:

**Step 1)** Head over to ``https://github.com/IIIT-Delhi/Arche`` and Click on the Fork Button.

![fork](https://cloud.githubusercontent.com/assets/20173739/22628529/59a828a6-ebfb-11e6-91d0-d2e8f9ea818d.png)

This will create a Copy of ``Arche`` into your account.
You now have a copy of this project at ``https://github.com/``**yourUsername**``/Arche``

**Step 2)** Copy this link ``https://github.com/``**yourUsername**``/Arche.git``

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

**Step 3)** Now, we are gonna add a new ``remote`` i.e. we will enable our local copy to sync with another repository too rather than just ``origin``.
This another repository will be the original Project (not the forked one!)
To do this, Execute the following command.

``git remote add upstream https://github.com/IIIT-Delhi/Arche.git`` (Not **yourUsername** this time!)

Checking ``git remote -v`` now will show you both repositories that your local copy is able to sync with.

![upstream](https://cloud.githubusercontent.com/assets/20173739/22628566/52c54284-ebfc-11e6-8bd6-4c08b6620cee.png)

**Step 4)** Finally, use the following command so that your local copy tracks the ``upstream``.

Execute this ``git branch -u upstream/master``

![track](https://cloud.githubusercontent.com/assets/20173739/22628626/263f2364-ebfd-11e6-9aae-f4cd514850d8.png)

This way, your cloned folder has 2 remotes now, one being the ``origin`` and the other being ``upstream``.
There is no direct way of syncing the Forked Repo (Origin) and the Original Repo (Upstream). Thus, the cloned repo acts as a bridge between the two. For syncing the origin and upstream, one can pull changes from upstream and push changes to origin.

## Branches

Very Often, one needs to work on new features and builds that are not fully ready. Thus, Git Supports Branches. The default branch for every project is known as the ``master`` branch. The ``master`` branch is supposed to have a fully stable project. Hence, for working on Experimental features, additional branches are created. While working on these additional branches, the ``master`` branch isn't affected. For solving any issue or working on any feature, always create a new branch!

**Step 1)** To create a new branch, use this ``git branch experimental`` (Here, ``experimental`` is the branch name, This can be changed)
However, this does not take us to the new ``experimental`` branch, it just creates one.

**Step 2)** To work on this ``experimental`` branch,
use the following ``git checkout experimental``.

![branch](https://cloud.githubusercontent.com/assets/20173739/22628855/8311eb72-ec01-11e6-833b-1bfee9cbd05f.png)

Remember: While solving an issue, always work on a new Branch. Contributions from the ``master`` branch will simply be rejected with a polite reminder.

## Adding & Committing Files

Please switch to another branch before continuing. This is not to be done inside the master branch.

**Step 1)** Do Some Work!!

For Contributing, You would obviously want to create new files OR modify some existing files. Go ahead and do that in your cloned copy just like you would do with any other file normally. For Example, You should edit the ``index.html`` file inside the ``Website`` folder with ``your name as a element of the list`` on your text-editor.

To do this,

a) Open the ``index.html`` in your text editor.

b) Search for the comment, ``Insert your names here`` in the file.

c) Add your name as a element of the same list.

d) Check the file by opening it in a browser to make sure your name is visible.

![1](https://cloud.githubusercontent.com/assets/20173739/23581386/a99cc5ae-0138-11e7-87f6-a2f6d5477f5e.png)

The HTML when opened in Browser will add your name in the list as shown below.

![2](https://cloud.githubusercontent.com/assets/20173739/23581396/cf39701e-0138-11e7-97cb-1db78aefe1af.png)

**Step 2)**
After saving your file, execute this ``git status``. Git will show you that the file you have created / modified is untracked.

**Step 3)**
To track this file, execute this ``git add Website/index.html``.

![3](https://cloud.githubusercontent.com/assets/20173739/23581478/a10f8316-013a-11e7-9465-6b6579b3280f.png)

All set, You are now ready to acknowledge, realize and tell the world what you have changed!!

**Step 4)** For this, use ``git commit``. This basically associates a message with what you have changed in the project.

Ideally, one should commit per every logical change. Executing ``git commit`` will open your default editor to be used with git.
Mine is set up to be atom. On executing, your editor will open automatically with the following contents.

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

![5](https://cloud.githubusercontent.com/assets/20173739/23581551/eb9157ce-013b-11e7-8e89-5381bebecfba.png)

![6](https://cloud.githubusercontent.com/assets/20173739/23581568/3496f9a6-013c-11e7-881c-1829e7da5f4a.png)

At this stage, you have committed this change but this hasn't been synced with both of your remote online repos (Origin & Upstream)
This simply means that the changes you have made only exist in your local PC and not on github!

To push these changes, use the following command
``git push origin experimental``
This command pushes the changes you made to the the forked repository (Origin).
**Note: Never Push to Upstream!!**

![push](https://cloud.githubusercontent.com/assets/20173739/22629213/e7320136-ec07-11e6-8132-f53981bdd4ce.png)

Your forked Repository will now look like this

![8](https://cloud.githubusercontent.com/assets/20173739/23581704/3c0928be-013f-11e7-9d83-c00ef9b59ec3.png)

## Submitting a PR (Pull Request)

After updating your personal copy with the changes you made. You would want to merge your changes in the actual project itself!
To accomplish this,

**Step 1)**
Simply Click ``Compare and Pull Request``
You will be directed to this Page

![9](https://cloud.githubusercontent.com/assets/20173739/23581746/6e0a48e2-0140-11e7-8e29-32d58157e727.png)

**Step 2)**
Click on ``Create Pull Request`` and you are done.

When your PR is merged by the maintainer, voila, you have successfully contributed to the ``Arche`` Project.

## Final Steps
When your contribution has been accepted, Notice that your contribution has been merged into the ``master`` branch of the Original Repo (Upstream).
The ``experimental`` branch doesn't even exist on Upstream. Now, your cloned folder and the Upstream are NOT in sync.
(As the new README.md file exists on master branch of Upstream while it exists on experimental branch of cloned repository.)
To update your cloned folder according to your Upstream, execute the following:

**Step 1)**
``git pull upstream master``

By doing this, your master branch in the cloned repo will pull changes from the Upstream and thus both of them will be in Sync now.

For a similar reason, your fork (Origin) and the original repo (Upstream) will be out of sync.

**Step 2)**
To update your fork, execute the following:

``git push origin master``

It is important that the above 2 commands are done in the same order as given above i.e pull first and push second.

## What's Next ?

As a part of finally completing these guidelines, please create an issue by your name.
Please assign the Issue to yourself. It should look something like this.

![7](https://cloud.githubusercontent.com/assets/20173739/23581668/1d30a0d0-013e-11e7-8a62-4e9098d79d60.png)

Change the ``index.html`` file by adding your name as a Contributor of this Repo. Follow
the guidelines above to successfully make a pull request and acknowledge yourself as a
contributor!

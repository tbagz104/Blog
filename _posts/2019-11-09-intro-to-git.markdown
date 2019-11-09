---
layout: post
title: "Introduction to Git"
date: 2019-11-09
categories:
  - Git
description:
image: https://i.imgur.com/5YZ4U0Y.jpg
image-sm: https://i.imgur.com/5YZ4U0Y.jpg
---

Working with Git on the command line can be daunting. To help with that, i’ve put together a list of common Git commands, what each one means, and how to use them.There are some actions that we tend to use a lot, so it’s good to learn them. Here are my favorites, learning from friends and internet,hope you find them useful.
<br>

<h3>What is Git? </h3>

Git is a distributed version control system. It is basically a command line program. You will be working with Git using git commands almost all the time. Using Git, many developers can make changes to the same code base at the same time without running into accidents like overriding someone else’s changes. Git will only update the differences made to a file.

<h3>Key Terms</h3>


<ul>
  <li><strong>Version Control System (VCS) or Source Code Manager (SCM):</strong> A VCS allows you to:
revert files back to a previous state, revert the entire project back to a previous state,
review changes made over time, see who last modified something that might be causing
a problem, who introduced an issue and when, and more. </li><br>
  <li><strong>Commit (snapshot):</strong> Git thinks of its data like a set of snapshots of a mini file system.
Every time you commit, or save the state of your project in Git, it basically takes a
picture of what all your files look like at that moment and stores a reference to that
snapshot. </li><br>
  <li><strong>Repository (repo):</strong> A directory that contains your project work, as well as a few files
(hidden by default in Mac OS X) which are used to communicate with Git. Repositories
can exist either locally on your computer or as a remote copy on another computer.</li><br>
  <li><strong>Working Directory:</strong> The files that you see in your computer's file system. When you
open your project files up on a code editor, you're working with files in the Working
Directory. </li><br>

  <li><strong>Branch:</strong> A branch is when a new line of development is created that diverges from the
main line of development. This alternative line of development can continue without
altering the main line.</li><br>

  <li><strong>Checkout:</strong> When content in the repository has been copied to the Working Directory. It
is possible to checkout many things from a repository; a file, a commit, a branch, etc. </li><br>

  <li><strong>Staging Area or Staging Index or Index:</strong> A file in the Git directory that stores
information about what will go into your next commit. You can think of the staging area
as a prep table where Git will take the next commit. Files on the Staging Index are
poised to be added to the repository.</li><br>


</ul>

<figure>
    <img src="https://i.imgur.com/FC2c36ig.jpg" align ="middle">

</figure>

<h3>How to Install?</h3>
 You can install Git on your system using a package manager, an installer or from source.<br>

All instructions are listed at <a href="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git" title="Install Git">here.</a><br>

A git installation must have a remote repository (remote code base) where the changes made by many developers accumulate. Two of the most popular repository hosting websites are GitHub and GitLab, however you can also choose to host your own remote repository on a server.

If you are not comfortable with Git commands, then you can use their official GUI which will be available to you after installing Git. If your repository is on GitHub, then you can download their official GUI application from <a href="https://desktop.github.com/" title="Install Git">this link.</a>

<figure>

  <img src="https://i.imgur.com/hT65vks.jpg" align ="middle">
  
</figure>



<blockquote>Since we're done with the basic terms and workflow let's write some code.
  
</blockquote>

<h3>Useful commands</h3><br>
<h4>Status</h4><br>
  <li><strong>Check the status of working directory and staging area:</strong>

   <pre><code>   git status
 </code></pre>  


 <li><strong>Show changes between HEAD and working directory:</strong>

  <pre><code>    git diff
</code></pre>
   
  
   
  

<li><strong>Show the list of commits in one line format:</strong>

  <pre><code>    git oneline
 </code></pre>

<h4>Tags</h4><br>  
  

  <li><strong>List all tags:</strong>

   <pre><code>    git tag
  </code></pre>

<h4>Remote</h4><br>
  

<li><strong>List all remote:</strong>

  <pre><code>    git remote
  </code></pre>
  
<h4> Branch</h4><br>
  <li><strong>List all branches:</strong>

   <pre><code>    git branch
</code></pre>
  
<li><strong>Create the branch on your local machine and switch in this branch:</strong>

   <pre><code>    git checkout -b branch_name
</code></pre>
  

  <li><strong>Push the branch to remote:</strong>

   <pre><code>    git push origin branch_name
  </code></pre>



  <li><strong>Delete a branch:</strong>

  <pre><code>    git branch -D the_local_branch
    git push origin :the_remote_branch
  </code></pre>

<h4>Commit</h4><br>

  <li><strong>Undo last commit:</strong>

  <pre><code>     git reset --hard HEAD~1
</code></pre>

<li><strong>Squash last n commits into one commit:</strong>

 <pre><code>      git rebase -i HEAD~5

      git reset --soft HEAD~5
      git add .
      git commit -m "Update"
      git push -f origin master
</code></pre>  
<h4>Cherry Pick</h4><br>

<li><strong>Add some commits to the top of the current branch:</strong>

  <pre><code>      git cherry-pick hash_commit_A hash_commit_B
</code></pre>  

<h4>Checkout</h4><br>

<li><strong>Checkout a branch:</strong>

  <pre><code>      git checkout destination_branch

      git checkout -m master // In case a merge conflict exists
</code></pre>
  <h4>Rebase</h4><br>

<li><strong>Rebase the current branch onto master:</strong>

<pre><code>       git rebase master // rebase the current branch onto master

       git rebase --continue // continue rebase

       git rebase --abort // abort rebase
</code></pre>
<br>

These are the most necessary commands you need while learning Git,obviously there is a lot more to explore which we'll be learning on the way later.Happy Coding!

# Chapter 1
## What is Version Control?
- **Version Control**: A system that records changes to a file or a set of files over time so that you can recall specific versions later
- For our purposes, mostly software, however, you can also version control basically *any* kind of file
  - e.g. .mp4, .mp3, .png, etc.
- A version control system allows you to handle version control
  - Set files back to previous state
  - Compares changes over time
  - Revert to previous state
  - Etc.
- Naive VC: simply copy files into another directory
  - Error-prone
  - Copying wrong files
  - Overwriting things you want to keep
  - Etc.
- Slightly Better Version: Local VCS
  - Currently checked out files
  - Database containing different versions of other files
  - Ex: RCS
- Another Iteration: Centralized VCSs
  - Need to collaborate with people on other systems (can't do this with local only!)
  - CVCS have single server containing all of the versioned files, clients check out files from this central server
  - Standard for a long time 
  - (See figure 1.2 in Git Pro)
  -  Advantages over local:
     -  everone knows what everyone else is doing (if they're committing to the server)
     -  Admins can control who does what
     -  Easier to deal with 1 central server than multiple local servers
  - Downisdes:
    - Single point of failure
    - Local VCSs also suffer from this
- Distributed Version Control 
  - Fully mirror repository including full history
  - If any server dies, any client repo can be copied to server to restore
  - **Clones are backups**
  - Deal with having several remopte repos to work with - collaborate with different groups of people simultaneously
  - New workflows possible that aren't possible in centralized systems (e.g. hierarchical models)
- History of Git
  - In early years of Linux development, devs used a proprietary DVCS called BitKeeper
  - Relations got bad with the company developing BitKeeper got bad, and the Linux devs decided to make their own version
  - New system needed to:
    - Fast
    - Simple
    - Support non-linear development
    - Distributed
    - Handle Large Systemn
  - Thus, Git was born

## What is Git?
- Distributed Version Control System
- Key difference in how Git sees its data:
  - Most systems store info as list of file-based changes (delta-based VC)
  - Git considers its data as a series of snapshots of a filesystem
    - Think of it like taking a picture of what your files look like @ that moment
  - Git, therefore, is almost like a miniature filesystem
- Most operations are local
  - No info needed from another machine on the network
  - This is fast (no network overhead)
  - This means that you can commit to your local even when offline
- Git Has Integrity
  - all commits are checksummed (impossible to change contents without git knowing)
  - Git uses an SHA-1 hash for its checksumming
    - 40 char string of hex calculated based on the contents of a file
- Git (Generally) Only Adds Data
  - nearly all actions only *add* data
  - this is to make sure that almost everything is undoable
  - to make sure you don't lose work, COMMIT!
    - Git doesn't know what you've done until you commit
- Files exist in one of three states:
  - modified: changed but not committed
  - staged: marked to go into the next commit snapshot
  - committed: stored in local database
- Three main sections of a Git projet:
  - working tree: single checkout of one version of the project
  - File that stores info about what goes into the next commit
  - Git Directory: where git stores the metadata and object database for your project (this is what's copied when you clone a repo from another computer)
  - Figure 1.6 illustrates the typical workflow w/ Git
- There are a lot of ways to use Git
  - Command line tools (what we will use)
  - Graphical interfaces (such as the Github interface)
- Why command line?
  - Most fully featured
  - Only place you can run ALL git commands
  - If you can do command-line git, you can do graphical git

## Installing Git
<hr>

**Recommended Approach**: Follow the appropriate instructions for your operating system at <a href=https://git-scm.com/downloads>this link</a>.

You can also install from source, instructions for which are detailed <a href="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git">here</a>. Personally, I would recommend against this as it is slightly more involved than using one of the installer methods. However, this version will likely leave you with a newer version than the installers do. This shouldn't matter for the scope of this class, but if you are interested, you can always check this out.


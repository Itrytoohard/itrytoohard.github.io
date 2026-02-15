# Git Notes
####### 2/15/2026

## Commands to display state

### state of git repo

* `git branch` : list all branches in local repo


### state of project

## Relations Between Commits

`O <-- O`

Child nodes point to their parent(s).
When a new commit is created, it is a new child node

#### Why not the other way around?

Because the old commit contains no new information. And the Acyclic nature means that only one of the node can know about the other.

## Hidden Behavior:

What git does without explicitly saying so

#### `git commit`:

* Creates a new node with your current project state (minus anything you've excluded from the staging area).
* Hashes the entire project (*not* just the changes) + project metadata.
* Creates a new node with the changes you have made since the parent commit.
* Moves the current branch pointer to the new commit
* 

A commit is the entire snapshot of a project, so while git may compress the data by analyzing similarities, it doesn't *only* operate on those similarities.

Data Model:
Inside a commit is the state of the entire project.

Reality:
git compresses things by storing references to blobs that it shares with other commits. However, when any action is performed, it does not just act on the reference, but follows the blob references to the blobs.

## A Branch is simply a pointer to a commit.

While tempting (and outwardly logial) to think of a branch as a chain of commits that starts from the first (or 0th) commit since diverging from the main branch, this is not strictly in line with how they behave. In reality, a branch is just a reference to the most recent commit 

## Realizing after committing that you should have started a branch:

Often, you will make some changes, commit, repeat a few times, then realize that what you're doing should have been on a branch the whole time. But its kind of a pain to do so at this point right? Wrong! If you could simply pull back main by `x` commits, as long as you could name the new branch, you'd be golden. But if 

>From main
```
git commit
git commit
git commit
git branch shouldHaveBranchedEarlier (creates a branch at the current head, but doesnt switch to it)
git checkout shouldHaveBranchedEarlier (cannot force following command if still on the same branch)
git branch -f main HEAD~3 (moves the main branch pointer 3 commits back. The shouldHaveBranchedEarlier branch pointer remains at the farthest commit)
git checkout shouldHaveBranchedEarlier (go back to the version of the project you'd been working on)
```
## heads vs HEAD : 

A head is a pointer to a commit. By default, it moves with 

A head 

A head is not a property of a branch itself.

HEAD is the pointer that by default points to the current branch's head.

### Google Searches:

#### does a git commit make a new parent or child node in a DAG?
A git commit creates a **new child node** in the directed acyclic graph (DAG). This new commit points back to the previous commit (or commits, in the case of a merge) as its **parent(s)**. Here is how it works within the DAG structure:

*   **Commits as Nodes**: Each commit is a node (or vertex) in the graph.
    
*   **Pointers to Parents**: Each commit object contains pointers to its immediate parents.
    
    *   A normal commit has exactly one parent, which is the commit that was at the HEAD of the branch when the new commit was made.
        
    *   A merge commit has two or more parents, connecting two or more lines of history.
        
    *   The initial (root) commit has no parents.
        
*   **Directionality**: The "directed" nature of the DAG means the relationships are one-way; commits know their parents, but parents do not contain information about their children. This structure naturally prevents cycles (hence "acyclic").
    
*   **Branch Movement**: When a new commit is created, the current branch reference (a "post-it note" in Git terminology) automatically moves forward to point to this new child commit.

#### Does a git hash hash the whole project or just the changes?

A Git commit hash hashes the **entire state of the project at that point in time**, not just the changes. It is a unique fingerprint that includes all the file contents, directory structure, and metadata of the commit. The information that is used to generate a commit hash includes:

*   The hash of the **root directory's tree object**, which recursively contains hashes for all files (blobs) and subdirectories within the project.
    
*   Metadata about the commit, such as the **author** (name, email, and date) and **committer** (name, email, and date).
    
*   The **commit message**.
    
*   The hashes of its **parent commit(s)**, which links it to the project's history. 
    

Because the hash depends on the parent commit's hash, it forms a secure, linked chain of history, ensuring the integrity of the entire project history. Any change to a file, the commit message, or even the timestamp would result in a completely different commit hash. This is why operations like rebasing or amending a commit create new commits with new hashes.

#### Everything git does when you run `commit`

When you run git commit, Git performs a series of actions to permanently record the changes that are currently in your **staging area** (also known as the index) into your **local repository**. Here is a breakdown of what happens:

*   **Creates a snapshot**: Git takes a snapshot of the files exactly as they are in the staging area. It does not store differences (deltas) like older systems; instead, it stores a complete picture of the project files at that specific moment.
    
*   **Creates a commit object**: A unique commit object is created in Git's internal database (located in the hidden .git/objects folder).
    
*   **Adds metadata**: The commit object is populated with essential metadata:
    
    *   A unique **SHA-1 hash identifier**.
        
    *   The author's name and email.
        
    *   The date and time of the commit.
        
    *   The commit message you provided.
        
    *   A pointer to the parent commit(s) (linking the history together).
        
    *   A pointer to a **tree object**, which represents the directory structure and file contents (stored as **blob objects**) of that snapshot.
        
*   **Updates the branch pointer**: The current branch's pointer (e.g., main or master) is automatically moved forward to point to this new commit, making it the latest commit on that branch.
    
*   **Saves locally**: The new commit is saved to your local repository only. It is not automatically sent to any remote repositories (like GitHub or GitLab). The changes only become visible to others when you explicitly run the git push command. 
    

The commit process effectively seals the staged changes into the project's history, creating a safe, unchangeable record that you can return to or compare against at any time.

#### does a git commit contain the entire state of the project or just the differences?
A Git commit stores a **snapshot of the entire project** at a specific point in time, not just the differences (diffs) from the previous commit. 

**How Git Commits Work**

*   **Logical Model (Snapshots):** Conceptually, every commit is a self-contained snapshot of the entire directory structure and file contents. This design allows Git to instantly access any historical version of a file without having to replay a series of incremental changes (deltas). Operations like git checkout are fast because they simply need to reconstruct the working directory from the snapshot data.
    
*   **Physical Storage (Efficiency):** To save disk space, Git employs clever storage optimizations.
    
    *   **Content-Addressable Storage:** Files are stored as "blob" objects, identified by a unique SHA-1 hash of their content. If a file has not changed from one commit to the next, the new commit's snapshot simply reuses the pointer to the existing blob object, rather than storing a duplicate copy.
        
    *   **Packfiles and Deltas:** Periodically, or during garbage collection (git gc), Git compresses older, "loose" objects into highly efficient "packfiles". Within a packfile, Git identifies similar versions of files and stores them as deltas (differences) against one another. This is a compression optimization, not the primary data model. 
        

In essence, you can think of commits as full, independent snapshots that are stored efficiently on the disk by sharing data where possible. Git commands like git diff dynamically calculate the differences between two snapshots when you run them.


### _old_google_text_
#### Does a git hash hash the whole project or just the changes?

A Git commit hash hashes the **entire state of the project at that point in time, not just the changes**. It is a unique fingerprint that includes all the file contents, directory structure, and metadata of the commit.
The information that is used to generate a commit hash includes:
* The hash of the root directory's tree object, which recursively contains hashes for all files (blobs) and subdirectories within the project.
* Metadata about the commit, such as the author (name, email, and date) and committer (name, email, and date).
* The commit message.
* The hashes of its parent commit(s), which links it to the project's history.
Because the hash depends on the parent commit's hash, it forms a secure, linked chain of history, ensuring the integrity of the entire project history. Any change to a file, the commit message, or even the timestamp would result in a completely different commit hash. This is why operations like rebasing or amending a commit create new commits with new hashes.


#### Everything git does when you run `commit`
When you run git commit, Git performs a series of actions to permanently record the changes that are currently in your staging area (also known as the index) into your local repository.
**Here is a breakdown of what happens:**
* Creates a snapshot: Git takes a snapshot of the files exactly as they are in the staging area. It does not store differences (deltas) like older systems; instead, it stores a complete picture of the project files at that specific moment.
* Creates a commit object: A unique commit object is created in Git's internal database (located in the hidden .git/objects folder).
    * Adds metadata: The commit object is populated with essential metadata:
    * A unique SHA-1 hash identifier.
    * The author's name and email.
    * The date and time of the commit.
    * The commit message you provided.
    * A pointer to the parent commit(s) (linking the history together).
    * A pointer to a tree object, which represents the directory structure and file contents (stored as blob objects) of that snapshot.
* Updates the branch pointer: The current branch's pointer (e.g., main or master) is automatically moved forward to point to this new commit, making it the latest commit on that branch.
* Saves locally: The new commit is saved to your local repository only. It is not automatically sent to any remote repositories (like GitHub or GitLab). The changes only become visible to others when you explicitly run the git push command.
The commit process effectively seals the staged changes into the project's history, creating a safe, unchangeable record that you can return to or compare against at any time.

#### does a git commit contain the entire state of the project or just the differences?

A Git commit stores a snapshot of the entire project at a specific point in time, not just the differences (diffs) from the previous commit.
**How Git Commits Work**
* Logical Model (Snapshots): Conceptually, every commit is a self-contained snapshot of the entire directory structure and file contents. This design allows Git to instantly access any historical version of a file without having to replay a series of incremental changes (deltas). Operations like git checkout are fast because they simply need to reconstruct the working directory from the snapshot data.
* Physical Storage (Efficiency): To save disk space, Git employs clever storage optimizations.
    * Content-Addressable Storage: Files are stored as "blob" objects, identified by a unique SHA-1 hash of their content. If a file has not changed from one commit to the next, the new commit's snapshot simply reuses the pointer to the existing blob object, rather than storing a duplicate copy.
    * Packfiles and Deltas: Periodically, or during garbage collection (git gc), Git compresses older, "loose" objects into highly efficient "packfiles". Within a packfile, Git identifies similar versions of files and stores them as deltas (differences) against one another. This is a compression optimization, not the primary data model.
In essence, you can think of commits as full, independent snapshots that are stored efficiently on the disk by sharing data where possible. Git commands like git diff dynamically calculate the differences between two snapshots when you run them.

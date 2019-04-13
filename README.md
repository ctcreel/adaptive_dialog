# Adaptive Dialog
The repo contains all of the dialog content for the Adaptive platform.  This repository will be automatically uploaded for every commit to the master branch.

The platform will fetch the content options in the dialog files in this repo based on the _subject_ and _context._  The subject is the specific thing that a user is looking at in an engagement or interaction.  The context is the situation that lead to the engagement or interaction. For example, a user could write a negative piece of feedback or include negative language in their personal improvement objectives.  These are two different sitations (two different contexts) that share the same subject - negative language.

Each dialog file in this repo is therefore organized in to directories that denote context and subject in the following format:

`adative-content/dialog/context/sub-context/.../subject.txt`

Where `...` could be multiple sub-contexts and the name of the dialog file is the subject ID.  The way this will be represented in DynamoDB is - 

 - __Hash__ - `context#sub-context#...`
 - __Subject__ - `file name without the txt`
 - __Dialog__ - `{dialog:["dialog option 1", "dialog option 2", "dialog option 3"]}`
 
 In the example above, when the user is working on writing a piece of feedback, the platform will respond by looking up the context `feedback#coaching#sentiment` and then the subject  `negative`.
 
 ## Naming Conventions
 The names of the contexts and sub-contexts should be only one or two words. This is also true of the name of the subject, or dialog file. If using two words then the first word must be an adjective (e.g., very).

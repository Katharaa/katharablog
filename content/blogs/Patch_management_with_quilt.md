---
title: "Patch management with quilt :)"
date: 2024-03-08
draft: false
ShowToc: true
slug: 
category: blog 
summary:
description: 
cover:
  image:
  alt:
  caption: 
  relative: true
showtoc: true
draft: false
--- 

In Debian packaging, a patch refers to a file containing changes to a source file or directory. 
**They help you fix bugs, add features, or make other changes without affecting the original code directly.**
Quilt is a tool used to manage these patches efficiently.Patches are like small updates to your code. 


## Common Terms :

*   **Export QUILT\_PATCHES:** This command sets the environment variable QUILT\_PATCHES to specify the directory containing patches. For example: `export QUILT_PATCHES=debian/patches`.
*   **Quilt Push:** Applies patches to the source files. The `-a` flag applies all patches. Usage: `quilt push -a`.
*   **Quilt New:** Creates a new patch. Use this command when manual patching is required. Usage: `quilt new <patch_name>`.
*   **Adding a File:** To add a file to a patch, use the `quilt add` command. For example: `quilt add README` (where 'README' is the name of the file you want to modify).
*   **Quilt Refresh:** Updates a patch with changes made to its files. This command can be executed as often as needed. Usage: `quilt refresh`.
*   **Quilt Header:** Edits the header of a patch. You can use this command to add descriptions or update the metadata of the patch. For example: `quilt header -e --dep3`.
*   **Quilt Pop:** Removes all patches from the stack and returns the source to its original state. Usage: `quilt pop -a`.
  

*  **.pc/ Directory:** This directory, hidden from plain sight, stores vital information about each patch, including its name, description, and application status. It acts like a behind-the-scenes organizer for Quilt's patching operations.

* **Series File:** This file acts as the roadmap for applying patches. It contains a simple list of patch names, indicating the exact order in which Quilt should apply them. Imagine it as a recipe for Quilt, guiding it through the patching process step-by-step.

Tutorial :
--------

### Exporting Quilt 

To begin, export the `QUILT_PATCHES` environment variable to specify the directory containing patches:

    export QUILT_PATCHES=debian/patches

### Applying Patches 

Apply patches using the `quilt push -a` command:

    quilt push -a

If any patch fails with an offset, follow the manual patching process.

#### Manual Patching Process :

If a patch fails with an offset, you'll need to apply it manually. For example:

        Applying patch 008-setup-xstatic
        patching file setup.py
        Hunk #1 FAILED at 90.
        1 out of 1 hunk FAILED -- rejects in file setup.py
        Patch 008-setup-xstatic does not apply (enforce with -f)

If you encounter an error like the one above, manual patching is required. Follow these steps:

1.  Delete the failed patch from the patches directory and the series file
2.  Create a new patch with `quilt new` and manually apply changes to the file
3.  Add the file to the patch with `quilt add`
4.  Edit the file using `quilt edit`
5.  Refresh the patch with `quilt refresh`

#### Handling Patches with Offsets :

If a patch fails with an offset, For example:

        Applying patch 010-setup-contrib-intermap
        patching file setup.py
        Hunk #1 succeeded at 63 (offset 1 line).
    
        Applying patch 011-setup-package-data
        patching file setup.py
        Hunk #3 succeeded at 67 (offset 1 line).
        
Follow these steps:

1.  If a patch fails with an offset, use `quilt pop -a` to revert changes
2.  Push the failed patch individually using `quilt push <patch_name>`
3.  Refresh the patch with `quilt refresh`
4. Do `quilt push -a` to apply all the patches again
5.  Repeat the process until all patches are successfully applied

### Before Committing :

Before committing changes, ensure all patches are popped. *(Also Remember not to commit this directory to version control as it contains temporary and metadata files specific to the patch management process.)*


    quilt pop -a
    git add debian/patches/
    git commit -m "Applied patches using Quilt"


    quilt pop -a
    git add debian/patches/
    git commit -m "Applied patches using Quilt"
    



--------------------------------------------------------------



# DLORG Nike Törnros

## Short introduction
Welcome! I have created a bash-based organization system that automatically sorts files in a simulated 'Downloads' folder on a computer. Link to **[video explanation](insertlink.here)**.

## Script functions
`sort_script` creates relevant directories and moves files into their corresponding directories based on file extensions. File prefix can also be used for further organization.

**Note**: Files must be present in `dlorg_nike_tornros/Downloads` in order to be affected by `sort_script`.

`monitor_script` monitors our `Downloads/` directory. Whenever a file enters this directory, `sort_script` is automatically triggered. Automatically launches on startup and continously runs.

`ignore.gitignore` makes Git ignore irrelevant files, such as Vim's `.swp` files.

## Structure

- "Downloaded" (created) files end up in `~/Documents/github/dlorg_nike_tornros/Downloads/`, simulating a downloads folder on a computer.
- *An older, archived, iteration of `sort_script` can be found in `admin/archived_codes`*.

With all relevant directories in use, the structure will look like this:

![tree_structure](admin/tree_structure.png)

## How it works

1. `monitor_script` launches when computer boots. If a file is moved into `Downloads`, `sort_script` gets triggered.

2. `sort_script` creates directories, if any are missing or **have been deleted**.

3a. `sort_script` checks the files in the `Downloads/` directory and determines which directory each file belongs in based on its **file extension**. For example:
- *.tixt, *.md, *.rtf --> `Downloads/text`
- *.mov, *.mp4, *.mkv, *.avi --> `Downloads/video`

3b. Some directories contain subdirectories. For example, files belonging in the umbrella-directory`Downloads/slides` are further organized based on their file type, `/slides/powerpoint`, `/slides/keynote` and `/slides/others`. This was done in order to showcase the script working with subdirectories.

- *.pptx --> `Downloads/slides/powerpoint`
- *.key --> `Downloads/slides/keynote`

3c. Files can also be moved into subdirectories based on prefix, for example:
- contract_*.pdf --> `Downloads/pdf/contracts`


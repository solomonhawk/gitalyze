# gitalyze

Gitalyze is a general purpose utility for mapping programs across commits in a [git](https://git-scm.com/) repository.

# Requirements

- bash
- [git](https://git-scm.com/)

# Setup

For now it's required that you add the path of the `gitalyze/bin` folder to your `PATH` environment variable for logging to work properly. Depending on your exact setup, the process may differ slightly.

# Usage

    $ gitalyze [options]
      -b BRANCH_NAME         The branch to analyze.
      -r REVISION_STRING     Revision string range to inspect.         (r - revision)
                                 This is a special format that `git rev-list`
                                 knows how to understand. If using the space-
                                 delimited form, wrap the parameter in quotes.
      -t FOLDER_PATH         Path to the temp directory.               (t - temp)
      -f EXECUTABLE_PATH     Run before analysis of each commit.       (f - before)
      -e EXECUTABLE_PATH     Run on each file in each commit.          (e - each)
                                 Note: may run on .gitignored files, but not
                                 on the .git or node_modules directorires.
      -a EXECUTABLE_PATH     Run after analysis of each commit.        (a - after)
      -d EXECUTABLE_PATH     Run after all commits are analyzed.       (d - done)
      -p GIT_PROJECT_PATH    Path or URL to 'git clone' for analysis.  (p - project/path)
      -x IGNORED_DIRS        List of files to ignore.                  (x - exclude)
                                Space delimited list of `path` identifiers.

      -l LOG_PATH            Path to log output file.
      -v                     Turn on verbose mode.

      -h                     Print this usage message.

# Example

    $ gitalyze -p git@github.com:solomonhawk/gifs-to-gifs.git \
               -r ba4c9ff..HEAD \
               -f gz.before \
               -e gz.file-size \
               -d gz.after \
               -l log.txt

You can specify multiple programs to execute for each hook:

    $ gitalyze -f "scriptA scriptB scriptC"

The above command would use the following:
- Default repo = `pwd`
- Default branch = `master`
- Default revision range = `complete history of selected branch`
- `-f "scriptA scriptB scriptC"` run all 3 programs before each commit
# gitalyze

Gitalyze is a general purpose utility for mapping programs across commits in a [git](https://git-scm.com/) repository.

# Requirements

- bash
- [git](https://git-scm.com/)
- [jq](https://stedolan.github.io/jq/)

# Setup

It's handy to add the path to the `gitalyze` binary to your `PATH` environment variable. Depending on your exact setup, the process may differ slightly.

# Usage

    $ gitalyze [options]
      -b BRANCH_NAME         The branch to analyze.
      -r REVISION_STRING     Revision string range to inspect.         (r - revision)
      -t FOLDER_PATH         Path to the temp directory.               (t - temp)
      -f EXECUTABLE_PATH     Run before analysis of each commit.       (f - before)
      -e EXECUTABLE_PATH     Run on each file in each commit.          (e - each)
                               Note: may run on .gitignored files, but
                               not on the .git directory itself.
      -a EXECUTABLE_PATH     Run after analysis of each commit.        (a - after)
      -d EXECUTABLE_PATH     Run after all commits are analyzed.       (d - done)
      -p GIT_PROJECT_PATH    Path or URL to 'git clone' for analysis.  (p - project/path)
      -v                     Turn on verbose mode.

      -h                     Print this usage message.

The git-diffall script provides a directory based diff mechanism
for git.  The script relies on the diff.tool configuration option
to determine what diff viewer is used.

This script is compatible with all the forms used to specify a range of revisions to diff:

  1. git diffall: shows diff between working tree and staged changes
  2. git diffall --cached [<commit>]: shows diff between staged changes and HEAD (or other named commit)
  3. git diffall <commit>: shows diff between working tree and named commit
  4. git diffall <commit> <commit>: show diff between two named commits
  5. git diffall <commit>..<commit>: same as above
  6. git diffall <commit>...<commit>: show the changes on the branch containing and up to the second, 
	 starting at a common ancestor of both <commit>

Note: all forms take an optional path limiter [--] [<path>*]

This script is based on an example provided by Thomas Rast on the Git list [1]:
[1] http://thread.gmane.org/gmane.comp.version-control.git/124807

Forked to add in an araxisgitdiffall AppleScript and modified git-diffall to use a customized diff tool.

	[diffall]
		external = /path/to/your/bin/araxisgitdiffall

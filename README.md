# bm

[bm](https://github.com/mcstafford-git/bm-bookmarks) is a set of shell
bookmark scripts adapted from a page on [jeroen janssens' website](http://jeroenjanssens.com/2013/08/16/quickly-navigate-your-filesystem-from-the-command-line.html).

I thought it might work well to add a different pattern to the commands
and worked them around.

## usage

- `bm`  - add bookmark

      $ cd /some/very/deep/often-used/directory
      # uses basename of ${PWD} as a default
      $ bm
      +  directory  ->  /some/very/deep/often-used/directory
      # otherwise, uses whatever first word you provide
      $ bm deep
      +  deep  ->  /some/very/deep/often-used/directory

- `bma` - audit (finds broken symlinks, if any)

      $ bma
      ?  broken  ->  /some/dir/since/(re)moved

- `bmc` - chdir [SUBDIR]

      $ pwd
      /some/dir

      $ bmc directory
      $ pwd
      /some/very/deep/often-used/directory

      $ bmc directory/sub
      $ pwd
      /some/very/deep/often-used/directory/sub

- `bml` - list

      $ bml
      =  deep       ->  /some/very/deep/often-used/directory
      =  directory  ->  /some/very/deep/often-used/directory
      =  thing1     ->  /tmp/thing1

- `bmr` - rm

      $ bmr directory
      -  directory  ->  /some/very/deep/often-used/directory

- `bmu` - update (calls `bmr [NAME]`, then `bm [NAME]`)

      $ pwd
      /tmp/thing1

      $ bmu
      -  thing1  ->  /var/tmp/thing1
      +  thing1  ->  /tmp/thing1

      $ bmu thing2
      -  thing2  ->  /var/tmp/thing1
      +  thing2  ->  /tmp/thing1

## dependencies

- [bash](https://www.gnu.org/software/bash/)
- [util-linux](https://kernel.org/pub/linux/utils/util-linux)'s `column`

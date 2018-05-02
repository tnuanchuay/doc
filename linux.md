# Linux Recommend Command line
### list all file extension recursively through directory
```sh
find . -path ./.git -prune -o -name '*.*' -print | awk '{n=split($0, a, "."); print a[n]}'
```

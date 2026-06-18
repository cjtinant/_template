# Shell Commands

## Remove macOS custom icon files -- Icon followed by carriage return char

Two steps: delete locally, then add to .gitignore so they don't come back.

Delete locally (run from project root):

`````bash
find . -name $'Icon\r' -delete

```

Remove from Git tracking if already committed:

````bash

git rm -r --cached .
git add .
git commit -m "chore: remove macOS"

`````

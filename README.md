# Delete Merged Branches

Since not all Git systems support the automatic deletion of merged branches like GitHub, this script can be used to automatically delete such branches via CI.
To do this, this script must be executed on the default branch of the repository.
Branches can be defined with the help of a whitelist, which are ignored by the script.

## Whitelist

In the whitelist, the names of branches that are not to be deleted by the script can be defined.
These are defined in a **whitelist** file and one name is defined per line, e.g.
```
main
release/
```
The script ignores all branches that contain a name from the file.
This is done via the command:
> grep -v "*name*"

## Configuration

The script can be configured via the following environment variables:
|Name|Description|
|---|---|
|ORIGIN|The remote to push to, default is *origin*.|
|DRY_RUN|If this variable is set to a non-empty value, the script only prints the branches that would be deleted.|

1. install this by `vsce package` and then install from `.vsix` file

ref: https://code.visualstudio.com/api/working-with-extensions/publishing-extension

2. add a `cscope_conf.json` file under `.vscode` dir in your project, here is an example:
```
{
   "open_new_column": "no",
   "engine_configurations": [
      {
         "cscope": {
            "paths": [
               "${workspaceRoot}/src_code_dir1",
               "${workspaceRoot}/src_code_dir2",
               "${workspaceRoot}/src_code_dir3",
               "${workspaceRoot}/src_code_dir4",
               "${workspaceRoot}/src_code_dir5"
            ]
         }
      }
   ]
}
```

3. go to settings, and search `scope4code`, customize the `find_cmd`, coz we could have different extensions for c/c++ files.
Here is an example:
```
    "scope4code.engineCommands": {
        "config": [
            {
                "find_cmd": "find ${src_path} -type f -name *.[cChH] -o -type f -name *.[ch]pp -o -type f -name *.[sS][qQ][cC] -o -type f -name *.skl -type f -name *.[ce]c -o -type f -name *.mm"
            }
        ]
    }
```
by default, `index 0` of `scope4code.engineCommands` array is for `linux/macos/others`, while `index 1` is for `windows`.

Ref: go to `Command customization` section of README.md in this project.
# recurisve command line tools
recursive git status powershell
```powershell
Get-ChildItem -Directory -Recurse | ForEach-Object { 
    if (Test-Path "$($_.FullName)\.git") { 
        Write-Host "Directory: $($_.FullName)"
        git -C $_.FullName status
        Write-Host "`n"
    }
}
```
recursive git status bash
```bash
find . -type d -name ".git" -execdir sh -c 'echo "Directory: $(pwd)"; git status; echo ""' \;
```

# windows power plans
balanced
```shell
powercfg /setactive 381b4222-f694-41f0-9685-ff5bb260df2e
```
ultimate performance
```shell
powercfg /setactive e9a42b02-d5df-448d-aa00-03f14749eb61
```

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

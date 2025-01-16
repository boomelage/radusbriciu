

# contact
<a
    id="cy-effective-orcid-url"
    class="underline"
     href="https://orcid.org/0009-0000-3772-0616"
     target="orcid.widget"
     rel="me noopener noreferrer"
     style="vertical-align: top">
     <img
        src="https://orcid.org/sites/default/files/images/orcid_16x16.png"
        style="width: 1em; margin-inline-start: 0.5em"
        alt="ORCID iD icon"/>
      https://orcid.org/0009-0000-3772-0616
    </a>

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
recursive pip install powershell
```powershell
Get-ChildItem -Directory | ForEach-Object {
    if ((Test-Path "$($_.FullName)\setup.py") -or (Test-Path "$($_.FullName)\pyproject.toml")) {
        Push-Location $_.FullName
        pip install .
        Pop-Location
    }
}
```


recursive git status bash
```bash
find . -type d -name ".git" -execdir sh -c 'echo "Directory: $(pwd)"; git status; echo ""' \;
```

recursive pip install .sh
```bash
#!/bin/bash

# Loop through each subdirectory
for dir in */; do
    # Check if setup.py or pyproject.toml exists in the subdirectory
    if [[ -f "${dir}setup.py" || -f "${dir}pyproject.toml" ]]; then
        echo "Installing package in $dir"
        # Change to the directory, install, and then return to the original directory
        (cd "$dir" && pip install .)
    else
        echo "No installable package found in $dir"
    fi
done
```


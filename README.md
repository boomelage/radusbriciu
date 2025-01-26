## About Me

<img src="https://photos.mendeley.com/69/ba/69bad913fd3d075f0b5ec050d29942c25c5ca4db-p128x128.jpg" alt="Radu Briciu" width="128" height="128" align="left" />


Hi, I'm **Radu Briciu**, a postgraduate student in **Quantitative Finance** at Bayes Business School, City, University of London. <br>

I am passionate about research and innovation in computational finance, currently looking to collaborate in topics around securities pricing, financial econometrics, and behavioural finance.

<br> <br>
Email: <a href="mailto:radu.briciu@bayes.city.ac.uk">
  <img src="https://upload.wikimedia.org/wikipedia/commons/0/01/Arms_of_City%2C_University_of_London.svg" alt="City, University of London" width="20" align="top"/>
</a>

## Academic Interests

- **Primary Discipline:** Economics, Econometrics and Finance
- **Focus Areas:** Financial modelling, quantitative methods, and econometric analysis



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


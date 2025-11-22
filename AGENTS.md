# Repository Guidelines

## Project Structure & Module Organization
- `CSharp/`: .NET Core 2.2 console sample (`Program.cs`, `ODataComposer.cs`, `Models/`) for downloading and printing StatLine tables.
- `Python/`: Standalone scripts (`basics.py`, `thematic_map.py`, `time_series_graph.py`) using `cbsodata` + pandas.
- `R/`: R scripts mirroring the Python flows with `cbsodataR`.
- `JavaScript/`: Browser demos (`basics.html`, `thematic_map.html`, `time_serie_graph.html`) using simple fetch/mapping logic.
- Keep language-specific assets inside their folder; no shared libraries across languages.

## Build, Test, and Development Commands
- C#: `cd CSharp && dotnet restore && dotnet run` (sample download + console output). Use `dotnet build` for a fast compile check.
- Python: `pip install pandas cbsodata` then `python basics.py` (or other scripts); edit dataset IDs inside the files as needed.
- R: `Rscript basics.R` (or other scripts) after `install.packages("cbsodataR")`.
- JavaScript: `cd JavaScript && python -m http.server 8000` and open `http://localhost:8000/basics.html`; static file open also works for quick checks.

## Coding Style & Naming Conventions
- Follow existing idioms: PascalCase for C# types/properties, camelCase for locals; 4-space indentation.
- Python: PEP8-friendly snake_case for files and variables; keep imports explicit and side effects minimal.
- R: lowercase with underscores, `<-` assignment; keep brief header comments describing dataset and intent.
- JavaScript: prefer `const`/`let`, descriptive names, minimal globals; keep HTML/JS readable and commented only where behavior is non-obvious.
- Preserve Dutch explanatory comments; add concise English notes only when clarifying API usage.

## Testing Guidelines
- No automated suite; validate by running each sample without errors.
- Before pushing, run `dotnet build`, each modified Python/R script, and load the HTML demos via a local server to confirm network calls and map rendering.
- For new samples, include a short usage note at the top (dataset ID, expected output shape).

## Commit & Pull Request Guidelines
- Use short, imperative commit messages (pattern in history: “Update thematic_map.R”, “Bump Newtonsoft.Json…”); include scope when helpful.
- PRs should state what changed, which language folders are affected, and any dataset/API notes. Link related CBS documentation or issues; add screenshots for visual JS updates.
- Do not commit large downloaded datasets; keep generated outputs out of version control.

# BigShell: POSIX Shell Clone

**BigShell** is a custom-built command-line shell that emulates core behaviors of a POSIX-compliant shell. It was developed as a senior project to explore advanced system-level programming concepts in C, including process management, I/O redirection, signal handling, and environment variable manipulation.

> **Note:** Due to academic integrity restrictions, source code is not published in this repository. Only compiled binaries, screenshots of test runs, and the final technical report are provided.

---

## Project Showcase

- **Screenshots**: 
BigShell supports key POSIX shell features including built-ins, job control, pipelines, I/O redirection, and signal handling.

The following categories are demonstrated in annotated test examples:

- `exit` built-in with custom status codes
- Variable assignment and `export` to environment
- Output redirection (`>`), with overwrite protection
- Command pipelines using `|` (e.g., `echo | sed | cat`)
- Signal handling (e.g., `SIGINT`, `SIGTSTP`, `SIGTTOU`)
- Background jobs with `$!` tracking

> View annotated terminal tests and screenshots:  
> [`BigShell_Annotated_Tests.pdf`](./docs/screenshots/BigShell_Annotated_Tests_072325_v01.pdf)

- **Executable Binaries**:  
  - `release/` — optimized build  
  - `debug/` — debug symbols included  
- **Documentation**:  
  - Full system report: [`BigShell_Report.pdf`](./docs/CS374_BigShell_Report_113024_v04.docx)

---

## Features Implemented

BigShell handles a significant subset of POSIX shell functionality, including:

- **Built-in Commands**:  
  `cd`, `exit`, `unset`, `export`, `pwd`, `fg`, `bg`, `jobs`

- **External Command Execution**:  
  Run binaries available in `$PATH`

- **Pipelines**:  
  Chain commands using `|` operator

- **I/O Redirection**:  
  Support for `<`, `>`, `>>`, `<>`, `>|`, `<&`, `>&`

- **Environment Variables**:  
  Assignment, export, evaluation (`$VAR`, `${VAR}`, `~` expansion)

- **Foreground/Background Jobs**:  
  Commands run with `;` (foreground) or `&` (background)

- **Signal Handling**:  
  Intercept `SIGINT`, `SIGTSTP`, and forward signals to child processes

---

## Learning Takeaways

This project was a deep dive into:

- POSIX system calls (`fork`, `execvp`, `waitpid`, `pipe`, `dup2`, `kill`, `tcsetpgrp`)
- Shell parsing techniques and token expansion
- Job control and process group management
- File descriptor manipulation and redirection
- Debugging with `gdb` in a remote server environment

---

## Build Instructions

The project includes a `Makefile` to streamline compilation:

```bash
make           # Builds both release and debug versions
make release   # Builds optimized executable in release/
make debug     # Builds debug executable with symbols in debug/
make clean     # Removes all build artifacts (release/ and debug/)
```

### Output Structure

- `release/bigshell` – Optimized executable (no debug output)
- `debug/bigshell` – Debug build with assertions and verbose messages

To run the shell:

```bash
cd release/
./bigshell
```

To debug:

```bash
cd debug/
gdb ./bigshell
```

---

## Documentation

See the final report: [`BigShell_Report.pdf`](./docs/CS374_BigShell_Report_113024_v04.docx)

Screenshots: available under [`docs/screenshots/`](./docs/screenshots/BigShell_Annotated_Tests_072325_v01.pdf)

---

## Directory Structure

```
.
- release/                                  # Compiled release version
- debug/                                    # Compiled debug version with symbols
- docs/
  -- CS374_BigShell_Report_113024_v04.docx  # Full project report
  -- screenshots/                           # Images of the shell in action
- README.md                                 # This file
```

---

## Author

Built with C and grit.  
See more projects at [https://github.com/Luckygoldjade](https://github.com/Luckygoldjade)

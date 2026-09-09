# Phase 1 — Weeks 1–8: Linux, Networking, Python, Git

Use 60–120 minutes per day. Do the lab before reading the answer/checkpoint. Save commands, notes, and failures in your own lab repo.

## Week 1 — Linux process model and shell fluency
**Day 1 — Processes and PIDs.** Learn process, parent/child process, PID, foreground/background. Lab: run `ps aux`, `ps -ef`, start `sleep 300`, find its PID, then stop it. Exit: explain what a process is and why a PID matters.
**Day 2 — Shell navigation and files.** Practice `pwd`, `ls -la`, `cd`, `mkdir`, `touch`, `cp`, `mv`, `rm`, `cat`, `less`, `head`, `tail`. Lab: create a fake app directory and inspect it entirely from CLI. Exit: navigate without File Explorer.
**Day 3 — stdin/stdout/stderr.** Learn file descriptors 0/1/2, pipes, redirection, `>`, `>>`, `2>`, `|`. Lab: separate normal and error output from a command into files. Exit: explain why logs sent to stderr matter in automation.
**Day 4 — Break/fix process lab.** Start a Python HTTP server, find the process and listening port, kill it, verify the service fails, restart it. Use `ps`, `ss -lntp`, `curl`. Exit: troubleshoot process → port → HTTP.
**Day 5 — Signals and exit codes.** Learn SIGTERM vs SIGKILL and `$?`. Lab: terminate processes cleanly and forcibly; write a tiny shell command sequence that stops on non-zero exit. Exit: explain why CI/CD cares about exit codes.
**Day 6 — Interview drill.** Answer aloud: “A Linux service is down. What do you check first?” Use process → port → logs → dependencies → resources. Practice 10 minutes.
**Day 7 — Review.** Rebuild the HTTP-server troubleshooting lab from memory. Write `runbooks/linux-process-triage.md` with symptoms, commands, interpretation, and recovery.

## Week 2 — Filesystems, permissions, users, services
**Day 1.** Learn absolute vs relative paths, `/etc`, `/var`, `/tmp`, `/home`, `/proc`. Lab: inspect these directories in WSL/Linux and identify what each stores.
**Day 2.** Learn owner/group/other plus read/write/execute. Practice `ls -l`, `chmod`, `chown`, numeric modes such as 644 and 755. Exit: explain why execute on a directory differs from execute on a file.
**Day 3.** Learn users, groups, `id`, `whoami`, `sudo`. Lab: inspect your memberships and file ownership. Explain least privilege.
**Day 4.** Failure lab: create a script that fails with permission denied, diagnose from `ls -l`, fix the minimum permission, then reverse it.
**Day 5.** Learn service management concepts with `systemctl` where available; inspect status/logs for a service. In WSL without systemd, document the difference.
**Day 6.** Interview drill: “Why does my app work as root but fail as a service account?” Give three likely causes and evidence for each.
**Day 7.** Review by writing a permissions cheat sheet and a one-page “Linux filesystem map” from memory.

## Week 3 — IP, ports, TCP, UDP
**Day 1.** Learn IP address, loopback, interface, subnet at a conceptual level. Inspect `ip addr` and identify loopback vs active interface.
**Day 2.** Learn ports and sockets. Use `ss -lntp` and map a process to a listening port. Explain source vs destination port.
**Day 3.** Learn TCP three-way handshake, reliable byte stream, retransmission; contrast UDP. Use `curl -v` against a local service and identify connection establishment.
**Day 4.** Failure lab: run an app on the wrong port, attempt connection to the expected port, then diagnose whether the failure is DNS, TCP, or HTTP.
**Day 5.** Bind addresses: compare `127.0.0.1` and `0.0.0.0`. Run the same service with each binding and explain reachability differences.
**Day 6.** Interview drill: “Connection refused vs timeout — what do they usually indicate?” Answer with network-layer reasoning.
**Day 7.** Draw client → source port → network → destination IP:port → server process. Reproduce the wrong-port lab from memory.

## Week 4 — DNS, routing, NAT, HTTP, TLS
**Day 1.** Learn DNS resolver flow and record types A/AAAA/CNAME at a practical level. Use `nslookup` or `dig` for several domains.
**Day 2.** Learn default gateway and routing table. Inspect `ip route`; explain how the OS decides where to send a packet.
**Day 3.** Learn private/public IP and NAT. Draw a home laptop reaching a public web service through a router.
**Day 4.** Learn HTTP request/response, methods, status codes, headers. Use `curl -v` and identify TCP connect, request headers, response headers, body.
**Day 5.** Learn TLS purpose, certificate identity, encryption, trust chain at a conceptual level. Inspect an HTTPS request with `curl -v`.
**Day 6.** Failure drill: given “website not loading,” walk DNS → routing → TCP → TLS → HTTP. Write which command validates each layer.
**Day 7.** Review with a one-page networking troubleshooting decision tree.

## Week 5 — Python fundamentals for operations
**Day 1.** Variables, strings, integers, booleans, lists, dictionaries. Build a server-health dictionary and print a summary.
**Day 2.** Conditions and loops. Given server status records, print only unhealthy systems.
**Day 3.** Functions and return values. Refactor health logic into `is_healthy(server)` and `summarize(servers)`.
**Day 4.** Exceptions. Add input validation and `try/except`; distinguish expected validation errors from unexpected failures.
**Day 5.** CLI arguments using `argparse`. Build a tiny health checker accepting `--host` and `--port`.
**Day 6.** DSA: arrays/lists and linear search. Write a function that finds an unhealthy host; state O(n) complexity.
**Day 7.** Review: recreate the health checker without copying previous code and explain each decision aloud.

## Week 6 — Python files, JSON, APIs, exceptions
**Day 1.** Read/write text files safely with `with open(...)`. Save health-check results to a log file.
**Day 2.** Parse JSON using `json.load` / `json.loads`. Create `servers.json` and load configuration from it.
**Day 3.** HTTP clients. Use `requests` or standard library to call an endpoint and handle status codes/timeouts.
**Day 4.** Failure lab: invalid JSON, missing file, connection timeout, 500 response. Handle each differently and print useful errors.
**Day 5.** Modules/imports. Split config, health logic, and CLI entrypoint into separate files.
**Day 6.** DSA: dictionaries/sets. Count status frequencies and deduplicate hosts. Explain average O(1) lookup.
**Day 7.** Review: build a JSON-configured endpoint checker from scratch.

## Week 7 — Python testing, logging, packaging
**Day 1.** Learn unit-test purpose. Add tests for healthy/unhealthy status logic using `pytest` or `unittest`.
**Day 2.** Boundary tests: empty config, missing keys, timeout values, malformed URLs.
**Day 3.** Logging levels DEBUG/INFO/WARNING/ERROR. Replace scattered prints with structured logging.
**Day 4.** Failure lab: intentionally introduce a bug, use a failing test and logs to isolate it, then fix it.
**Day 5.** Virtual environments and dependency pinning. Create `requirements.txt` or `pyproject.toml`; recreate environment cleanly.
**Day 6.** Interview drill: explain unit vs integration testing and why operational scripts need tests.
**Day 7.** Review: clean checkout → install dependencies → run tests → run app. Document exact bootstrap steps.

## Week 8 — Git and collaborative workflows
**Day 1.** Learn working tree, staging area, commit. Practice `git status`, `add`, `commit`, `log`.
**Day 2.** Branches. Create a feature branch, make a change, compare branches, merge it.
**Day 3.** Learn remote, fetch, pull, push, upstream. Explain local vs remote branch.
**Day 4.** Conflict lab: create conflicting changes on two branches, resolve manually, verify final result.
**Day 5.** Commit quality. Rewrite noisy changes into small logical commits; write useful messages explaining why.
**Day 6.** Interview/behavioral drill: explain a safe team workflow for code review and production changes.
**Day 7.** Phase checkpoint: from an empty directory, initialize a repo, create branch, add Python health checker, tests, README, merge cleanly. No tutorial copying.

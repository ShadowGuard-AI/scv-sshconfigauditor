# scv-SshConfigAuditor
Analyzes SSH server configuration files (`sshd_config`) for security vulnerabilities and misconfigurations, providing recommendations for hardening using regular expressions and basic file parsing. The operator supplies the rules in a YAML or JSON file: this tool ships no predefined benchmark rule set. The included example_rules.yaml file is a starting point covering the absent, match, and present rule shapes, and the operator is expected to adapt or replace it. Parses configuration files (YAML, JSON) and reports deviations from the rules supplied. Comment lines are skipped before any rule is tested: a line whose first non space character is a hash is not treated as an active setting, so a commented out value neither satisfies nor fails a rule. A match rule means the file must contain a line fully matching its expression, so a missing setting is reported with an empty line field. An empty rules list exits 1 with a no rules to audit line instead of reporting a clean result.

## Install
`git clone https://github.com/ShadowGuardAI/scv-sshconfigauditor`

## Usage
`./scv-sshconfigauditor [params]`

## Parameters
- `-h`: Show help message and exit
- `-c`: Path to the configuration file (YAML/JSON) holding the rules.
- `-f`: Path to the sshd_config file.
- `-v`: Enable verbose logging (debug level).

## License
Copyright (c) ShadowGuardAI

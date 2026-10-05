# Debian 12 CIS

# 1.1.0 - Initial

## October 2026 Updates

- 1.1.2.6.4 and 1.1.2.7.4 gated on their own rule toggles
- 1.3.1.3 AppArmor profile count comparison corrected
- 1.3.1.4 complain mode test made dash-compatible and corrected
- 1.5.1 and 1.5.2 sysctl conf regex fixed, conflicting values detected
- 1.5.3 limits regex anchored to the file path
- 1.7.2 checks the gdm profile and the dconf db banner settings
- 1.7.3 checks the gdm profile and the dconf db disable-user-list setting
- 2.4.1.3 to 2.4.1.7 split into one file per control
- 4.3.3 iptables flushed test uses iptables -S without policy lines
- 5.1.2 private key mode 0600 required when group is root
- 5.1.3 public host key perms test fixed: variable name, mask /133
- 5.1.2 and 5.1.3 find -name globs quoted
- 5.1.5 sshd_config.d Banner grep missing space fixed
- 5.3.3.4.1 and 5.3.3.4.2 brace expansion replaced with explicit file list
- 5.4.1.1 to 5.4.1.3 per-user checks flag each failing account
- 5.4.1.1 to 5.4.1.3 per-user checks skipped unless deb12cis_force_user_* set
- 5.4.1.5 per-user INACTIVE check flags each failing account
- 5.4.1.5 INACTIVE default regex anchored
- 5.4.2.1 detects any non-root UID 0 account
- 5.4.2.2 and 5.4.2.3 GID 0 tests flag any non-root entry
- 5.4.2.5 root PATH test detects empty and relative entries
- 6.1.1.3, 6.1.2.2 to 6.1.2.4 and 6.1.3.3 journald tests read systemd-analyze cat-config
- 6.1.2.1.4 checks not enabled and not active instead of masked
- 6.1.3.5 rsyslog rule regexes anchored and escaped
- 6.2.4.1 to 6.2.4.10 test bodies realigned to their titles
- 6.2.4.x log, config and tool tests report every non-compliant file
- 6.3.2 cron check requires an aide --check or --update job
- 6.3.2 timer check uses dailyaidecheck units, service static or enabled
- 7.1.11 and 7.1.12 df mount point column corrected
- 7.1.12 find limited to unowned and ungrouped files
- 7.1.13 lists SUID/SGID files, fails on unpackaged or modified ones
- 7.2.5 to 7.2.8 duplicate checks sort before uniq -d
- 7.2.9 home directory mode check covers every home directory
- 7.2.9 owner check exit status and /nonexistent home corrected
- run_audit.sh: OS name and version fallback without /etc/os-release
- vars/CIS.yml: force_user defaults added, unowned search path spacing fixed
- LICENSE: company name updated to MindPoint Group - A Quantum Sky Company
- 6.2.3.6 live rule regex accepts the -S all form auditctl prints
- 6.3.3 reads the Debian AIDE config path /etc/aide/aide.conf
- 1.7.2 and 1.7.3 check system-db:gdm and the gdm.d keyfiles
- 1.7.4 to 1.7.9 dconf paths templated, section headers matched literally
- 1.7.5, 1.7.7 and 1.7.9 lock tests read every file in the locks directory
- 1.7.4 checks the user profile

## Sep26

- 6.2.3.6 was a placeholder that echoed "Manual" then asserted the output must not contain
  "Manual", so it could only ever fail and checked nothing. Replaced with conf and running
  checks on the -k privileged rules, matching 6.2.3.5

## Aug26

- 5.4.2.8 used bash process substitution. Goss runs commands under sh, which is dash on Debian,
  so the check failed to parse, produced no output and always reported compliant. Rewritten
  POSIX-safe and verified against a real host
- 5.4.1.6 used a bash [[ ]] test, so the comparison never fired, and asserted on "Failure" while
  the script echoes "failure". Both corrected, plus a guard for accounts with no last-change date
- 2.3.2.1 joined the configured NTP names with no separator, so the pattern only matched when
  exactly one pool or server was set
- Added .yamllint so the repo has a working YAML gate, and cleared the issues it surfaced in
  vars/CIS.yml (sequence indentation, comment spacing, missing trailing newline)
- 1.6.1, 1.6.2 and 1.6.3 carried an unterminated regex '!/[Ll]inux' which goss treats as a
  literal substring, so the OS-leak check never fired
- align_1.1.0 branch
  - 2.1.7: duplicated 2.1.6 ftp content replaced with ldap checks
  - 2.1.15: duplicated 2.1.14 samba content replaced with snmp checks
  - 5.3.3.3.3: duplicated 5.3.3.3.2 content replaced with use_authtok checks
  - 5.4.2.8: missing check added
  - 6.1.2.2: title and CIS_ID corrected
  - 1.4.2: title separator corrected
  - 2.1.6: package name corrected to vsftpd
  - 1.7.2: invalid YAML escaping corrected
  - 6.1.2.x tests moved to own directory, goss.yml include added
  - CISv8 references removed
  - YAML headers added
  - vars/CIS.yml defaults aligned with remediation
  - goss documentation link moved to krameff
  - run_audit.sh replaced with the current version
    - goss version discovery fixed for the krameff two line banner
    - OS discovery replaced by BENCHMARK_OS
    - AUDIT_BIN_MIN_VER raised to 0.4.8, typos corrected
  - goss.yml and vars/CIS.yml given YAML document markers
  - 6.2.4.3: checked owner not group, stat %U corrected to %G
  - 6.2.4.3: accepts root or adm, matching the benchmark
  - README updates and updated contributing and contributors

## March26

- Title updates
- meta data aligned
- renamed several variables inline with remediation role
  - deb12cis_gui to deb12cis_desktop_required
  - deb12_time_pool_name to deb12_time_pool
  - Tidy up of SSHD var naming including ciphers, Macs and Kex
  - sshd variable naming
  - deb12cis_syslog now deb12cis_syslog_type
  - deb12cis_is_syslog_server now deb12cis_system_is_log_server
- CIS_v8 references removed

## Oct25
PR #9 many thanks to @aderumier fixing 7.2.4-10 numbering
max-concurrent option added and run audit script updated

Thanks to @aderumier
- #11
- #12
- #13
- #14
- #15
- #23

## Aug25
fixed time pool naming
updated benchmark

## May 25
Initial release



# 1.0.0 - Initial
# based upon Version 1.0.1 - 15-04-2024


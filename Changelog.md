# Debian 12 CIS

# 1.1.0 - Initial

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


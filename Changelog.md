# Debian 12 CIS

# 1.1.0 - Initial

## Aug26

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


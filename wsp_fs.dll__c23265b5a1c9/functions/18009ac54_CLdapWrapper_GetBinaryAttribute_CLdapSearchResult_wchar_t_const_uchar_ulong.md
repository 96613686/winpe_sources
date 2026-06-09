# CLdapWrapper::GetBinaryAttribute(CLdapSearchResult *,wchar_t const *,uchar * *,ulong *)

- ea: `0x18009ac54`
- end: `0x18009ad54`
- name: `?GetBinaryAttribute@CLdapWrapper@@QEAAJPEAVCLdapSearchResult@@PEB_WPEAPEAEPEAK@Z`
- size: `256`
- prototype: `__int64 __fastcall(LDAP **this, LDAPMessage **, const wchar_t *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180099a3c`

## callees

- `0x180002ee4`
- `0x180005051`
- `0x18009ac54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009acde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009acde`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18009acb4`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18009acb4`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18009ad3a`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18009ad3a`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18009ac9a`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18009ac9a`

## string_xrefs

- `0x18009ac8c`: `objectSid`

## pseudocode

```c

```

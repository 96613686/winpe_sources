# CLdapWrapper::GetBinaryAttribute(CLdapSearchResult *,wchar_t const *,uchar * *,ulong *)

- ea: `0x180098888`
- end: `0x18009896b`
- name: `?GetBinaryAttribute@CLdapWrapper@@QEAAJPEAVCLdapSearchResult@@PEB_WPEAPEAEPEAK@Z`
- size: `227`
- prototype: `__int64 __fastcall(LDAP **this, LDAPMessage **, const wchar_t *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18009774c`

## callees

- `0x180002e84`
- `0x180004fc1`
- `0x180098888`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098902`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180098902`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800988de`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800988de`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180098958`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180098958`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800988ca`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800988ca`

## string_xrefs

- `0x1800988bc`: `objectSid`

## pseudocode

```c

```

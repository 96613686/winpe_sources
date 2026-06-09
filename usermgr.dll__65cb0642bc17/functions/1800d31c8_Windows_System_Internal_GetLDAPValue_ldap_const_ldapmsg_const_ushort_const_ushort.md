# Windows::System::Internal::_GetLDAPValue(ldap const *,ldapmsg const *,ushort const *,ushort * *)

- ea: `0x1800d31c8`
- end: `0x1800d32bc`
- name: `?_GetLDAPValue@Internal@System@Windows@@YAJPEBUldap@@PEBUldapmsg@@PEBGPEAPEAG@Z`
- size: `244`
- prototype: `__int64 __fastcall(LDAP *ld, LDAPMessage *entry, PWSTR attr, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065c6c`

## callees

- `0x1800088e8`
- `0x1800d1e7c`
- `0x1800d2154`
- `0x1800d31c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d31fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d31fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d320a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d320a`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800d3255`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800d3255`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800d325d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1800d325d`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800d3247`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800d3247`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800d3296`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800d3296`

## string_xrefs

- `0x1800d322b`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x1800d31f3`: `wldap32.dll`

## pseudocode

```c

```

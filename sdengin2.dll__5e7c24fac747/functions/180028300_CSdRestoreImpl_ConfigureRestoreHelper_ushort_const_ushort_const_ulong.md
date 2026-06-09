# CSdRestoreImpl::_ConfigureRestoreHelper(ushort const *,ushort const *,ulong)

- ea: `0x180028300`
- end: `0x180028860`
- name: `?_ConfigureRestoreHelper@CSdRestoreImpl@@AEAAJPEBG0K@Z`
- size: `1376`
- prototype: `__int64 __fastcall(CSdRestoreImpl *this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800232b0`

## callees

- `0x180003430`
- `0x180003444`
- `0x180009a98`
- `0x180011274`
- `0x180021904`
- `0x1800262f8`
- `0x180028300`
- `0x1800307c4`
- `0x18004b444`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070564`
- `0x180070ac0`
- `0x180086ef8`
- `0x180087a70`
- `0x180088e88`
- `0x18008f5d0`
- `0x180092b94`
- `0x180099bdc`
- `0x1800c97da`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180028831`
- `KERNEL32!CloseHandle` at `0x180028831`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028521`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180028521`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002881a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002881a`

## string_xrefs

- `0x180028331`: `CSdRestoreImpl::_ConfigureRestoreHelper`

## pseudocode

```c

```

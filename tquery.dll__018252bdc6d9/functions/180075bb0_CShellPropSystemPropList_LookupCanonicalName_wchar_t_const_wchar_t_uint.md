# CShellPropSystemPropList::LookupCanonicalName(wchar_t const *,wchar_t *,uint)

- ea: `0x180075bb0`
- end: `0x180075ceb`
- name: `?LookupCanonicalName@CShellPropSystemPropList@@AEAAJPEB_WPEA_WI@Z`
- size: `315`
- prototype: `__int64 __fastcall(CShellPropSystemPropList *__hidden this, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180075980`

## callees

- `0x18002f914`
- `0x180030a84`
- `0x180038f08`
- `0x1800749f0`
- `0x180075bb0`
- `0x180075cf4`
- `0x180075d8c`
- `0x18007608c`
- `0x180188d90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180075c20`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x180075c20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075bee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802ba5f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802ba5f2`

## string_xrefs

- `0x1802ba62c`: `Client-side property cache has updated, found %ls`
- `0x1802ba625`: `Client-side property cache has updated, still can not find %ls`

## pseudocode

```c

```

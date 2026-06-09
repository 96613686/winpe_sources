# IServerConfiguration::GetBlobAccessWinHttpTimeoutSettingMs(bool,wchar_t const *,int *,int,bool)

- ea: `0x100463b80`
- end: `0x100463c7b`
- name: `?GetBlobAccessWinHttpTimeoutSettingMs@IServerConfiguration@@UEAA_N_NPEB_WPEAHH0@Z`
- size: `251`
- prototype: `bool(IServerConfiguration *__hidden this, bool, const wchar_t *, int *, int, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x100463b80`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x100463c12`
- `KERNEL32!GetEnvironmentVariableW` at `0x100463c12`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100463bc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100463bf0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100463bc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100463bf0`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x100463c21`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x100463c21`

## string_xrefs

- `0x100463c39`: `BlobAccess`
- `0x100463bb9`: `"serverconfig.cpp"`
- `0x100463bdf`: `"serverconfig.cpp"`

## pseudocode

```c

```

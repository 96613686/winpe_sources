# IsLocalHost(wchar_t const *)

- ea: `0x10041f610`
- end: `0x10041f6a4`
- name: `?IsLocalHost@@YA_NPEB_W@Z`
- size: `148`
- prototype: `bool __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10041f6b0`

## callees

- `0x10041f610`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x10041f689`
- `KERNEL32!CompareStringW` at `0x10041f689`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041f62b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041f648`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041f62b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041f648`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x10041f63e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x10041f65b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x10041f63e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x10041f65b`

## pseudocode

```c

```

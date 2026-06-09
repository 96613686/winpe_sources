# WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)

- ea: `0x1800852d4`
- end: `0x1800853a9`
- name: `?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `213`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int *)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d86c`
- `0x18001f3b4`
- `0x180029d9c`
- `0x180041940`
- `0x1800471d8`
- `0x18005cef8`
- `0x1800643d4`
- `0x18006546c`
- `0x18006558c`
- `0x18006e52c`
- `0x18006e724`
- `0x18008df50`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085334`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085334`

## string_xrefs

- `0x180085352`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c

```

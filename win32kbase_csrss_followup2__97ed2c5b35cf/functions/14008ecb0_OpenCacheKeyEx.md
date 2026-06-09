# OpenCacheKeyEx

- ea: `0x14008ecb0`
- end: `0x14008f0c5`
- name: `OpenCacheKeyEx`
- size: `1045`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `15`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14008c990`
- `0x14008e330`
- `0x14008e790`
- `0x14008e8e0`
- `0x14008ead0`
- `0x14008f310`
- `0x14008f574`
- `0x14008fad0`
- `0x14008fb80`
- `0x140090310`
- `0x14009041c`
- `0x1400af810`
- `0x1401c90b0`
- `0x1401c9280`
- `0x1402dc9b0`

## callees

- `0x140031bf4`
- `0x14008ecb0`
- `0x14008f0cc`
- `0x14008f490`
- `0x14008fa44`
- `0x140235a1c`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14008ed08`
- `ntoskrnl!PsGetCurrentProcess` at `0x14008ed08`
- `ntoskrnl!ZwOpenKey` at `0x14008ee82`
- `ntoskrnl!ZwOpenKey` at `0x14008ee82`
- `ntoskrnl!ZwClose` at `0x14008eedb`
- `ntoskrnl!ZwClose` at `0x14008f0af`
- `ntoskrnl!ZwClose` at `0x14008eedb`
- `ntoskrnl!ZwClose` at `0x14008f0af`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008edb7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008edf5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ee24`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ee3d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ef35`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ef4d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008f050`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008f082`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008edb7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008edf5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ee24`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ee3d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ef35`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008ef4d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008f050`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008f082`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ef03`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008ef03`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008eff9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008eff9`
- `ntoskrnl!ObfDereferenceObject` at `0x14008f02e`
- `ntoskrnl!ObfDereferenceObject` at `0x14008f02e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14008ed25`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14008ed25`
- `WIN32K!W32GetUserGdiSessionState` at `0x14008ef98`
- `WIN32K!W32GetUserGdiSessionState` at `0x14008ef98`
- `WIN32K!W32GetUserSessionState` at `0x14008ef73`
- `WIN32K!W32GetUserSessionState` at `0x14008efae`
- `WIN32K!W32GetUserSessionState` at `0x14008ef73`
- `WIN32K!W32GetUserSessionState` at `0x14008efae`

## string_xrefs

- `0x14008edab`: `\Registry\Machine\`
- `0x14008ef29`: `\Registry\Machine\`

## pseudocode

```c

```

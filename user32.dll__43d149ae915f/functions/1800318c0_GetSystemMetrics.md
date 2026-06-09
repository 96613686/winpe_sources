# GetSystemMetrics

- ea: `0x1800318c0`
- end: `0x180031a26`
- name: `GetSystemMetrics`
- size: `358`
- prototype: `int __stdcall(int nIndex)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180031580`
- `0x180031720`

## callees

- `0x180006440`
- `0x180007ef0`
- `0x1800318c0`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserLoadUserApiHook` at `0x18003199e`
- `win32u!NtUserLoadUserApiHook` at `0x18003199e`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x180031990`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x180031990`
- `ntdll!RtlEnterCriticalSection` at `0x1800319b5`
- `ntdll!RtlEnterCriticalSection` at `0x1800319b5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800319ef`
- `ntdll!RtlLeaveCriticalSection` at `0x1800319ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031a15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031a15`

## pseudocode

```c

```

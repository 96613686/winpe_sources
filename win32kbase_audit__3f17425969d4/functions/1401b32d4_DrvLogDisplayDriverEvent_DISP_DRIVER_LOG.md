# DrvLogDisplayDriverEvent(_DISP_DRIVER_LOG)

- ea: `0x1401b32d4`
- end: `0x1401b3518`
- name: `?DrvLogDisplayDriverEvent@@YAXW4_DISP_DRIVER_LOG@@@Z`
- size: `580`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400d34f8`
- `0x1400d4fc8`
- `0x14019338c`
- `0x14019ca3c`
- `0x1401ecb9c`

## callees

- `0x1401b32d4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401b34f6`
- `ntoskrnl!ZwClose` at `0x1401b34f6`
- `ntoskrnl!ZwSetValueKey` at `0x1401b34e6`
- `ntoskrnl!ZwSetValueKey` at `0x1401b34e6`
- `ntoskrnl!ZwCreateKey` at `0x1401b34b4`
- `ntoskrnl!ZwCreateKey` at `0x1401b34b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b333b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b33d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b345d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b333b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b33d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401b345d`
- `watchdog!WdLogSingleEntry0` at `0x1401b3374`
- `watchdog!WdLogSingleEntry0` at `0x1401b3394`
- `watchdog!WdLogSingleEntry0` at `0x1401b33b4`
- `watchdog!WdLogSingleEntry0` at `0x1401b33e8`
- `watchdog!WdLogSingleEntry0` at `0x1401b3405`
- `watchdog!WdLogSingleEntry0` at `0x1401b3422`
- `watchdog!WdLogSingleEntry0` at `0x1401b3374`
- `watchdog!WdLogSingleEntry0` at `0x1401b3394`
- `watchdog!WdLogSingleEntry0` at `0x1401b33b4`
- `watchdog!WdLogSingleEntry0` at `0x1401b33e8`
- `watchdog!WdLogSingleEntry0` at `0x1401b3405`
- `watchdog!WdLogSingleEntry0` at `0x1401b3422`
- `WIN32K!W32GetSessionState` at `0x1401b3314`
- `WIN32K!W32GetSessionState` at `0x1401b3442`
- `WIN32K!W32GetSessionState` at `0x1401b3314`
- `WIN32K!W32GetSessionState` at `0x1401b3442`

## string_xrefs

- `0x1401b344e`: `\Registry\Machine\System\CurrentControlSet\Control\GraphicsDrivers\InvalidDisplay`

## pseudocode

```c

```

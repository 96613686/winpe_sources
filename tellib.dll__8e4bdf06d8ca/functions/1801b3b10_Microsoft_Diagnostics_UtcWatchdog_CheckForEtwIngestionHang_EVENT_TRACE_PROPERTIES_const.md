# Microsoft::Diagnostics::UtcWatchdog::CheckForEtwIngestionHang(_EVENT_TRACE_PROPERTIES const &)

- ea: `0x1801b3b10`
- end: `0x1801b4033`
- name: `?CheckForEtwIngestionHang@UtcWatchdog@Diagnostics@Microsoft@@AEAAXAEBU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `1315`
- prototype: `void __fastcall(Microsoft::Diagnostics::UtcWatchdog *__hidden this, const struct _EVENT_TRACE_PROPERTIES *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801b5480`

## callees

- `0x180040258`
- `0x180050504`
- `0x180052734`
- `0x18005372c`
- `0x180054158`
- `0x180054788`
- `0x18005a2a4`
- `0x1800a0d08`
- `0x1800e1a54`
- `0x1800e2610`
- `0x1800e2934`
- `0x1800e2950`
- `0x1800e295c`
- `0x1800e29b8`
- `0x18012de40`
- `0x1801ad2ec`
- `0x1801b1d8c`
- `0x1801b2cc8`
- `0x1801b3b10`
- `0x1801b589c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801b3e10`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801b3e10`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801b3be9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801b3e67`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801b3be9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801b3e67`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1801b3fdc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1801b3fdc`

## string_xrefs

- `0x1801b3fba`: `onecore\base\telemetry\utc\service\engine\utcwatchdog.cpp`

## pseudocode

```c

```

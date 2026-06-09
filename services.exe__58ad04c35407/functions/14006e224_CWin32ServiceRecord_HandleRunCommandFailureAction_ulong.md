# CWin32ServiceRecord::HandleRunCommandFailureAction(ulong)

- ea: `0x14006e224`
- end: `0x14006e577`
- name: `?HandleRunCommandFailureAction@CWin32ServiceRecord@@IEAAXK@Z`
- size: `851`
- prototype: `void __fastcall(CWin32ServiceRecord *__hidden this, ULONG ulMilliseconds)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14006f128`

## callees

- `0x140004c58`
- `0x14000bebc`
- `0x14000c8f0`
- `0x14000cee0`
- `0x14000cf60`
- `0x1400188fc`
- `0x14001e12c`
- `0x14001f99c`
- `0x14002e6f0`
- `0x14003f9b0`
- `0x1400575b0`
- `0x14006e0d0`
- `0x14006e1f8`
- `0x14006e224`
- `0x14006e624`
- `0x14006f59c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006e502`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006e502`
- `ntdll!RtlInitUnicodeString` at `0x14006e312`
- `ntdll!RtlInitUnicodeString` at `0x14006e312`
- `ntdll!RtlFreeHeap` at `0x14006e52c`
- `ntdll!RtlFreeHeap` at `0x14006e549`
- `ntdll!RtlFreeHeap` at `0x14006e52c`
- `ntdll!RtlFreeHeap` at `0x14006e549`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x14006e3c0`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x14006e3c0`
- `ntdll!RtlAllocateHeap` at `0x14006e345`
- `ntdll!RtlAllocateHeap` at `0x14006e345`

## string_xrefs

- `0x14006e2a6`: `FailureCommand`

## pseudocode

```c

```

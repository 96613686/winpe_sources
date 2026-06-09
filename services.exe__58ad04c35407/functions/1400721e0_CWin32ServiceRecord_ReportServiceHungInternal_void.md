# CWin32ServiceRecord::ReportServiceHungInternal(void)

- ea: `0x1400721e0`
- end: `0x1400725e2`
- name: `?ReportServiceHungInternal@CWin32ServiceRecord@@MEAAXXZ`
- size: `1026`
- prototype: `void __fastcall(CWin32ServiceRecord *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callees

- `0x140001468`
- `0x140003e54`
- `0x14000bb80`
- `0x14000cee0`
- `0x14000cf60`
- `0x140013b0c`
- `0x1400188fc`
- `0x14001bf10`
- `0x14001c87c`
- `0x140020d84`
- `0x140023c94`
- `0x140038698`
- `0x140064a90`
- `0x1400721e0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400725cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400725cb`
- `ntdll!RtlFreeHeap` at `0x14007259f`
- `ntdll!RtlFreeHeap` at `0x1400725bc`
- `ntdll!RtlFreeHeap` at `0x14007259f`
- `ntdll!RtlFreeHeap` at `0x1400725bc`
- `ntdll!DbgPrintEx` at `0x14007249b`
- `ntdll!DbgPrintEx` at `0x14007249b`
- `ntdll!RtlAllocateHeap` at `0x1400723e5`
- `ntdll!RtlAllocateHeap` at `0x1400723e5`

## string_xrefs

- `0x14007248a`: `\n=======================================================================================================================\n\n[SCM] !! Breaking into KD -- contact service '%ws' owner to debug why it hung on startup !!\n\n\n=======================================================================================================================\n\n`

## pseudocode

```c

```

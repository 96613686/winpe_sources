# ScGetWow64Service(HKEY__ *,ushort *)

- ea: `0x1400233ac`
- end: `0x1400234fb`
- name: `?ScGetWow64Service@@YAKPEAUHKEY__@@PEAG@Z`
- size: `335`
- prototype: `unsigned int __fastcall(HKEY KeyHandle, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1400108c0`
- `0x14003c510`

## callees

- `0x14001f99c`
- `0x1400233ac`
- `0x140031144`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140023475`
- `ntdll!RtlNtStatusToDosError` at `0x140023475`
- `ntdll!RtlInitUnicodeString` at `0x1400233e7`
- `ntdll!RtlInitUnicodeString` at `0x1400233e7`
- `ntdll!RtlFreeHeap` at `0x14002346d`
- `ntdll!RtlFreeHeap` at `0x14002346d`
- `ntdll!NtQueryValueKey` at `0x14002343b`
- `ntdll!NtQueryValueKey` at `0x14002343b`
- `ntdll!RtlAllocateHeap` at `0x140023408`
- `ntdll!RtlAllocateHeap` at `0x140023408`

## pseudocode

```c

```

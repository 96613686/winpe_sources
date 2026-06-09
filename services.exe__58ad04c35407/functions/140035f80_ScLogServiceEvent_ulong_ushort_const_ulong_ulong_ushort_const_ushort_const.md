# ScLogServiceEvent(ulong,ushort const *,ulong,ulong,ushort const *,ushort const *)

- ea: `0x140035f80`
- end: `0x1400361e5`
- name: `?ScLogServiceEvent@@YAXKPEBGKK00@Z`
- size: `613`
- prototype: `void __usercall(unsigned int@<ecx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x14001e800`
- `0x14003d5f0`
- `0x140068b60`
- `0x14006b060`

## callees

- `0x140013b0c`
- `0x14001dc6c`
- `0x140035f80`
- `0x1400575b0`
- `0x140081b6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14003600e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400360ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14003600e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400360ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140035ff8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140036097`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140035ff8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140036097`
- `ntdll!RtlFreeHeap` at `0x1400360ca`
- `ntdll!RtlFreeHeap` at `0x1400360ca`

## pseudocode

```c

```

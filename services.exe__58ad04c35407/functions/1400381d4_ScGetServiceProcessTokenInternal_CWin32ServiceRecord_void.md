# ScGetServiceProcessTokenInternal(CWin32ServiceRecord *,void * *)

- ea: `0x1400381d4`
- end: `0x140038641`
- name: `?ScGetServiceProcessTokenInternal@@YAKPEAVCWin32ServiceRecord@@PEAPEAX@Z`
- size: `1133`
- prototype: `unsigned int __fastcall(struct CWin32ServiceRecord *this, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x140025360`

## callees

- `0x140003e54`
- `0x14000bac8`
- `0x140014824`
- `0x140027320`
- `0x14002c220`
- `0x1400322dc`
- `0x1400381d4`
- `0x1400575b0`
- `0x140063144`
- `0x140063928`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140038566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003857a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400385d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140038566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003857a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400385d4`
- `ntdll!RtlReleaseResource` at `0x140038299`
- `ntdll!RtlReleaseResource` at `0x1400382b9`
- `ntdll!RtlReleaseResource` at `0x14003839a`
- `ntdll!RtlReleaseResource` at `0x1400383f7`
- `ntdll!RtlReleaseResource` at `0x140038299`
- `ntdll!RtlReleaseResource` at `0x1400382b9`
- `ntdll!RtlReleaseResource` at `0x14003839a`
- `ntdll!RtlReleaseResource` at `0x1400383f7`
- `ntdll!RtlAcquireResourceShared` at `0x140038276`
- `ntdll!RtlAcquireResourceShared` at `0x140038276`
- `ntdll!RtlFreeHeap` at `0x1400385a3`
- `ntdll!RtlFreeHeap` at `0x1400385c1`
- `ntdll!RtlFreeHeap` at `0x1400385f1`
- `ntdll!RtlFreeHeap` at `0x140038612`
- `ntdll!RtlFreeHeap` at `0x1400385a3`
- `ntdll!RtlFreeHeap` at `0x1400385c1`
- `ntdll!RtlFreeHeap` at `0x1400385f1`
- `ntdll!RtlFreeHeap` at `0x140038612`

## pseudocode

```c

```

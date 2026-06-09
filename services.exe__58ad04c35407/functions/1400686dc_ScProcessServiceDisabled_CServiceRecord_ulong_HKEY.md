# ScProcessServiceDisabled(CServiceRecord *,ulong,HKEY__ *)

- ea: `0x1400686dc`
- end: `0x140068b51`
- name: `?ScProcessServiceDisabled@@YAKPEAVCServiceRecord@@KPEAUHKEY__@@@Z`
- size: `1141`
- prototype: `unsigned int __fastcall(struct CServiceRecord *, unsigned int, HKEY)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x140068b60`

## callees

- `0x140003e54`
- `0x140004c98`
- `0x14000512c`
- `0x140005464`
- `0x14001c87c`
- `0x140020d84`
- `0x140026508`
- `0x1400265ac`
- `0x1400282a4`
- `0x14002e844`
- `0x140030488`
- `0x1400575b0`
- `0x1400644c0`
- `0x1400686dc`
- `0x14007b640`
- `0x140094020`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x140068862`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068a4b`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068aa9`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068862`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068a4b`
- `ntdll!RtlAcquireResourceExclusive` at `0x140068aa9`
- `ntdll!RtlReleaseResource` at `0x1400687cb`
- `ntdll!RtlReleaseResource` at `0x140068998`
- `ntdll!RtlReleaseResource` at `0x140068a92`
- `ntdll!RtlReleaseResource` at `0x1400687cb`
- `ntdll!RtlReleaseResource` at `0x140068998`
- `ntdll!RtlReleaseResource` at `0x140068a92`
- `ntdll!RtlFreeHeap` at `0x140068acf`
- `ntdll!RtlFreeHeap` at `0x140068acf`
- `ntdll!RtlAcquireSRWLockShared` at `0x140068738`
- `ntdll!RtlAcquireSRWLockShared` at `0x140068738`

## pseudocode

```c

```

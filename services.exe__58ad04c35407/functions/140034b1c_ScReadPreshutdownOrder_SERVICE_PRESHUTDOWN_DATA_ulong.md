# ScReadPreshutdownOrder(_SERVICE_PRESHUTDOWN_DATA * *,ulong *)

- ea: `0x140034b1c`
- end: `0x140034f8e`
- name: `?ScReadPreshutdownOrder@@YAKPEAPEAU_SERVICE_PRESHUTDOWN_DATA@@PEAK@Z`
- size: `1138`
- prototype: `unsigned int __fastcall(struct _SERVICE_PRESHUTDOWN_DATA **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x1400386c4`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x140007960`
- `0x14000bcc4`
- `0x14000c310`
- `0x140011ba0`
- `0x140013f60`
- `0x14001c1e0`
- `0x14001f99c`
- `0x14002193c`
- `0x140029228`
- `0x14002b4a4`
- `0x140034b1c`
- `0x14006df40`
- `0x140094020`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x140034d9b`
- `ntdll!RtlAcquireResourceExclusive` at `0x140034d9b`
- `ntdll!RtlReleaseResource` at `0x140034e0b`
- `ntdll!RtlReleaseResource` at `0x140034eba`
- `ntdll!RtlReleaseResource` at `0x140034efe`
- `ntdll!RtlReleaseResource` at `0x140034e0b`
- `ntdll!RtlReleaseResource` at `0x140034eba`
- `ntdll!RtlReleaseResource` at `0x140034efe`
- `ntdll!NtClose` at `0x140034f55`
- `ntdll!NtClose` at `0x140034f55`
- `ntdll!RtlNtStatusToDosError` at `0x140034f5d`
- `ntdll!RtlNtStatusToDosError` at `0x140034f5d`
- `ntdll!RtlFreeHeap` at `0x140034f46`
- `ntdll!RtlFreeHeap` at `0x140034f75`
- `ntdll!RtlFreeHeap` at `0x140034f46`
- `ntdll!RtlFreeHeap` at `0x140034f75`
- `ntdll!RtlAllocateHeap` at `0x140034d08`
- `ntdll!RtlAllocateHeap` at `0x140034d08`

## pseudocode

```c

```

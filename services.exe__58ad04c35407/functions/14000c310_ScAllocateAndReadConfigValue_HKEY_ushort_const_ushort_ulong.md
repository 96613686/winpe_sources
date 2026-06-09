# ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)

- ea: `0x14000c310`
- end: `0x14000c8ea`
- name: `?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z`
- size: `1498`
- prototype: `unsigned int __fastcall(HKEY KeyHandle, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `27`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140009910`
- `0x14000b2e4`
- `0x14000bb80`
- `0x14000c8f0`
- `0x14000ca18`
- `0x14000cf60`
- `0x14000d1dc`
- `0x140010064`
- `0x1400108c0`
- `0x140014824`
- `0x14002178c`
- `0x140034234`
- `0x140034b1c`
- `0x140037480`
- `0x140037614`
- `0x140037f90`
- `0x1400406c8`
- `0x140042c90`
- `0x140068b60`
- `0x1400706a0`
- `0x140071fe0`
- `0x140072cec`
- `0x140079d10`
- `0x14007af50`
- `0x14007b0e8`
- `0x14007b1cc`
- `0x14008446c`

## callees

- `0x140004c58`
- `0x14000c310`
- `0x1400188fc`
- `0x140019014`
- `0x14001f99c`
- `0x1400575b0`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000c54e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000c59b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000c54e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000c59b`
- `ntdll!RtlNtStatusToDosError` at `0x14000c40d`
- `ntdll!RtlNtStatusToDosError` at `0x14000c71b`
- `ntdll!RtlNtStatusToDosError` at `0x14000c40d`
- `ntdll!RtlNtStatusToDosError` at `0x14000c71b`
- `ntdll!RtlInitUnicodeString` at `0x14000c36c`
- `ntdll!RtlInitUnicodeString` at `0x14000c683`
- `ntdll!RtlInitUnicodeString` at `0x14000c36c`
- `ntdll!RtlInitUnicodeString` at `0x14000c683`
- `ntdll!RtlFreeHeap` at `0x14000c405`
- `ntdll!RtlFreeHeap` at `0x14000c4a5`
- `ntdll!RtlFreeHeap` at `0x14000c5be`
- `ntdll!RtlFreeHeap` at `0x14000c711`
- `ntdll!RtlFreeHeap` at `0x14000c894`
- `ntdll!RtlFreeHeap` at `0x14000c405`
- `ntdll!RtlFreeHeap` at `0x14000c4a5`
- `ntdll!RtlFreeHeap` at `0x14000c5be`
- `ntdll!RtlFreeHeap` at `0x14000c711`
- `ntdll!RtlFreeHeap` at `0x14000c894`
- `ntdll!NtQueryValueKey` at `0x14000c3c4`
- `ntdll!NtQueryValueKey` at `0x14000c6da`
- `ntdll!NtQueryValueKey` at `0x14000c3c4`
- `ntdll!NtQueryValueKey` at `0x14000c6da`
- `ntdll!RtlAllocateHeap` at `0x14000c391`
- `ntdll!RtlAllocateHeap` at `0x14000c4c7`
- `ntdll!RtlAllocateHeap` at `0x14000c57b`
- `ntdll!RtlAllocateHeap` at `0x14000c636`
- `ntdll!RtlAllocateHeap` at `0x14000c6a3`
- `ntdll!RtlAllocateHeap` at `0x14000c391`
- `ntdll!RtlAllocateHeap` at `0x14000c4c7`
- `ntdll!RtlAllocateHeap` at `0x14000c57b`
- `ntdll!RtlAllocateHeap` at `0x14000c636`
- `ntdll!RtlAllocateHeap` at `0x14000c6a3`

## pseudocode

```c

```

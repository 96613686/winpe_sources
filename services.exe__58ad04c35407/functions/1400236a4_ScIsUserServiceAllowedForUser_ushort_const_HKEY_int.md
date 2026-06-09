# ScIsUserServiceAllowedForUser(ushort const *,HKEY__ *,int)

- ea: `0x1400236a4`
- end: `0x1400238b8`
- name: `?ScIsUserServiceAllowedForUser@@YAHPEBGPEAUHKEY__@@H@Z`
- size: `532`
- prototype: `int(const unsigned __int16 *, HKEY, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140029908`

## callees

- `0x14001f99c`
- `0x1400236a4`
- `0x14007ded4`
- `0x14007e4cc`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140023795`
- `ntdll!RtlNtStatusToDosError` at `0x140023795`
- `ntdll!RtlInitUnicodeString` at `0x1400236ea`
- `ntdll!RtlInitUnicodeString` at `0x1400236ea`
- `ntdll!RtlFreeHeap` at `0x14002378c`
- `ntdll!RtlFreeHeap` at `0x14002378c`
- `ntdll!NtQueryValueKey` at `0x14002374e`
- `ntdll!NtQueryValueKey` at `0x14002374e`
- `ntdll!RtlAllocateHeap` at `0x14002370e`
- `ntdll!RtlAllocateHeap` at `0x14002370e`

## string_xrefs

- `0x1400236cd`: `UserServiceFlags`

## pseudocode

```c

```

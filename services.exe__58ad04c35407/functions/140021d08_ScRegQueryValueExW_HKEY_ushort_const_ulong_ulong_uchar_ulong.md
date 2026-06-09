# ScRegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)

- ea: `0x140021d08`
- end: `0x140021e80`
- name: `?ScRegQueryValueExW@@YAKPEAUHKEY__@@PEBGPEAK2PEAE2@Z`
- size: `376`
- prototype: `unsigned int __usercall@<eax>(HKEY KeyHandle@<rcx>, const unsigned __int16 *@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, unsigned __int8 *, unsigned int *)`
- caller_count: `20`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000cb18`
- `0x1400108c0`
- `0x140015fd8`
- `0x140021b78`
- `0x140021c54`
- `0x140027074`
- `0x1400282a4`
- `0x14002cfec`
- `0x14002edf8`
- `0x14002f90c`
- `0x140041778`
- `0x1400420d0`
- `0x140043584`
- `0x140043610`
- `0x140065804`
- `0x140065d60`
- `0x140068118`
- `0x14007b06c`
- `0x14007b1cc`
- `0x14007b418`

## callees

- `0x14001f99c`
- `0x140021d08`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140021e00`
- `ntdll!RtlNtStatusToDosError` at `0x140021e00`
- `ntdll!RtlInitUnicodeString` at `0x140021d48`
- `ntdll!RtlInitUnicodeString` at `0x140021d48`
- `ntdll!RtlFreeHeap` at `0x140021df8`
- `ntdll!RtlFreeHeap` at `0x140021df8`
- `ntdll!NtQueryValueKey` at `0x140021db1`
- `ntdll!NtQueryValueKey` at `0x140021db1`
- `ntdll!RtlAllocateHeap` at `0x140021d76`
- `ntdll!RtlAllocateHeap` at `0x140021d76`

## pseudocode

```c

```

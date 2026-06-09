# RemotelyOpenClientKeyHandle(ushort const *,ushort const *,uchar *,ulong,ulong,ulong)

- ea: `0x18005bdc4`
- end: `0x18005c168`
- name: `?RemotelyOpenClientKeyHandle@@YAKPEBG0PEAEKKK@Z`
- size: `932`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18003b294`
- `0x18005ca90`

## callees

- `0x180021da8`
- `0x180021e64`
- `0x18002acc0`
- `0x180036550`
- `0x180057c8c`
- `0x18005bdc4`
- `0x18005c330`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005be70`
- `ntdll!RtlNtStatusToDosError` at `0x18005be70`

## pseudocode

```c

```

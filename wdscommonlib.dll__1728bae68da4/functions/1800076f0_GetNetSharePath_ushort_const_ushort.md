# GetNetSharePath(ushort const *,ushort * *)

- ea: `0x1800076f0`
- end: `0x180007763`
- name: `?GetNetSharePath@@YAKPEBGPEAPEAG@Z`
- size: `115`
- prototype: `unsigned int __fastcall(LPWSTR netname, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b280`

## callees

- `0x1800076f0`
- `0x1800172b0`

## import_xrefs

- `NETAPI32!NetShareGetInfo` at `0x180007713`
- `NETAPI32!NetShareGetInfo` at `0x180007713`
- `NETAPI32!NetApiBufferFree` at `0x180007749`
- `NETAPI32!NetApiBufferFree` at `0x180007749`

## pseudocode

```c

```

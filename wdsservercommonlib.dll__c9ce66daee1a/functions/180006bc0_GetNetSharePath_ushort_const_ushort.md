# GetNetSharePath(ushort const *,ushort * *)

- ea: `0x180006bc0`
- end: `0x180006c33`
- name: `?GetNetSharePath@@YAKPEBGPEAPEAG@Z`
- size: `115`
- prototype: `unsigned int __fastcall(LPWSTR netname, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a440`

## callees

- `0x180006bc0`
- `0x180016520`

## import_xrefs

- `NETAPI32!NetApiBufferFree` at `0x180006c19`
- `NETAPI32!NetApiBufferFree` at `0x180006c19`
- `NETAPI32!NetShareGetInfo` at `0x180006be3`
- `NETAPI32!NetShareGetInfo` at `0x180006be3`

## pseudocode

```c

```

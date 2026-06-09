# CDeleteMe<ushort>::~CDeleteMe<ushort>(void)

- ea: `0x18000bb8c`
- end: `0x18000bb9f`
- name: `??1?$CDeleteMe@G@@QEAA@XZ`
- size: `19`
- prototype: `int __fastcall(void **)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000fe68`
- `0x180010ae0`
- `0x180015ca0`
- `0x180016b89`
- `0x180016b9b`
- `0x180016bbf`
- `0x180016bd1`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bb93`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000bb93`

## pseudocode

```c
int __fastcall CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(void **a1)
{
  return CWin32DefaultArena::WbemMemFree(*a1);
}

```

## disassembly

```asm
0x18000bb8c  sub     rsp, 28h
0x18000bb90  mov     rcx, [rcx]
0x18000bb93  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000bb99  nop
0x18000bb9a  add     rsp, 28h
0x18000bb9e  retn
```

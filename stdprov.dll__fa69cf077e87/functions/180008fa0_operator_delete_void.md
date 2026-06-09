# operator delete(void *)

- ea: `0x180008fa0`
- end: `0x180008fb0`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `16`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c100`
- `0x180015770`
- `0x180015790`
- `0x180015830`
- `0x180015950`
- `0x1800159d0`
- `0x180015a50`
- `0x180015ad8`
- `0x180015b30`
- `0x180015eb4`
- `0x180015ed8`
- `0x180015eea`
- `0x18001640a`
- `0x180016a66`
- `0x180016a8a`
- `0x180016d8e`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008fa4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008fa4`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  CWin32DefaultArena::WbemMemFree(a1);
}

```

## disassembly

```asm
0x180008fa0  sub     rsp, 28h
0x180008fa4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180008faa  nop
0x180008fab  add     rsp, 28h
0x180008faf  retn
```

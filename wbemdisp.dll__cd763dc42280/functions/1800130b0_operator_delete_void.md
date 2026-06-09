# operator delete(void *)

- ea: `0x1800130b0`
- end: `0x1800130c0`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `36`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a640`
- `0x18001a670`
- `0x18001a6b0`
- `0x18001a6e8`
- `0x18001a7e8`
- `0x18001b360`
- `0x180034160`
- `0x1800341d0`
- `0x180034270`
- `0x1800342a0`
- `0x1800342c0`
- `0x1800342e0`
- `0x180034300`
- `0x1800343c0`
- `0x180034420`
- `0x180034690`
- `0x1800346f0`
- `0x180034800`
- `0x180034840`
- `0x180034860`
- `0x1800348c0`
- `0x180034900`
- `0x180034920`
- `0x1800349a0`
- `0x180034a20`
- `0x180034b00`
- `0x180034b40`
- `0x180034c16`
- `0x180034c70`
- `0x180034df2`
- `0x180034f70`
- `0x180034fb0`
- `0x18003506c`
- `0x1800350d5`
- `0x180035180`
- `0x180035818`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800130b4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800130b4`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  CWin32DefaultArena::WbemMemFree(a1);
}

```

## disassembly

```asm
0x1800130b0  sub     rsp, 28h
0x1800130b4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800130ba  nop
0x1800130bb  add     rsp, 28h
0x1800130bf  retn
```

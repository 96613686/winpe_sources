# deleteArray<ushort>(ushort *)

- ea: `0x18000f580`
- end: `0x18000f587`
- name: `??$deleteArray@G@@YAXPEAG@Z`
- size: `7`
- prototype: `int __fastcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f580`

## pseudocode

```c
// attributes: thunk
int __fastcall deleteArray<unsigned short>(void *a1)
{
  return CWin32DefaultArena::WbemMemFree(a1);
}

```

## disassembly

```asm
0x18000f580  jmp     cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
```

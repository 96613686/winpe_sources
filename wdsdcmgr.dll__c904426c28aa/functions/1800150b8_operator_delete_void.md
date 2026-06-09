# operator delete(void *)

- ea: `0x1800150b8`
- end: `0x1800150bf`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `80`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001b70`
- `0x180002268`
- `0x18000259c`
- `0x180002bd8`
- `0x1800036dc`
- `0x180003acc`
- `0x1800040ac`
- `0x1800042f4`
- `0x180004dbc`
- `0x180004f98`
- `0x1800051e8`
- `0x1800063b4`
- `0x180006ab0`
- `0x180006b84`
- `0x180006bec`
- `0x180006c98`
- `0x180006ff0`
- `0x180007b40`
- `0x180007f90`
- `0x180008510`
- `0x180008700`
- `0x180008780`
- `0x180008920`
- `0x180008b68`
- `0x180008db4`
- `0x180009680`
- `0x180009838`
- `0x180009894`
- `0x180009b3c`
- `0x18000a15c`
- `0x18000a380`
- `0x18000a3f0`
- `0x18000a644`
- `0x18000a870`
- `0x18000ac50`
- `0x18000ae38`
- `0x18000af78`
- `0x18000b228`
- `0x18000b47c`
- `0x18000b834`
- `0x18000b92c`
- `0x18000ba74`
- `0x18000bb58`
- `0x18000bd00`
- `0x18000be10`
- `0x18000bf44`
- `0x18000c03c`
- `0x18000c158`
- `0x18000c2d0`
- `0x18000ca00`

## import_xrefs

- `msvcrt!free` at `0x1800150b8`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1800150b8  jmp     cs:__imp_free
```

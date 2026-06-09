# operator delete(void *)

- ea: `0x180002080`
- end: `0x180002087`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000145c`
- `0x180002130`

## import_xrefs

- `msvcrt!free` at `0x180002080`

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
0x180002080  jmp     cs:__imp_free
```

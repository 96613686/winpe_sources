# RtlCopyVolatileMemory

- ea: `0x140007c90`
- end: `0x140007c95`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140004058`
- `0x14001439c`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`
- `0x1400179f4`
- `0x140017ad0`
- `0x14001a364`

## callees

- `0x140007dc0`

## pseudocode

```c
// attributes: thunk
void *__cdecl RtlCopyVolatileMemory(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x140007c90  jmp     memmove
```

# RtlCopyVolatileMemory

- ea: `0x140002be0`
- end: `0x140002be5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001044`

## callees

- `0x140002d00`

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
0x140002be0  jmp     memmove
```

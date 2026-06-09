# RtlCopyVolatileMemory

- ea: `0x1400054e0`
- end: `0x1400054e5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039d0`
- `0x140003da0`

## callees

- `0x140005600`

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
0x1400054e0  jmp     memmove
```

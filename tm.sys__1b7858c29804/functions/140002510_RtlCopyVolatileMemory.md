# RtlCopyVolatileMemory

- ea: `0x140002510`
- end: `0x140002515`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014d4`
- `0x14000d198`
- `0x140012154`
- `0x1400122b8`
- `0x140013690`
- `0x140013c50`
- `0x1400147e0`
- `0x140017950`
- `0x14001e120`

## callees

- `0x140002640`

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
0x140002510  jmp     memmove
```

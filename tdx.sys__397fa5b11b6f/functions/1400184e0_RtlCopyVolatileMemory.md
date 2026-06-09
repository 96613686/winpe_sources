# RtlCopyVolatileMemory

- ea: `0x1400184e0`
- end: `0x1400184e5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010f10`
- `0x1400121d8`
- `0x14001606c`
- `0x140016fec`

## callees

- `0x140018600`

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
0x1400184e0  jmp     memmove
```

# RtlSetVolatileMemory

- ea: `0x140007cb0`
- end: `0x140007cb5`
- name: `RtlSetVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001443c`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x14001771c`
- `0x14001a364`

## callees

- `0x1400080c0`

## pseudocode

```c
// attributes: thunk
void *__cdecl RtlSetVolatileMemory(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x140007cb0  jmp     memset
```

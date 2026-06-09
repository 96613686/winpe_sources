# RtlCopyVolatileMemory

- ea: `0x14000f930`
- end: `0x14000f935`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140001220`
- `0x140007668`
- `0x14001e044`
- `0x14001e174`
- `0x14001e23c`
- `0x14001e2ec`
- `0x14001e464`
- `0x14001e524`
- `0x14001e5cc`
- `0x14001e630`
- `0x14001e71c`

## callees

- `0x14000fa40`

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
0x14000f930  jmp     memmove
```

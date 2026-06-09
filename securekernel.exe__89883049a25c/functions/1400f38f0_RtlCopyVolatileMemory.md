# RtlCopyVolatileMemory

- ea: `0x1400f38f0`
- end: `0x1400f38f5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `50`
- callee_count: `1`
- tags: ``

## callers

- `0x140040250`
- `0x140041234`
- `0x1400416dc`
- `0x140041954`
- `0x1400425ac`
- `0x140042760`
- `0x1400427c4`
- `0x140042824`
- `0x140042afc`
- `0x140042c40`
- `0x140042e68`
- `0x140043654`
- `0x1400440b4`
- `0x140044378`
- `0x14004439c`
- `0x1400443c0`
- `0x140064ea0`
- `0x140066b20`
- `0x140067ecc`
- `0x1400883a4`
- `0x14008969c`
- `0x140089b8c`
- `0x1400a1a40`
- `0x1400ad5c4`
- `0x1400addd0`
- `0x1400adfe8`
- `0x1400aea50`
- `0x1400af910`
- `0x1400b18ac`
- `0x1400b2690`
- `0x1400b3d38`
- `0x1400b4c40`
- `0x1400b6c24`
- `0x1400b86ec`
- `0x1400be36c`
- `0x1400be4f8`
- `0x1400be63c`
- `0x1400be778`
- `0x1400be870`
- `0x1400be910`
- `0x1400becc8`
- `0x1400bed44`
- `0x1400bee00`
- `0x1400bef5c`
- `0x1400c2b18`
- `0x1400d4e8c`
- `0x1400daa0c`
- `0x1400fc1a8`
- `0x1400fc554`
- `0x1400fc5b8`

## callees

- `0x1400f9780`

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
0x1400f38f0  jmp     memmove
```

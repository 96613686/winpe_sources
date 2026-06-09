# NdrOleAllocate_0

- ea: `0x180001700`
- end: `0x180001706`
- name: `NdrOleAllocate_0`
- size: `6`
- prototype: `void *__stdcall(size_t Size)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrOleAllocate` at `0x180001700`

## pseudocode

```c
// attributes: thunk
void *__stdcall NdrOleAllocate_0(size_t Size)
{
  return NdrOleAllocate(Size);
}

```

## disassembly

```asm
0x180001700  jmp     cs:__imp_NdrOleAllocate
```

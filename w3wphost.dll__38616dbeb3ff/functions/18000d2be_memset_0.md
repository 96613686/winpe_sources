# memset_0

- ea: `0x18000d2be`
- end: `0x18000d2c4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cd0`
- `0x180004100`
- `0x180004ee4`
- `0x18000561c`
- `0x1800062bc`
- `0x180007b48`
- `0x18000b8e8`
- `0x18000c88c`

## import_xrefs

- `msvcrt!memset` at `0x18000d2be`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18000d2be  jmp     cs:__imp_memset
```

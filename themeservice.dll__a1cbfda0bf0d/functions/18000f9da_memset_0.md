# memset_0

- ea: `0x18000f9da`
- end: `0x18000f9e0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18000546c`
- `0x1800082dc`
- `0x18000838c`
- `0x180008480`
- `0x180008ca4`
- `0x1800096fc`
- `0x180009bd4`
- `0x18000a180`
- `0x18000b6cc`
- `0x18000c930`
- `0x18000d094`
- `0x18000dcb0`
- `0x18000de20`
- `0x18000df48`
- `0x18000ecd4`

## import_xrefs

- `msvcrt!memset` at `0x18000f9da`

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
0x18000f9da  jmp     cs:__imp_memset
```

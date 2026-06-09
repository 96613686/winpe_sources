# memset_0

- ea: `0x18001bf0a`
- end: `0x18001bf10`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030f4`
- `0x180006a34`
- `0x1800071d8`
- `0x180007604`
- `0x1800078f4`
- `0x180007df0`
- `0x180008670`
- `0x180008b0c`
- `0x18000a7f8`
- `0x18000ad4c`
- `0x18000e918`
- `0x18000ef50`
- `0x18000fc8c`
- `0x18000fe78`
- `0x1800104cc`
- `0x180013120`
- `0x1800151b4`
- `0x180017394`
- `0x180019710`

## import_xrefs

- `msvcrt!memset` at `0x18001bf0a`

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
0x18001bf0a  jmp     cs:__imp_memset
```

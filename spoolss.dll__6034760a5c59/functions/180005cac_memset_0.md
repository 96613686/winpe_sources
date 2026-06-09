# memset_0

- ea: `0x180005cac`
- end: `0x180005cb2`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180001af0`
- `0x1800037fc`
- `0x180003ea4`
- `0x180003ff8`
- `0x180006920`
- `0x1800069d0`
- `0x180006c6c`
- `0x1800085b4`
- `0x18000a8e0`
- `0x18000aa1c`
- `0x18000b878`
- `0x18000c098`
- `0x18000f1d8`
- `0x180011df8`
- `0x180012cd0`
- `0x180014360`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180005cac`

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
0x180005cac  jmp     cs:__imp_memset
```

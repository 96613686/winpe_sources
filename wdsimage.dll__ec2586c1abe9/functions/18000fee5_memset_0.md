# memset_0

- ea: `0x18000fee5`
- end: `0x18000feeb`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003790`
- `0x1800037c0`
- `0x1800039a8`
- `0x1800074f8`
- `0x18000844c`
- `0x18000bd94`
- `0x18000bef8`

## import_xrefs

- `msvcrt!memset` at `0x18000fee5`

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
0x18000fee5  jmp     cs:__imp_memset
```

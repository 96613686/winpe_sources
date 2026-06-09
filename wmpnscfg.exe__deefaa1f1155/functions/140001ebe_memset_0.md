# memset_0

- ea: `0x140001ebe`
- end: `0x140001ec4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018fc`
- `0x1400028bc`
- `0x1400055c8`
- `0x140007258`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x140001ebe`

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
0x140001ebe  jmp     cs:__imp_memset
```

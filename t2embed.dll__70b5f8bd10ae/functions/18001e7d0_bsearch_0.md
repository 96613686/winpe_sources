# bsearch_0

- ea: `0x18001e7d0`
- end: `0x18001e7d6`
- name: `bsearch_0`
- size: `6`
- prototype: `void *__cdecl(const void *Key, const void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180027b5c`

## import_xrefs

- `msvcrt!bsearch` at `0x18001e7d0`

## pseudocode

```c
// attributes: thunk
void *__cdecl bsearch_0(
        const void *Key,
        const void *Base,
        size_t NumOfElements,
        size_t SizeOfElements,
        _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)
{
  return bsearch(Key, Base, NumOfElements, SizeOfElements, CompareFunction);
}

```

## disassembly

```asm
0x18001e7d0  jmp     cs:__imp_bsearch
```

# _o_bsearch_s_0

- ea: `0x1400058ce`
- end: `0x1400058d4`
- name: `_o_bsearch_s_0`
- size: `6`
- prototype: `void *__cdecl(const void *Key, const void *Base, rsize_t NumOfElements, rsize_t SizeOfElements, _CoreCrtSecureSearchSortCompareFunction CompareFunction, void *Context)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch_s` at `0x1400058ce`

## pseudocode

```c
// attributes: thunk
void *__cdecl o_bsearch_s_0(
        const void *Key,
        const void *Base,
        rsize_t NumOfElements,
        rsize_t SizeOfElements,
        _CoreCrtSecureSearchSortCompareFunction CompareFunction,
        void *Context)
{
  return bsearch_s(Key, Base, NumOfElements, SizeOfElements, CompareFunction, Context);
}

```

## disassembly

```asm
0x1400058ce  jmp     cs:__imp_bsearch_s
```

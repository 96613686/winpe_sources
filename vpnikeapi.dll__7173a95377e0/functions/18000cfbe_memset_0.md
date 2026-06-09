# memset_0

- ea: `0x18000cfbe`
- end: `0x18000cfc4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `40`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011c0`
- `0x1800013c0`
- `0x180001670`
- `0x180002360`
- `0x180002660`
- `0x180002910`
- `0x180002b70`
- `0x180002f80`
- `0x180003120`
- `0x1800032c0`
- `0x180003470`
- `0x180003620`
- `0x1800038d0`
- `0x180003b80`
- `0x180003e30`
- `0x180004110`
- `0x1800044a0`
- `0x180004780`
- `0x180004a20`
- `0x180004cd0`
- `0x180004f80`
- `0x1800052f0`
- `0x1800055b0`
- `0x180005880`
- `0x180005b30`
- `0x180005de0`
- `0x1800060c0`
- `0x180006620`
- `0x180006720`
- `0x18000701c`
- `0x180007284`
- `0x180007520`
- `0x180007730`
- `0x180008a04`
- `0x180009a80`
- `0x18000ae54`
- `0x18000bae0`
- `0x18000c154`
- `0x18000c330`
- `0x18000cd44`

## import_xrefs

- `msvcrt!memset` at `0x18000cfbe`

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
0x18000cfbe  jmp     cs:__imp_memset
```

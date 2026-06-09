# memcmp

- ea: `0x1800932cc`
- end: `0x1800932d2`
- name: `memcmp`
- size: `6`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180019a14`
- `0x180019d00`
- `0x180019e78`
- `0x18001ae0c`
- `0x18001b9d0`
- `0x180038c50`
- `0x180076124`
- `0x180089520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x1800932cc`

## pseudocode

```c
// attributes: thunk
int __cdecl memcmp(const void *Buf1, const void *Buf2, size_t Size)
{
  return __imp_memcmp(Buf1, Buf2, Size);
}

```

## disassembly

```asm
0x1800932cc  jmp     cs:__imp_memcmp
```

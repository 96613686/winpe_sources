# memset_0

- ea: `0x180010fca`
- end: `0x180010fd0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019c8`
- `0x180001e28`
- `0x180002c90`
- `0x180002f24`
- `0x18000331c`
- `0x1800034fc`
- `0x180003f90`
- `0x180004f90`
- `0x180005660`
- `0x180007f90`
- `0x180009364`
- `0x18000a09c`
- `0x18000a65c`
- `0x18000b100`
- `0x18000b5b0`
- `0x18000c894`
- `0x18000ca70`
- `0x18000cf58`
- `0x18000d68c`
- `0x18000e7c0`
- `0x18000f8bc`
- `0x18000feb0`
- `0x18000ffc0`

## import_xrefs

- `msvcrt!memset` at `0x180010fca`

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
0x180010fca  jmp     cs:__imp_memset
```

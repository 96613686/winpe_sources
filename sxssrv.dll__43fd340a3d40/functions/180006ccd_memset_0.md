# memset_0

- ea: `0x180006ccd`
- end: `0x180006cd3`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001450`
- `0x180001e00`
- `0x180002d40`
- `0x180003230`
- `0x180003310`
- `0x180004390`
- `0x180004e60`
- `0x180005170`
- `0x180006b08`

## import_xrefs

- `ntdll!memset` at `0x180006ccd`

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
0x180006ccd  jmp     cs:__imp_memset
```

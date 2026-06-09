# memset_0

- ea: `0x18000ae4e`
- end: `0x18000ae54`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a6c`
- `0x180001d10`
- `0x180002518`
- `0x180002a00`
- `0x180003280`
- `0x180003510`
- `0x180003820`
- `0x180003aac`
- `0x180003e10`
- `0x180004000`
- `0x1800044a0`
- `0x180004c30`
- `0x180004f10`
- `0x180005370`
- `0x180005830`
- `0x180005ea0`
- `0x180006168`
- `0x180006380`
- `0x180006590`
- `0x180006794`
- `0x180006a20`
- `0x1800070f0`
- `0x180007450`
- `0x18000863c`
- `0x180008968`
- `0x180008be4`
- `0x180008e70`
- `0x180009330`
- `0x180009550`
- `0x180009720`
- `0x180009b34`
- `0x180009ee4`
- `0x18000a414`

## import_xrefs

- `msvcrt!memset` at `0x18000ae4e`

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
0x18000ae4e  jmp     cs:__imp_memset
```

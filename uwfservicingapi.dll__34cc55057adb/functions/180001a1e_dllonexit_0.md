# __dllonexit_0

- ea: `0x180001a1e`
- end: `0x180001a24`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000175c`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001a1e`

## pseudocode

```c
// attributes: thunk
__int64 _dllonexit_0()
{
  return __dllonexit();
}

```

## disassembly

```asm
0x180001a1e  jmp     cs:__imp___dllonexit
```

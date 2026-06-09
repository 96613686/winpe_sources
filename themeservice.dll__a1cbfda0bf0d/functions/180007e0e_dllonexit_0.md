# __dllonexit_0

- ea: `0x180007e0e`
- end: `0x180007e14`
- name: `__dllonexit_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007948`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180007e0e`

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
0x180007e0e  jmp     cs:__imp___dllonexit
```

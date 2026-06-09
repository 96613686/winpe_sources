# __dllonexit

- ea: `0x18000428e`
- end: `0x180004294`
- name: `__dllonexit`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003dd8`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18000428e`

## pseudocode

```c
// attributes: thunk
__int64 _dllonexit()
{
  return __dllonexit();
}

```

## disassembly

```asm
0x18000428e  jmp     cs:__imp___dllonexit
```

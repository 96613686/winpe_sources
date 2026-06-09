# __dllonexit_0

- ea: `0x180001f3b`
- end: `0x180001f41`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001b6c`

## import_xrefs

- `msvcrt!__dllonexit` at `0x180001f3b`

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
0x180001f3b  jmp     cs:__imp___dllonexit
```

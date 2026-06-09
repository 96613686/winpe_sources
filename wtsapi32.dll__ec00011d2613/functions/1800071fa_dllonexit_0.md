# __dllonexit_0

- ea: `0x1800071fa`
- end: `0x180007200`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006d24`

## import_xrefs

- `msvcrt!__dllonexit` at `0x1800071fa`

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
0x1800071fa  jmp     cs:__imp___dllonexit
```

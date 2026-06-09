# __dllonexit_0

- ea: `0x18002ac7c`
- end: `0x18002ac82`
- name: `__dllonexit_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18002a568`

## import_xrefs

- `msvcrt!__dllonexit` at `0x18002ac7c`

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
0x18002ac7c  jmp     cs:__imp___dllonexit
```

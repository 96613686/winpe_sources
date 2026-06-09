# __dllonexit3_0

- ea: `0x180018bb7`
- end: `0x180018bbd`
- name: `__dllonexit3_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180018a44`

## import_xrefs

- `api-ms-win-core-crt-l2-1-0!__dllonexit3` at `0x180018bb7`

## pseudocode

```c
// attributes: thunk
__int64 _dllonexit3_0()
{
  return __dllonexit3();
}

```

## disassembly

```asm
0x180018bb7  jmp     cs:__imp___dllonexit3
```

# _XcptFilter_0

- ea: `0x14000156e`
- end: `0x140001574`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001140`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x14000156e`

## pseudocode

```c
// attributes: thunk
__int64 XcptFilter_0()
{
  return _XcptFilter();
}

```

## disassembly

```asm
0x14000156e  jmp     cs:__imp__XcptFilter
```

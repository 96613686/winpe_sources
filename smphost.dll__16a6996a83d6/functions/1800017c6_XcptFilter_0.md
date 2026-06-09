# _XcptFilter_0

- ea: `0x1800017c6`
- end: `0x1800017cc`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015a4`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x1800017c6`

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
0x1800017c6  jmp     cs:__imp__XcptFilter
```

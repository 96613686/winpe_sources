# _XcptFilter_0

- ea: `0x180001bf8`
- end: `0x180001bfe`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018d0`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x180001bf8`

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
0x180001bf8  jmp     cs:__imp__XcptFilter
```

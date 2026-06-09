# _XcptFilter_0

- ea: `0x180001d1a`
- end: `0x180001d20`
- name: `_XcptFilter_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ae4`

## import_xrefs

- `msvcrt!_XcptFilter` at `0x180001d1a`

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
0x180001d1a  jmp     cs:__imp__XcptFilter
```

# __CxxFrameHandler4_0

- ea: `0x1800014e2`
- end: `0x1800014e8`
- name: `__CxxFrameHandler4_0`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `msvcrt!__CxxFrameHandler4` at `0x1800014e2`

## pseudocode

```c
// attributes: thunk
__int64 _CxxFrameHandler4_0()
{
  return __CxxFrameHandler4();
}

```

## disassembly

```asm
0x1800014e2  jmp     cs:__imp___CxxFrameHandler4
```

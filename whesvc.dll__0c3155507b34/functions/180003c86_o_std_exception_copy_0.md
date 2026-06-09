# _o___std_exception_copy_0

- ea: `0x180003c86`
- end: `0x180003c8c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004f98`
- `0x1800050ac`
- `0x180005118`
- `0x180005150`
- `0x180005194`
- `0x180010e84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003c86`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180003c86  jmp     cs:__imp__o___std_exception_copy
```

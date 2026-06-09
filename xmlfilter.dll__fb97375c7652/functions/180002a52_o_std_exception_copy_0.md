# _o___std_exception_copy_0

- ea: `0x180002a52`
- end: `0x180002a58`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040e4`
- `0x1800042c0`
- `0x180004304`
- `0x180004370`
- `0x180013dc8`
- `0x180013e0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002a52`

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
0x180002a52  jmp     cs:__imp__o___std_exception_copy
```

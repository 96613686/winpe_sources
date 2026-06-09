# _o___std_exception_copy_0

- ea: `0x1800131fa`
- end: `0x180013200`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180013a5c`
- `0x180013ac8`
- `0x1800338a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800131fa`

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
0x1800131fa  jmp     cs:__imp__o___std_exception_copy
```

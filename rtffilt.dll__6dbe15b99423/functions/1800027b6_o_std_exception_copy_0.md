# _o___std_exception_copy_0

- ea: `0x1800027b6`
- end: `0x1800027bc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c10`
- `0x180003dec`
- `0x180003e58`
- `0x180003ec4`
- `0x180003efc`
- `0x180003f40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800027b6`

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
0x1800027b6  jmp     cs:__imp__o___std_exception_copy
```

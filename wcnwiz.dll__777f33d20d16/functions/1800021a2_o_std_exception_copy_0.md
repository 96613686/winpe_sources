# _o___std_exception_copy_0

- ea: `0x1800021a2`
- end: `0x1800021a8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800108a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800021a2`

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
0x1800021a2  jmp     cs:__imp__o___std_exception_copy
```

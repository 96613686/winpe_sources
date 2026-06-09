# _o___std_exception_copy_0

- ea: `0x180001c1e`
- end: `0x180001c24`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d84`
- `0x180001df0`
- `0x180001e5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001c1e`

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
0x180001c1e  jmp     cs:__imp__o___std_exception_copy
```

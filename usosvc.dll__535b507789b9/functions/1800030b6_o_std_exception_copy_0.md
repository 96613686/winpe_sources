# _o___std_exception_copy_0

- ea: `0x1800030b6`
- end: `0x1800030bc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b60`
- `0x180003c74`
- `0x18000837c`
- `0x180008574`
- `0x1800085c8`
- `0x18000860c`
- `0x180008678`
- `0x1800088bc`
- `0x180008900`
- `0x180008960`
- `0x1800089c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800030b6`

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
0x1800030b6  jmp     cs:__imp__o___std_exception_copy
```

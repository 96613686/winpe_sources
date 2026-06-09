# _o___std_exception_copy

- ea: `0x180004112`
- end: `0x180004118`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006c3c`
- `0x180006c90`
- `0x180006d0c`
- `0x180006d50`
- `0x18001a40c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180004112`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180004112  jmp     cs:__imp__o___std_exception_copy
```

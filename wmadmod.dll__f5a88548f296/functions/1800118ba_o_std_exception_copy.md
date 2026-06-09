# _o___std_exception_copy

- ea: `0x1800118ba`
- end: `0x1800118c0`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18008c9d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800118ba`

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
0x1800118ba  jmp     cs:__imp__o___std_exception_copy
```

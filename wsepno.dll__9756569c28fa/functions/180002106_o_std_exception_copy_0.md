# _o___std_exception_copy_0

- ea: `0x180002106`
- end: `0x18000210c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000232c`
- `0x180002440`
- `0x18000c518`
- `0x18000c584`
- `0x18000c5f0`
- `0x18000c634`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002106`

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
0x180002106  jmp     cs:__imp__o___std_exception_copy
```

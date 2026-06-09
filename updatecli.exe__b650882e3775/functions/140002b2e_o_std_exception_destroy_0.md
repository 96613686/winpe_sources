# _o___std_exception_destroy_0

- ea: `0x140002b2e`
- end: `0x140002b34`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000381c`
- `0x1400039d0`
- `0x1400089c8`
- `0x1400089e4`
- `0x140009130`
- `0x140009180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140002b2e`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x140002b2e  jmp     cs:__imp___std_exception_destroy
```

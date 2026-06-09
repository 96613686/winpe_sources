# _o___std_exception_destroy_0

- ea: `0x140002b46`
- end: `0x140002b4c`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000383c`
- `0x1400039f0`
- `0x140008998`
- `0x1400089b4`
- `0x140009100`
- `0x140009150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x140002b46`

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
0x140002b46  jmp     cs:__imp___std_exception_destroy
```

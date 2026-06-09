# _o___std_exception_copy_0

- ea: `0x18000fb62`
- end: `0x18000fb68`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d68`
- `0x18000307c`
- `0x180006a98`
- `0x180006e34`
- `0x180007f60`
- `0x180008038`
- `0x180008098`
- `0x180008484`
- `0x180008dfc`
- `0x180008e78`
- `0x18000a718`
- `0x18000a75c`
- `0x18000eff0`
- `0x18000f06c`
- `0x18000f110`
- `0x18000f17c`
- `0x180014374`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000fb62`

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
0x18000fb62  jmp     cs:__imp__o___std_exception_copy
```

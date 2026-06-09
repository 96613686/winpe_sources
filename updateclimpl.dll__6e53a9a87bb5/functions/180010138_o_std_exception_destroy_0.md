# _o___std_exception_destroy_0

- ea: `0x180010138`
- end: `0x18001013e`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004670`
- `0x1800056ac`
- `0x18000a1f4`
- `0x18000a210`
- `0x1800135b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180010138`

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
0x180010138  jmp     cs:__imp___std_exception_destroy
```

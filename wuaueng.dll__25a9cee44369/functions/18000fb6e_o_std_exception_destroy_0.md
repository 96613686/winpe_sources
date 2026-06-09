# _o___std_exception_destroy_0

- ea: `0x18000fb6e`
- end: `0x18000fb74`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dc0`
- `0x180002edc`
- `0x180007ca4`
- `0x180007ce8`
- `0x180007d10`
- `0x180007ff0`
- `0x1800143e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x18000fb6e`

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
0x18000fb6e  jmp     cs:__imp___std_exception_destroy
```

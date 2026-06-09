# _o___std_exception_destroy_0

- ea: `0x180002fe2`
- end: `0x180002fe8`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002ef4`
- `0x180002f10`
- `0x1800040e4`
- `0x1800041e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x180002fe2`

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
0x180002fe2  jmp     cs:__imp___std_exception_destroy
```

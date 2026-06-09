# _o___std_exception_destroy_0

- ea: `0x18000ec25`
- end: `0x18000ec2b`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800013d0`
- `0x180001494`
- `0x1800017b0`
- `0x180002650`
- `0x1800026b4`
- `0x1800087ec`
- `0x1800134a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x18000ec25`

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
0x18000ec25  jmp     cs:__imp___std_exception_destroy
```

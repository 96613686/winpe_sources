# _o___std_exception_destroy_0

- ea: `0x18000fbbe`
- end: `0x18000fbc4`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dc0`
- `0x180002edc`
- `0x180005660`
- `0x180005970`
- `0x180006810`
- `0x180006874`
- `0x180014430`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x18000fbbe`

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
0x18000fbbe  jmp     cs:__imp___std_exception_destroy
```

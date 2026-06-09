# _o___std_exception_copy_0

- ea: `0x18001012c`
- end: `0x180010132`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180004618`
- `0x18000584c`
- `0x180009c54`
- `0x18000a258`
- `0x18000a2b8`
- `0x18000a318`
- `0x18000a3bc`
- `0x18000d2f8`
- `0x18000d33c`
- `0x18000d468`
- `0x18000d4ac`
- `0x18000da40`
- `0x18000dabc`
- `0x18000db60`
- `0x18000dbcc`
- `0x18000dc38`
- `0x180013538`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18001012c`

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
0x18001012c  jmp     cs:__imp__o___std_exception_copy
```

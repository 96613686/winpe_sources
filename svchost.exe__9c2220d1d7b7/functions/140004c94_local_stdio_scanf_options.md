# __local_stdio_scanf_options

- ea: `0x140004c94`
- end: `0x140004c9c`
- name: `__local_stdio_scanf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140004c60`
- `0x140004cb0`
- `0x14000533c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_scanf_options()
{
  return (unsigned __int64 *)&`__local_stdio_scanf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x140004c94  lea     rax, ?_OptionsStorage@?1??__local_stdio_scanf_options@@9@4_KA; unsigned __int64 `__local_stdio_scanf_options'::`2'::_OptionsStorage
0x140004c9b  retn
```

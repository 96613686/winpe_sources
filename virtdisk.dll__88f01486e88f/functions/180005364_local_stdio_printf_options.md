# __local_stdio_printf_options

- ea: `0x180005364`
- end: `0x18000536c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005340`
- `0x180005390`
- `0x180005864`
- `0x180005fe4`
- `0x180006038`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180005364  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18000536b  retn
```

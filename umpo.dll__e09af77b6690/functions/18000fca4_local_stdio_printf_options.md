# __local_stdio_printf_options

- ea: `0x18000fca4`
- end: `0x18000fcac`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fc80`
- `0x18000fcd0`
- `0x1800101d0`
- `0x180010954`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x18000fca4  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18000fcab  retn
```

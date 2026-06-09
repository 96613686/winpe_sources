# __local_stdio_printf_options

- ea: `0x18000b184`
- end: `0x18000b18c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b160`
- `0x18000b1b0`
- `0x18000ba70`
- `0x18000c1bc`
- `0x18000c210`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x18000b184  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18000b18b  retn
```

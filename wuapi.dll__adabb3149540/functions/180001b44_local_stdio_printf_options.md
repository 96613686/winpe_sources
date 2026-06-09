# __local_stdio_printf_options

- ea: `0x180001b44`
- end: `0x180001b4c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001bfc`
- `0x180001ca8`
- `0x18000ae48`
- `0x18000dc70`
- `0x18000df84`
- `0x180010c14`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180001b44  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x180001b4b  retn
```

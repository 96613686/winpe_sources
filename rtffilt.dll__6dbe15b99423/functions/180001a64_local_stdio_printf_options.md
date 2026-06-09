# __local_stdio_printf_options

- ea: `0x180001a64`
- end: `0x180001a6c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a40`
- `0x180001a90`
- `0x1800023ec`
- `0x1800028cc`
- `0x18000292c`
- `0x180002980`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180001a64  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x180001a6b  retn
```

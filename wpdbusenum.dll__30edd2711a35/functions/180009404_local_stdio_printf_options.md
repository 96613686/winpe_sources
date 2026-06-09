# __local_stdio_printf_options

- ea: `0x180009404`
- end: `0x18000940c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800093e0`
- `0x180009430`
- `0x180009ce8`
- `0x18000a1a0`
- `0x18000a1f4`
- `0x18000a244`
- `0x18000a294`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180009404  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18000940b  retn
```

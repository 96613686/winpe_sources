# ___local_stdio_printf_options

- ea: `0x10003835`
- end: `0x1000383b`
- name: `___local_stdio_printf_options`
- size: `6`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x10003810`
- `0x10003850`
- `0x10003d51`
- `0x10004573`
- `0x100045d0`

## pseudocode

```c
unsigned __int64 *__cdecl __local_stdio_printf_options()
{
  return (unsigned __int64 *)`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x10003835  mov     eax, offset ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x1000383a  retn
```

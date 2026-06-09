# __stdio_common_vfwprintf

- ea: `0x180006e56`
- end: `0x180006e5c`
- name: `__stdio_common_vfwprintf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfwprintf` at `0x180006e56`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vfwprintf(
        unsigned __int64 Options,
        FILE *Stream,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vfwprintf(Options, Stream, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x180006e56  jmp     cs:__imp___stdio_common_vfwprintf
```

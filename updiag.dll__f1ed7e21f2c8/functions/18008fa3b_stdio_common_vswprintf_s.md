# __stdio_common_vswprintf_s

- ea: `0x18008fa3b`
- end: `0x18008fa41`
- name: `__stdio_common_vswprintf_s`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003b24c`
- `0x18003b8b0`
- `0x180068de8`
- `0x180068fb8`
- `0x18007486c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x18008fa3b`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vswprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return _o___stdio_common_vswprintf_s(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x18008fa3b  jmp     cs:__imp__o___stdio_common_vswprintf_s
```

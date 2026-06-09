# _create_locale

- ea: `0x1800424c2`
- end: `0x1800424c8`
- name: `_create_locale`
- size: `6`
- prototype: `_locale_t __cdecl(int Category, const char *Locale)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180031b14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800424c2`

## pseudocode

```c
// attributes: thunk
_locale_t __cdecl create_locale(int Category, const char *Locale)
{
  return _create_locale(Category, Locale);
}

```

## disassembly

```asm
0x1800424c2  jmp     cs:__imp__create_locale
```

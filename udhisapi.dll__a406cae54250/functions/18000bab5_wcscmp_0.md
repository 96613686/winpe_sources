# wcscmp_0

- ea: `0x18000bab5`
- end: `0x18000babb`
- name: `wcscmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008a4c`
- `0x18000afb4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x18000bab5`

## pseudocode

```c
// attributes: thunk
int __cdecl wcscmp_0(const wchar_t *String1, const wchar_t *String2)
{
  return wcscmp(String1, String2);
}

```

## disassembly

```asm
0x18000bab5  jmp     cs:__imp_wcscmp
```

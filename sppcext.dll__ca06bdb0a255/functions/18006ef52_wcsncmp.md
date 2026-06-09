# wcsncmp

- ea: `0x18006ef52`
- end: `0x18006ef58`
- name: `wcsncmp`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x1800361a0`
- `0x18003882c`
- `0x180041130`
- `0x180046788`
- `0x180046b34`
- `0x18004f990`
- `0x1800507c8`
- `0x1800510d8`
- `0x180053a6c`
- `0x180055880`
- `0x180055ee0`
- `0x180056290`
- `0x180057144`
- `0x1800573f0`
- `0x180059094`

## import_xrefs

- `msvcrt!wcsncmp` at `0x18006ef52`

## pseudocode

```c
// attributes: thunk
int __cdecl wcsncmp(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)
{
  return __imp_wcsncmp(String1, String2, MaxCount);
}

```

## disassembly

```asm
0x18006ef52  jmp     cs:__imp_wcsncmp
```

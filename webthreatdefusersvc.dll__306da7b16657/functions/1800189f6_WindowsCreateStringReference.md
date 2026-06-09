# WindowsCreateStringReference

- ea: `0x1800189f6`
- end: `0x1800189fc`
- name: `WindowsCreateStringReference`
- size: `6`
- prototype: `HRESULT __stdcall(PCWSTR sourceString, UINT32 length, HSTRING_HEADER *hstringHeader, HSTRING *string)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800042c0`
- `0x18000ab70`
- `0x18000b774`
- `0x18000bd70`
- `0x18000ca50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800189f6`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsCreateStringReference(
        PCWSTR sourceString,
        UINT32 length,
        HSTRING_HEADER *hstringHeader,
        HSTRING *string)
{
  return __imp_WindowsCreateStringReference(sourceString, length, hstringHeader, string);
}

```

## disassembly

```asm
0x1800189f6  jmp     cs:__imp_WindowsCreateStringReference
```

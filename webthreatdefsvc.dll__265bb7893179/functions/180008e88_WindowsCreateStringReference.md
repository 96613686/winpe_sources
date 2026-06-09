# WindowsCreateStringReference

- ea: `0x180008e88`
- end: `0x180008e8e`
- name: `WindowsCreateStringReference`
- size: `6`
- prototype: `HRESULT __stdcall(PCWSTR sourceString, UINT32 length, HSTRING_HEADER *hstringHeader, HSTRING *string)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180004df0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008e88`

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
0x180008e88  jmp     cs:__imp_WindowsCreateStringReference
```

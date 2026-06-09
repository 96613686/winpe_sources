# WindowsCreateString

- ea: `0x180008df1`
- end: `0x180008df7`
- name: `WindowsCreateString`
- size: `6`
- prototype: `HRESULT __stdcall(PCNZWCH sourceString, UINT32 length, HSTRING *string)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005590`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180008df1`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsCreateString(PCNZWCH sourceString, UINT32 length, HSTRING *string)
{
  return __imp_WindowsCreateString(sourceString, length, string);
}

```

## disassembly

```asm
0x180008df1  jmp     cs:__imp_WindowsCreateString
```

# WindowsCreateString

- ea: `0x180018953`
- end: `0x180018959`
- name: `WindowsCreateString`
- size: `6`
- prototype: `HRESULT __stdcall(PCNZWCH sourceString, UINT32 length, HSTRING *string)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a5f0`
- `0x18000a6b0`
- `0x18000a6e0`
- `0x180011620`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018953`

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
0x180018953  jmp     cs:__imp_WindowsCreateString
```

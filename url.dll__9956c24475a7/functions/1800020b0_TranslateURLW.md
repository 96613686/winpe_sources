# TranslateURLW

- ea: `0x1800020b0`
- end: `0x1800020b7`
- name: `TranslateURLW`
- size: `7`
- prototype: `HRESULT __stdcall(PCWSTR pcszURL, DWORD dwInFlags, PWSTR *ppszTranslatedURL)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `IEFRAME!URLQualifyW` at `0x1800020b0`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall TranslateURLW(PCWSTR pcszURL, DWORD dwInFlags, PWSTR *ppszTranslatedURL)
{
  return URLQualifyW(pcszURL, dwInFlags, ppszTranslatedURL);
}

```

## disassembly

```asm
0x1800020b0  jmp     cs:__imp_URLQualifyW
```

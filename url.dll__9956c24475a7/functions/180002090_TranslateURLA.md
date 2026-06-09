# TranslateURLA

- ea: `0x180002090`
- end: `0x180002097`
- name: `TranslateURLA`
- size: `7`
- prototype: `HRESULT __stdcall(PCSTR pcszURL, DWORD dwInFlags, PSTR *ppszTranslatedURL)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `IEFRAME!URLQualifyA` at `0x180002090`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall TranslateURLA(PCSTR pcszURL, DWORD dwInFlags, PSTR *ppszTranslatedURL)
{
  return URLQualifyA(pcszURL, dwInFlags, ppszTranslatedURL);
}

```

## disassembly

```asm
0x180002090  jmp     cs:__imp_URLQualifyA
```

# BCryptOpenAlgorithmProvider

- ea: `0x14001693e`
- end: `0x140016945`
- name: `BCryptOpenAlgorithmProvider`
- size: `7`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000338c`
- `0x140004e34`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x14001693e`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall BCryptOpenAlgorithmProvider(
        BCRYPT_ALG_HANDLE *phAlgorithm,
        LPCWSTR pszAlgId,
        LPCWSTR pszImplementation,
        ULONG dwFlags)
{
  return __imp_BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, pszImplementation, dwFlags);
}

```

## disassembly

```asm
0x14001693e  jmp     cs:__imp_BCryptOpenAlgorithmProvider
```

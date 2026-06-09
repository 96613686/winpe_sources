# GetFileVersionInfoSizeExWStub

- ea: `0x180001040`
- end: `0x180001047`
- name: `GetFileVersionInfoSizeExWStub`
- size: `7`
- prototype: `DWORD __stdcall(DWORD dwFlags, LPCWSTR lpwstrFilename, LPDWORD lpdwHandle)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180001040`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetFileVersionInfoSizeExWStub(DWORD dwFlags, LPCWSTR lpwstrFilename, LPDWORD lpdwHandle)
{
  return GetFileVersionInfoSizeExW(dwFlags, lpwstrFilename, lpdwHandle);
}

```

## disassembly

```asm
0x180001040  jmp     cs:__imp_GetFileVersionInfoSizeExW
```

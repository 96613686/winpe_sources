# GetFileVersionInfoSizeWStub

- ea: `0x180001010`
- end: `0x180001017`
- name: `GetFileVersionInfoSizeWStub`
- size: `7`
- prototype: `DWORD __stdcall(LPCWSTR lptstrFilename, LPDWORD lpdwHandle)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180001010`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetFileVersionInfoSizeWStub(LPCWSTR lptstrFilename, LPDWORD lpdwHandle)
{
  return GetFileVersionInfoSizeW(lptstrFilename, lpdwHandle);
}

```

## disassembly

```asm
0x180001010  jmp     cs:__imp_GetFileVersionInfoSizeW
```

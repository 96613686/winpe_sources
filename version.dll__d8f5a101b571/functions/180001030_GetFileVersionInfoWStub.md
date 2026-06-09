# GetFileVersionInfoWStub

- ea: `0x180001030`
- end: `0x180001037`
- name: `GetFileVersionInfoWStub`
- size: `7`
- prototype: `BOOL __stdcall(LPCWSTR lptstrFilename, DWORD dwHandle, DWORD dwLen, LPVOID lpData)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180001030`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall GetFileVersionInfoWStub(LPCWSTR lptstrFilename, DWORD dwHandle, DWORD dwLen, LPVOID lpData)
{
  return GetFileVersionInfoW(lptstrFilename, dwHandle, dwLen, lpData);
}

```

## disassembly

```asm
0x180001030  jmp     cs:__imp_GetFileVersionInfoW
```

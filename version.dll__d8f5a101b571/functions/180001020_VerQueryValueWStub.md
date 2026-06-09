# VerQueryValueWStub

- ea: `0x180001020`
- end: `0x180001027`
- name: `VerQueryValueWStub`
- size: `7`
- prototype: `BOOL __stdcall(LPCVOID pBlock, LPCWSTR lpSubBlock, LPVOID *lplpBuffer, PUINT puLen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180001020`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall VerQueryValueWStub(LPCVOID pBlock, LPCWSTR lpSubBlock, LPVOID *lplpBuffer, PUINT puLen)
{
  return VerQueryValueW(pBlock, lpSubBlock, lplpBuffer, puLen);
}

```

## disassembly

```asm
0x180001020  jmp     cs:__imp_VerQueryValueW
```

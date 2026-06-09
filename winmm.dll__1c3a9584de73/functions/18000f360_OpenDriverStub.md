# OpenDriverStub

- ea: `0x18000f360`
- end: `0x18000f367`
- name: `OpenDriverStub`
- size: `7`
- prototype: `HDRVR __stdcall(LPCWSTR szDriverName, LPCWSTR szSectionName, LPARAM lParam2)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `WINMMBASE!OpenDriver` at `0x18000f360`

## pseudocode

```c
// attributes: thunk
HDRVR __stdcall OpenDriverStub(LPCWSTR szDriverName, LPCWSTR szSectionName, LPARAM lParam2)
{
  return OpenDriver(szDriverName, szSectionName, lParam2);
}

```

## disassembly

```asm
0x18000f360  jmp     cs:__imp_OpenDriver
```

# WTSOpenServerExA

- ea: `0x1800082f0`
- end: `0x1800082f7`
- name: `WTSOpenServerExA`
- size: `7`
- prototype: `HANDLE __stdcall(LPSTR pServerName)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `WINSTA!WinStationOpenServerExA` at `0x1800082f0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WTSOpenServerExA(LPSTR pServerName)
{
  return WinStationOpenServerExA(pServerName);
}

```

## disassembly

```asm
0x1800082f0  jmp     cs:__imp_WinStationOpenServerExA
```

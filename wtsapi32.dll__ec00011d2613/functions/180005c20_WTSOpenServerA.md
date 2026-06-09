# WTSOpenServerA

- ea: `0x180005c20`
- end: `0x180005c27`
- name: `WTSOpenServerA`
- size: `7`
- prototype: `HANDLE __stdcall(LPSTR pServerName)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `WINSTA!WinStationOpenServerA` at `0x180005c20`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WTSOpenServerA(LPSTR pServerName)
{
  return WinStationOpenServerA(pServerName);
}

```

## disassembly

```asm
0x180005c20  jmp     cs:__imp_WinStationOpenServerA
```

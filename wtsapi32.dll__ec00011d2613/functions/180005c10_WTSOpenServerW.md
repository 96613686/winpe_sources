# WTSOpenServerW

- ea: `0x180005c10`
- end: `0x180005c17`
- name: `WTSOpenServerW`
- size: `7`
- prototype: `HANDLE __stdcall(LPWSTR pServerName)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `WINSTA!WinStationOpenServerW` at `0x180005c10`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WTSOpenServerW(LPWSTR pServerName)
{
  return WinStationOpenServerW(pServerName);
}

```

## disassembly

```asm
0x180005c10  jmp     cs:__imp_WinStationOpenServerW
```

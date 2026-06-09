# WTSOpenServerExW

- ea: `0x180005bc0`
- end: `0x180005bc7`
- name: `WTSOpenServerExW`
- size: `7`
- prototype: `HANDLE __stdcall(LPWSTR pServerName)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `WINSTA!WinStationOpenServerExW` at `0x180005bc0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WTSOpenServerExW(LPWSTR pServerName)
{
  return WinStationOpenServerExW(pServerName);
}

```

## disassembly

```asm
0x180005bc0  jmp     cs:__imp_WinStationOpenServerExW
```

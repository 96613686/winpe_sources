# WTSVirtualChannelOpen

- ea: `0x180006570`
- end: `0x180006578`
- name: `WTSVirtualChannelOpen`
- size: `8`
- prototype: `HANDLE __stdcall(HANDLE hServer, DWORD SessionId, LPSTR pVirtualName)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005190`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HANDLE __stdcall WTSVirtualChannelOpen(HANDLE hServer, DWORD SessionId, LPSTR pVirtualName)
{
  return WTSVirtualChannelOpen((__int64)hServer, *(__int64 *)&SessionId, pVirtualName, 0);
}

```

## disassembly

```asm
0x180006570  xor     r9d, r9d
0x180006573  jmp     _WTSVirtualChannelOpen
```

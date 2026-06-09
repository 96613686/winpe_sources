# WTSVirtualChannelOpenEx

- ea: `0x180005170`
- end: `0x18000517f`
- name: `WTSVirtualChannelOpenEx`
- size: `15`
- prototype: `HANDLE __stdcall(DWORD SessionId, LPSTR pVirtualName, DWORD flags)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005190`

## pseudocode

```c
HANDLE __stdcall WTSVirtualChannelOpenEx(DWORD SessionId, LPSTR pVirtualName, DWORD flags)
{
  return WTSVirtualChannelOpen(0, SessionId, pVirtualName, flags);
}

```

## disassembly

```asm
0x180005170  mov     r9d, r8d
0x180005173  mov     r8, rdx
0x180005176  mov     edx, ecx
0x180005178  xor     ecx, ecx
0x18000517a  jmp     _WTSVirtualChannelOpen
```

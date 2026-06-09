# W32WinStationStopScreenUpdates

- ea: `0x180010950`
- end: `0x1800109c8`
- name: `W32WinStationStopScreenUpdates`
- size: `120`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180010950`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800109b3`
- `ntdll!NtDeviceIoControlFile` at `0x1800109b3`
- `win32u!NtUserRemoteStopScreenUpdates` at `0x180010956`
- `win32u!NtUserRemoteStopScreenUpdates` at `0x180010956`

## pseudocode

```c
__int64 W32WinStationStopScreenUpdates()
{
  int v0; // ebx
  HANDLE v1; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  v0 = NtUserRemoteStopScreenUpdates();
  if ( v0 >= 0 )
  {
    v1 = G_IcaVideoChannel;
    if ( G_fConsoleShadow )
      v1 = G_DupConsoleShadowVideoChannel;
    IoStatusBlock = 0;
    NtDeviceIoControlFile(v1, 0, 0, 0, &IoStatusBlock, 0x381010u, 0, 0, 0, 0);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180010950  push    rbx
0x180010952  sub     rsp, 60h
0x180010956  call    cs:__imp_NtUserRemoteStopScreenUpdates
0x18001095d  nop     dword ptr [rax+rax+00h]
0x180010962  mov     ebx, eax
0x180010964  xor     eax, eax
0x180010966  test    ebx, ebx
0x180010968  js      short loc_1800109BF
0x18001096a  cmp     cs:G_fConsoleShadow, eax
0x180010970  xorps   xmm0, xmm0
0x180010973  mov     rcx, cs:G_IcaVideoChannel
0x18001097a  cmovnz  rcx, cs:G_DupConsoleShadowVideoChannel; FileHandle
0x180010982  xor     r9d, r9d; ApcContext
0x180010985  mov     [rsp+68h+OutputBufferLength], eax; OutputBufferLength
0x180010989  xor     r8d, r8d; ApcRoutine
0x18001098c  mov     [rsp+68h+OutputBuffer], rax; OutputBuffer
0x180010991  xor     edx, edx; Event
0x180010993  mov     [rsp+68h+InputBufferLength], eax; InputBufferLength
0x180010997  mov     [rsp+68h+InputBuffer], rax; InputBuffer
0x18001099c  lea     rax, [rsp+68h+var_18]
0x1800109a1  mov     [rsp+68h+IoControlCode], 381010h; IoControlCode
0x1800109a9  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800109ae  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1800109b3  call    cs:__imp_NtDeviceIoControlFile
0x1800109ba  nop     dword ptr [rax+rax+00h]
0x1800109bf  mov     eax, ebx
0x1800109c1  add     rsp, 60h
0x1800109c5  pop     rbx
0x1800109c6  retn
```

# W32WinStationDoDisconnect

- ea: `0x180010220`
- end: `0x1800103fc`
- name: `W32WinStationDoDisconnect`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e3b8`
- `0x18000f954`
- `0x180010220`
- `0x1800138c5`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800102f8`
- `ntdll!NtDeviceIoControlFile` at `0x180010358`
- `ntdll!NtDeviceIoControlFile` at `0x1800102f8`
- `ntdll!NtDeviceIoControlFile` at `0x180010358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001028e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001030d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001036d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001038c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001028e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001030d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001036d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001038c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103ab`
- `win32u!NtUserRemoteConsoleShadowStop` at `0x180010274`
- `win32u!NtUserRemoteConsoleShadowStop` at `0x180010274`
- `win32u!NtUserRemoteDisconnect` at `0x180010254`
- `win32u!NtUserRemoteDisconnect` at `0x180010254`
- `USER32!SystemParametersInfoW` at `0x1800103d4`
- `USER32!SystemParametersInfoW` at `0x1800103d4`

## pseudocode

```c
__int64 __fastcall W32WinStationDoDisconnect(__int64 a1)
{
  unsigned int v2; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  if ( *(_BYTE *)(a1 + 56) )
  {
    v2 = NtUserRemoteConsoleShadowStop();
    if ( G_ConsoleShadowMouseChannel )
    {
      CloseHandle(G_ConsoleShadowMouseChannel);
      G_ConsoleShadowMouseChannel = 0;
    }
    if ( G_ConsoleShadowKeyboardChannel )
    {
      CloseHandle(G_ConsoleShadowKeyboardChannel);
      G_ConsoleShadowKeyboardChannel = 0;
    }
    if ( G_ConsoleShadowCommandChannel )
    {
      v2 = NtDeviceIoControlFile(G_ConsoleShadowCommandChannel, 0, 0, 0, &IoStatusBlock, 0x38013Fu, 0, 0, 0, 0);
      CloseHandle(G_ConsoleShadowCommandChannel);
      G_ConsoleShadowCommandChannel = 0;
    }
    if ( G_ConsoleShadowVideoChannel )
    {
      v2 = NtDeviceIoControlFile(G_ConsoleShadowVideoChannel, 0, 0, 0, &IoStatusBlock, 0x38013Fu, 0, 0, 0, 0);
      CloseHandle(G_ConsoleShadowVideoChannel);
      G_ConsoleShadowVideoChannel = 0;
    }
    if ( G_ConsoleShadowBeepChannel )
    {
      CloseHandle(G_ConsoleShadowBeepChannel);
      G_ConsoleShadowBeepChannel = 0;
    }
    if ( G_ConsoleShadowThinwireChannel )
    {
      CloseHandle(G_ConsoleShadowThinwireChannel);
      G_ConsoleShadowThinwireChannel = 0;
    }
    if ( G_fCursorShadow )
      SystemParametersInfoW(0x101Bu, 0, (PVOID)1, 0);
  }
  else
  {
    memset_0(&G_WinStationName, 0, 0x40u);
    v2 = NtUserRemoteDisconnect();
    if ( !v2 )
      CloseAllInputHandles();
  }
  RemoveRemoteDisplayDeviceNode(a1 + 64);
  return v2;
}

```

## disassembly

```asm
0x180010220  mov     [rsp+arg_0], rbx
0x180010225  mov     [rsp+arg_8], rsi
0x18001022a  push    rdi
0x18001022b  sub     rsp, 60h
0x18001022f  xor     esi, esi
0x180010231  xorps   xmm0, xmm0
0x180010234  mov     rdi, rcx
0x180010237  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x18001023c  cmp     [rcx+38h], sil
0x180010240  jnz     short loc_180010274
0x180010242  xor     edx, edx; Val
0x180010244  lea     r8d, [rsi+40h]; Size
0x180010248  lea     rcx, G_WinStationName; void *
0x18001024f  call    memset_0
0x180010254  call    cs:__imp_NtUserRemoteDisconnect
0x18001025b  nop     dword ptr [rax+rax+00h]
0x180010260  mov     ebx, eax
0x180010262  test    eax, eax
0x180010264  jnz     loc_1800103E0
0x18001026a  call    CloseAllInputHandles
0x18001026f  jmp     loc_1800103E0
0x180010274  call    cs:__imp_NtUserRemoteConsoleShadowStop
0x18001027b  nop     dword ptr [rax+rax+00h]
0x180010280  mov     rcx, cs:G_ConsoleShadowMouseChannel; hObject
0x180010287  mov     ebx, eax
0x180010289  test    rcx, rcx
0x18001028c  jz      short loc_1800102A1
0x18001028e  call    cs:__imp_CloseHandle
0x180010295  nop     dword ptr [rax+rax+00h]
0x18001029a  mov     cs:G_ConsoleShadowMouseChannel, rsi
0x1800102a1  mov     rcx, cs:G_ConsoleShadowKeyboardChannel; hObject
0x1800102a8  test    rcx, rcx
0x1800102ab  jz      short loc_1800102C0
0x1800102ad  call    cs:__imp_CloseHandle
0x1800102b4  nop     dword ptr [rax+rax+00h]
0x1800102b9  mov     cs:G_ConsoleShadowKeyboardChannel, rsi
0x1800102c0  mov     rcx, cs:G_ConsoleShadowCommandChannel; FileHandle
0x1800102c7  test    rcx, rcx
0x1800102ca  jz      short loc_180010320
0x1800102cc  mov     [rsp+68h+OutputBufferLength], esi; OutputBufferLength
0x1800102d0  lea     rax, [rsp+68h+var_18]
0x1800102d5  mov     [rsp+68h+OutputBuffer], rsi; OutputBuffer
0x1800102da  xor     r9d, r9d; ApcContext
0x1800102dd  mov     [rsp+68h+InputBufferLength], esi; InputBufferLength
0x1800102e1  xor     r8d, r8d; ApcRoutine
0x1800102e4  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x1800102e9  xor     edx, edx; Event
0x1800102eb  mov     [rsp+68h+IoControlCode], 38013Fh; IoControlCode
0x1800102f3  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800102f8  call    cs:__imp_NtDeviceIoControlFile
0x1800102ff  nop     dword ptr [rax+rax+00h]
0x180010304  mov     rcx, cs:G_ConsoleShadowCommandChannel; hObject
0x18001030b  mov     ebx, eax
0x18001030d  call    cs:__imp_CloseHandle
0x180010314  nop     dword ptr [rax+rax+00h]
0x180010319  mov     cs:G_ConsoleShadowCommandChannel, rsi
0x180010320  mov     rcx, cs:G_ConsoleShadowVideoChannel; FileHandle
0x180010327  test    rcx, rcx
0x18001032a  jz      short loc_180010380
0x18001032c  mov     [rsp+68h+OutputBufferLength], esi; OutputBufferLength
0x180010330  lea     rax, [rsp+68h+var_18]
0x180010335  mov     [rsp+68h+OutputBuffer], rsi; OutputBuffer
0x18001033a  xor     r9d, r9d; ApcContext
0x18001033d  mov     [rsp+68h+InputBufferLength], esi; InputBufferLength
0x180010341  xor     r8d, r8d; ApcRoutine
0x180010344  mov     [rsp+68h+InputBuffer], rsi; InputBuffer
0x180010349  xor     edx, edx; Event
0x18001034b  mov     [rsp+68h+IoControlCode], 38013Fh; IoControlCode
0x180010353  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180010358  call    cs:__imp_NtDeviceIoControlFile
0x18001035f  nop     dword ptr [rax+rax+00h]
0x180010364  mov     rcx, cs:G_ConsoleShadowVideoChannel; hObject
0x18001036b  mov     ebx, eax
0x18001036d  call    cs:__imp_CloseHandle
0x180010374  nop     dword ptr [rax+rax+00h]
0x180010379  mov     cs:G_ConsoleShadowVideoChannel, rsi
0x180010380  mov     rcx, cs:G_ConsoleShadowBeepChannel; hObject
0x180010387  test    rcx, rcx
0x18001038a  jz      short loc_18001039F
0x18001038c  call    cs:__imp_CloseHandle
0x180010393  nop     dword ptr [rax+rax+00h]
0x180010398  mov     cs:G_ConsoleShadowBeepChannel, rsi
0x18001039f  mov     rcx, cs:G_ConsoleShadowThinwireChannel; hObject
0x1800103a6  test    rcx, rcx
0x1800103a9  jz      short loc_1800103BE
0x1800103ab  call    cs:__imp_CloseHandle
0x1800103b2  nop     dword ptr [rax+rax+00h]
0x1800103b7  mov     cs:G_ConsoleShadowThinwireChannel, rsi
0x1800103be  cmp     cs:G_fCursorShadow, esi
0x1800103c4  jz      short loc_1800103E0
0x1800103c6  xor     r9d, r9d; fWinIni
0x1800103c9  xor     edx, edx; uiParam
0x1800103cb  mov     ecx, 101Bh; uiAction
0x1800103d0  lea     r8d, [r9+1]; pvParam
0x1800103d4  call    cs:__imp_SystemParametersInfoW
0x1800103db  nop     dword ptr [rax+rax+00h]
0x1800103e0  lea     rcx, [rdi+40h]
0x1800103e4  call    RemoveRemoteDisplayDeviceNode
0x1800103e9  mov     rsi, [rsp+68h+arg_8]
0x1800103ee  mov     eax, ebx
0x1800103f0  mov     rbx, [rsp+68h+arg_0]
0x1800103f5  add     rsp, 60h
0x1800103f9  pop     rdi
0x1800103fa  retn
```

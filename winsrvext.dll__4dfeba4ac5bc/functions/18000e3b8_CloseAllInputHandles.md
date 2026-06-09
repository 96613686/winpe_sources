# CloseAllInputHandles

- ea: `0x18000e3b8`
- end: `0x18000e4e3`
- name: `CloseAllInputHandles`
- size: `299`
- prototype: `int()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010220`
- `0x1800109d0`

## callees

- `0x18000e3b8`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18000e3fb`
- `ntdll!NtDeviceIoControlFile` at `0x18000e459`
- `ntdll!NtDeviceIoControlFile` at `0x18000e3fb`
- `ntdll!NtDeviceIoControlFile` at `0x18000e459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e40e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e46c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e48b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e40e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e46c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e48b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4aa`
- `CSRSRV!CsrDereferenceThread` at `0x18000e4c9`
- `CSRSRV!CsrDereferenceThread` at `0x18000e4c9`

## pseudocode

```c
int CloseAllInputHandles()
{
  _UNKNOWN **v0; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF

  v0 = &retaddr;
  IoStatusBlock = 0;
  if ( G_IcaCommandChannel )
  {
    NtDeviceIoControlFile(G_IcaCommandChannel, 0, 0, 0, &IoStatusBlock, 0x38013Fu, 0, 0, 0, 0);
    LODWORD(v0) = CloseHandle(G_IcaCommandChannel);
    G_IcaCommandChannel = 0;
  }
  if ( G_IcaVideoChannel )
  {
    NtDeviceIoControlFile(G_IcaVideoChannel, 0, 0, 0, &IoStatusBlock, 0x38013Fu, 0, 0, 0, 0);
    LODWORD(v0) = CloseHandle(G_IcaVideoChannel);
    G_IcaVideoChannel = 0;
  }
  if ( G_IcaBeepChannel )
  {
    LODWORD(v0) = CloseHandle(G_IcaBeepChannel);
    G_IcaBeepChannel = 0;
  }
  if ( G_IcaThinwireChannel )
  {
    LODWORD(v0) = CloseHandle(G_IcaThinwireChannel);
    G_IcaThinwireChannel = 0;
  }
  if ( g_pcsrCommandThread )
  {
    LODWORD(v0) = CsrDereferenceThread(g_pcsrCommandThread);
    g_pcsrCommandThread = 0;
  }
  return (int)v0;
}

```

## disassembly

```asm
0x18000e3b8  mov     rax, rsp
0x18000e3bb  push    rbx
0x18000e3bc  sub     rsp, 60h
0x18000e3c0  mov     rcx, cs:G_IcaCommandChannel; FileHandle
0x18000e3c7  xor     ebx, ebx
0x18000e3c9  xorps   xmm0, xmm0
0x18000e3cc  movups  xmmword ptr [rax-18h], xmm0
0x18000e3d0  test    rcx, rcx
0x18000e3d3  jz      short loc_18000E421
0x18000e3d5  mov     [rax-20h], ebx
0x18000e3d8  xor     r9d, r9d; ApcContext
0x18000e3db  mov     [rax-28h], rbx
0x18000e3df  xor     r8d, r8d; ApcRoutine
0x18000e3e2  mov     [rax-30h], ebx
0x18000e3e5  xor     edx, edx; Event
0x18000e3e7  mov     [rax-38h], rbx
0x18000e3eb  mov     dword ptr [rax-40h], 38013Fh
0x18000e3f2  lea     rax, [rax-18h]
0x18000e3f6  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18000e3fb  call    cs:__imp_NtDeviceIoControlFile
0x18000e402  nop     dword ptr [rax+rax+00h]
0x18000e407  mov     rcx, cs:G_IcaCommandChannel; hObject
0x18000e40e  call    cs:__imp_CloseHandle
0x18000e415  nop     dword ptr [rax+rax+00h]
0x18000e41a  mov     cs:G_IcaCommandChannel, rbx
0x18000e421  mov     rcx, cs:G_IcaVideoChannel; FileHandle
0x18000e428  test    rcx, rcx
0x18000e42b  jz      short loc_18000E47F
0x18000e42d  mov     [rsp+68h+OutputBufferLength], ebx; OutputBufferLength
0x18000e431  lea     rax, [rsp+68h+var_18]
0x18000e436  mov     [rsp+68h+OutputBuffer], rbx; OutputBuffer
0x18000e43b  xor     r9d, r9d; ApcContext
0x18000e43e  mov     [rsp+68h+InputBufferLength], ebx; InputBufferLength
0x18000e442  xor     r8d, r8d; ApcRoutine
0x18000e445  mov     [rsp+68h+InputBuffer], rbx; InputBuffer
0x18000e44a  xor     edx, edx; Event
0x18000e44c  mov     [rsp+68h+IoControlCode], 38013Fh; IoControlCode
0x18000e454  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18000e459  call    cs:__imp_NtDeviceIoControlFile
0x18000e460  nop     dword ptr [rax+rax+00h]
0x18000e465  mov     rcx, cs:G_IcaVideoChannel; hObject
0x18000e46c  call    cs:__imp_CloseHandle
0x18000e473  nop     dword ptr [rax+rax+00h]
0x18000e478  mov     cs:G_IcaVideoChannel, rbx
0x18000e47f  mov     rcx, cs:G_IcaBeepChannel; hObject
0x18000e486  test    rcx, rcx
0x18000e489  jz      short loc_18000E49E
0x18000e48b  call    cs:__imp_CloseHandle
0x18000e492  nop     dword ptr [rax+rax+00h]
0x18000e497  mov     cs:G_IcaBeepChannel, rbx
0x18000e49e  mov     rcx, cs:G_IcaThinwireChannel; hObject
0x18000e4a5  test    rcx, rcx
0x18000e4a8  jz      short loc_18000E4BD
0x18000e4aa  call    cs:__imp_CloseHandle
0x18000e4b1  nop     dword ptr [rax+rax+00h]
0x18000e4b6  mov     cs:G_IcaThinwireChannel, rbx
0x18000e4bd  mov     rcx, cs:g_pcsrCommandThread
0x18000e4c4  test    rcx, rcx
0x18000e4c7  jz      short loc_18000E4DC
0x18000e4c9  call    cs:__imp_CsrDereferenceThread
0x18000e4d0  nop     dword ptr [rax+rax+00h]
0x18000e4d5  mov     cs:g_pcsrCommandThread, rbx
0x18000e4dc  add     rsp, 60h
0x18000e4e0  pop     rbx
0x18000e4e1  retn
```

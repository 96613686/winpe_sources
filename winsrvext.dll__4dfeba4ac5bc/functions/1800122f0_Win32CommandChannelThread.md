# Win32CommandChannelThread

- ea: `0x1800122f0`
- end: `0x18001260f`
- name: `Win32CommandChannelThread`
- size: `799`
- prototype: `void __fastcall(void *p)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800122dc`
- `0x1800122f0`
- `0x180012918`
- `0x180012c5c`
- `0x1800138c5`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800124ef`
- `ntdll!NtDeviceIoControlFile` at `0x1800124ef`
- `ntdll!RtlExitUserThread` at `0x180012602`
- `ntdll!RtlExitUserThread` at `0x180012602`
- `ntdll!NtClose` at `0x180012578`
- `ntdll!NtClose` at `0x180012597`
- `ntdll!NtClose` at `0x1800125cb`
- `ntdll!NtClose` at `0x180012578`
- `ntdll!NtClose` at `0x180012597`
- `ntdll!NtClose` at `0x1800125cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001238f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001238f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001237f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001237f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800123bb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800123bb`
- `win32u!NtUserRemoteStopScreenUpdates` at `0x180012486`
- `win32u!NtUserRemoteStopScreenUpdates` at `0x180012486`
- `win32u!NtUserRemoteRedrawRectangle` at `0x180012523`
- `win32u!NtUserRemoteRedrawRectangle` at `0x180012523`
- `win32u!NtUserRemoteRedrawScreen` at `0x1800124fd`
- `win32u!NtUserRemoteRedrawScreen` at `0x1800124fd`
- `win32u!NtUserCtxDisplayIOCtl` at `0x18001246b`
- `win32u!NtUserCtxDisplayIOCtl` at `0x18001246b`
- `win32u!NtUserSetInformationThread` at `0x180012411`
- `win32u!NtUserSetInformationThread` at `0x180012557`
- `win32u!NtUserSetInformationThread` at `0x180012411`
- `win32u!NtUserSetInformationThread` at `0x180012557`

## pseudocode

```c
void __fastcall Win32CommandChannelThread(void *p)
{
  unsigned int v2; // eax
  HANDLE v3; // rdi
  unsigned int v4; // ebx
  DWORD v5; // r8d
  char v6; // al
  int v7; // esi
  __int64 v8; // rcx
  HANDLE v9; // rcx
  HANDLE v10; // rcx
  __int128 v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+60h] [rbp-A0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+78h] [rbp-88h] BYREF
  char Buffer; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v16; // [rsp+A1h] [rbp-5Fh]
  char v17; // [rsp+A3h] [rbp-5Dh]
  unsigned int v18; // [rsp+A4h] [rbp-5Ch]
  unsigned int v19; // [rsp+A8h] [rbp-58h]
  _BYTE v20[2084]; // [rsp+ACh] [rbp-54h] BYREF
  DWORD NumberOfBytesRead; // [rsp+8E8h] [rbp+7E8h] BYREF

  v16 = 0;
  v17 = 0;
  memset_0(&Buffer, 0, 0x805u);
  NumberOfBytesRead = 0;
  v12 = 0;
  v11 = 0;
  v2 = PtrToUlong(p);
  v3 = G_DupIcaCommandChannel;
  v4 = v2;
  if ( v2 )
    v3 = G_DupConsoleShadowCommandChannel;
  while ( 1 )
  {
    do
    {
      memset(&Overlapped, 0, sizeof(Overlapped));
      if ( !ReadFile(v3, &Buffer, 0x808u, &NumberOfBytesRead, &Overlapped)
        && (GetLastError() != 997 || !GetOverlappedResult(v3, &Overlapped, &NumberOfBytesRead, 1)) )
      {
        if ( !v4 && WinStationIcaApiPort )
        {
          NtClose(WinStationIcaApiPort);
          WinStationIcaApiPort = 0;
        }
        if ( v3 )
        {
          NtClose(v3);
          if ( v4 )
          {
            G_DupConsoleShadowCommandChannel = 0;
            goto LABEL_44;
          }
          G_DupIcaCommandChannel = 0;
LABEL_39:
          v10 = G_DupIcaVideoChannel;
        }
        else
        {
          if ( !v4 )
            goto LABEL_39;
LABEL_44:
          v10 = G_DupConsoleShadowVideoChannel;
        }
        if ( v10 )
        {
          NtClose(v10);
          if ( v4 )
            G_DupConsoleShadowVideoChannel = 0;
          else
            G_DupIcaVideoChannel = 0;
        }
        RtlExitUserThread(0);
        __debugbreak();
        JUMPOUT(0x18001260FLL);
      }
      v5 = NumberOfBytesRead;
    }
    while ( !NumberOfBytesRead );
    v6 = Buffer;
    v7 = 0;
    if ( Buffer == 1 || Buffer == 6 )
      goto LABEL_13;
    if ( Buffer == 7 && (v8 = v18, (v18 & 1) == 0) )
    {
LABEL_14:
      switch ( v6 )
      {
        case 1:
          BrokenConnection(v8, v19);
          break;
        case 2:
          if ( v5 >= 9 )
            NtUserRemoteRedrawRectangle(
              (unsigned int)(__int16)v18,
              (unsigned int)SHIWORD(v18),
              (unsigned int)(__int16)v19,
              (unsigned int)SHIWORD(v19));
          break;
        case 3:
          NtUserRemoteRedrawScreen();
          break;
        case 4:
          if ( (int)NtUserRemoteStopScreenUpdates() >= 0 )
          {
            v9 = G_DupIcaVideoChannel;
            if ( v4 )
              v9 = G_DupConsoleShadowVideoChannel;
            IoStatusBlock = 0;
            NtDeviceIoControlFile(v9, 0, 0, 0, &IoStatusBlock, 0x381010u, 0, 0, 0, 0);
          }
          break;
        case 6:
          ShadowHotkey();
          break;
        case 7:
          NtUserCtxDisplayIOCtl(v8, v20, v19);
          break;
      }
      if ( v7 )
        NtUserSetInformationThread(-2, 9, &v11);
    }
    else
    {
      v7 = 1;
      if ( (int)NtUserSetInformationThread(-2, 7, &v11) >= 0 )
      {
        v6 = Buffer;
        v5 = NumberOfBytesRead;
LABEL_13:
        v8 = v18;
        goto LABEL_14;
      }
    }
  }
}

```

## disassembly

```asm
0x1800122f0  push    rbp
0x1800122f2  push    rbx
0x1800122f3  push    rsi
0x1800122f4  push    rdi
0x1800122f5  lea     rbp, [rsp-7B8h]
0x1800122fd  sub     rsp, 8B8h
0x180012304  xor     eax, eax
0x180012306  mov     rbx, rcx
0x180012309  lea     rcx, [rbp+7D0h+Buffer]; void *
0x18001230d  mov     [rbp+7D0h+var_82F], ax
0x180012311  xor     edx, edx; Val
0x180012313  mov     [rbp+7D0h+var_82D], al
0x180012316  mov     r8d, 805h; Size
0x18001231c  call    memset_0
0x180012321  xor     eax, eax
0x180012323  mov     [rbp+7D0h+NumberOfBytesRead], 0
0x18001232d  xorps   xmm0, xmm0
0x180012330  mov     [rsp+8D0h+var_870], rax
0x180012335  mov     rcx, rbx; p
0x180012338  movups  [rsp+8D0h+var_880], xmm0
0x18001233d  call    PtrToUlong
0x180012342  mov     rdi, cs:G_DupIcaCommandChannel
0x180012349  test    eax, eax
0x18001234b  mov     ebx, eax
0x18001234d  cmovnz  rdi, cs:G_DupConsoleShadowCommandChannel
0x180012355  xorps   xmm0, xmm0
0x180012358  lea     rax, [rsp+8D0h+Overlapped]
0x18001235d  lea     r9, [rbp+7D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180012364  mov     [rsp+8D0h+lpOverlapped], rax; lpOverlapped
0x180012369  mov     r8d, 808h; nNumberOfBytesToRead
0x18001236f  lea     rdx, [rbp+7D0h+Buffer]; lpBuffer
0x180012373  mov     rcx, rdi; hFile
0x180012376  movups  xmmword ptr [rsp+8D0h+Overlapped.Internal], xmm0
0x18001237b  movups  xmmword ptr [rbp+7D0h+Overlapped.10h], xmm0
0x18001237f  call    cs:__imp_ReadFile
0x180012386  nop     dword ptr [rax+rax+00h]
0x18001238b  test    eax, eax
0x18001238d  jnz     short loc_1800123CF
0x18001238f  call    cs:__imp_GetLastError
0x180012396  nop     dword ptr [rax+rax+00h]
0x18001239b  cmp     eax, 3E5h
0x1800123a0  jnz     loc_180012568
0x1800123a6  mov     r9d, 1; bWait
0x1800123ac  lea     r8, [rbp+7D0h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x1800123b3  lea     rdx, [rsp+8D0h+Overlapped]; lpOverlapped
0x1800123b8  mov     rcx, rdi; hFile
0x1800123bb  call    cs:__imp_GetOverlappedResult
0x1800123c2  nop     dword ptr [rax+rax+00h]
0x1800123c7  test    eax, eax
0x1800123c9  jz      loc_180012568
0x1800123cf  mov     r8d, [rbp+7D0h+NumberOfBytesRead]
0x1800123d6  cmp     r8d, 1
0x1800123da  jb      loc_180012355
0x1800123e0  mov     al, [rbp+7D0h+Buffer]
0x1800123e3  xor     esi, esi
0x1800123e5  cmp     al, 1
0x1800123e7  jz      short loc_18001242F
0x1800123e9  cmp     al, 6
0x1800123eb  jz      short loc_18001242F
0x1800123ed  cmp     al, 7
0x1800123ef  jnz     short loc_1800123F9
0x1800123f1  mov     ecx, [rbp+7D0h+var_82C]
0x1800123f4  test    cl, 1
0x1800123f7  jz      short loc_180012432
0x1800123f9  mov     esi, 1
0x1800123fe  lea     r8, [rsp+8D0h+var_880]
0x180012403  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18001240a  lea     r9d, [rsi+17h]
0x18001240e  lea     edx, [rsi+6]
0x180012411  call    cs:__imp_NtUserSetInformationThread
0x180012418  nop     dword ptr [rax+rax+00h]
0x18001241d  test    eax, eax
0x18001241f  js      loc_180012355
0x180012425  mov     al, [rbp+7D0h+Buffer]
0x180012428  mov     r8d, [rbp+7D0h+NumberOfBytesRead]
0x18001242f  mov     ecx, [rbp+7D0h+var_82C]
0x180012432  movzx   edx, al
0x180012435  sub     edx, 1
0x180012438  jz      loc_180012531
0x18001243e  sub     edx, 1
0x180012441  jz      loc_18001250B
0x180012447  sub     edx, 1
0x18001244a  jz      loc_1800124FD
0x180012450  sub     edx, 1
0x180012453  jz      short loc_180012486
0x180012455  sub     edx, 2
0x180012458  jz      short loc_18001247C
0x18001245a  cmp     edx, 1
0x18001245d  jnz     loc_180012539
0x180012463  mov     r8d, [rbp+7D0h+var_828]
0x180012467  lea     rdx, [rbp+7D0h+var_824]
0x18001246b  call    cs:__imp_NtUserCtxDisplayIOCtl
0x180012472  nop     dword ptr [rax+rax+00h]
0x180012477  jmp     loc_180012539
0x18001247c  call    ShadowHotkey
0x180012481  jmp     loc_180012539
0x180012486  call    cs:__imp_NtUserRemoteStopScreenUpdates
0x18001248d  nop     dword ptr [rax+rax+00h]
0x180012492  test    eax, eax
0x180012494  js      loc_180012539
0x18001249a  mov     rcx, cs:G_DupIcaVideoChannel
0x1800124a1  lea     rax, [rsp+8D0h+IoStatusBlock]
0x1800124a6  mov     [rsp+8D0h+OutputBufferLength], 0; OutputBufferLength
0x1800124ae  test    ebx, ebx
0x1800124b0  mov     [rsp+8D0h+OutputBuffer], 0; OutputBuffer
0x1800124b9  xorps   xmm0, xmm0
0x1800124bc  cmovnz  rcx, cs:G_DupConsoleShadowVideoChannel; FileHandle
0x1800124c4  xor     r9d, r9d; ApcContext
0x1800124c7  mov     [rsp+8D0h+InputBufferLength], 0; InputBufferLength
0x1800124cf  xor     r8d, r8d; ApcRoutine
0x1800124d2  mov     [rsp+8D0h+InputBuffer], 0; InputBuffer
0x1800124db  xor     edx, edx; Event
0x1800124dd  mov     [rsp+8D0h+IoControlCode], 381010h; IoControlCode
0x1800124e5  mov     [rsp+8D0h+lpOverlapped], rax; IoStatusBlock
0x1800124ea  movups  xmmword ptr [rsp+8D0h+IoStatusBlock], xmm0
0x1800124ef  call    cs:__imp_NtDeviceIoControlFile
0x1800124f6  nop     dword ptr [rax+rax+00h]
0x1800124fb  jmp     short loc_180012539
0x1800124fd  call    cs:__imp_NtUserRemoteRedrawScreen
0x180012504  nop     dword ptr [rax+rax+00h]
0x180012509  jmp     short loc_180012539
0x18001250b  cmp     r8d, 9
0x18001250f  jb      short loc_180012539
0x180012511  movsx   r9d, word ptr [rbp+7D0h+var_828+2]
0x180012516  movsx   r8d, word ptr [rbp+7D0h+var_828]
0x18001251b  movsx   edx, word ptr [rbp+7D0h+var_82C+2]
0x18001251f  movsx   ecx, word ptr [rbp+7D0h+var_82C]
0x180012523  call    cs:__imp_NtUserRemoteRedrawRectangle
0x18001252a  nop     dword ptr [rax+rax+00h]
0x18001252f  jmp     short loc_180012539
0x180012531  mov     edx, [rbp+7D0h+var_828]
0x180012534  call    BrokenConnection
0x180012539  test    esi, esi
0x18001253b  jz      loc_180012355
0x180012541  mov     r9d, 18h
0x180012547  lea     r8, [rsp+8D0h+var_880]
0x18001254c  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180012553  lea     edx, [r9-0Fh]
0x180012557  call    cs:__imp_NtUserSetInformationThread
0x18001255e  nop     dword ptr [rax+rax+00h]
0x180012563  jmp     loc_180012355
0x180012568  test    ebx, ebx
0x18001256a  jnz     short loc_18001258F
0x18001256c  mov     rcx, cs:WinStationIcaApiPort; Handle
0x180012573  test    rcx, rcx
0x180012576  jz      short loc_18001258F
0x180012578  call    cs:__imp_NtClose
0x18001257f  nop     dword ptr [rax+rax+00h]
0x180012584  mov     cs:WinStationIcaApiPort, 0
0x18001258f  test    rdi, rdi
0x180012592  jz      short loc_1800125E8
0x180012594  mov     rcx, rdi; Handle
0x180012597  call    cs:__imp_NtClose
0x18001259e  nop     dword ptr [rax+rax+00h]
0x1800125a3  test    ebx, ebx
0x1800125a5  jz      short loc_1800125B4
0x1800125a7  mov     cs:G_DupConsoleShadowCommandChannel, 0
0x1800125b2  jmp     short loc_1800125EC
0x1800125b4  mov     cs:G_DupIcaCommandChannel, 0
0x1800125bf  mov     rcx, cs:G_DupIcaVideoChannel; Handle
0x1800125c6  test    rcx, rcx
0x1800125c9  jz      short loc_180012600
0x1800125cb  call    cs:__imp_NtClose
0x1800125d2  nop     dword ptr [rax+rax+00h]
0x1800125d7  test    ebx, ebx
0x1800125d9  jz      short loc_1800125F5
0x1800125db  mov     cs:G_DupConsoleShadowVideoChannel, 0
0x1800125e6  jmp     short loc_180012600
0x1800125e8  test    ebx, ebx
0x1800125ea  jz      short loc_1800125BF
0x1800125ec  mov     rcx, cs:G_DupConsoleShadowVideoChannel
0x1800125f3  jmp     short loc_1800125C6
0x1800125f5  mov     cs:G_DupIcaVideoChannel, 0
0x180012600  xor     ecx, ecx; Status
0x180012602  call    cs:__imp_RtlExitUserThread
0x180012609  nop     dword ptr [rax+rax+00h]
0x18001260e  int     3; Trap to Debugger
```

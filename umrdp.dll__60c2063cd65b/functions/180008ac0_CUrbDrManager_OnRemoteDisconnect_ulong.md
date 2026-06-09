# CUrbDrManager::OnRemoteDisconnect(ulong)

- ea: `0x180008ac0`
- end: `0x180008f18`
- name: `?OnRemoteDisconnect@CUrbDrManager@@AEAAJK@Z`
- size: `1112`
- prototype: `__int64 __fastcall(CUrbDrManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180002170`

## callees

- `0x180008ac0`
- `0x18000b8f8`
- `0x18000bd04`
- `0x18000bd44`
- `0x18000f75c`
- `0x18000f79c`
- `0x180017cbc`
- `0x180019d90`
- `0x18002ed04`
- `0x18002f954`
- `0x180033640`
- `0x18003368c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ef0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ef0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008d25`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008d25`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008b85`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008b85`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008e90`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008e90`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180008be9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180008be9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008bc1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008bc1`
- `WTSAPI32!WTSVirtualChannelClose` at `0x180008c79`
- `WTSAPI32!WTSVirtualChannelClose` at `0x180008c79`

## pseudocode

```c
__int64 __fastcall CUrbDrManager::OnRemoteDisconnect(CUrbDrManager *this, unsigned int a2)
{
  char *v3; // rdi
  unsigned int v5; // esi
  __int64 v6; // rax
  void **v7; // r15
  unsigned __int64 v8; // xmm1_8
  unsigned int v9; // r12d
  void *v10; // rcx
  HANDLE v11; // r13
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v13; // r12d
  unsigned int NumItems; // r13d
  HANDLE v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // r15d
  unsigned int *v23; // rax
  unsigned int *v24; // rdi
  HANDLE v25; // rax
  DWORD LastError; // ebx
  unsigned int v27; // eax
  HANDLE hDevice[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h]
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-11h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+D0h] [rbp+67h] BYREF
  DWORD ThreadId; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int64 v34; // [rsp+E0h] [rbp+77h]
  unsigned __int64 InBuffer; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = (char *)this + 80;
  *(_OWORD *)hDevice = 0;
  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  InBuffer = 0;
  if ( a2 >= *((_DWORD *)this + 21) )
    return (unsigned int)-2147418113;
  v6 = *((_QWORD *)this + 11);
  v5 = 0;
  v7 = *(void ***)(v6 + 24LL * a2 + 16);
  if ( !v7 )
    return v5;
  v8 = _mm_srli_si128(*(__m128i *)(v6 + 24LL * a2), 8).m128i_u64[0];
  v9 = 0;
  v34 = HIDWORD(v8);
  InBuffer = __PAIR64__(HIDWORD(v8), a2);
  if ( *((_DWORD *)this + 13) )
  {
    do
    {
      DynArray<_USBHUB_DEVICE_DATA,unsigned long>::GetAt((char *)this + 48, v9, hDevice);
      v10 = (void *)*((_QWORD *)this + 14);
      memset(&Overlapped, 0, sizeof(Overlapped));
      ResetEvent(v10);
      Overlapped.hEvent = (HANDLE)*((_QWORD *)this + 14);
      v11 = hDevice[0];
      if ( DeviceIoControl(hDevice[0], 0x86000404, &InBuffer, 8u, 0, 0, 0, &Overlapped) )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            47,
            WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
      }
      else if ( GetLastError() == 997 )
      {
        GetOverlappedResult(v11, &Overlapped, &NumberOfBytesTransferred, 1);
      }
      ++v9;
    }
    while ( v9 < *((_DWORD *)this + 13) );
    v3 = (char *)this + 80;
    v5 = 0;
  }
  ThreadId = 0;
  v13 = 0;
  NumItems = CSimpleHash::GetNumItems((CSimpleHash *)v7);
  if ( NumItems )
  {
    do
    {
      hDevice[0] = 0;
      CSimpleHash::FindNextItem((CSimpleHash *)v7, &ThreadId, hDevice);
      WTSVirtualChannelClose(hDevice[0]);
      ++ThreadId;
      ++v13;
    }
    while ( v13 < NumItems );
  }
  operator delete(v7[1]);
  operator delete(v7);
  v30 = 0;
  *(_OWORD *)hDevice = 0;
  DynArray<_SESSION_DATA,unsigned long>::AddAt(v3, a2, hDevice);
  if ( !*((_DWORD *)this + 41) )
    return v5;
  v15 = g_hServiceStartupTSUSBDevnodesCleanupThread;
  if ( !g_hServiceStartupTSUSBDevnodesCleanupThread )
    goto LABEL_31;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      48,
      WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v16);
    v15 = g_hServiceStartupTSUSBDevnodesCleanupThread;
  }
  if ( WaitForSingleObject(v15, 0) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 49;
LABEL_42:
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v18,
        WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
        v17);
      return v5;
    }
    return v5;
  }
  v19 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_36;
  if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      50,
      WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v20);
LABEL_31:
    v19 = *(_QWORD *)&WPP_GLOBAL_Control;
  }
  if ( (unsigned int *)v19 != &WPP_GLOBAL_Control && (*(_BYTE *)(v19 + 28) & 1) != 0 && *(_BYTE *)(v19 + 25) >= 4u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    v22 = v34;
    WPP_SF_DDd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      51,
      WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v21,
      a2,
      v34);
    goto LABEL_37;
  }
LABEL_36:
  v22 = v34;
LABEL_37:
  ThreadId = 0;
  v23 = (unsigned int *)operator new(0x10u);
  v24 = v23;
  if ( v23 )
  {
    *v23 = a2;
    v23[1] = v22;
    *((_QWORD *)v23 + 1) = *((_QWORD *)this + 21);
    v25 = CreateThread(0, 0, CUrbDrManager::staticSessionDisconnectTSUSBDevnodesCleanupThreadProc, v23, 0, &ThreadId);
    if ( v25 )
    {
      CloseHandle(v25);
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        LastError = GetLastError();
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          53,
          WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          v27,
          LastError);
      }
      operator delete(v24);
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 52;
    goto LABEL_42;
  }
  return v5;
}

```

## disassembly

```asm
0x180008ac0  push    rbp
0x180008ac2  push    rbx
0x180008ac3  push    rsi
0x180008ac4  push    rdi
0x180008ac5  push    r13
0x180008ac7  push    r14
0x180008ac9  lea     rbp, [rsp-2Fh]
0x180008ace  sub     rsp, 98h
0x180008ad5  xor     r13d, r13d
0x180008ad8  mov     ebx, edx
0x180008ada  lea     rdi, [rcx+50h]
0x180008ade  xorps   xmm1, xmm1
0x180008ae1  xorps   xmm0, xmm0
0x180008ae4  mov     r14, rcx
0x180008ae7  movups  xmmword ptr [rbp+57h+hDevice], xmm0
0x180008aeb  mov     [rbp+57h+NumberOfBytesTransferred], r13d
0x180008aef  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm1
0x180008af3  mov     [rbp+57h+InBuffer], r13
0x180008af7  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm1
0x180008afb  cmp     edx, [rdi+4]
0x180008afe  jb      short loc_180008B0A
0x180008b00  mov     esi, 8000FFFFh
0x180008b05  jmp     loc_180008F06
0x180008b0a  mov     rax, [rdi+8]
0x180008b0e  lea     rcx, [rbx+rbx*2]
0x180008b12  mov     [rsp+0C0h+var_38], r15
0x180008b1a  mov     esi, r13d
0x180008b1d  mov     r15, [rax+rcx*8+10h]
0x180008b22  movups  xmm1, xmmword ptr [rax+rcx*8]
0x180008b26  test    r15, r15
0x180008b29  jz      loc_180008EFE
0x180008b2f  psrldq  xmm1, 8
0x180008b34  movq    rax, xmm1
0x180008b39  mov     [rsp+0C0h+var_30], r12
0x180008b41  shr     rax, 20h
0x180008b45  mov     r12d, r13d
0x180008b48  mov     [rbp+57h+arg_10], rax
0x180008b4c  mov     dword ptr [rbp+57h+InBuffer+4], eax
0x180008b52  mov     dword ptr [rbp+57h+InBuffer], ebx
0x180008b55  cmp     [r14+34h], r13d
0x180008b59  jbe     loc_180008C47
0x180008b5f  lea     rsi, WPP_GLOBAL_Control
0x180008b66  lea     r8, [rbp+57h+hDevice]
0x180008b6a  mov     edx, r12d
0x180008b6d  lea     rcx, [r14+30h]
0x180008b71  call    ?GetAt@?$DynArray@U_USBHUB_DEVICE_DATA@@K@@QEAAHKPEAU_USBHUB_DEVICE_DATA@@@Z; DynArray<_USBHUB_DEVICE_DATA,ulong>::GetAt(ulong,_USBHUB_DEVICE_DATA *)
0x180008b76  mov     rcx, [r14+70h]; hEvent
0x180008b7a  xorps   xmm1, xmm1
0x180008b7d  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm1
0x180008b81  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm1
0x180008b85  call    cs:__imp_ResetEvent
0x180008b8b  mov     rax, [r14+70h]
0x180008b8f  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180008b93  mov     [rbp+57h+Overlapped.hEvent], rax
0x180008b97  mov     r9d, 8; nInBufferSize
0x180008b9d  lea     rax, [rbp+57h+Overlapped]
0x180008ba1  mov     edx, 86000404h; dwIoControlCode
0x180008ba6  mov     [rsp+0C0h+lpOverlapped], rax; lpOverlapped
0x180008bab  mov     [rsp+0C0h+lpBytesReturned], r13; lpBytesReturned
0x180008bb0  mov     [rsp+0C0h+nOutBufferSize], r13d; nOutBufferSize
0x180008bb5  mov     [rsp+0C0h+lpOutBuffer], r13; lpOutBuffer
0x180008bba  mov     r13, [rbp+57h+hDevice]
0x180008bbe  mov     rcx, r13; hDevice
0x180008bc1  call    cs:__imp_DeviceIoControl
0x180008bc7  test    eax, eax
0x180008bc9  jnz     short loc_180008BF1
0x180008bcb  call    cs:__imp_GetLastError
0x180008bd1  cmp     eax, 3E5h
0x180008bd6  jnz     short loc_180008C2D
0x180008bd8  mov     r9d, 1; bWait
0x180008bde  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180008be2  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180008be6  mov     rcx, r13; hFile
0x180008be9  call    cs:__imp_GetOverlappedResult
0x180008bef  jmp     short loc_180008C2D
0x180008bf1  mov     rax, cs:WPP_GLOBAL_Control
0x180008bf8  cmp     rax, rsi
0x180008bfb  jz      short loc_180008C2D
0x180008bfd  test    byte ptr [rax+1Ch], 1
0x180008c01  jz      short loc_180008C2D
0x180008c03  cmp     byte ptr [rax+19h], 2
0x180008c07  jb      short loc_180008C2D
0x180008c09  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c15  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180008c1c  mov     edx, 2Fh ; '/'
0x180008c21  mov     r9d, eax
0x180008c24  mov     rcx, [rcx+10h]
0x180008c28  call    WPP_SF_D
0x180008c2d  inc     r12d
0x180008c30  mov     r13d, 0
0x180008c36  cmp     r12d, [r14+34h]
0x180008c3a  jb      loc_180008B66
0x180008c40  lea     rdi, [r14+50h]
0x180008c44  mov     esi, r13d
0x180008c47  mov     rcx, r15; this
0x180008c4a  mov     [rbp+57h+ThreadId], r13d
0x180008c4e  call    ?GetNumItems@CSimpleHash@@QEAAKXZ; CSimpleHash::GetNumItems(void)
0x180008c53  xor     r12d, r12d
0x180008c56  mov     r13d, eax
0x180008c59  test    eax, eax
0x180008c5b  jz      short loc_180008C8A
0x180008c5d  lea     r8, [rbp+57h+hDevice]; void **
0x180008c61  mov     [rbp+57h+hDevice], 0
0x180008c69  lea     rdx, [rbp+57h+ThreadId]; unsigned int *
0x180008c6d  mov     rcx, r15; this
0x180008c70  call    ?FindNextItem@CSimpleHash@@QEAAJPEAKPEAPEAX@Z; CSimpleHash::FindNextItem(ulong *,void * *)
0x180008c75  mov     rcx, [rbp+57h+hDevice]; hChannelHandle
0x180008c79  call    cs:__imp_WTSVirtualChannelClose
0x180008c7f  inc     [rbp+57h+ThreadId]
0x180008c82  inc     r12d
0x180008c85  cmp     r12d, r13d
0x180008c88  jb      short loc_180008C5D
0x180008c8a  test    r15, r15
0x180008c8d  jz      short loc_180008CA0
0x180008c8f  mov     rcx, [r15+8]; Block
0x180008c93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008c98  mov     rcx, r15; Block
0x180008c9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ca0  xorps   xmm0, xmm0
0x180008ca3  lea     r8, [rbp+57h+hDevice]
0x180008ca7  xor     eax, eax
0x180008ca9  mov     edx, ebx
0x180008cab  mov     rcx, rdi
0x180008cae  mov     [rbp+57h+var_70], rax
0x180008cb2  movups  xmmword ptr [rbp+57h+hDevice], xmm0
0x180008cb6  call    ?AddAt@?$DynArray@U_SESSION_DATA@@K@@QEAAHKAEAU_SESSION_DATA@@@Z; DynArray<_SESSION_DATA,ulong>::AddAt(ulong,_SESSION_DATA &)
0x180008cbb  cmp     dword ptr [r14+0A4h], 0
0x180008cc3  jz      loc_180008EF6
0x180008cc9  mov     rcx, cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA; void * g_hServiceStartupTSUSBDevnodesCleanupThread
0x180008cd0  test    rcx, rcx
0x180008cd3  jz      loc_180008DA4
0x180008cd9  mov     rax, cs:WPP_GLOBAL_Control
0x180008ce0  lea     r12, WPP_GLOBAL_Control
0x180008ce7  cmp     rax, r12
0x180008cea  jz      short loc_180008D23
0x180008cec  test    byte ptr [rax+1Ch], 1
0x180008cf0  jz      short loc_180008D23
0x180008cf2  cmp     byte ptr [rax+19h], 4
0x180008cf6  jb      short loc_180008D23
0x180008cf8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d04  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180008d0b  mov     edx, 30h ; '0'
0x180008d10  mov     r9d, eax
0x180008d13  mov     rcx, [rcx+10h]
0x180008d17  call    WPP_SF_D
0x180008d1c  mov     rcx, cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA; hHandle
0x180008d23  xor     edx, edx; dwMilliseconds
0x180008d25  call    cs:__imp_WaitForSingleObject
0x180008d2b  test    eax, eax
0x180008d2d  jz      short loc_180008D62
0x180008d2f  mov     rax, cs:WPP_GLOBAL_Control
0x180008d36  cmp     rax, r12
0x180008d39  jz      loc_180008EF6
0x180008d3f  test    byte ptr [rax+1Ch], 1
0x180008d43  jz      loc_180008EF6
0x180008d49  cmp     byte ptr [rax+19h], 2
0x180008d4d  jb      loc_180008EF6
0x180008d53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008d58  mov     edx, 31h ; '1'
0x180008d5d  jmp     loc_180008E41
0x180008d62  mov     rax, cs:WPP_GLOBAL_Control
0x180008d69  cmp     rax, r12
0x180008d6c  jz      loc_180008DF6
0x180008d72  test    byte ptr [rax+1Ch], 1
0x180008d76  jz      short loc_180008DB2
0x180008d78  cmp     byte ptr [rax+19h], 4
0x180008d7c  jb      short loc_180008DB2
0x180008d7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d8a  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180008d91  mov     edx, 32h ; '2'
0x180008d96  mov     r9d, eax
0x180008d99  mov     rcx, [rcx+10h]
0x180008d9d  call    WPP_SF_D
0x180008da2  jmp     short loc_180008DAB
0x180008da4  lea     r12, WPP_GLOBAL_Control
0x180008dab  mov     rax, cs:WPP_GLOBAL_Control
0x180008db2  cmp     rax, r12
0x180008db5  jz      short loc_180008DF6
0x180008db7  test    byte ptr [rax+1Ch], 1
0x180008dbb  jz      short loc_180008DF6
0x180008dbd  cmp     byte ptr [rax+19h], 4
0x180008dc1  jb      short loc_180008DF6
0x180008dc3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dcf  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180008dd6  mov     r15, [rbp+57h+arg_10]
0x180008dda  mov     edx, 33h ; '3'
0x180008ddf  mov     [rsp+0C0h+nOutBufferSize], r15d
0x180008de4  mov     r9d, eax
0x180008de7  mov     dword ptr [rsp+0C0h+lpOutBuffer], ebx
0x180008deb  mov     rcx, [rcx+10h]
0x180008def  call    WPP_SF_DDd
0x180008df4  jmp     short loc_180008DFA
0x180008df6  mov     r15, [rbp+57h+arg_10]
0x180008dfa  mov     ecx, 10h; Size
0x180008dff  mov     [rbp+57h+ThreadId], 0
0x180008e06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008e0b  mov     rdi, rax
0x180008e0e  test    rax, rax
0x180008e11  jnz     short loc_180008E60
0x180008e13  mov     rax, cs:WPP_GLOBAL_Control
0x180008e1a  cmp     rax, r12
0x180008e1d  jz      loc_180008EF6
0x180008e23  test    byte ptr [rax+1Ch], 1
0x180008e27  jz      loc_180008EF6
0x180008e2d  cmp     byte ptr [rax+19h], 2
0x180008e31  jb      loc_180008EF6
0x180008e37  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008e3c  mov     edx, 34h ; '4'
0x180008e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e48  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180008e4f  mov     r9d, eax
0x180008e52  mov     rcx, [rcx+10h]
0x180008e56  call    WPP_SF_D
0x180008e5b  jmp     loc_180008EF6
0x180008e60  mov     [rax], ebx
0x180008e62  lea     r8, ?staticSessionDisconnectTSUSBDevnodesCleanupThreadProc@CUrbDrManager@@SAKPEAX@Z; lpStartAddress
0x180008e69  mov     [rax+4], r15d
0x180008e6d  mov     r9, rdi; lpParameter
0x180008e70  mov     rax, [r14+0A8h]
0x180008e77  xor     edx, edx; dwStackSize
0x180008e79  mov     [rdi+8], rax
0x180008e7d  xor     ecx, ecx; lpThreadAttributes
0x180008e7f  lea     rax, [rbp+57h+ThreadId]
0x180008e83  mov     qword ptr [rsp+0C0h+nOutBufferSize], rax; lpThreadId
0x180008e88  mov     dword ptr [rsp+0C0h+lpOutBuffer], 0; dwCreationFlags
0x180008e90  call    cs:__imp_CreateThread
0x180008e96  test    rax, rax
0x180008e99  jnz     short loc_180008EED
0x180008e9b  mov     rax, cs:WPP_GLOBAL_Control
0x180008ea2  cmp     rax, r12
0x180008ea5  jz      short loc_180008EE3
0x180008ea7  test    byte ptr [rax+1Ch], 1
0x180008eab  jz      short loc_180008EE3
0x180008ead  cmp     byte ptr [rax+19h], 2
0x180008eb1  jb      short loc_180008EE3
0x180008eb3  call    cs:__imp_GetLastError
0x180008eb9  mov     ebx, eax
0x180008ebb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ec7  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180008ece  mov     edx, 35h ; '5'
0x180008ed3  mov     dword ptr [rsp+0C0h+lpOutBuffer], ebx
0x180008ed7  mov     r9d, eax
0x180008eda  mov     rcx, [rcx+10h]
0x180008ede  call    WPP_SF_Dd
0x180008ee3  mov     rcx, rdi; Block
0x180008ee6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008eeb  jmp     short loc_180008EF6
0x180008eed  mov     rcx, rax; hObject
0x180008ef0  call    cs:__imp_CloseHandle
0x180008ef6  mov     r12, [rsp+0C0h+var_30]
0x180008efe  mov     r15, [rsp+0C0h+var_38]
0x180008f06  mov     eax, esi
0x180008f08  add     rsp, 98h
0x180008f0f  pop     r14
0x180008f11  pop     r13
0x180008f13  pop     rdi
0x180008f14  pop     rsi
0x180008f15  pop     rbx
0x180008f16  pop     rbp
0x180008f17  retn
```

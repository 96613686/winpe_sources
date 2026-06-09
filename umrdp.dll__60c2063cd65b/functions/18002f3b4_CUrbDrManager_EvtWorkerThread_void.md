# CUrbDrManager::EvtWorkerThread(void)

- ea: `0x18002f3b4`
- end: `0x18002f94b`
- name: `?EvtWorkerThread@CUrbDrManager@@QEAAXXZ`
- size: `1431`
- prototype: `void __fastcall(CUrbDrManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180031070`

## callees

- `0x180007da0`
- `0x180008340`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000f75c`
- `0x18000f79c`
- `0x180017cbc`
- `0x18002f3b4`
- `0x18002f954`
- `0x180033474`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f8e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f45f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f45f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f4d4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f7b7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f4d4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f7b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f40e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f40e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002f567`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002f81a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002f567`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002f81a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002f50c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002f7ec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002f50c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002f7ec`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002f53c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002f53c`
- `KERNEL32!CancelIoEx` at `0x18002f54e`
- `KERNEL32!CancelIoEx` at `0x18002f54e`
- `KERNEL32!GetThreadId` at `0x18002f436`
- `KERNEL32!GetThreadId` at `0x18002f436`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x18002f619`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x18002f619`
- `WTSAPI32!WTSVirtualChannelOpenEx` at `0x18002f5f0`
- `WTSAPI32!WTSVirtualChannelOpenEx` at `0x18002f5f0`
- `WTSAPI32!WTSVirtualChannelClose` at `0x18002f741`
- `WTSAPI32!WTSVirtualChannelClose` at `0x18002f741`
- `WTSAPI32!WTSFreeMemory` at `0x18002f6e5`
- `WTSAPI32!WTSFreeMemory` at `0x18002f6e5`

## pseudocode

```c
void __fastcall CUrbDrManager::EvtWorkerThread(CUrbDrManager *this)
{
  CUrbDrManager *v1; // r15
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // esi
  DWORD ThreadId; // eax
  HANDLE EventW; // r14
  unsigned int v6; // eax
  __int64 v7; // rdx
  DWORD LastError; // esi
  BOOL OverlappedResult; // eax
  unsigned int v10; // eax
  __int64 v11; // r13
  HANDLE v12; // rax
  void *v13; // rsi
  int v14; // r12d
  unsigned int *v15; // r8
  __int64 v16; // rcx
  DWORD v17; // r15d
  unsigned int v18; // eax
  unsigned int v19; // eax
  DWORD v20; // esi
  unsigned int v21; // eax
  BOOL v22; // eax
  unsigned int v23; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v25; // eax
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp-89h] BYREF
  DWORD pBytesReturned; // [rsp+44h] [rbp-85h] BYREF
  CUrbDrManager *v28; // [rsp+48h] [rbp-81h]
  PVOID ppBuffer; // [rsp+50h] [rbp-79h] BYREF
  HANDLE Thread[2]; // [rsp+58h] [rbp-71h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-61h] BYREF
  __int128 InBuffer; // [rsp+88h] [rbp-41h] BYREF
  char *v33; // [rsp+98h] [rbp-31h] BYREF
  HANDLE Handles[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-19h] BYREF
  CSimpleHash *v36; // [rsp+C0h] [rbp-9h]
  __int64 OutBuffer; // [rsp+C8h] [rbp-1h] BYREF
  DWORD SessionId; // [rsp+D0h] [rbp+7h]

  v28 = this;
  OutBuffer = 0;
  SessionId = 0;
  v1 = this;
  *(_OWORD *)Handles = 0;
  NumberOfBytesTransferred = 0;
  InBuffer = 0;
  *(_OWORD *)Thread = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( !*((_DWORD *)v1 + 13) )
    goto LABEL_71;
  do
  {
    DynArray<_USBHUB_DEVICE_DATA,unsigned long>::GetAt((char *)v1 + 48, v2, Thread);
    ThreadId = GetThreadId(Thread[1]);
    if ( ThreadId == CurrentThreadId )
      break;
    ++v2;
    ThreadId = 0;
  }
  while ( v2 < *((_DWORD *)v1 + 13) );
  if ( ThreadId )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW )
    {
      Handles[0] = *((HANDLE *)v1 + 13);
      Handles[1] = EventW;
      while ( 1 )
      {
        memset(&Overlapped, 0, sizeof(Overlapped));
        ResetEvent(EventW);
        Overlapped.hEvent = EventW;
        if ( DeviceIoControl(Thread[0], 0x8600040C, 0, 0, &OutBuffer, 0xCu, 0, &Overlapped) )
          break;
        LastError = GetLastError();
        if ( LastError != 997 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              65,
              WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
              CurrentThreadActivityIdPrefix,
              LastError);
          }
          goto LABEL_68;
        }
        if ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
          CancelIoEx(Thread[0], &Overlapped);
        OverlappedResult = GetOverlappedResult(Thread[0], &Overlapped, &NumberOfBytesTransferred, 1);
        if ( OverlappedResult )
        {
          if ( NumberOfBytesTransferred != 12 )
          {
            if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
              && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              v10 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_D(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                64,
                WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
                v10);
            }
            OverlappedResult = 0;
          }
          if ( OverlappedResult && !(_DWORD)OutBuffer )
          {
            ppBuffer = 0;
            v36 = 0;
            v35 = 0;
            v11 = 0;
            pBytesReturned = 0;
            v12 = WTSVirtualChannelOpenEx(SessionId, (LPSTR)"URBDRC", 1u);
            v13 = v12;
            if ( v12 )
            {
              v14 = -1073741823;
              if ( WTSVirtualChannelQuery(v12, WTSVirtualFileHandle, &ppBuffer, &pBytesReturned) )
              {
                if ( pBytesReturned == 8 )
                {
                  v33 = (char *)v1 + 64;
                  v11 = *(_QWORD *)ppBuffer;
                  CTSCriticalSection::Lock((CUrbDrManager *)((char *)v1 + 64));
                  if ( (unsigned int)DynArray<_SESSION_DATA,unsigned long>::GetAt((char *)v1 + 80, SessionId, &v35)
                    && v36
                    && HIDWORD(v35) == HIDWORD(OutBuffer) )
                  {
                    v14 = CSimpleHash::AddItemNoDuplicate(v36, v13, v15);
                  }
                  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v33);
                }
                v16 = *(_QWORD *)&WPP_GLOBAL_Control;
              }
              else
              {
                v17 = GetLastError();
                v16 = *(_QWORD *)&WPP_GLOBAL_Control;
                if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                  && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
                {
                  v18 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DDd(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                    67,
                    WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
                    v18,
                    v17,
                    SessionId);
                  v16 = *(_QWORD *)&WPP_GLOBAL_Control;
                }
                v1 = v28;
              }
              if ( ppBuffer )
              {
                WTSFreeMemory(ppBuffer);
                v16 = *(_QWORD *)&WPP_GLOBAL_Control;
              }
              if ( v14 < 0 )
              {
                if ( (unsigned int *)v16 != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(v16 + 28) & 1) != 0
                  && *(_BYTE *)(v16 + 25) >= 2u )
                {
                  v19 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DDd(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                    68,
                    WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
                    v19,
                    v14,
                    SessionId);
                }
                v11 = 0;
                WTSVirtualChannelClose(v13);
              }
            }
            else
            {
              v20 = GetLastError();
              if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                v21 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DDd(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                  69,
                  WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
                  v21,
                  v20,
                  SessionId);
              }
            }
            *(_QWORD *)&InBuffer = __PAIR64__(HIDWORD(OutBuffer), SessionId);
            *((_QWORD *)&InBuffer + 1) = v11;
            memset(&Overlapped, 0, sizeof(Overlapped));
            ResetEvent(EventW);
            Overlapped.hEvent = EventW;
            if ( DeviceIoControl(Thread[0], 0x86000408, &InBuffer, 0x10u, 0, 0, 0, &Overlapped) )
            {
              if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                v23 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_D(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                  70,
                  WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
                  v23);
              }
              v22 = 0;
            }
            else
            {
              if ( GetLastError() != 997 )
                goto LABEL_68;
              v22 = GetOverlappedResult(Thread[0], &Overlapped, &NumberOfBytesTransferred, 1);
            }
            if ( v22 )
              continue;
          }
        }
        goto LABEL_68;
      }
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          66,
          WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          v25);
      }
LABEL_68:
      CloseHandle(EventW);
    }
    else
    {
      GetLastError();
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 63;
LABEL_73:
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v7,
          WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          v6);
      }
    }
  }
  else
  {
LABEL_71:
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 62;
      goto LABEL_73;
    }
  }
}

```

## disassembly

```asm
0x18002f3b4  push    rbp
0x18002f3b6  push    rbx
0x18002f3b7  push    rsi
0x18002f3b8  push    rdi
0x18002f3b9  push    r12
0x18002f3bb  push    r13
0x18002f3bd  push    r14
0x18002f3bf  push    r15
0x18002f3c1  lea     rbp, [rsp-1Fh]
0x18002f3c6  sub     rsp, 0E8h
0x18002f3cd  mov     rax, cs:__security_cookie
0x18002f3d4  xor     rax, rsp
0x18002f3d7  mov     [rbp+57h+var_48], rax
0x18002f3db  xorps   xmm0, xmm0
0x18002f3de  mov     [rsp+120h+var_D8], rcx
0x18002f3e3  xor     eax, eax
0x18002f3e5  xorps   xmm1, xmm1
0x18002f3e8  xor     r12d, r12d
0x18002f3eb  mov     [rbp+57h+OutBuffer], rax
0x18002f3ef  mov     [rbp+57h+SessionId], eax
0x18002f3f2  mov     r15, rcx
0x18002f3f5  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x18002f3f9  mov     [rsp+120h+NumberOfBytesTransferred], r12d
0x18002f3fe  movups  [rbp+57h+InBuffer], xmm0
0x18002f402  movups  xmmword ptr [rbp+57h+Thread], xmm1
0x18002f406  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002f40a  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002f40e  call    cs:__imp_GetCurrentThreadId
0x18002f414  mov     ebx, r12d
0x18002f417  mov     esi, eax
0x18002f419  cmp     [r15+34h], r12d
0x18002f41d  jbe     loc_18002F8E8
0x18002f423  lea     r8, [rbp+57h+Thread]
0x18002f427  mov     edx, ebx
0x18002f429  lea     rcx, [r15+30h]
0x18002f42d  call    ?GetAt@?$DynArray@U_USBHUB_DEVICE_DATA@@K@@QEAAHKPEAU_USBHUB_DEVICE_DATA@@@Z; DynArray<_USBHUB_DEVICE_DATA,ulong>::GetAt(ulong,_USBHUB_DEVICE_DATA *)
0x18002f432  mov     rcx, [rbp+57h+Thread+8]; Thread
0x18002f436  call    cs:__imp_GetThreadId
0x18002f43c  cmp     eax, esi
0x18002f43e  jz      short loc_18002F44B
0x18002f440  inc     ebx
0x18002f442  mov     eax, r12d
0x18002f445  cmp     ebx, [r15+34h]
0x18002f449  jb      short loc_18002F423
0x18002f44b  test    eax, eax
0x18002f44d  jz      loc_18002F8E8
0x18002f453  xor     r9d, r9d; lpName
0x18002f456  xor     r8d, r8d; bInitialState
0x18002f459  xor     ecx, ecx; lpEventAttributes
0x18002f45b  lea     edx, [r9+1]; bManualReset
0x18002f45f  call    cs:__imp_CreateEventW
0x18002f465  mov     r14, rax
0x18002f468  test    rax, rax
0x18002f46b  jnz     short loc_18002F4AC
0x18002f46d  call    cs:__imp_GetLastError
0x18002f473  mov     rax, cs:WPP_GLOBAL_Control
0x18002f47a  lea     rbx, WPP_GLOBAL_Control
0x18002f481  cmp     rax, rbx
0x18002f484  jz      loc_18002F92B
0x18002f48a  test    byte ptr [rax+1Ch], 1
0x18002f48e  jz      loc_18002F92B
0x18002f494  cmp     byte ptr [rax+19h], 2
0x18002f498  jb      loc_18002F92B
0x18002f49e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f4a3  lea     edx, [r14+3Fh]
0x18002f4a7  jmp     loc_18002F911
0x18002f4ac  mov     rax, [r15+68h]
0x18002f4b0  lea     rbx, WPP_GLOBAL_Control
0x18002f4b7  mov     [rbp+57h+Handles], rax
0x18002f4bb  lea     rdi, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002f4c2  mov     [rbp+57h+Handles+8], r14
0x18002f4c6  xorps   xmm0, xmm0
0x18002f4c9  mov     rcx, r14; hEvent
0x18002f4cc  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002f4d0  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002f4d4  call    cs:__imp_ResetEvent
0x18002f4da  mov     rcx, [rbp+57h+Thread]; hDevice
0x18002f4de  lea     rax, [rbp+57h+Overlapped]
0x18002f4e2  mov     [rsp+120h+lpOverlapped], rax; lpOverlapped
0x18002f4e7  xor     r9d, r9d; nInBufferSize
0x18002f4ea  mov     [rsp+120h+lpBytesReturned], r12; lpBytesReturned
0x18002f4ef  lea     rax, [rbp+57h+OutBuffer]
0x18002f4f3  mov     [rsp+120h+nOutBufferSize], 0Ch; nOutBufferSize
0x18002f4fb  xor     r8d, r8d; lpInBuffer
0x18002f4fe  mov     edx, 8600040Ch; dwIoControlCode
0x18002f503  mov     [rsp+120h+lpOutBuffer], rax; lpOutBuffer
0x18002f508  mov     [rbp+57h+Overlapped.hEvent], r14
0x18002f50c  call    cs:__imp_DeviceIoControl
0x18002f512  test    eax, eax
0x18002f514  jnz     loc_18002F8A5
0x18002f51a  call    cs:__imp_GetLastError
0x18002f520  mov     esi, eax
0x18002f522  cmp     eax, 3E5h
0x18002f527  jnz     loc_18002F867
0x18002f52d  xor     r8d, r8d; bWaitAll
0x18002f530  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18002f534  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002f538  lea     ecx, [r8+2]; nCount
0x18002f53c  call    cs:__imp_WaitForMultipleObjects
0x18002f542  test    eax, eax
0x18002f544  jnz     short loc_18002F554
0x18002f546  mov     rcx, [rbp+57h+Thread]; hFile
0x18002f54a  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002f54e  call    cs:__imp_CancelIoEx
0x18002f554  mov     rcx, [rbp+57h+Thread]; hFile
0x18002f558  lea     r8, [rsp+120h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002f55d  mov     r9d, 1; bWait
0x18002f563  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002f567  call    cs:__imp_GetOverlappedResult
0x18002f56d  test    eax, eax
0x18002f56f  jz      loc_18002F8DD
0x18002f575  cmp     [rsp+120h+NumberOfBytesTransferred], 0Ch
0x18002f57a  jz      short loc_18002F5B7
0x18002f57c  mov     rax, cs:WPP_GLOBAL_Control
0x18002f583  cmp     rax, rbx
0x18002f586  jz      short loc_18002F5B4
0x18002f588  test    byte ptr [rax+1Ch], 1
0x18002f58c  jz      short loc_18002F5B4
0x18002f58e  cmp     byte ptr [rax+19h], 2
0x18002f592  jb      short loc_18002F5B4
0x18002f594  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f599  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5a0  mov     edx, 40h ; '@'
0x18002f5a5  mov     r9d, eax
0x18002f5a8  mov     r8, rdi
0x18002f5ab  mov     rcx, [rcx+10h]
0x18002f5af  call    WPP_SF_D
0x18002f5b4  mov     eax, r12d
0x18002f5b7  test    eax, eax
0x18002f5b9  jz      loc_18002F8DD
0x18002f5bf  cmp     dword ptr [rbp+57h+OutBuffer], r12d
0x18002f5c3  jnz     loc_18002F8DD
0x18002f5c9  mov     ecx, [rbp+57h+SessionId]; SessionId
0x18002f5cc  lea     rdx, pVirtualName; "URBDRC"
0x18002f5d3  xor     eax, eax
0x18002f5d5  mov     [rbp+57h+ppBuffer], r12
0x18002f5d9  xorps   xmm0, xmm0
0x18002f5dc  mov     [rbp+57h+var_60], rax
0x18002f5e0  movups  [rbp+57h+var_70], xmm0
0x18002f5e4  mov     r13, r12
0x18002f5e7  mov     [rsp+120h+pBytesReturned], r12d
0x18002f5ec  lea     r8d, [rax+1]; flags
0x18002f5f0  call    cs:__imp_WTSVirtualChannelOpenEx
0x18002f5f6  mov     rsi, rax
0x18002f5f9  test    rax, rax
0x18002f5fc  jz      loc_18002F749
0x18002f602  lea     r9, [rsp+120h+pBytesReturned]; pBytesReturned
0x18002f607  mov     edx, 1; WTS_VIRTUAL_CLASS
0x18002f60c  lea     r8, [rbp+57h+ppBuffer]; ppBuffer
0x18002f610  mov     rcx, rax; hChannelHandle
0x18002f613  mov     r12d, 0C0000001h
0x18002f619  call    cs:__imp_WTSVirtualChannelQuery
0x18002f61f  test    eax, eax
0x18002f621  jz      short loc_18002F680
0x18002f623  cmp     [rsp+120h+pBytesReturned], 8
0x18002f628  jnz     short loc_18002F677
0x18002f62a  mov     rax, [rbp+57h+ppBuffer]
0x18002f62e  lea     rcx, [r15+40h]; this
0x18002f632  mov     [rbp+57h+var_88], rcx
0x18002f636  mov     r13, [rax]
0x18002f639  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002f63e  mov     edx, [rbp+57h+SessionId]
0x18002f641  lea     rcx, [r15+50h]
0x18002f645  lea     r8, [rbp+57h+var_70]
0x18002f649  call    ?GetAt@?$DynArray@U_SESSION_DATA@@K@@QEAAHKPEAU_SESSION_DATA@@@Z; DynArray<_SESSION_DATA,ulong>::GetAt(ulong,_SESSION_DATA *)
0x18002f64e  test    eax, eax
0x18002f650  jz      short loc_18002F66E
0x18002f652  mov     rcx, [rbp+57h+var_60]; this
0x18002f656  test    rcx, rcx
0x18002f659  jz      short loc_18002F66E
0x18002f65b  mov     eax, dword ptr [rbp+57h+OutBuffer+4]
0x18002f65e  cmp     dword ptr [rbp+57h+var_70+0Ch], eax
0x18002f661  jnz     short loc_18002F66E
0x18002f663  mov     rdx, rsi; void *
0x18002f666  call    ?AddItemNoDuplicate@CSimpleHash@@QEAAJPEAXPEAK@Z; CSimpleHash::AddItemNoDuplicate(void *,ulong *)
0x18002f66b  mov     r12d, eax
0x18002f66e  lea     rcx, [rbp+57h+var_88]; this
0x18002f672  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002f677  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f67e  jmp     short loc_18002F6D9
0x18002f680  call    cs:__imp_GetLastError
0x18002f686  mov     r15d, eax
0x18002f689  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f690  cmp     rcx, rbx
0x18002f693  jz      short loc_18002F6D4
0x18002f695  test    byte ptr [rcx+1Ch], 1
0x18002f699  jz      short loc_18002F6D4
0x18002f69b  cmp     byte ptr [rcx+19h], 2
0x18002f69f  jb      short loc_18002F6D4
0x18002f6a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f6a6  mov     ecx, [rbp+57h+SessionId]
0x18002f6a9  mov     edx, 43h ; 'C'
0x18002f6ae  mov     [rsp+120h+nOutBufferSize], ecx
0x18002f6b2  mov     r9d, eax
0x18002f6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6bc  mov     r8, rdi
0x18002f6bf  mov     dword ptr [rsp+120h+lpOutBuffer], r15d
0x18002f6c4  mov     rcx, [rcx+10h]
0x18002f6c8  call    WPP_SF_DDd
0x18002f6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6d4  mov     r15, [rsp+120h+var_D8]
0x18002f6d9  mov     rax, [rbp+57h+ppBuffer]
0x18002f6dd  test    rax, rax
0x18002f6e0  jz      short loc_18002F6F2
0x18002f6e2  mov     rcx, rax; pMemory
0x18002f6e5  call    cs:__imp_WTSFreeMemory
0x18002f6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6f2  test    r12d, r12d
0x18002f6f5  jns     loc_18002F796
0x18002f6fb  cmp     rcx, rbx
0x18002f6fe  jz      short loc_18002F738
0x18002f700  test    byte ptr [rcx+1Ch], 1
0x18002f704  jz      short loc_18002F738
0x18002f706  cmp     byte ptr [rcx+19h], 2
0x18002f70a  jb      short loc_18002F738
0x18002f70c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f711  mov     ecx, [rbp+57h+SessionId]
0x18002f714  mov     edx, 44h ; 'D'
0x18002f719  mov     [rsp+120h+nOutBufferSize], ecx
0x18002f71d  mov     r9d, eax
0x18002f720  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f727  mov     r8, rdi
0x18002f72a  mov     dword ptr [rsp+120h+lpOutBuffer], r12d
0x18002f72f  mov     rcx, [rcx+10h]
0x18002f733  call    WPP_SF_DDd
0x18002f738  xor     r12d, r12d
0x18002f73b  mov     rcx, rsi; hChannelHandle
0x18002f73e  mov     r13d, r12d
0x18002f741  call    cs:__imp_WTSVirtualChannelClose
0x18002f747  jmp     short loc_18002F799
0x18002f749  call    cs:__imp_GetLastError
0x18002f74f  mov     esi, eax
0x18002f751  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f758  cmp     rcx, rbx
0x18002f75b  jz      short loc_18002F799
0x18002f75d  test    byte ptr [rcx+1Ch], 1
0x18002f761  jz      short loc_18002F799
0x18002f763  cmp     byte ptr [rcx+19h], 2
0x18002f767  jb      short loc_18002F799
0x18002f769  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f76e  mov     ecx, [rbp+57h+SessionId]
0x18002f771  mov     edx, 45h ; 'E'
0x18002f776  mov     [rsp+120h+nOutBufferSize], ecx
0x18002f77a  mov     r9d, eax
0x18002f77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f784  mov     r8, rdi
0x18002f787  mov     dword ptr [rsp+120h+lpOutBuffer], esi
0x18002f78b  mov     rcx, [rcx+10h]
0x18002f78f  call    WPP_SF_DDd
0x18002f794  jmp     short loc_18002F799
0x18002f796  xor     r12d, r12d
0x18002f799  mov     eax, dword ptr [rbp+57h+OutBuffer+4]
0x18002f79c  xorps   xmm0, xmm0
0x18002f79f  mov     dword ptr [rbp+57h+InBuffer+4], eax
0x18002f7a2  mov     rcx, r14; hEvent
0x18002f7a5  mov     eax, [rbp+57h+SessionId]
0x18002f7a8  mov     dword ptr [rbp+57h+InBuffer], eax
0x18002f7ab  mov     qword ptr [rbp+57h+InBuffer+8], r13
0x18002f7af  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002f7b3  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002f7b7  call    cs:__imp_ResetEvent
0x18002f7bd  mov     rcx, [rbp+57h+Thread]; hDevice
0x18002f7c1  lea     rax, [rbp+57h+Overlapped]
0x18002f7c5  mov     [rsp+120h+lpOverlapped], rax; lpOverlapped
0x18002f7ca  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18002f7ce  mov     [rsp+120h+lpBytesReturned], r12; lpBytesReturned
0x18002f7d3  mov     r9d, 10h; nInBufferSize
0x18002f7d9  mov     [rsp+120h+nOutBufferSize], r12d; nOutBufferSize
0x18002f7de  mov     edx, 86000408h; dwIoControlCode
0x18002f7e3  mov     [rsp+120h+lpOutBuffer], r12; lpOutBuffer
0x18002f7e8  mov     [rbp+57h+Overlapped.hEvent], r14
0x18002f7ec  call    cs:__imp_DeviceIoControl
0x18002f7f2  test    eax, eax
0x18002f7f4  jnz     short loc_18002F822
0x18002f7f6  call    cs:__imp_GetLastError
0x18002f7fc  cmp     eax, 3E5h
0x18002f801  jnz     loc_18002F8DD
0x18002f807  mov     rcx, [rbp+57h+Thread]; hFile
0x18002f80b  lea     r8, [rsp+120h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002f810  mov     r9d, 1; bWait
0x18002f816  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002f81a  call    cs:__imp_GetOverlappedResult
0x18002f820  jmp     short loc_18002F85D
0x18002f822  mov     rax, cs:WPP_GLOBAL_Control
0x18002f829  cmp     rax, rbx
0x18002f82c  jz      short loc_18002F85A
0x18002f82e  test    byte ptr [rax+1Ch], 1
0x18002f832  jz      short loc_18002F85A
0x18002f834  cmp     byte ptr [rax+19h], 2
0x18002f838  jb      short loc_18002F85A
0x18002f83a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f83f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f846  mov     edx, 46h ; 'F'
0x18002f84b  mov     r9d, eax
0x18002f84e  mov     r8, rdi
0x18002f851  mov     rcx, [rcx+10h]
0x18002f855  call    WPP_SF_D
0x18002f85a  mov     eax, r12d
0x18002f85d  test    eax, eax
0x18002f85f  jnz     loc_18002F4C6
  ... truncated ...
```

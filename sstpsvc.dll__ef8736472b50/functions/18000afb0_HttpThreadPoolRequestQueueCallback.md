# HttpThreadPoolRequestQueueCallback

- ea: `0x18000afb0`
- end: `0x18000b9bf`
- name: `HttpThreadPoolRequestQueueCallback`
- size: `2575`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002320`
- `0x180002aac`
- `0x180002f50`
- `0x180002f80`
- `0x180004fb0`
- `0x180005680`
- `0x180006f00`
- `0x1800071cc`
- `0x180007520`
- `0x1800089dc`
- `0x180008b90`
- `0x18000a710`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000c768`
- `0x18000ca68`
- `0x18000d2ec`
- `0x1800142b8`
- `0x18001d1c2`
- `0x18001d1da`
- `0x18001d210`
- `0x18001d2a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b1de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b35c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b418`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b484`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b508`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b63e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b6db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b919`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b1de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b35c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b418`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b484`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b508`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b5ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b63e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b6db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b919`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b49a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b66d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b49a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b66d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b86c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b86c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b856`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b856`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000b59e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000b59e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000b538`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000b538`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b780`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000b780`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000b56f`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000b56f`
- `prxyqry!GetSstpDestinationInfo` at `0x18000b810`
- `prxyqry!GetSstpDestinationInfo` at `0x18000b810`
- `prxyqry!GetSstpGroupIDFromQueryString` at `0x18000b725`
- `prxyqry!GetSstpGroupIDFromQueryString` at `0x18000b725`

## string_xrefs

- `0x18000b01c`: `HttpThreadPoolRequestQueueCallback`
- `0x18000b953`: `HttpThreadPoolRequestQueueCallback`
- `0x18000b7aa`: `Failed to create Correlation GUID: %d`

## pseudocode

```c
void __fastcall HttpThreadPoolRequestQueueCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        char *Overlapped,
        ULONG IoResult,
        ULONG_PTR NumberOfBytesTransferred)
{
  __int64 v7; // r8
  const wchar_t *v8; // r8
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rcx
  char *v18; // rcx
  unsigned int v19; // eax
  char *v20; // rcx
  char *v21; // rbx
  int v22; // r15d
  PTP_IO *v23; // rcx
  ULONG v24; // eax
  ULONG v25; // edi
  int v26; // r15d
  __int64 SstpGroupIDFromQueryString; // rax
  HRESULT v28; // eax
  __int64 v29; // r9
  unsigned int SstpDestinationInfo; // eax
  DWORD v31; // edi
  HANDLE ProcessHeap; // rax
  unsigned int v33; // eax
  ULONG RequestBufferLength[2]; // [rsp+20h] [rbp-E0h]
  DWORD Size; // [rsp+50h] [rbp-B0h] BYREF
  int Size_4; // [rsp+54h] [rbp-ACh] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v40; // [rsp+78h] [rbp-88h]
  _BYTE v41[8196]; // [rsp+7Ch] [rbp-84h] BYREF
  int v42; // [rsp+2080h] [rbp+1F80h] BYREF
  _BYTE v43[2044]; // [rsp+2084h] [rbp+1F84h] BYREF
  __int16 v44; // [rsp+2880h] [rbp+2780h] BYREF
  _BYTE v45[510]; // [rsp+2882h] [rbp+2782h] BYREF

  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v42, L"Entering %ws", L"HttpThreadPoolRequestQueueCallback");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v42);
  }
  if ( !Overlapped )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_94;
    v8 = L"NULL overlapped received";
    goto LABEL_7;
  }
  v9 = *((_DWORD *)Overlapped + 8);
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v42, L"Received overlapID %d", v9);
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v42);
  }
  v10 = v9 - 17767;
  if ( !v10 )
  {
    LOWORD(Size) = 0;
    v44 = 0;
    memset_0(v45, 0, 0x1FCu);
    v16 = *((_QWORD *)Overlapped + 7);
    if ( IoResult )
    {
      if ( IoResult == 234 )
      {
        if ( (byte_18002E903 & 0x10) != 0 )
        {
          LOWORD(v42) = 0;
          FormatRRASErrorString(&v42, L"CoId=%hs:RECEIVE_REQUEST with MORE_DATA", v16 + 552);
          if ( (byte_18002E903 & 0x10) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v42);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
        *(_DWORD *)(v16 + 252) |= 2u;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
        v22 = ProcessReceivedHttpRequest(Overlapped + 96, &Size);
        if ( v22 )
        {
          if ( (byte_18002E903 & 8) != 0 )
          {
            LOWORD(v42) = 0;
            FormatRRASErrorString(&v42, L"CoId=%hs:Validation of the header fails. Initiating termination", v16 + 552);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v42);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
          *(_DWORD *)(v16 + 268) = v22;
        }
        else
        {
          v23 = (PTP_IO *)SstpSvcGlobals;
          *(_OWORD *)Overlapped = 0;
          *((_OWORD *)Overlapped + 1) = 0;
          StartThreadpoolIo(v23[21]);
          v24 = HttpReceiveHttpRequest(
                  *((HANDLE *)SstpSvcGlobals + 8),
                  *((_QWORD *)Overlapped + 14),
                  0,
                  (PHTTP_REQUEST)(Overlapped + 96),
                  0x4000u,
                  0,
                  (LPOVERLAPPED)Overlapped);
          v25 = v24;
          if ( v24 == 997 || !v24 )
            goto LABEL_94;
          CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
          if ( (byte_18002E903 & 8) != 0 )
          {
            RequestBufferLength[0] = v25;
            LOWORD(v42) = 0;
            FormatRRASErrorString(
              &v42,
              L"CoId=%hs:Reposting HttpReceiveHttpRequest failed with %d [%d]",
              v16 + 552,
              v25,
              *(_QWORD *)RequestBufferLength);
            if ( (byte_18002E903 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v42);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
          *(_DWORD *)(v16 + 268) = v25;
        }
        InitiateCallContextCleanup(v16, 2);
        DereferenceRefCount(v16 + 208);
        PostNewHttpRequest();
        goto LABEL_94;
      }
      if ( IoResult != 995 )
      {
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_94;
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"CoId=%hs:IOResult: %d - Unhandled", v16 + 552, IoResult);
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_94;
        goto LABEL_49;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
      *(_DWORD *)(v16 + 268) = 995;
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
      *(_DWORD *)(v16 + 252) |= 0x202u;
      *(_QWORD *)(v16 + 280) = *((_QWORD *)Overlapped + 13);
      *(_QWORD *)(v16 + 272) = *((_QWORD *)Overlapped + 14);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
      v26 = ProcessReceivedHttpRequest(Overlapped + 96, &Size);
      if ( v26 )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          LOWORD(v42) = 0;
          FormatRRASErrorString(&v42, L"CoId=%hs:Validation of the header fails. Initiating termination", v16 + 552);
          if ( (byte_18002E903 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v42);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
        *(_DWORD *)(v16 + 268) = v26;
        InitiateCallContextCleanup(v16, 2);
        PostNewHttpRequest();
        goto LABEL_92;
      }
      PostNewHttpRequest();
      if ( (unsigned int)GetSstpConfigFlag(1) )
      {
        SstpGroupIDFromQueryString = GetSstpGroupIDFromQueryString(
                                       *((_QWORD *)Overlapped + 24),
                                       *((unsigned __int16 *)Overlapped + 83));
        if ( (unsigned int)FindSstpGatewayByGroup(SstpGroupIDFromQueryString, &v44) )
        {
          Src = 0;
          Size = 0;
          memset_0(v39, 0, 0x200Cu);
          Size_4 = 0;
          pguid = 0;
          v28 = CoCreateGuid(&pguid);
          if ( v28 )
          {
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_94;
            LOWORD(v42) = 0;
            FormatRRASErrorString(&v42, L"Failed to create Correlation GUID: %d", (unsigned __int16)v28);
          }
          else
          {
            LOBYTE(v29) = 1;
            SstpDestinationInfo = GetSstpDestinationInfo(&v44, &Src, &Size, v29, &Size_4, &pguid, 0, 0, 0);
            if ( !SstpDestinationInfo )
            {
              if ( Src )
              {
                v31 = Size;
                if ( Size < 0x2000 )
                {
                  memcpy_0(v41, Src, Size);
                  v40 = v31;
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, Src);
                  v33 = ForwardMakeCallRequest(v39, v16);
                  if ( v33 && (byte_18002E903 & 8) != 0 )
                  {
                    LOWORD(v42) = 0;
                    FormatRRASErrorString(&v42, L"ForwardMakeCallRequest failed: %d", v33);
LABEL_84:
                    if ( (byte_18002E903 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v42);
                  }
LABEL_92:
                  v20 = (char *)(v16 + 208);
                  goto LABEL_93;
                }
              }
            }
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_94;
            LOWORD(v42) = 0;
            FormatRRASErrorString(&v42, L"GetSstpDestinationInfo failed: %d", SstpDestinationInfo);
          }
          if ( (byte_18002E903 & 8) == 0 )
            goto LABEL_94;
LABEL_49:
          v8 = (const wchar_t *)&v42;
LABEL_7:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v8);
          goto LABEL_94;
        }
      }
      if ( (unsigned int)GetSstpConfigFlag(2) )
      {
        ProcessNewCall(v16, Overlapped, Overlapped + 96);
        goto LABEL_92;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 288));
      *(_DWORD *)(v16 + 268) = 0;
    }
    InitiateCallContextCleanup(v16, 2);
    goto LABEL_92;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"TerminatePartialConnection returns");
    LOBYTE(v7) = 1;
    v21 = (char *)*((_QWORD *)Overlapped + 7);
    FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v7);
    EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 288));
    *((_DWORD *)v21 + 63) &= ~0x2000u;
    v18 = v21;
    goto LABEL_43;
  }
  v12 = v11 - 3;
  if ( !v12 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)Overlapped + 4);
    InitiateCallContextCleanup(Overlapped - 128, 1);
    v20 = Overlapped + 80;
LABEL_93:
    DereferenceRefCount(v20);
    goto LABEL_94;
  }
  v13 = v12 - 2;
  if ( !v13 )
  {
    v16 = *((_QWORD *)Overlapped + 7);
    if ( !IoResult )
    {
      if ( (byte_18002E903 & 0x10) != 0 )
      {
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"CoId=%hs:Successfully established the Layer-2", v16 + 552);
        if ( (byte_18002E903 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v42);
      }
      IndicateCallConnectedToTPI((LPOVERLAPPED)v16);
      goto LABEL_92;
    }
    if ( !(unsigned int)IsProxyCall(*((_QWORD *)Overlapped + 7)) )
    {
      Size = 0;
      v19 = SyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212480, (int)v16 + 240, 4, 0, 0, &Size);
      if ( v19 )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          LOWORD(v42) = 0;
          FormatRRASErrorString(&v42, L"CoId=%hs:SyncDevCtrl for Fast disconnect notify fails with %d", v16 + 552, v19);
          goto LABEL_84;
        }
      }
    }
    goto LABEL_92;
  }
  v14 = v13 - 2;
  if ( !v14 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)Overlapped + 3);
    *((_DWORD *)Overlapped + 21) &= ~0x2000u;
    v18 = Overlapped - 168;
LABEL_43:
    InitiateCallContextCleanup(v18, 2);
    goto LABEL_94;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v16 = *((_QWORD *)Overlapped + 7);
    if ( IoResult )
    {
      LOBYTE(v7) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v7);
    }
    else
    {
      v17 = *((_QWORD *)Overlapped + 7);
      *((_DWORD *)Overlapped + 23) = NumberOfBytesTransferred;
      *((_DWORD *)Overlapped + 22) = *(_DWORD *)(v16 + 240);
      if ( (unsigned int)IsProxyCall(v17) )
        ProxySendToRelatedCtx((LPOVERLAPPED)Overlapped);
      else
        ProcessReceivedBytes(Overlapped);
      PostReceiveOnCall(v16);
    }
    goto LABEL_92;
  }
  if ( v15 == 2 )
  {
    if ( IoResult )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"SendToHttp fails with %d", IoResult);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v42);
      }
    }
    LOBYTE(v7) = 1;
    FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v7);
  }
LABEL_94:
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v42) = 0;
    FormatRRASErrorString(&v42, L"LEaving %ws", L"HttpThreadPoolRequestQueueCallback");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v42);
  }
}

```

## disassembly

```asm
0x18000afb0  mov     [rsp-8+arg_0], rbx
0x18000afb5  mov     [rsp-8+arg_8], rsi
0x18000afba  push    rbp
0x18000afbb  push    rdi
0x18000afbc  push    r13
0x18000afbe  push    r14
0x18000afc0  push    r15
0x18000afc2  lea     rbp, [rsp-2990h]
0x18000afca  mov     eax, 2A90h
0x18000afcf  call    _alloca_probe
0x18000afd4  sub     rsp, rax
0x18000afd7  mov     rax, cs:__security_cookie
0x18000afde  xor     rax, rsp
0x18000afe1  mov     [rbp+29B0h+var_30], rax
0x18000afe8  mov     rdi, r8
0x18000afeb  lea     rcx, [rbp+29B0h+var_A2C]; void *
0x18000aff2  xor     eax, eax
0x18000aff4  mov     r8d, 7FCh; Size
0x18000affa  xor     edx, edx; Val
0x18000affc  mov     [rbp+29B0h+var_A30], eax
0x18000b002  mov     esi, r9d
0x18000b005  call    memset_0
0x18000b00a  test    cs:byte_18002E903, 10h
0x18000b011  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b018  jz      short loc_18000B05C
0x18000b01a  xor     eax, eax
0x18000b01c  lea     r8, aHttpthreadpool; "HttpThreadPoolRequestQueueCallback"
0x18000b023  lea     rdx, aEnteringWs; "Entering %ws"
0x18000b02a  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000b031  lea     rcx, [rbp+29B0h+var_A30]
0x18000b038  call    FormatRRASErrorString
0x18000b03d  test    cs:byte_18002E903, 10h
0x18000b044  jz      short loc_18000B05C
0x18000b046  lea     r8, [rbp+29B0h+var_A30]
0x18000b04d  mov     rcx, r13
0x18000b050  lea     rdx, RasSSTPSvcTraceInfo
0x18000b057  call    McTemplateU0z_EventWriteTransfer
0x18000b05c  test    rdi, rdi
0x18000b05f  jnz     short loc_18000B089
0x18000b061  test    cs:byte_18002E903, 8
0x18000b068  jz      loc_18000B948
0x18000b06e  lea     r8, aNullOverlapped; "NULL overlapped received"
0x18000b075  lea     rdx, RasSSTPSvcTraceError
0x18000b07c  mov     rcx, r13
0x18000b07f  call    McTemplateU0z_EventWriteTransfer
0x18000b084  jmp     loc_18000B948
0x18000b089  test    cs:byte_18002E903, 10h
0x18000b090  mov     ebx, [rdi+20h]
0x18000b093  jz      short loc_18000B0D3
0x18000b095  xor     eax, eax
0x18000b097  lea     rdx, aReceivedOverla; "Received overlapID %d"
0x18000b09e  mov     r8d, ebx
0x18000b0a1  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000b0a8  lea     rcx, [rbp+29B0h+var_A30]
0x18000b0af  call    FormatRRASErrorString
0x18000b0b4  test    cs:byte_18002E903, 10h
0x18000b0bb  jz      short loc_18000B0D3
0x18000b0bd  lea     r8, [rbp+29B0h+var_A30]
0x18000b0c4  mov     rcx, r13
0x18000b0c7  lea     rdx, RasSSTPSvcTraceInfo
0x18000b0ce  call    McTemplateU0z_EventWriteTransfer
0x18000b0d3  sub     ebx, 4567h
0x18000b0d9  jz      loc_18000B382
0x18000b0df  sub     ebx, 1
0x18000b0e2  jz      loc_18000B319
0x18000b0e8  sub     ebx, 3
0x18000b0eb  jz      loc_18000B2EF
0x18000b0f1  sub     ebx, 2
0x18000b0f4  jz      loc_18000B1FB
0x18000b0fa  sub     ebx, 2
0x18000b0fd  jz      loc_18000B1DA
0x18000b103  sub     ebx, 1
0x18000b106  jz      short loc_18000B17A
0x18000b108  cmp     ebx, 2
0x18000b10b  jnz     loc_18000B948
0x18000b111  test    esi, esi
0x18000b113  jz      short loc_18000B15C
0x18000b115  test    cs:byte_18002E903, 8
0x18000b11c  jz      short loc_18000B15C
0x18000b11e  xor     eax, eax
0x18000b120  lea     rdx, aSendtohttpFail; "SendToHttp fails with %d"
0x18000b127  mov     r8d, esi
0x18000b12a  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000b131  lea     rcx, [rbp+29B0h+var_A30]
0x18000b138  call    FormatRRASErrorString
0x18000b13d  test    cs:byte_18002E903, 8
0x18000b144  jz      short loc_18000B15C
0x18000b146  lea     r8, [rbp+29B0h+var_A30]
0x18000b14d  mov     rcx, r13
0x18000b150  lea     rdx, RasSSTPSvcTraceError
0x18000b157  call    McTemplateU0z_EventWriteTransfer
0x18000b15c  mov     rcx, cs:SstpSvcGlobals
0x18000b163  mov     r8b, 1
0x18000b166  add     rcx, 1A8h
0x18000b16d  mov     rdx, rdi
0x18000b170  call    FreeBufferToPool
0x18000b175  jmp     loc_18000B948
0x18000b17a  mov     rbx, [rdi+38h]
0x18000b17e  test    esi, esi
0x18000b180  jnz     short loc_18000B1BC
0x18000b182  mov     eax, dword ptr [rbp+29B0h+NumberOfBytesTransferred]
0x18000b188  mov     rcx, rbx
0x18000b18b  mov     [rdi+5Ch], eax
0x18000b18e  mov     eax, [rbx+0F0h]
0x18000b194  mov     [rdi+58h], eax
0x18000b197  call    IsProxyCall
0x18000b19c  mov     rcx, rdi; Overlapped
0x18000b19f  test    eax, eax
0x18000b1a1  jz      short loc_18000B1AA
0x18000b1a3  call    ProxySendToRelatedCtx
0x18000b1a8  jmp     short loc_18000B1AF
0x18000b1aa  call    ProcessReceivedBytes
0x18000b1af  mov     rcx, rbx
0x18000b1b2  call    PostReceiveOnCall
0x18000b1b7  jmp     loc_18000B93C
0x18000b1bc  mov     rcx, cs:SstpSvcGlobals
0x18000b1c3  mov     r8b, 1
0x18000b1c6  add     rcx, 1A8h
0x18000b1cd  mov     rdx, rdi
0x18000b1d0  call    FreeBufferToPool
0x18000b1d5  jmp     loc_18000B93C
0x18000b1da  lea     rcx, [rdi+78h]; lpCriticalSection
0x18000b1de  call    cs:__imp_EnterCriticalSection
0x18000b1e5  nop     dword ptr [rax+rax+00h]
0x18000b1ea  btr     dword ptr [rdi+54h], 0Dh
0x18000b1ef  lea     rcx, [rdi-0A8h]
0x18000b1f6  jmp     loc_18000B373
0x18000b1fb  mov     rbx, [rdi+38h]
0x18000b1ff  test    esi, esi
0x18000b201  jnz     short loc_18000B25B
0x18000b203  test    cs:byte_18002E903, 10h
0x18000b20a  jz      short loc_18000B24E
0x18000b20c  xor     eax, eax
0x18000b20e  lea     r8, [rbx+228h]
0x18000b215  lea     rdx, aCoidHsSuccessf; "CoId=%hs:Successfully established the L"...
0x18000b21c  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000b223  lea     rcx, [rbp+29B0h+var_A30]
0x18000b22a  call    FormatRRASErrorString
0x18000b22f  test    cs:byte_18002E903, 10h
0x18000b236  jz      short loc_18000B24E
0x18000b238  lea     r8, [rbp+29B0h+var_A30]
0x18000b23f  mov     rcx, r13
0x18000b242  lea     rdx, RasSSTPSvcTraceInfo
0x18000b249  call    McTemplateU0z_EventWriteTransfer
0x18000b24e  mov     rcx, rbx; LPOVERLAPPED
0x18000b251  call    IndicateCallConnectedToTPI
0x18000b256  jmp     loc_18000B93C
0x18000b25b  mov     rcx, rbx
0x18000b25e  call    IsProxyCall
0x18000b263  test    eax, eax
0x18000b265  jnz     loc_18000B93C
0x18000b26b  mov     rcx, cs:SstpSvcGlobals
0x18000b272  lea     r8, [rbx+0F0h]; int
0x18000b279  mov     dword ptr [rsp+2AB0h+Size], eax
0x18000b27d  mov     edx, 128040h; int
0x18000b282  lea     rax, [rsp+2AB0h+Size]
0x18000b287  mov     r9d, 4; int
0x18000b28d  mov     [rsp+2AB0h+Overlapped], rax; LPDWORD
0x18000b292  mov     rcx, [rcx+118h]; int
0x18000b299  mov     dword ptr [rsp+2AB0h+BytesReturned], 0; DWORD
0x18000b2a1  mov     qword ptr [rsp+2AB0h+RequestBufferLength], 0; LPVOID
0x18000b2aa  call    SyncDeviceControl
0x18000b2af  test    eax, eax
0x18000b2b1  jz      loc_18000B93C
0x18000b2b7  test    cs:byte_18002E903, 8
0x18000b2be  jz      loc_18000B93C
0x18000b2c4  xor     ecx, ecx
0x18000b2c6  lea     r8, [rbx+228h]
0x18000b2cd  mov     word ptr [rbp+29B0h+var_A30], cx
0x18000b2d4  lea     rdx, aCoidHsSyncdevc; "CoId=%hs:SyncDevCtrl for Fast disconnec"...
0x18000b2db  lea     rcx, [rbp+29B0h+var_A30]
0x18000b2e2  mov     r9d, eax
0x18000b2e5  call    FormatRRASErrorString
0x18000b2ea  jmp     loc_18000B8B9
0x18000b2ef  lea     rcx, [rdi+0A0h]; lpCriticalSection
0x18000b2f6  call    cs:__imp_EnterCriticalSection
0x18000b2fd  nop     dword ptr [rax+rax+00h]
0x18000b302  mov     edx, 1
0x18000b307  lea     rcx, [rdi-80h]
0x18000b30b  call    InitiateCallContextCleanup
0x18000b310  lea     rcx, [rdi+50h]
0x18000b314  jmp     loc_18000B943
0x18000b319  test    cs:byte_18002E903, 10h
0x18000b320  jz      short loc_18000B338
0x18000b322  lea     r8, aTerminateparti; "TerminatePartialConnection returns"
0x18000b329  mov     rcx, r13
0x18000b32c  lea     rdx, RasSSTPSvcTraceInfo
0x18000b333  call    McTemplateU0z_EventWriteTransfer
0x18000b338  mov     rcx, cs:SstpSvcGlobals
0x18000b33f  mov     r8b, 1
0x18000b342  mov     rbx, [rdi+38h]
0x18000b346  add     rcx, 1A8h
0x18000b34d  mov     rdx, rdi
0x18000b350  call    FreeBufferToPool
0x18000b355  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000b35c  call    cs:__imp_EnterCriticalSection
0x18000b363  nop     dword ptr [rax+rax+00h]
0x18000b368  btr     dword ptr [rbx+0FCh], 0Dh
0x18000b370  mov     rcx, rbx
0x18000b373  mov     edx, 2
0x18000b378  call    InitiateCallContextCleanup
0x18000b37d  jmp     loc_18000B948
0x18000b382  xor     eax, eax
0x18000b384  lea     rcx, [rbp+29B0h+var_22E]; void *
0x18000b38b  xor     edx, edx; Val
0x18000b38d  mov     word ptr [rsp+2AB0h+Size], ax
0x18000b392  mov     r8d, 1FCh; Size
0x18000b398  mov     [rbp+29B0h+var_230], ax
0x18000b39f  call    memset_0
0x18000b3a4  mov     rbx, [rdi+38h]
0x18000b3a8  lea     r14, [rdi+60h]
0x18000b3ac  test    esi, esi
0x18000b3ae  jz      loc_18000B634
0x18000b3b4  cmp     esi, 0EAh
0x18000b3ba  jz      short loc_18000B42F
0x18000b3bc  mov     edi, 3E3h
0x18000b3c1  cmp     esi, edi
0x18000b3c3  jz      short loc_18000B411
0x18000b3c5  test    cs:byte_18002E903, 8
0x18000b3cc  jz      loc_18000B948
0x18000b3d2  xor     eax, eax
0x18000b3d4  lea     r8, [rbx+228h]
0x18000b3db  mov     r9d, esi
0x18000b3de  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000b3e5  lea     rdx, aCoidHsIoresult; "CoId=%hs:IOResult: %d - Unhandled"
0x18000b3ec  lea     rcx, [rbp+29B0h+var_A30]
0x18000b3f3  call    FormatRRASErrorString
0x18000b3f8  test    cs:byte_18002E903, 8
0x18000b3ff  jz      loc_18000B948
0x18000b405  lea     r8, [rbp+29B0h+var_A30]
0x18000b40c  jmp     loc_18000B075
0x18000b411  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000b418  call    cs:__imp_EnterCriticalSection
0x18000b41f  nop     dword ptr [rax+rax+00h]
0x18000b424  mov     [rbx+10Ch], edi
0x18000b42a  jmp     loc_18000B92F
0x18000b42f  test    cs:byte_18002E903, 10h
0x18000b436  jz      short loc_18000B47A
0x18000b438  xor     eax, eax
0x18000b43a  lea     r8, [rbx+228h]
0x18000b441  lea     rdx, aCoidHsReceiveR; "CoId=%hs:RECEIVE_REQUEST with MORE_DATA"
0x18000b448  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000b44f  lea     rcx, [rbp+29B0h+var_A30]
0x18000b456  call    FormatRRASErrorString
0x18000b45b  test    cs:byte_18002E903, 10h
0x18000b462  jz      short loc_18000B47A
0x18000b464  lea     r8, [rbp+29B0h+var_A30]
0x18000b46b  mov     rcx, r13
0x18000b46e  lea     rdx, RasSSTPSvcTraceInfo
0x18000b475  call    McTemplateU0z_EventWriteTransfer
0x18000b47a  lea     rsi, [rbx+120h]
0x18000b481  mov     rcx, rsi; lpCriticalSection
0x18000b484  call    cs:__imp_EnterCriticalSection
0x18000b48b  nop     dword ptr [rax+rax+00h]
0x18000b490  or      dword ptr [rbx+0FCh], 2
0x18000b497  mov     rcx, rsi; lpCriticalSection
0x18000b49a  call    cs:__imp_LeaveCriticalSection
0x18000b4a1  nop     dword ptr [rax+rax+00h]
0x18000b4a6  lea     rdx, [rsp+2AB0h+Size]
0x18000b4ab  mov     rcx, r14
0x18000b4ae  call    ProcessReceivedHttpRequest
0x18000b4b3  mov     r15d, eax
0x18000b4b6  test    eax, eax
0x18000b4b8  jz      short loc_18000B520
0x18000b4ba  test    cs:byte_18002E903, 8
0x18000b4c1  jz      short loc_18000B505
0x18000b4c3  xor     ecx, ecx
0x18000b4c5  lea     r8, [rbx+228h]
0x18000b4cc  mov     word ptr [rbp+29B0h+var_A30], cx
0x18000b4d3  lea     rdx, aCoidHsValidati; "CoId=%hs:Validation of the header fails"...
0x18000b4da  lea     rcx, [rbp+29B0h+var_A30]
0x18000b4e1  call    FormatRRASErrorString
0x18000b4e6  test    cs:byte_18002E903, 8
0x18000b4ed  jz      short loc_18000B505
0x18000b4ef  lea     r8, [rbp+29B0h+var_A30]
0x18000b4f6  mov     rcx, r13
0x18000b4f9  lea     rdx, RasSSTPSvcTraceError
0x18000b500  call    McTemplateU0z_EventWriteTransfer
0x18000b505  mov     rcx, rsi; lpCriticalSection
0x18000b508  call    cs:__imp_EnterCriticalSection
0x18000b50f  nop     dword ptr [rax+rax+00h]
0x18000b514  mov     [rbx+10Ch], r15d
0x18000b51b  jmp     loc_18000B611
0x18000b520  mov     rcx, cs:SstpSvcGlobals
0x18000b527  xorps   xmm0, xmm0
0x18000b52a  movups  xmmword ptr [rdi], xmm0
0x18000b52d  movups  xmmword ptr [rdi+10h], xmm0
0x18000b531  mov     rcx, [rcx+0A8h]; pio
0x18000b538  call    cs:__imp_StartThreadpoolIo
0x18000b53f  nop     dword ptr [rax+rax+00h]
0x18000b544  mov     rcx, cs:SstpSvcGlobals
0x18000b54b  mov     r9, r14; RequestBuffer
0x18000b54e  mov     rdx, [r14+10h]; RequestId
0x18000b552  xor     r8d, r8d; Flags
0x18000b555  mov     [rsp+2AB0h+Overlapped], rdi; Overlapped
0x18000b55a  mov     [rsp+2AB0h+BytesReturned], 0; BytesReturned
0x18000b563  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000b567  mov     [rsp+2AB0h+RequestBufferLength], 4000h; RequestBufferLength
0x18000b56f  call    cs:__imp_HttpReceiveHttpRequest
0x18000b576  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

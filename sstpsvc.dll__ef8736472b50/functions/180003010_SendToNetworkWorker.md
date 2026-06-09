# SendToNetworkWorker

- ea: `0x180003010`
- end: `0x180003612`
- name: `SendToNetworkWorker`
- size: `1538`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800011b0`
- `0x180002aac`
- `0x180002f80`
- `0x180003010`
- `0x180003620`
- `0x1800075a0`
- `0x180007f48`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003071`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003230`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003288`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003071`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003230`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003288`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800030c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003127`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000354d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800030c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003127`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000354d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003487`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000317d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000317d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800033ea`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800033ea`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180003355`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180003355`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x1800033a2`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x1800033a2`
- `webio!__imp_WebSendHttpRequestEntity` at `0x1800031f4`
- `webio!__imp_WebSendHttpRequestEntity` at `0x1800031f4`

## pseudocode

```c
void __fastcall SendToNetworkWorker(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  int v4; // r12d
  char *v5; // rsi
  char *v6; // rbx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 Overlapped; // rbx
  _DWORD *v11; // rsi
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // esi
  _QWORD *v15; // rbx
  char *v16; // rsi
  __int64 v17; // rax
  struct _TP_IO *v18; // rcx
  ULONG v19; // eax
  __int64 v20; // r8
  ULONG v21; // esi
  DWORD LastError; // eax
  __int64 v23; // r8
  LPVOID lpOutBuffer; // [rsp+28h] [rbp-E0h]
  __int64 InBuffer; // [rsp+58h] [rbp-B0h] BYREF
  _HTTP_DATA_CHUNK EntityChunks; // [rsp+60h] [rbp-A8h] BYREF
  int v27; // [rsp+88h] [rbp-80h] BYREF
  char v28[2044]; // [rsp+8Ch] [rbp-7Ch] BYREF

  LODWORD(InBuffer) = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Entering %ws", L"SendToNetworkWorker");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v27);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  *((_DWORD *)Context + 63) |= 0x80u;
  if ( Context[435] )
    goto LABEL_18;
  v4 = 20;
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  LODWORD(InBuffer) = *((_DWORD *)Context + 60);
  while ( 1 )
  {
    v5 = (char *)SstpSvcGlobals;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
    v6 = (char *)*((_QWORD *)v5 + 58);
    if ( v6 == v5 + 464 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 488));
      Overlapped = AddBufferBlockToPool(v5 + 424);
    }
    else
    {
      v7 = (_QWORD *)*((_QWORD *)v6 + 1);
      v8 = *(_QWORD *)v6;
      *v7 = *(_QWORD *)v6;
      *(_QWORD *)(v8 + 8) = v7;
      v9 = *((_QWORD *)v6 + 2);
      *((_QWORD *)v6 + 1) = v6;
      *(_QWORD *)v6 = v6;
      --*(_DWORD *)(v9 + 28);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 488));
      Overlapped = (__int64)(v6 + 24);
    }
    if ( !Overlapped )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_17;
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v27,
        L"CoId=%hs:Not enough buffer pool memory to process receive.Deferring...",
        Context + 552);
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_17;
      goto LABEL_31;
    }
    v11 = (_DWORD *)(Overlapped + 92);
    if ( !DeviceIoControl(
            *((HANDLE *)SstpSvcGlobals + 35),
            0x128026u,
            &InBuffer,
            4u,
            (LPVOID)(Overlapped + 96),
            0x4000u,
            (LPDWORD)(Overlapped + 92),
            0) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( (byte_18002E903 & 8) != 0 )
        {
          LOWORD(v27) = 0;
          FormatRRASErrorString(&v27, L"CoId=%hs:SendToNetwork fails with error %d", Context + 552, LastError);
          if ( (byte_18002E903 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v27);
        }
        LOBYTE(v23) = 1;
        FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v23);
        goto LABEL_17;
      }
    }
    if ( !*v11 )
      break;
    *(_DWORD *)(Overlapped + 32) = 17778;
    *(_OWORD *)Overlapped = 0;
    *(_OWORD *)(Overlapped + 16) = 0;
    v12 = (unsigned int)*v11;
    if ( !Context[248] )
    {
      *(_QWORD *)&EntityChunks.DataChunkType = 0;
      *(ULONGLONG *)((char *)&EntityChunks.FromFragmentCacheEx.ByteRange.Length.QuadPart + 4) = 0;
      EntityChunks.FromFileHandle.ByteRange.StartingOffset.QuadPart = Overlapped + 96;
      v18 = (struct _TP_IO *)*((_QWORD *)SstpSvcGlobals + 21);
      EntityChunks.FromMemory.BufferLength = v12;
      StartThreadpoolIo(v18);
      v19 = HttpSendResponseEntityBody(
              *((HANDLE *)SstpSvcGlobals + 8),
              *((_QWORD *)Context + 34),
              2u,
              1u,
              &EntityChunks,
              0,
              0,
              0,
              (LPOVERLAPPED)Overlapped,
              0);
      v21 = v19;
      if ( v19 == 997 || !v19 )
        goto LABEL_11;
      LOBYTE(v20) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v20);
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_17;
      LOWORD(v27) = 0;
      LODWORD(lpOutBuffer) = v21;
      FormatRRASErrorString(
        &v27,
        L"CoId=%hs:HttpSendResponseEntityBody fails with error %d [%d]",
        Context + 552,
        v21,
        lpOutBuffer);
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_17;
LABEL_31:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v27);
      goto LABEL_17;
    }
    *(_QWORD *)(Overlapped + 72) = Overlapped + 96;
    *(_DWORD *)(Overlapped + 64) = 0;
    *(_QWORD *)(Overlapped + 80) = v12;
    _InterlockedIncrement((volatile signed __int32 *)Context + 52);
    *(_QWORD *)(Overlapped + 56) = Context;
    v13 = WebSendHttpRequestEntity(
            *((_QWORD *)Context + 56),
            0,
            Overlapped + 64,
            1,
            SstpWebSendRequestEntityCompletion,
            Overlapped);
    v14 = v13;
    if ( v13 != 997 )
    {
      SstpWebSendRequestEntityCompletion(Overlapped, v13, 0);
      if ( v14 )
        goto LABEL_17;
    }
LABEL_11:
    if ( !v4 )
      goto LABEL_17;
    --v4;
  }
  v15 = (_QWORD *)(Overlapped - 24);
  v16 = (char *)SstpSvcGlobals + 424;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
  if ( (_QWORD *)*v15 == v15 )
  {
    v17 = *((_QWORD *)v16 + 5);
    *v15 = v17;
    v15[1] = v16 + 40;
    *(_QWORD *)(v17 + 8) = v15;
    *((_QWORD *)v16 + 5) = v15;
    ++*(_DWORD *)(v15[2] + 28LL);
    if ( ++*((_DWORD *)v16 + 5) >= *((_DWORD *)v16 + 4) )
    {
      FreeUnusedBufferPoolBlocks(v16);
      *((_DWORD *)v16 + 5) = 0;
    }
  }
  else
  {
    ++g_ulDoubleBufferFrees;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 64));
LABEL_17:
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 288));
LABEL_18:
  *((_DWORD *)Context + 63) &= ~0x80u;
  if ( Context[435] )
  {
    InitiateCallContextCleanup((__int64)Context, 2u);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 288));
    PostSendNotificationRequest((__int64)Context);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context + 52, 0xFFFFFFFF) == 1 )
    (*((void (__fastcall **)(char *))Context + 27))(Context + 208);
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"LEaving %ws", L"SendToNetworkWorker");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v27);
  }
}

```

## disassembly

```asm
0x180003010  mov     r11, rsp
0x180003013  push    rbp
0x180003014  push    r13
0x180003016  lea     rbp, [r11-7B8h]
0x18000301d  sub     rsp, 8A8h
0x180003024  mov     rax, cs:__security_cookie
0x18000302b  xor     rax, rsp
0x18000302e  mov     [rbp+7B0h+var_30], rax
0x180003035  mov     [r11+20h], rdi
0x180003039  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18000303d  mov     rdi, rdx
0x180003040  mov     [r11-28h], r15
0x180003044  xor     r13d, r13d
0x180003047  xor     edx, edx; Val
0x180003049  mov     r8d, 7FCh; Size
0x18000304f  mov     dword ptr [rsp+8B0h+InBuffer], r13d
0x180003054  mov     [rbp+7B0h+var_830], r13d
0x180003058  call    memset_0
0x18000305d  test    cs:byte_18002E903, 10h
0x180003064  jnz     loc_180003501
0x18000306a  lea     rcx, [rdi+120h]; lpCriticalSection
0x180003071  call    cs:__imp_EnterCriticalSection
0x180003078  nop     dword ptr [rax+rax+00h]
0x18000307d  or      dword ptr [rdi+0FCh], 80h
0x180003087  cmp     [rdi+1B3h], r13b
0x18000308e  jnz     loc_1800032B4
0x180003094  mov     [rsp+8B0h+arg_0], rbx
0x18000309c  lea     rcx, [rdi+120h]; lpCriticalSection
0x1800030a3  mov     [rsp+8B0h+arg_10], rsi
0x1800030ab  mov     [rsp+8A0h], r12
0x1800030b3  mov     r12d, 14h
0x1800030b9  mov     [rsp+8B0h+var_18], r14
0x1800030c1  call    cs:__imp_LeaveCriticalSection
0x1800030c8  nop     dword ptr [rax+rax+00h]
0x1800030cd  mov     eax, [rdi+0F0h]
0x1800030d3  mov     dword ptr [rsp+8B0h+InBuffer], eax
0x1800030d7  mov     rsi, cs:SstpSvcGlobals
0x1800030de  lea     rcx, [rsi+1E8h]; lpCriticalSection
0x1800030e5  call    cs:__imp_EnterCriticalSection
0x1800030ec  nop     dword ptr [rax+rax+00h]
0x1800030f1  lea     rax, [rsi+1D0h]
0x1800030f8  mov     rbx, [rax]
0x1800030fb  cmp     rbx, rax
0x1800030fe  jz      loc_180003546
0x180003104  mov     rax, [rbx+8]
0x180003108  mov     rcx, [rbx]
0x18000310b  mov     [rax], rcx
0x18000310e  mov     [rcx+8], rax
0x180003112  lea     rcx, [rsi+1E8h]; lpCriticalSection
0x180003119  mov     rax, [rbx+10h]
0x18000311d  mov     [rbx+8], rbx
0x180003121  mov     [rbx], rbx
0x180003124  dec     dword ptr [rax+1Ch]
0x180003127  call    cs:__imp_LeaveCriticalSection
0x18000312e  nop     dword ptr [rax+rax+00h]
0x180003133  add     rbx, 18h
0x180003137  test    rbx, rbx
0x18000313a  jz      loc_180003435
0x180003140  mov     rcx, cs:SstpSvcGlobals
0x180003147  lea     rsi, [rbx+5Ch]
0x18000314b  mov     [rsp+8B0h+lpOverlapped], r13; lpOverlapped
0x180003150  lea     r14, [rbx+60h]
0x180003154  mov     [rsp+8B0h+lpBytesReturned], rsi; lpBytesReturned
0x180003159  lea     r8, [rsp+8B0h+InBuffer]; lpInBuffer
0x18000315e  mov     [rsp+8B0h+nOutBufferSize], 4000h; nOutBufferSize
0x180003166  mov     r9d, 4; nInBufferSize
0x18000316c  mov     rcx, [rcx+118h]; hDevice
0x180003173  mov     edx, 128026h; dwIoControlCode
0x180003178  mov     [rsp+8B0h+lpOutBuffer], r14; lpOutBuffer
0x18000317d  call    cs:__imp_DeviceIoControl
0x180003184  nop     dword ptr [rax+rax+00h]
0x180003189  test    eax, eax
0x18000318b  jz      loc_180003487
0x180003191  cmp     [rsi], r13d
0x180003194  jbe     loc_18000321A
0x18000319a  mov     dword ptr [rbx+20h], 4572h
0x1800031a1  xorps   xmm0, xmm0
0x1800031a4  movups  xmmword ptr [rbx], xmm0
0x1800031a7  movups  xmmword ptr [rbx+10h], xmm0
0x1800031ab  mov     eax, [rsi]
0x1800031ad  cmp     [rdi+0F8h], r13b
0x1800031b4  jz      loc_180003334
0x1800031ba  lea     r8, [rbx+40h]
0x1800031be  mov     [rbx+48h], r14
0x1800031c2  mov     [r8], r13d
0x1800031c5  mov     [rbx+50h], rax
0x1800031c9  lock inc dword ptr [rdi+0D0h]
0x1800031d0  mov     [rbx+38h], rdi
0x1800031d4  lea     rax, SstpWebSendRequestEntityCompletion
0x1800031db  mov     rcx, [rdi+1C0h]
0x1800031e2  xor     edx, edx
0x1800031e4  mov     qword ptr [rsp+8B0h+nOutBufferSize], rbx
0x1800031e9  mov     r9d, 1
0x1800031ef  mov     [rsp+8B0h+lpOutBuffer], rax
0x1800031f4  call    cs:__imp_WebSendHttpRequestEntity
0x1800031fb  nop     dword ptr [rax+rax+00h]
0x180003200  mov     esi, eax
0x180003202  cmp     eax, 3E5h
0x180003207  jnz     loc_18000356D
0x18000320d  test    r12d, r12d
0x180003210  jz      short loc_180003281
0x180003212  dec     r12d
0x180003215  jmp     loc_1800030D7
0x18000321a  mov     rsi, cs:SstpSvcGlobals
0x180003221  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180003225  add     rsi, 1A8h
0x18000322c  lea     rcx, [rsi+40h]; lpCriticalSection
0x180003230  call    cs:__imp_EnterCriticalSection
0x180003237  nop     dword ptr [rax+rax+00h]
0x18000323c  cmp     [rbx], rbx
0x18000323f  jnz     loc_180003587
0x180003245  mov     rax, [rsi+28h]
0x180003249  lea     rcx, [rsi+28h]
0x18000324d  mov     [rbx], rax
0x180003250  mov     [rbx+8], rcx
0x180003254  mov     [rax+8], rbx
0x180003258  mov     [rcx], rbx
0x18000325b  mov     rax, [rbx+10h]
0x18000325f  inc     dword ptr [rax+1Ch]
0x180003262  inc     dword ptr [rsi+14h]
0x180003265  mov     eax, [rsi+14h]
0x180003268  cmp     eax, [rsi+10h]
0x18000326b  jnb     loc_180003592
0x180003271  lea     rcx, [rsi+40h]; lpCriticalSection
0x180003275  call    cs:__imp_LeaveCriticalSection
0x18000327c  nop     dword ptr [rax+rax+00h]
0x180003281  lea     rcx, [rdi+120h]; lpCriticalSection
0x180003288  call    cs:__imp_EnterCriticalSection
0x18000328f  nop     dword ptr [rax+rax+00h]
0x180003294  mov     r14, [rsp+8B0h+var_18]
0x18000329c  mov     r12, [rsp+8A0h]
0x1800032a4  mov     rsi, [rsp+8B0h+arg_10]
0x1800032ac  mov     rbx, [rsp+8B0h+arg_0]
0x1800032b4  and     dword ptr [rdi+0FCh], 0FFFFFF7Fh
0x1800032be  cmp     [rdi+1B3h], r13b
0x1800032c5  jnz     loc_1800035A3
0x1800032cb  lea     rcx, [rdi+120h]; lpCriticalSection
0x1800032d2  call    cs:__imp_LeaveCriticalSection
0x1800032d9  nop     dword ptr [rax+rax+00h]
0x1800032de  mov     rcx, rdi
0x1800032e1  call    PostSendNotificationRequest
0x1800032e6  mov     eax, 0FFFFFFFFh
0x1800032eb  lock xadd [rdi+0D0h], eax
0x1800032f3  mov     r15, [rsp+8B0h+var_20]
0x1800032fb  cmp     eax, 1
0x1800032fe  jz      loc_1800035B5
0x180003304  test    cs:byte_18002E903, 10h
0x18000330b  mov     rdi, [rsp+8B0h+arg_18]
0x180003313  jnz     loc_1800035CD
0x180003319  mov     rcx, [rbp+7B0h+var_30]
0x180003320  xor     rcx, rsp; StackCookie
0x180003323  call    __security_check_cookie
0x180003328  add     rsp, 8A8h
0x18000332f  pop     r13
0x180003331  pop     rbp
0x180003332  retn
0x180003334  mov     rcx, cs:SstpSvcGlobals
0x18000333b  mov     qword ptr [rsp+8B0h+EntityChunks.DataChunkType], r13
0x180003340  mov     qword ptr [rsp+8B0h+EntityChunks.8+0Ch], r13
0x180003345  mov     qword ptr [rsp+8B0h+EntityChunks.8], r14
0x18000334a  mov     rcx, [rcx+0A8h]; pio
0x180003351  mov     dword ptr [rsp+8B0h+EntityChunks.8+8], eax
0x180003355  call    cs:__imp_StartThreadpoolIo
0x18000335c  nop     dword ptr [rax+rax+00h]
0x180003361  mov     rcx, cs:SstpSvcGlobals
0x180003368  lea     rax, [rsp+8B0h+EntityChunks]
0x18000336d  mov     rdx, [rdi+110h]; RequestId
0x180003374  mov     r9d, 1; EntityChunkCount
0x18000337a  mov     [rsp+8B0h+LogData], r13; LogData
0x18000337f  mov     r8d, 2; Flags
0x180003385  mov     [rsp+8B0h+Overlapped], rbx; Overlapped
0x18000338a  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000338e  mov     dword ptr [rsp+8B0h+lpOverlapped], r13d; Reserved2
0x180003393  mov     [rsp+8B0h+lpBytesReturned], r13; Reserved1
0x180003398  mov     qword ptr [rsp+8B0h+nOutBufferSize], r13; BytesSent
0x18000339d  mov     [rsp+8B0h+lpOutBuffer], rax; EntityChunks
0x1800033a2  call    cs:__imp_HttpSendResponseEntityBody
0x1800033a9  nop     dword ptr [rax+rax+00h]
0x1800033ae  mov     esi, eax
0x1800033b0  cmp     eax, 3E5h
0x1800033b5  jz      loc_18000320D
0x1800033bb  test    eax, eax
0x1800033bd  jz      loc_18000320D
0x1800033c3  mov     rcx, cs:SstpSvcGlobals
0x1800033ca  mov     r8b, 1
0x1800033cd  add     rcx, 1A8h
0x1800033d4  mov     rdx, rbx
0x1800033d7  call    FreeBufferToPool
0x1800033dc  mov     rcx, cs:SstpSvcGlobals
0x1800033e3  mov     rcx, [rcx+0A8h]; pio
0x1800033ea  call    cs:__imp_CancelThreadpoolIo
0x1800033f1  nop     dword ptr [rax+rax+00h]
0x1800033f6  test    cs:byte_18002E903, 8
0x1800033fd  jz      loc_180003281
0x180003403  lea     r8, [rdi+228h]
0x18000340a  mov     word ptr [rbp+7B0h+var_830], r13w
0x18000340f  mov     r9d, esi
0x180003412  mov     dword ptr [rsp+8B0h+lpOutBuffer], esi
0x180003416  lea     rdx, aCoidHsHttpsend; "CoId=%hs:HttpSendResponseEntityBody fai"...
0x18000341d  lea     rcx, [rbp+7B0h+var_830]
0x180003421  call    FormatRRASErrorString
0x180003426  test    cs:byte_18002E903, 8
0x18000342d  jz      loc_180003281
0x180003433  jmp     short loc_18000346B
0x180003435  test    cs:byte_18002E903, 8
0x18000343c  jz      loc_180003281
0x180003442  lea     r8, [rdi+228h]
0x180003449  mov     word ptr [rbp+7B0h+var_830], r13w
0x18000344e  lea     rdx, aCoidHsNotEnoug; "CoId=%hs:Not enough buffer pool memory "...
0x180003455  lea     rcx, [rbp+7B0h+var_830]
0x180003459  call    FormatRRASErrorString
0x18000345e  test    cs:byte_18002E903, 8
0x180003465  jz      loc_180003281
0x18000346b  lea     r8, [rbp+7B0h+var_830]
0x18000346f  lea     rdx, RasSSTPSvcTraceError
0x180003476  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000347d  call    McTemplateU0z_EventWriteTransfer
0x180003482  jmp     loc_180003281
0x180003487  call    cs:__imp_GetLastError
0x18000348e  nop     dword ptr [rax+rax+00h]
0x180003493  mov     r9d, eax
0x180003496  test    eax, eax
0x180003498  jz      loc_180003191
0x18000349e  test    cs:byte_18002E903, 8
0x1800034a5  jz      short loc_1800034E3
0x1800034a7  lea     r8, [rdi+228h]
0x1800034ae  mov     word ptr [rbp+7B0h+var_830], r13w
0x1800034b3  lea     rdx, aCoidHsSendtone; "CoId=%hs:SendToNetwork fails with error"...
0x1800034ba  lea     rcx, [rbp+7B0h+var_830]
0x1800034be  call    FormatRRASErrorString
0x1800034c3  test    cs:byte_18002E903, 8
0x1800034ca  jz      short loc_1800034E3
0x1800034cc  lea     r8, [rbp+7B0h+var_830]
0x1800034d0  lea     rdx, RasSSTPSvcTraceError
0x1800034d7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800034de  call    McTemplateU0z_EventWriteTransfer
0x1800034e3  mov     rcx, cs:SstpSvcGlobals
0x1800034ea  mov     r8b, 1
0x1800034ed  add     rcx, 1A8h
0x1800034f4  mov     rdx, rbx
0x1800034f7  call    FreeBufferToPool
0x1800034fc  jmp     loc_180003281
0x180003501  lea     r8, aSendtonetworkw; "SendToNetworkWorker"
0x180003508  mov     word ptr [rbp+7B0h+var_830], r13w
0x18000350d  lea     rdx, aEnteringWs; "Entering %ws"
0x180003514  lea     rcx, [rbp+7B0h+var_830]
0x180003518  call    FormatRRASErrorString
0x18000351d  test    cs:byte_18002E903, 10h
0x180003524  jz      loc_18000306A
0x18000352a  lea     r8, [rbp+7B0h+var_830]
0x18000352e  lea     rdx, RasSSTPSvcTraceInfo
0x180003535  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000353c  call    McTemplateU0z_EventWriteTransfer
0x180003541  jmp     loc_18000306A
0x180003546  lea     rcx, [rsi+1E8h]; lpCriticalSection
0x18000354d  call    cs:__imp_LeaveCriticalSection
0x180003554  nop     dword ptr [rax+rax+00h]
0x180003559  lea     rcx, [rsi+1A8h]
0x180003560  call    AddBufferBlockToPool
0x180003565  mov     rbx, rax
0x180003568  jmp     loc_180003137
0x18000356d  xor     r8d, r8d
0x180003570  mov     edx, esi
0x180003572  mov     rcx, rbx
0x180003575  call    SstpWebSendRequestEntityCompletion
0x18000357a  test    esi, esi
0x18000357c  jnz     loc_180003281
0x180003582  jmp     loc_18000320D
0x180003587  inc     cs:g_ulDoubleBufferFrees
0x18000358d  jmp     loc_180003271
0x180003592  mov     rcx, rsi
0x180003595  call    FreeUnusedBufferPoolBlocks
0x18000359a  mov     [rsi+14h], r13d
0x18000359e  jmp     loc_180003271
0x1800035a3  mov     edx, 2
0x1800035a8  mov     rcx, rdi
0x1800035ab  call    InitiateCallContextCleanup
0x1800035b0  jmp     loc_1800032E6
0x1800035b5  mov     rax, [rdi+0D8h]
0x1800035bc  lea     rcx, [rdi+0D0h]
0x1800035c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c8  jmp     loc_180003304
0x1800035cd  lea     r8, aSendtonetworkw; "SendToNetworkWorker"
0x1800035d4  mov     word ptr [rbp+7B0h+var_830], r13w
0x1800035d9  lea     rdx, aLeavingWs; "LEaving %ws"
0x1800035e0  lea     rcx, [rbp+7B0h+var_830]
0x1800035e4  call    FormatRRASErrorString
0x1800035e9  test    cs:byte_18002E903, 10h
0x1800035f0  jz      loc_180003319
0x1800035f6  lea     r8, [rbp+7B0h+var_830]
0x1800035fa  lea     rdx, RasSSTPSvcTraceInfo
0x180003601  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003608  call    McTemplateU0z_EventWriteTransfer
0x18000360d  jmp     loc_180003319
```

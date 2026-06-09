# SendToNetworkWorker

- ea: `0x180002e00`
- end: `0x1800033a3`
- name: `SendToNetworkWorker`
- size: `1443`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001160`
- `0x180002908`
- `0x180002d70`
- `0x180002e00`
- `0x1800033b0`
- `0x180006ef0`
- `0x1800077bc`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ff8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003044`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ff8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003044`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003224`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002f55`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002f55`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000318d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000318d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180003104`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180003104`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000314b`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000314b`
- `webio!__imp_WebSendHttpRequestEntity` at `0x180002fc2`
- `webio!__imp_WebSendHttpRequestEntity` at `0x180002fc2`

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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Entering %ws", L"SendToNetworkWorker");
    if ( (byte_18002D803 & 0x10) != 0 )
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
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_17;
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v27,
        L"CoId=%hs:Not enough buffer pool memory to process receive.Deferring...",
        Context + 552);
      if ( (byte_18002D803 & 8) == 0 )
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
        if ( (byte_18002D803 & 8) != 0 )
        {
          LOWORD(v27) = 0;
          FormatRRASErrorString(&v27, L"CoId=%hs:SendToNetwork fails with error %d", Context + 552, LastError);
          if ( (byte_18002D803 & 8) != 0 )
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
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_17;
      LOWORD(v27) = 0;
      LODWORD(lpOutBuffer) = v21;
      FormatRRASErrorString(
        &v27,
        L"CoId=%hs:HttpSendResponseEntityBody fails with error %d [%d]",
        Context + 552,
        v21,
        lpOutBuffer);
      if ( (byte_18002D803 & 8) == 0 )
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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"LEaving %ws", L"SendToNetworkWorker");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v27);
  }
}

```

## disassembly

```asm
0x180002e00  mov     r11, rsp
0x180002e03  push    rbp
0x180002e04  push    r13
0x180002e06  lea     rbp, [r11-7B8h]
0x180002e0d  sub     rsp, 8A8h
0x180002e14  mov     rax, cs:__security_cookie
0x180002e1b  xor     rax, rsp
0x180002e1e  mov     [rbp+7B0h+var_30], rax
0x180002e25  mov     [r11+20h], rdi
0x180002e29  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180002e2d  mov     rdi, rdx
0x180002e30  mov     [r11-28h], r15
0x180002e34  xor     r13d, r13d
0x180002e37  xor     edx, edx; Val
0x180002e39  mov     r8d, 7FCh; Size
0x180002e3f  mov     dword ptr [rsp+8B0h+InBuffer], r13d
0x180002e44  mov     [rbp+7B0h+var_830], r13d
0x180002e48  call    memset_0
0x180002e4d  test    cs:byte_18002D803, 10h
0x180002e54  jnz     loc_180003298
0x180002e5a  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002e61  call    cs:__imp_EnterCriticalSection
0x180002e67  or      dword ptr [rdi+0FCh], 80h
0x180002e71  cmp     [rdi+1B3h], r13b
0x180002e78  jnz     loc_18000306A
0x180002e7e  mov     [rsp+8B0h+arg_0], rbx
0x180002e86  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002e8d  mov     [rsp+8B0h+arg_10], rsi
0x180002e95  mov     [rsp+8A0h], r12
0x180002e9d  mov     r12d, 14h
0x180002ea3  mov     [rsp+8B0h+var_18], r14
0x180002eab  call    cs:__imp_LeaveCriticalSection
0x180002eb1  mov     eax, [rdi+0F0h]
0x180002eb7  mov     dword ptr [rsp+8B0h+InBuffer], eax
0x180002ebb  mov     rsi, cs:SstpSvcGlobals
0x180002ec2  lea     rcx, [rsi+1E8h]; lpCriticalSection
0x180002ec9  call    cs:__imp_EnterCriticalSection
0x180002ecf  lea     rax, [rsi+1D0h]
0x180002ed6  mov     rbx, [rax]
0x180002ed9  cmp     rbx, rax
0x180002edc  jz      loc_1800032DD
0x180002ee2  mov     rax, [rbx+8]
0x180002ee6  mov     rcx, [rbx]
0x180002ee9  mov     [rax], rcx
0x180002eec  mov     [rcx+8], rax
0x180002ef0  lea     rcx, [rsi+1E8h]; lpCriticalSection
0x180002ef7  mov     rax, [rbx+10h]
0x180002efb  mov     [rbx+8], rbx
0x180002eff  mov     [rbx], rbx
0x180002f02  dec     dword ptr [rax+1Ch]
0x180002f05  call    cs:__imp_LeaveCriticalSection
0x180002f0b  add     rbx, 18h
0x180002f0f  test    rbx, rbx
0x180002f12  jz      loc_1800031D2
0x180002f18  mov     rcx, cs:SstpSvcGlobals
0x180002f1f  lea     rsi, [rbx+5Ch]
0x180002f23  mov     [rsp+8B0h+lpOverlapped], r13; lpOverlapped
0x180002f28  lea     r14, [rbx+60h]
0x180002f2c  mov     [rsp+8B0h+lpBytesReturned], rsi; lpBytesReturned
0x180002f31  lea     r8, [rsp+8B0h+InBuffer]; lpInBuffer
0x180002f36  mov     [rsp+8B0h+nOutBufferSize], 4000h; nOutBufferSize
0x180002f3e  mov     r9d, 4; nInBufferSize
0x180002f44  mov     rcx, [rcx+118h]; hDevice
0x180002f4b  mov     edx, 128026h; dwIoControlCode
0x180002f50  mov     [rsp+8B0h+lpOutBuffer], r14; lpOutBuffer
0x180002f55  call    cs:__imp_DeviceIoControl
0x180002f5b  test    eax, eax
0x180002f5d  jz      loc_180003224
0x180002f63  cmp     [rsi], r13d
0x180002f66  jbe     short loc_180002FE2
0x180002f68  mov     dword ptr [rbx+20h], 4572h
0x180002f6f  xorps   xmm0, xmm0
0x180002f72  movups  xmmword ptr [rbx], xmm0
0x180002f75  movups  xmmword ptr [rbx+10h], xmm0
0x180002f79  mov     eax, [rsi]
0x180002f7b  cmp     [rdi+0F8h], r13b
0x180002f82  jz      loc_1800030E3
0x180002f88  lea     r8, [rbx+40h]
0x180002f8c  mov     [rbx+48h], r14
0x180002f90  mov     [r8], r13d
0x180002f93  mov     [rbx+50h], rax
0x180002f97  lock inc dword ptr [rdi+0D0h]
0x180002f9e  mov     [rbx+38h], rdi
0x180002fa2  lea     rax, SstpWebSendRequestEntityCompletion
0x180002fa9  mov     rcx, [rdi+1C0h]
0x180002fb0  xor     edx, edx
0x180002fb2  mov     qword ptr [rsp+8B0h+nOutBufferSize], rbx
0x180002fb7  mov     r9d, 1
0x180002fbd  mov     [rsp+8B0h+lpOutBuffer], rax
0x180002fc2  call    cs:__imp_WebSendHttpRequestEntity
0x180002fc8  mov     esi, eax
0x180002fca  cmp     eax, 3E5h
0x180002fcf  jnz     loc_1800032FE
0x180002fd5  test    r12d, r12d
0x180002fd8  jz      short loc_18000303D
0x180002fda  dec     r12d
0x180002fdd  jmp     loc_180002EBB
0x180002fe2  mov     rsi, cs:SstpSvcGlobals
0x180002fe9  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180002fed  add     rsi, 1A8h
0x180002ff4  lea     rcx, [rsi+40h]; lpCriticalSection
0x180002ff8  call    cs:__imp_EnterCriticalSection
0x180002ffe  cmp     [rbx], rbx
0x180003001  jnz     loc_180003318
0x180003007  mov     rax, [rsi+28h]
0x18000300b  lea     rcx, [rsi+28h]
0x18000300f  mov     [rbx], rax
0x180003012  mov     [rbx+8], rcx
0x180003016  mov     [rax+8], rbx
0x18000301a  mov     [rcx], rbx
0x18000301d  mov     rax, [rbx+10h]
0x180003021  inc     dword ptr [rax+1Ch]
0x180003024  inc     dword ptr [rsi+14h]
0x180003027  mov     eax, [rsi+14h]
0x18000302a  cmp     eax, [rsi+10h]
0x18000302d  jnb     loc_180003323
0x180003033  lea     rcx, [rsi+40h]; lpCriticalSection
0x180003037  call    cs:__imp_LeaveCriticalSection
0x18000303d  lea     rcx, [rdi+120h]; lpCriticalSection
0x180003044  call    cs:__imp_EnterCriticalSection
0x18000304a  mov     r14, [rsp+8B0h+var_18]
0x180003052  mov     r12, [rsp+8A0h]
0x18000305a  mov     rsi, [rsp+8B0h+arg_10]
0x180003062  mov     rbx, [rsp+8B0h+arg_0]
0x18000306a  and     dword ptr [rdi+0FCh], 0FFFFFF7Fh
0x180003074  cmp     [rdi+1B3h], r13b
0x18000307b  jnz     loc_180003334
0x180003081  lea     rcx, [rdi+120h]; lpCriticalSection
0x180003088  call    cs:__imp_LeaveCriticalSection
0x18000308e  mov     rcx, rdi
0x180003091  call    PostSendNotificationRequest
0x180003096  mov     eax, 0FFFFFFFFh
0x18000309b  lock xadd [rdi+0D0h], eax
0x1800030a3  mov     r15, [rsp+8B0h+var_20]
0x1800030ab  cmp     eax, 1
0x1800030ae  jz      loc_180003346
0x1800030b4  test    cs:byte_18002D803, 10h
0x1800030bb  mov     rdi, [rsp+8B0h+arg_18]
0x1800030c3  jnz     loc_18000335E
0x1800030c9  mov     rcx, [rbp+7B0h+var_30]
0x1800030d0  xor     rcx, rsp; StackCookie
0x1800030d3  call    __security_check_cookie
0x1800030d8  add     rsp, 8A8h
0x1800030df  pop     r13
0x1800030e1  pop     rbp
0x1800030e2  retn
0x1800030e3  mov     rcx, cs:SstpSvcGlobals
0x1800030ea  mov     qword ptr [rsp+8B0h+EntityChunks.DataChunkType], r13
0x1800030ef  mov     qword ptr [rsp+8B0h+EntityChunks.8+0Ch], r13
0x1800030f4  mov     qword ptr [rsp+8B0h+EntityChunks.8], r14
0x1800030f9  mov     rcx, [rcx+0A8h]; pio
0x180003100  mov     dword ptr [rsp+8B0h+EntityChunks.8+8], eax
0x180003104  call    cs:__imp_StartThreadpoolIo
0x18000310a  mov     rcx, cs:SstpSvcGlobals
0x180003111  lea     rax, [rsp+8B0h+EntityChunks]
0x180003116  mov     rdx, [rdi+110h]; RequestId
0x18000311d  mov     r9d, 1; EntityChunkCount
0x180003123  mov     [rsp+8B0h+LogData], r13; LogData
0x180003128  mov     r8d, 2; Flags
0x18000312e  mov     [rsp+8B0h+Overlapped], rbx; Overlapped
0x180003133  mov     rcx, [rcx+40h]; RequestQueueHandle
0x180003137  mov     dword ptr [rsp+8B0h+lpOverlapped], r13d; Reserved2
0x18000313c  mov     [rsp+8B0h+lpBytesReturned], r13; Reserved1
0x180003141  mov     qword ptr [rsp+8B0h+nOutBufferSize], r13; BytesSent
0x180003146  mov     [rsp+8B0h+lpOutBuffer], rax; EntityChunks
0x18000314b  call    cs:__imp_HttpSendResponseEntityBody
0x180003151  mov     esi, eax
0x180003153  cmp     eax, 3E5h
0x180003158  jz      loc_180002FD5
0x18000315e  test    eax, eax
0x180003160  jz      loc_180002FD5
0x180003166  mov     rcx, cs:SstpSvcGlobals
0x18000316d  mov     r8b, 1
0x180003170  add     rcx, 1A8h
0x180003177  mov     rdx, rbx
0x18000317a  call    FreeBufferToPool
0x18000317f  mov     rcx, cs:SstpSvcGlobals
0x180003186  mov     rcx, [rcx+0A8h]; pio
0x18000318d  call    cs:__imp_CancelThreadpoolIo
0x180003193  test    cs:byte_18002D803, 8
0x18000319a  jz      loc_18000303D
0x1800031a0  lea     r8, [rdi+228h]
0x1800031a7  mov     word ptr [rbp+7B0h+var_830], r13w
0x1800031ac  mov     r9d, esi
0x1800031af  mov     dword ptr [rsp+8B0h+lpOutBuffer], esi
0x1800031b3  lea     rdx, aCoidHsHttpsend; "CoId=%hs:HttpSendResponseEntityBody fai"...
0x1800031ba  lea     rcx, [rbp+7B0h+var_830]
0x1800031be  call    FormatRRASErrorString
0x1800031c3  test    cs:byte_18002D803, 8
0x1800031ca  jz      loc_18000303D
0x1800031d0  jmp     short loc_180003208
0x1800031d2  test    cs:byte_18002D803, 8
0x1800031d9  jz      loc_18000303D
0x1800031df  lea     r8, [rdi+228h]
0x1800031e6  mov     word ptr [rbp+7B0h+var_830], r13w
0x1800031eb  lea     rdx, aCoidHsNotEnoug; "CoId=%hs:Not enough buffer pool memory "...
0x1800031f2  lea     rcx, [rbp+7B0h+var_830]
0x1800031f6  call    FormatRRASErrorString
0x1800031fb  test    cs:byte_18002D803, 8
0x180003202  jz      loc_18000303D
0x180003208  lea     r8, [rbp+7B0h+var_830]
0x18000320c  lea     rdx, RasSSTPSvcTraceError
0x180003213  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000321a  call    McTemplateU0z_EventWriteTransfer
0x18000321f  jmp     loc_18000303D
0x180003224  call    cs:__imp_GetLastError
0x18000322a  mov     r9d, eax
0x18000322d  test    eax, eax
0x18000322f  jz      loc_180002F63
0x180003235  test    cs:byte_18002D803, 8
0x18000323c  jz      short loc_18000327A
0x18000323e  lea     r8, [rdi+228h]
0x180003245  mov     word ptr [rbp+7B0h+var_830], r13w
0x18000324a  lea     rdx, aCoidHsSendtone; "CoId=%hs:SendToNetwork fails with error"...
0x180003251  lea     rcx, [rbp+7B0h+var_830]
0x180003255  call    FormatRRASErrorString
0x18000325a  test    cs:byte_18002D803, 8
0x180003261  jz      short loc_18000327A
0x180003263  lea     r8, [rbp+7B0h+var_830]
0x180003267  lea     rdx, RasSSTPSvcTraceError
0x18000326e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003275  call    McTemplateU0z_EventWriteTransfer
0x18000327a  mov     rcx, cs:SstpSvcGlobals
0x180003281  mov     r8b, 1
0x180003284  add     rcx, 1A8h
0x18000328b  mov     rdx, rbx
0x18000328e  call    FreeBufferToPool
0x180003293  jmp     loc_18000303D
0x180003298  lea     r8, aSendtonetworkw; "SendToNetworkWorker"
0x18000329f  mov     word ptr [rbp+7B0h+var_830], r13w
0x1800032a4  lea     rdx, aEnteringWs; "Entering %ws"
0x1800032ab  lea     rcx, [rbp+7B0h+var_830]
0x1800032af  call    FormatRRASErrorString
0x1800032b4  test    cs:byte_18002D803, 10h
0x1800032bb  jz      loc_180002E5A
0x1800032c1  lea     r8, [rbp+7B0h+var_830]
0x1800032c5  lea     rdx, RasSSTPSvcTraceInfo
0x1800032cc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800032d3  call    McTemplateU0z_EventWriteTransfer
0x1800032d8  jmp     loc_180002E5A
0x1800032dd  lea     rcx, [rsi+1E8h]; lpCriticalSection
0x1800032e4  call    cs:__imp_LeaveCriticalSection
0x1800032ea  lea     rcx, [rsi+1A8h]
0x1800032f1  call    AddBufferBlockToPool
0x1800032f6  mov     rbx, rax
0x1800032f9  jmp     loc_180002F0F
0x1800032fe  xor     r8d, r8d
0x180003301  mov     edx, esi
0x180003303  mov     rcx, rbx
0x180003306  call    SstpWebSendRequestEntityCompletion
0x18000330b  test    esi, esi
0x18000330d  jnz     loc_18000303D
0x180003313  jmp     loc_180002FD5
0x180003318  inc     cs:g_ulDoubleBufferFrees
0x18000331e  jmp     loc_180003033
0x180003323  mov     rcx, rsi
0x180003326  call    FreeUnusedBufferPoolBlocks
0x18000332b  mov     [rsi+14h], r13d
0x18000332f  jmp     loc_180003033
0x180003334  mov     edx, 2
0x180003339  mov     rcx, rdi
0x18000333c  call    InitiateCallContextCleanup
0x180003341  jmp     loc_180003096
0x180003346  mov     rax, [rdi+0D8h]
0x18000334d  lea     rcx, [rdi+0D0h]
0x180003354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003359  jmp     loc_1800030B4
0x18000335e  lea     r8, aSendtonetworkw; "SendToNetworkWorker"
0x180003365  mov     word ptr [rbp+7B0h+var_830], r13w
0x18000336a  lea     rdx, aLeavingWs; "LEaving %ws"
0x180003371  lea     rcx, [rbp+7B0h+var_830]
0x180003375  call    FormatRRASErrorString
0x18000337a  test    cs:byte_18002D803, 10h
0x180003381  jz      loc_1800030C9
0x180003387  lea     r8, [rbp+7B0h+var_830]
0x18000338b  lea     rdx, RasSSTPSvcTraceInfo
0x180003392  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003399  call    McTemplateU0z_EventWriteTransfer
0x18000339e  jmp     loc_1800030C9
```

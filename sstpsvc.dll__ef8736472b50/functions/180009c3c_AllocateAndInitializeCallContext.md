# AllocateAndInitializeCallContext

- ea: `0x180009c3c`
- end: `0x18000a2ee`
- name: `AllocateAndInitializeCallContext`
- size: `1714`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000530c`
- `0x18000a710`
- `0x18000c768`

## callees

- `0x180002f80`
- `0x1800048c0`
- `0x1800089dc`
- `0x180008b90`
- `0x180009c3c`
- `0x180015b6c`
- `0x180015b9c`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a23b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a23b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a29a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a29a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a2b4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a203`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a203`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009db4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fa8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009e7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009e7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f8e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a1a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a1c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a1a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a1c4`

## pseudocode

```c
__int64 __fastcall AllocateAndInitializeCallContext(char a1, __int64 *a2)
{
  char *v4; // rcx
  __int64 BufferFromPool; // rax
  __int64 v6; // rbx
  DWORD v7; // esi
  _QWORD *v8; // r12
  DWORD LastError; // eax
  __int64 v10; // r8
  _QWORD *v11; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  PTP_WORK ThreadpoolWork; // rax
  PTP_WORK v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  char *v16; // rcx
  int v17; // eax
  char *v18; // rcx
  _QWORD *v19; // rax
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  char v24[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v4 = (char *)SstpSvcGlobals + 536;
  *a2 = 0;
  BufferFromPool = GetBufferFromPool(v4);
  v6 = BufferFromPool;
  if ( !BufferFromPool )
  {
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceError,
        L"TpCallCtxPool: Alloc failed for initrequest fails");
    return 8;
  }
  if ( (byte_18002E903 & 8) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Allocating Call context 0x%p", BufferFromPool);
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
  }
  memset_0((void *)v6, 0, 0x278u);
  *(_DWORD *)(v6 + 32) = 17767;
  *(_QWORD *)(v6 + 216) = CleanupCallCtx;
  v8 = (_QWORD *)(v6 + 224);
  *(_QWORD *)(v6 + 240) = 0;
  *(_QWORD *)(v6 + 272) = 0;
  *(_QWORD *)(v6 + 280) = 0;
  *(_BYTE *)(v6 + 432) = 0;
  *(_QWORD *)(v6 + 624) = 0;
  *(_QWORD *)(v6 + 232) = v6 + 224;
  *(_QWORD *)(v6 + 224) = v6 + 224;
  *(_QWORD *)(v6 + 424) = v6 + 416;
  *(_QWORD *)(v6 + 416) = v6 + 416;
  *(_BYTE *)(v6 + 248) = a1;
  *(_QWORD *)(v6 + 612) = 1;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v6 + 288), 0xFA0u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Error initializing callctx critsec [%d]", LastError);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_42;
  }
  v11 = SstpSvcGlobals;
  *(_DWORD *)(v6 + 344) = 3;
  *(_QWORD *)(v6 + 352) = 0;
  *(_QWORD *)(v6 + 360) = 0;
  *(_QWORD *)(v6 + 368) = 0;
  *(_QWORD *)(v6 + 376) = 0;
  *(_QWORD *)(v6 + 384) = 0;
  *(_QWORD *)(v6 + 392) = 0;
  *(_DWORD *)(v6 + 400) = 0;
  *(_DWORD *)(v6 + 404) = 1;
  *(_DWORD *)(v6 + 408) = 72;
  *(_QWORD *)(v6 + 352) = v11[20];
  if ( a1 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ResponseWaitTimeout, (PVOID)v6, (PTP_CALLBACK_ENVIRON)(v6 + 344));
    *(_QWORD *)(v6 + 456) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      v7 = GetLastError();
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v23, L"Error allocating response wait timeout [%d]", v7);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
      }
LABEL_41:
      DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
LABEL_42:
      LOBYTE(v10) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 536, v6, v10);
      return v7;
    }
  }
  *(_OWORD *)(v6 + 40) = 0;
  *(_OWORD *)(v6 + 56) = 0;
  *(_QWORD *)(v6 + 72) = 0;
  *(_DWORD *)(v6 + 72) = 17770;
  ThreadpoolWork = CreateThreadpoolWork(SendToNetworkWorker, (PVOID)v6, (PTP_CALLBACK_ENVIRON)(v6 + 344));
  *(_QWORD *)(v6 + 328) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    v7 = GetLastError();
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Unable to allocate send work item: %d", v7);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_39;
  }
  v14 = CreateThreadpoolWork(ProcessReceivedBytesWorker, (PVOID)v6, (PTP_CALLBACK_ENVIRON)(v6 + 344));
  *(_QWORD *)(v6 + 336) = v14;
  if ( !v14 )
  {
    v7 = GetLastError();
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Unable to allocate process received bytes work item: %d", v7);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_38;
  }
  *(_DWORD *)(v6 + 160) = 17771;
  *(_OWORD *)(v6 + 128) = 0;
  *(_OWORD *)(v6 + 144) = 0;
  *(_DWORD *)(v6 + 112) = 17777;
  *(_OWORD *)(v6 + 80) = 0;
  *(_OWORD *)(v6 + 96) = 0;
  *(_DWORD *)(v6 + 72) = 17770;
  *(_OWORD *)(v6 + 40) = 0;
  *(_OWORD *)(v6 + 56) = 0;
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Setting %p callcontext->SendOverlapPosted to %ws", v6, L"FALSE");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v23);
  }
  v15 = (struct _RTL_CRITICAL_SECTION *)((char *)SstpSvcGlobals + 184);
  *(_QWORD *)(v6 + 256) = 0;
  *(_WORD *)(v6 + 264) = 0;
  *(_BYTE *)(v6 + 434) = 0;
  EnterCriticalSection(v15);
  v16 = (char *)SstpSvcGlobals;
  if ( *((_QWORD *)SstpSvcGlobals + 22) )
  {
    v17 = assign_HF_handle(*((_QWORD *)SstpSvcGlobals + 22), v6);
    v16 = (char *)SstpSvcGlobals;
    *(_DWORD *)(v6 + 244) = v17;
    v7 = v17 == 0 ? 8 : 0;
  }
  else
  {
    v7 = 87;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 184));
  if ( v7 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Unable to get the handle32 for the request: %d", v7);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
    }
    goto LABEL_37;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
  if ( *(_DWORD *)SstpSvcGlobals == 3 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
    v7 = 995;
    HfFreeHandle32(*((_QWORD *)SstpSvcGlobals + 22), v6 + 244);
LABEL_37:
    CloseThreadpoolWork(*(PTP_WORK *)(v6 + 336));
    *(_QWORD *)(v6 + 336) = 0;
LABEL_38:
    CloseThreadpoolWork(*(PTP_WORK *)(v6 + 328));
    *(_QWORD *)(v6 + 328) = 0;
LABEL_39:
    if ( a1 )
    {
      CloseThreadpoolTimer(*(PTP_TIMER *)(v6 + 456));
      *(_QWORD *)(v6 + 456) = 0;
    }
    goto LABEL_41;
  }
  *(_QWORD *)(v6 + 232) = v8;
  *v8 = v8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
  *(_DWORD *)(v6 + 252) = 1;
  if ( *(_BYTE *)(v6 + 248) )
  {
    *(_QWORD *)(v6 + 440) = 0;
    *(_QWORD *)(v6 + 448) = 0;
    *(_DWORD *)(v6 + 252) = 65537;
  }
  v18 = (char *)SstpSvcGlobals + 264;
  v19 = (_QWORD *)*((_QWORD *)SstpSvcGlobals + 34);
  *v8 = (char *)SstpSvcGlobals + 264;
  *(_QWORD *)(v6 + 232) = v19;
  *v19 = v8;
  *((_QWORD *)v18 + 1) = v8;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
  *a2 = v6;
  return v7;
}

```

## disassembly

```asm
0x180009c3c  push    rbp
0x180009c3e  push    rbx
0x180009c3f  push    rsi
0x180009c40  push    rdi
0x180009c41  push    r12
0x180009c43  push    r13
0x180009c45  push    r14
0x180009c47  push    r15
0x180009c49  lea     rbp, [rsp-748h]
0x180009c51  sub     rsp, 848h
0x180009c58  mov     rax, cs:__security_cookie
0x180009c5f  xor     rax, rsp
0x180009c62  mov     [rbp+780h+var_50], rax
0x180009c69  mov     rbx, rdx
0x180009c6c  mov     [rsp+880h+var_858], rdx
0x180009c71  mov     sil, cl
0x180009c74  mov     [rsp+880h+var_860], cl
0x180009c78  xor     r13d, r13d
0x180009c7b  lea     rcx, [rsp+880h+var_84C]; void *
0x180009c80  xor     edx, edx; Val
0x180009c82  mov     [rsp+880h+var_850], r13d
0x180009c87  mov     r8d, 7FCh; Size
0x180009c8d  call    memset_0
0x180009c92  mov     rcx, cs:SstpSvcGlobals
0x180009c99  add     rcx, 218h
0x180009ca0  mov     [rbx], r13
0x180009ca3  call    GetBufferFromPool
0x180009ca8  lea     edi, [r13+8]
0x180009cac  mov     rbx, rax
0x180009caf  test    rax, rax
0x180009cb2  jnz     short loc_180009CDE
0x180009cb4  test    cs:byte_18002E903, dil
0x180009cbb  jz      short loc_180009CD7
0x180009cbd  lea     r8, aTpcallctxpoolA; "TpCallCtxPool: Alloc failed for initreq"...
0x180009cc4  lea     rdx, RasSSTPSvcTraceError
0x180009ccb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009cd2  call    McTemplateU0z_EventWriteTransfer
0x180009cd7  mov     esi, edi
0x180009cd9  jmp     loc_18000A2C8
0x180009cde  test    cs:byte_18002E903, dil
0x180009ce5  lea     r15, RasSSTPSvcTraceError
0x180009cec  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009cf3  jz      short loc_180009D28
0x180009cf5  mov     r8, rbx
0x180009cf8  mov     word ptr [rsp+880h+var_850], r13w
0x180009cfe  lea     rdx, aAllocatingCall; "Allocating Call context 0x%p"
0x180009d05  lea     rcx, [rsp+880h+var_850]
0x180009d0a  call    FormatRRASErrorString
0x180009d0f  test    cs:byte_18002E903, dil
0x180009d16  jz      short loc_180009D28
0x180009d18  lea     r8, [rsp+880h+var_850]
0x180009d1d  mov     rdx, r15
0x180009d20  mov     rcx, r14
0x180009d23  call    McTemplateU0z_EventWriteTransfer
0x180009d28  xor     edx, edx; Val
0x180009d2a  mov     r8d, 278h; Size
0x180009d30  mov     rcx, rbx; void *
0x180009d33  call    memset_0
0x180009d38  lea     rax, CleanupCallCtx
0x180009d3f  mov     dword ptr [rbx+20h], 4567h
0x180009d46  mov     [rbx+0D8h], rax
0x180009d4d  lea     r12, [rbx+0E0h]
0x180009d54  lea     rax, [rbx+1A0h]
0x180009d5b  mov     [rbx+0F0h], r13
0x180009d62  mov     [rbx+110h], r13
0x180009d69  mov     edx, 0FA0h; dwSpinCount
0x180009d6e  mov     [rbx+118h], r13
0x180009d75  mov     [rbx+1B0h], r13b
0x180009d7c  mov     [rbx+270h], r13
0x180009d83  lea     r13, [rbx+120h]
0x180009d8a  mov     rcx, r13; lpCriticalSection
0x180009d8d  mov     [rbx+0E8h], r12
0x180009d94  mov     [r12], r12
0x180009d98  mov     [rbx+1A8h], rax
0x180009d9f  mov     [rax], rax
0x180009da2  mov     [rbx+0F8h], sil
0x180009da9  mov     qword ptr [rbx+264h], 1
0x180009db4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180009dbb  nop     dword ptr [rax+rax+00h]
0x180009dc0  xor     edx, edx
0x180009dc2  test    eax, eax
0x180009dc4  jnz     short loc_180009E1E
0x180009dc6  call    cs:__imp_GetLastError
0x180009dcd  nop     dword ptr [rax+rax+00h]
0x180009dd2  test    cs:byte_18002E903, dil
0x180009dd9  mov     esi, eax
0x180009ddb  jz      loc_18000A20F
0x180009de1  xor     ecx, ecx
0x180009de3  lea     rdx, aErrorInitializ; "Error initializing callctx critsec [%d]"
0x180009dea  mov     word ptr [rsp+880h+var_850], cx
0x180009def  mov     r8d, eax
0x180009df2  lea     rcx, [rsp+880h+var_850]
0x180009df7  call    FormatRRASErrorString
0x180009dfc  test    cs:byte_18002E903, dil
0x180009e03  jz      loc_18000A20F
0x180009e09  lea     r8, [rsp+880h+var_850]
0x180009e0e  mov     rdx, r15
0x180009e11  mov     rcx, r14
0x180009e14  call    McTemplateU0z_EventWriteTransfer
0x180009e19  jmp     loc_18000A20F
0x180009e1e  lea     rsi, [rbx+158h]
0x180009e25  mov     rax, cs:SstpSvcGlobals
0x180009e2c  mov     dword ptr [rsi], 3
0x180009e32  mov     [rsi+8], rdx
0x180009e36  mov     [rsi+10h], rdx
0x180009e3a  mov     [rsi+18h], rdx
0x180009e3e  mov     [rsi+20h], rdx
0x180009e42  mov     [rsi+28h], rdx
0x180009e46  mov     [rsi+30h], rdx
0x180009e4a  mov     [rsi+38h], edx
0x180009e4d  mov     dword ptr [rsi+3Ch], 1
0x180009e54  mov     dword ptr [rsi+40h], 48h ; 'H'
0x180009e5b  mov     rcx, [rax+0A0h]
0x180009e62  mov     [rbx+160h], rcx
0x180009e69  cmp     [rsp+880h+var_860], dl
0x180009e6d  jz      short loc_180009EEC
0x180009e6f  mov     r8, rsi; pcbe
0x180009e72  lea     rcx, ResponseWaitTimeout; pfnti
0x180009e79  mov     rdx, rbx; pv
0x180009e7c  call    cs:__imp_CreateThreadpoolTimer
0x180009e83  nop     dword ptr [rax+rax+00h]
0x180009e88  mov     [rbx+1C8h], rax
0x180009e8f  test    rax, rax
0x180009e92  jnz     short loc_180009EEC
0x180009e94  call    cs:__imp_GetLastError
0x180009e9b  nop     dword ptr [rax+rax+00h]
0x180009ea0  test    cs:byte_18002E903, dil
0x180009ea7  mov     esi, eax
0x180009ea9  jz      loc_18000A200
0x180009eaf  xor     eax, eax
0x180009eb1  lea     rdx, aErrorAllocatin; "Error allocating response wait timeout "...
0x180009eb8  mov     r8d, esi
0x180009ebb  mov     word ptr [rsp+880h+var_850], ax
0x180009ec0  lea     rcx, [rsp+880h+var_850]
0x180009ec5  call    FormatRRASErrorString
0x180009eca  test    cs:byte_18002E903, dil
0x180009ed1  jz      loc_18000A200
0x180009ed7  lea     r8, [rsp+880h+var_850]
0x180009edc  mov     rdx, r15
0x180009edf  mov     rcx, r14
0x180009ee2  call    McTemplateU0z_EventWriteTransfer
0x180009ee7  jmp     loc_18000A200
0x180009eec  xorps   xmm0, xmm0
0x180009eef  lea     rcx, SendToNetworkWorker; pfnwk
0x180009ef6  movups  xmmword ptr [rbx+28h], xmm0
0x180009efa  xor     eax, eax
0x180009efc  mov     r8, rsi; pcbe
0x180009eff  movups  xmmword ptr [rbx+38h], xmm0
0x180009f03  mov     [rbx+48h], rax
0x180009f07  mov     rdx, rbx; pv
0x180009f0a  mov     dword ptr [rbx+48h], 456Ah
0x180009f11  call    cs:__imp_CreateThreadpoolWork
0x180009f18  nop     dword ptr [rax+rax+00h]
0x180009f1d  mov     [rbx+148h], rax
0x180009f24  test    rax, rax
0x180009f27  jnz     short loc_180009F81
0x180009f29  call    cs:__imp_GetLastError
0x180009f30  nop     dword ptr [rax+rax+00h]
0x180009f35  test    cs:byte_18002E903, dil
0x180009f3c  mov     esi, eax
0x180009f3e  jz      loc_18000A1DB
0x180009f44  xor     eax, eax
0x180009f46  lea     rdx, aUnableToAlloca; "Unable to allocate send work item: %d"
0x180009f4d  mov     r8d, esi
0x180009f50  mov     word ptr [rsp+880h+var_850], ax
0x180009f55  lea     rcx, [rsp+880h+var_850]
0x180009f5a  call    FormatRRASErrorString
0x180009f5f  test    cs:byte_18002E903, dil
0x180009f66  jz      loc_18000A1DB
0x180009f6c  lea     r8, [rsp+880h+var_850]
0x180009f71  mov     rdx, r15
0x180009f74  mov     rcx, r14
0x180009f77  call    McTemplateU0z_EventWriteTransfer
0x180009f7c  jmp     loc_18000A1DB
0x180009f81  mov     r8, rsi; pcbe
0x180009f84  lea     rcx, ProcessReceivedBytesWorker; pfnwk
0x180009f8b  mov     rdx, rbx; pv
0x180009f8e  call    cs:__imp_CreateThreadpoolWork
0x180009f95  nop     dword ptr [rax+rax+00h]
0x180009f9a  xor     esi, esi
0x180009f9c  mov     [rbx+150h], rax
0x180009fa3  test    rax, rax
0x180009fa6  jnz     short loc_18000A000
0x180009fa8  call    cs:__imp_GetLastError
0x180009faf  nop     dword ptr [rax+rax+00h]
0x180009fb4  test    cs:byte_18002E903, dil
0x180009fbb  mov     esi, eax
0x180009fbd  jz      loc_18000A1BD
0x180009fc3  xor     eax, eax
0x180009fc5  lea     rdx, aUnableToAlloca_0; "Unable to allocate process received byt"...
0x180009fcc  mov     r8d, esi
0x180009fcf  mov     word ptr [rsp+880h+var_850], ax
0x180009fd4  lea     rcx, [rsp+880h+var_850]
0x180009fd9  call    FormatRRASErrorString
0x180009fde  test    cs:byte_18002E903, dil
0x180009fe5  jz      loc_18000A1BD
0x180009feb  lea     r8, [rsp+880h+var_850]
0x180009ff0  mov     rdx, r15
0x180009ff3  mov     rcx, r14
0x180009ff6  call    McTemplateU0z_EventWriteTransfer
0x180009ffb  jmp     loc_18000A1BD
0x18000a000  mov     dword ptr [rbx+0A0h], 456Bh
0x18000a00a  xorps   xmm0, xmm0
0x18000a00d  movups  xmmword ptr [rbx+80h], xmm0
0x18000a014  movups  xmmword ptr [rbx+90h], xmm0
0x18000a01b  mov     dword ptr [rbx+70h], 4571h
0x18000a022  xorps   xmm1, xmm1
0x18000a025  movups  xmmword ptr [rbx+50h], xmm0
0x18000a029  movups  xmmword ptr [rbx+60h], xmm0
0x18000a02d  mov     dword ptr [rbx+48h], 456Ah
0x18000a034  movups  xmmword ptr [rbx+28h], xmm1
0x18000a038  movups  xmmword ptr [rbx+38h], xmm1
0x18000a03c  test    cs:byte_18002E903, 10h
0x18000a043  jz      short loc_18000A082
0x18000a045  lea     r9, aFalse; "FALSE"
0x18000a04c  mov     word ptr [rsp+880h+var_850], si
0x18000a051  mov     r8, rbx
0x18000a054  lea     rdx, aSettingPCallco; "Setting %p callcontext->SendOverlapPost"...
0x18000a05b  lea     rcx, [rsp+880h+var_850]
0x18000a060  call    FormatRRASErrorString
0x18000a065  test    cs:byte_18002E903, 10h
0x18000a06c  jz      short loc_18000A082
0x18000a06e  lea     r8, [rsp+880h+var_850]
0x18000a073  mov     rcx, r14
0x18000a076  lea     rdx, RasSSTPSvcTraceInfo
0x18000a07d  call    McTemplateU0z_EventWriteTransfer
0x18000a082  mov     rcx, cs:SstpSvcGlobals
0x18000a089  add     rcx, 0B8h; lpCriticalSection
0x18000a090  mov     [rbx+100h], rsi
0x18000a097  mov     [rbx+108h], si
0x18000a09e  mov     [rbx+1B2h], sil
0x18000a0a5  call    cs:__imp_EnterCriticalSection
0x18000a0ac  nop     dword ptr [rax+rax+00h]
0x18000a0b1  mov     rcx, cs:SstpSvcGlobals
0x18000a0b8  mov     rax, [rcx+0B0h]
0x18000a0bf  test    rax, rax
0x18000a0c2  jnz     short loc_18000A0C9
0x18000a0c4  lea     esi, [rax+57h]
0x18000a0c7  jmp     short loc_18000A0E9
0x18000a0c9  mov     rdx, rbx
0x18000a0cc  mov     rcx, rax
0x18000a0cf  call    assign_HF_handle
0x18000a0d4  mov     rcx, cs:SstpSvcGlobals
0x18000a0db  mov     [rbx+0F4h], eax
0x18000a0e1  neg     eax
0x18000a0e3  sbb     esi, esi
0x18000a0e5  not     esi
0x18000a0e7  and     esi, edi
0x18000a0e9  add     rcx, 0B8h; lpCriticalSection
0x18000a0f0  call    cs:__imp_LeaveCriticalSection
0x18000a0f7  nop     dword ptr [rax+rax+00h]
0x18000a0fc  test    esi, esi
0x18000a0fe  jz      short loc_18000A143
0x18000a100  test    cs:byte_18002E903, dil
0x18000a107  jz      loc_18000A19F
0x18000a10d  xor     eax, eax
0x18000a10f  lea     rdx, aUnableToGetThe; "Unable to get the handle32 for the requ"...
0x18000a116  mov     r8d, esi
0x18000a119  mov     word ptr [rsp+880h+var_850], ax
0x18000a11e  lea     rcx, [rsp+880h+var_850]
0x18000a123  call    FormatRRASErrorString
0x18000a128  test    cs:byte_18002E903, dil
0x18000a12f  jz      short loc_18000A19F
0x18000a131  lea     r8, [rsp+880h+var_850]
0x18000a136  mov     rdx, r15
0x18000a139  mov     rcx, r14
0x18000a13c  call    McTemplateU0z_EventWriteTransfer
0x18000a141  jmp     short loc_18000A19F
0x18000a143  mov     rcx, cs:SstpSvcGlobals
0x18000a14a  add     rcx, 0E0h; lpCriticalSection
0x18000a151  call    cs:__imp_EnterCriticalSection
0x18000a158  nop     dword ptr [rax+rax+00h]
0x18000a15d  mov     rcx, cs:SstpSvcGlobals
0x18000a164  cmp     dword ptr [rcx], 3
0x18000a167  jnz     loc_18000A22D
0x18000a16d  add     rcx, 0E0h; lpCriticalSection
0x18000a174  call    cs:__imp_LeaveCriticalSection
0x18000a17b  nop     dword ptr [rax+rax+00h]
0x18000a180  mov     esi, 3E3h
0x18000a185  mov     rcx, cs:SstpSvcGlobals
0x18000a18c  lea     rdx, [rbx+0F4h]
0x18000a193  mov     rcx, [rcx+0B0h]
0x18000a19a  call    HfFreeHandle32
0x18000a19f  mov     rcx, [rbx+150h]; pwk
0x18000a1a6  call    cs:__imp_CloseThreadpoolWork
0x18000a1ad  nop     dword ptr [rax+rax+00h]
0x18000a1b2  mov     qword ptr [rbx+150h], 0
0x18000a1bd  mov     rcx, [rbx+148h]; pwk
0x18000a1c4  call    cs:__imp_CloseThreadpoolWork
0x18000a1cb  nop     dword ptr [rax+rax+00h]
0x18000a1d0  mov     qword ptr [rbx+148h], 0
0x18000a1db  cmp     [rsp+880h+var_860], 0
0x18000a1e0  jz      short loc_18000A200
0x18000a1e2  mov     rcx, [rbx+1C8h]; pti
0x18000a1e9  call    cs:__imp_CloseThreadpoolTimer
0x18000a1f0  nop     dword ptr [rax+rax+00h]
0x18000a1f5  mov     qword ptr [rbx+1C8h], 0
0x18000a200  mov     rcx, r13; lpCriticalSection
0x18000a203  call    cs:__imp_DeleteCriticalSection
0x18000a20a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

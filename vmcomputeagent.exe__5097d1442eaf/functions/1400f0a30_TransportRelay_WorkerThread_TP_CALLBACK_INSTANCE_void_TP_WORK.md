# TransportRelay::WorkerThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1400f0a30`
- end: `0x1400f0ea9`
- name: `?WorkerThread@TransportRelay@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1145`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ddac`
- `0x14000ea44`
- `0x1400ee0cc`
- `0x1400ee5b8`
- `0x1400eec70`
- `0x1400efba0`
- `0x1400efc0c`
- `0x1400efe04`
- `0x1400f0a30`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400f0dd1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400f0dd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0bdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0d11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0d4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0bdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0d11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0d4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f0b97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f0cf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f0b97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f0cf3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400f0c72`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400f0cad`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400f0c72`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400f0cad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400f0c15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400f0c15`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1400f0a95`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1400f0a95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f0b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f0cf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f0b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f0cf9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400f0c3e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400f0c3e`

## string_xrefs

- `0x1400f0e59`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400f0e84`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400f0e96`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400f0e73`: `onecore\vm\compute\common\transport\transportrelay.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TransportRelay::WorkerThread(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_WORK Work)
{
  RTL_SRWLOCK *v4; // r13
  RTL_SRWLOCK *v5; // r14
  RTL_SRWLOCK *v6; // rax
  int Ptr; // eax
  RTL_SRWLOCK *v8; // rcx
  wil *v9; // rcx
  _DWORD *v10; // r15
  RTL_SRWLOCK *v11; // r12
  const char *v12; // r9
  DWORD v13; // eax
  const char *v14; // r9
  bool v15; // r14
  const char *v16; // r9
  int v17; // edx
  const char *v18; // r9
  RTL_SRWLOCK *v19; // rcx
  bool v20; // zf
  RTL_SRWLOCK *v21; // [rsp+20h] [rbp-1A8h] BYREF
  RTL_SRWLOCK *v22; // [rsp+28h] [rbp-1A0h]
  void **v23; // [rsp+30h] [rbp-198h] BYREF
  int v24; // [rsp+38h] [rbp-190h] BYREF
  char v25; // [rsp+3Ch] [rbp-18Ch]
  int v26; // [rsp+60h] [rbp-168h] BYREF
  const char *v27; // [rsp+68h] [rbp-160h]
  __int64 v28; // [rsp+70h] [rbp-158h]
  char v29; // [rsp+78h] [rbp-150h]
  int v30; // [rsp+80h] [rbp-148h]
  _BYTE v31[152]; // [rsp+88h] [rbp-140h] BYREF
  __int128 v32; // [rsp+120h] [rbp-A8h]
  int v33; // [rsp+130h] [rbp-98h]
  __int64 v34; // [rsp+138h] [rbp-90h]
  int *v35; // [rsp+140h] [rbp-88h]
  __int64 v36; // [rsp+148h] [rbp-80h]
  __int64 v37; // [rsp+150h] [rbp-78h]
  void ***v38; // [rsp+158h] [rbp-70h]
  __int64 v39; // [rsp+160h] [rbp-68h]
  int v40; // [rsp+168h] [rbp-60h]
  int *v41; // [rsp+170h] [rbp-58h]
  char v42; // [rsp+178h] [rbp-50h]
  HANDLE Handles[3]; // [rsp+180h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v22 = Context;
  Handles[0] = Context[23].Ptr;
  v4 = Context + 18;
  Handles[1] = *((HANDLE *)Context[18].Ptr + 7);
  v5 = Context + 20;
  Handles[2] = *((HANDLE *)Context[20].Ptr + 7);
  CallbackMayRunLong(Instance);
  memset_0(&v23, 0, 0x150u);
  v6 = Context + 25;
  if ( Context[28].Ptr > (PVOID)7 )
    v6 = (RTL_SRWLOCK *)v6->Ptr;
  v21 = v6;
  v24 = 0;
  v25 = 0;
  v29 = 0;
  v26 = 0;
  v27 = "TransportRelay_ConnectWorker";
  v28 = 0;
  v30 = 0;
  v32 = 0;
  memset_0(v31, 0, sizeof(v31));
  try
  {
    v33 = 1;
    v34 = 0;
    v35 = &v24;
    v36 = 0;
    v37 = 0;
    v38 = &v23;
    v39 = 0;
    v40 = 0;
    v41 = &v26;
    v42 = 0;
    v23 = &ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable';
    ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::StartActivity<unsigned short const *>(
      &v23,
      &v21);
    while ( 1 )
    {
      AcquireSRWLockExclusive(Context + 15);
      LODWORD(Context[16].Ptr) = GetCurrentThreadId();
      Ptr = (int)Context[17].Ptr;
      LODWORD(Context[16].Ptr) = 0;
      v8 = Context + 15;
      if ( Ptr != 4 )
      {
        ReleaseSRWLockExclusive(v8);
        v23 = &ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable';
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v23);
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(&v23);
        return;
      }
      ReleaseSRWLockExclusive(v8);
      v10 = (_DWORD *)&Context[11].Ptr + 1;
      TransportRelay::StartConnect(Context, Context[1].Ptr, v4, (char *)&Context[11].Ptr + 4, v21);
      v11 = Context + 12;
      TransportRelay::StartConnect(Context, Context[3].Ptr, v5, &Context[12], v21);
      if ( !SetEvent(Context[24].Ptr) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v12);
      v13 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
      if ( !v13 )
        break;
      v15 = 0;
      switch ( v13 )
      {
        case 1u:
          if ( !ResetEvent(*((HANDLE *)v4->Ptr + 7)) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA06,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v18);
          if ( *((_DWORD *)v4->Ptr + 12) )
          {
            *v10 = 0;
            v15 = 1;
          }
          else
          {
            *v10 = 2;
          }
          break;
        case 2u:
          if ( !ResetEvent(*((HANDLE *)Context[20].Ptr + 7)) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA06,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v16);
          v17 = *((_DWORD *)Context[20].Ptr + 12);
          LODWORD(v11->Ptr) = v17 == 0 ? 2 : 0;
          v15 = v17 != 0;
          break;
        case 0xFFFFFFFF:
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x163,
            (unsigned int)"onecore\\vm\\compute\\common\\transport\\transportrelay.cpp",
            v14);
      }
      if ( *v10 == 2 && LODWORD(v11->Ptr) == 2 )
      {
        AcquireSRWLockExclusive(Context + 15);
        LODWORD(Context[16].Ptr) = GetCurrentThreadId();
        v19 = Context + 15;
        if ( LODWORD(Context[17].Ptr) == 4 )
        {
          LODWORD(Context[17].Ptr) = 5;
          LODWORD(Context[16].Ptr) = 0;
          ReleaseSRWLockExclusive(v19);
          (*(void (__fastcall **)(PVOID, RTL_SRWLOCK *, PVOID))(*(_QWORD *)Context[13].Ptr + 8LL))(
            Context[13].Ptr,
            Context,
            Context[14].Ptr);
          TransportRelay::StartReceiveLoop(Context, Context[1].Ptr, &Context[5]);
          TransportRelay::StartReceiveLoop(Context, Context[3].Ptr, &Context[7]);
          wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v23);
        }
        else
        {
          LODWORD(Context[16].Ptr) = 0;
          ReleaseSRWLockExclusive(v19);
        }
        break;
      }
      v20 = !v15;
      v5 = Context + 20;
      if ( !v20 )
      {
        Sleep(0x12Cu);
        v5 = Context + 20;
      }
    }
    v23 = &ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable';
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v23);
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(&v23);
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::ResultFromCaughtException(v9);
    if ( (int)v21 < 0 )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v22[13].Ptr + 16LL))(v22[13].Ptr);
  }
}

```

## disassembly

```asm
0x1400f0a30  mov     r11, rsp
0x1400f0a33  mov     [r11+18h], rbx
0x1400f0a37  mov     [r11+20h], rsi
0x1400f0a3b  push    rdi
0x1400f0a3c  push    r12
0x1400f0a3e  push    r13
0x1400f0a40  push    r14
0x1400f0a42  push    r15
0x1400f0a44  sub     rsp, 1A0h
0x1400f0a4b  mov     rax, cs:__security_cookie
0x1400f0a52  xor     rax, rsp
0x1400f0a55  mov     [rsp+1C8h+var_30], rax
0x1400f0a5d  mov     rbx, rdx
0x1400f0a60  mov     [rsp+1C8h+var_1A0], rdx
0x1400f0a65  mov     rax, [rdx+0B8h]
0x1400f0a6c  mov     [r11-48h], rax
0x1400f0a70  lea     r13, [rdx+90h]
0x1400f0a77  mov     rax, [r13+0]
0x1400f0a7b  mov     rdx, [rax+38h]
0x1400f0a7f  mov     [r11-40h], rdx
0x1400f0a83  lea     r14, [rbx+0A0h]
0x1400f0a8a  mov     rax, [r14]
0x1400f0a8d  mov     rdx, [rax+38h]
0x1400f0a91  mov     [r11-38h], rdx
0x1400f0a95  call    cs:__imp_CallbackMayRunLong
0x1400f0a9b  nop
0x1400f0a9c  xor     edx, edx; Val
0x1400f0a9e  mov     r8d, 150h; Size
0x1400f0aa4  lea     rcx, [rsp+1C8h+var_198]; void *
0x1400f0aa9  call    memset_0
0x1400f0aae  lea     rax, [rbx+0C8h]
0x1400f0ab5  cmp     qword ptr [rax+18h], 7
0x1400f0aba  jbe     short loc_1400F0ABF
0x1400f0abc  mov     rax, [rax]
0x1400f0abf  mov     [rsp+1C8h+var_1A8], rax
0x1400f0ac4  xor     edi, edi
0x1400f0ac6  mov     [rsp+1C8h+var_190], edi
0x1400f0aca  mov     [rsp+1C8h+var_18C], dil
0x1400f0acf  mov     [rsp+1C8h+var_150], dil
0x1400f0ad4  mov     [rsp+1C8h+var_168], edi
0x1400f0ad8  lea     rax, aTransportrelay_0; "TransportRelay_ConnectWorker"
0x1400f0adf  mov     [rsp+1C8h+var_160], rax
0x1400f0ae4  mov     [rsp+1C8h+var_158], rdi
0x1400f0ae9  mov     [rsp+1C8h+var_148], edi
0x1400f0af0  xorps   xmm0, xmm0
0x1400f0af3  movdqa  [rsp+1C8h+var_A8], xmm0
0x1400f0afc  xor     edx, edx; Val
0x1400f0afe  mov     r8d, 98h; Size
0x1400f0b04  lea     rcx, [rsp+1C8h+var_140]; void *
0x1400f0b0c  call    memset_0
0x1400f0b11  mov     [rsp+1C8h+var_98], 1
0x1400f0b1c  xor     eax, eax
0x1400f0b1e  mov     [rsp+1C8h+var_90], rax
0x1400f0b26  lea     rax, [rsp+1C8h+var_190]
0x1400f0b2b  mov     [rsp+1C8h+var_88], rax
0x1400f0b33  mov     [rsp+1C8h+var_80], rdi
0x1400f0b3b  mov     [rsp+1C8h+var_78], rdi
0x1400f0b43  lea     rax, [rsp+1C8h+var_198]
0x1400f0b48  mov     [rsp+1C8h+var_70], rax
0x1400f0b50  mov     [rsp+1C8h+var_68], rdi
0x1400f0b58  mov     [rsp+1C8h+var_60], edi
0x1400f0b5f  lea     rax, [rsp+1C8h+var_168]
0x1400f0b64  mov     [rsp+1C8h+var_58], rax
0x1400f0b6c  mov     [rsp+1C8h+var_50], dil
0x1400f0b74  lea     r15, ??_7TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable'
0x1400f0b7b  mov     [rsp+1C8h+var_198], r15
0x1400f0b80  lea     rdx, [rsp+1C8h+var_1A8]
0x1400f0b85  lea     rcx, [rsp+1C8h+var_198]
0x1400f0b8a  call    ??$StartActivity@PEBG@TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::StartActivity<ushort const *>(ushort const * &&)
0x1400f0b8f  nop
0x1400f0b90  lea     rsi, [rbx+78h]
0x1400f0b94  mov     rcx, rsi; SRWLock
0x1400f0b97  call    cs:__imp_AcquireSRWLockExclusive
0x1400f0b9d  call    cs:__imp_GetCurrentThreadId
0x1400f0ba3  mov     [rsi+8], eax
0x1400f0ba6  mov     eax, [rbx+88h]
0x1400f0bac  mov     [rsi+8], edi
0x1400f0baf  mov     rcx, rsi; SRWLock
0x1400f0bb2  cmp     eax, 4
0x1400f0bb5  jz      short loc_1400F0BDC
0x1400f0bb7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f0bbd  nop
0x1400f0bbe  mov     [rsp+1C8h+var_198], r15
0x1400f0bc3  lea     rcx, [rsp+1C8h+var_198]
0x1400f0bc8  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f0bcd  lea     rcx, [rsp+1C8h+var_198]
0x1400f0bd2  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f0bd7  jmp     loc_1400F0E2C
0x1400f0bdc  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f0be2  lea     r15, [rbx+5Ch]
0x1400f0be6  mov     r9, r15
0x1400f0be9  mov     r8, r13
0x1400f0bec  mov     rdx, [rbx+8]
0x1400f0bf0  mov     rcx, rbx
0x1400f0bf3  call    ?StartConnect@TransportRelay@@AEAAXPEAVTransport@@AEBV?$shared_ptr@VTransportIoContext@@@std@@AEAW4TransportState@1@@Z; TransportRelay::StartConnect(Transport *,std::shared_ptr<TransportIoContext> const &,TransportRelay::TransportState &)
0x1400f0bf8  lea     r12, [rbx+60h]
0x1400f0bfc  mov     r9, r12
0x1400f0bff  mov     r8, r14
0x1400f0c02  mov     rdx, [rbx+18h]
0x1400f0c06  mov     rcx, rbx
0x1400f0c09  call    ?StartConnect@TransportRelay@@AEAAXPEAVTransport@@AEBV?$shared_ptr@VTransportIoContext@@@std@@AEAW4TransportState@1@@Z; TransportRelay::StartConnect(Transport *,std::shared_ptr<TransportIoContext> const &,TransportRelay::TransportState &)
0x1400f0c0e  mov     rcx, [rbx+0C0h]; hEvent
0x1400f0c15  call    cs:__imp_SetEvent
0x1400f0c1b  mov     rcx, [rsp+1C8h]; this
0x1400f0c23  test    eax, eax
0x1400f0c25  jz      loc_1400F0E59
0x1400f0c2b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400f0c2f  xor     r8d, r8d; bWaitAll
0x1400f0c32  lea     rdx, [rsp+1C8h+Handles]; lpHandles
0x1400f0c3a  lea     ecx, [r8+3]; nCount
0x1400f0c3e  call    cs:__imp_WaitForMultipleObjects
0x1400f0c44  test    eax, eax
0x1400f0c46  jz      loc_1400F0DEA
0x1400f0c4c  mov     r14b, dil
0x1400f0c4f  cmp     eax, 1
0x1400f0c52  jz      short loc_1400F0CA5
0x1400f0c54  cmp     eax, 2
0x1400f0c57  jz      short loc_1400F0C64
0x1400f0c59  cmp     eax, 0FFFFFFFFh
0x1400f0c5c  jz      loc_1400F0E6B
0x1400f0c62  jmp     short loc_1400F0CDB
0x1400f0c64  lea     r14, [rbx+0A0h]
0x1400f0c6b  mov     rcx, [r14]
0x1400f0c6e  mov     rcx, [rcx+38h]; hEvent
0x1400f0c72  call    cs:__imp_ResetEvent
0x1400f0c78  mov     rcx, [rsp+1C8h]; this
0x1400f0c80  test    eax, eax
0x1400f0c82  jz      loc_1400F0E84
0x1400f0c88  mov     rax, [r14]
0x1400f0c8b  mov     edx, [rax+30h]
0x1400f0c8e  mov     eax, edx
0x1400f0c90  neg     eax
0x1400f0c92  sbb     ecx, ecx
0x1400f0c94  not     ecx
0x1400f0c96  and     ecx, 2
0x1400f0c99  mov     [r12], ecx
0x1400f0c9d  test    edx, edx
0x1400f0c9f  setnz   r14b
0x1400f0ca3  jmp     short loc_1400F0CDB
0x1400f0ca5  mov     rcx, [r13+0]
0x1400f0ca9  mov     rcx, [rcx+38h]; hEvent
0x1400f0cad  call    cs:__imp_ResetEvent
0x1400f0cb3  mov     rcx, [rsp+1C8h]; this
0x1400f0cbb  test    eax, eax
0x1400f0cbd  jz      loc_1400F0E96
0x1400f0cc3  mov     rax, [r13+0]
0x1400f0cc7  cmp     [rax+30h], edi
0x1400f0cca  jnz     short loc_1400F0CD5
0x1400f0ccc  mov     dword ptr [r15], 2
0x1400f0cd3  jmp     short loc_1400F0CDB
0x1400f0cd5  mov     [r15], edi
0x1400f0cd8  mov     r14b, 1
0x1400f0cdb  cmp     dword ptr [r15], 2
0x1400f0cdf  jnz     loc_1400F0DB5
0x1400f0ce5  cmp     dword ptr [r12], 2
0x1400f0cea  jnz     loc_1400F0DB5
0x1400f0cf0  mov     rcx, rsi; SRWLock
0x1400f0cf3  call    cs:__imp_AcquireSRWLockExclusive
0x1400f0cf9  call    cs:__imp_GetCurrentThreadId
0x1400f0cff  mov     [rsi+8], eax
0x1400f0d02  mov     rcx, rsi; SRWLock
0x1400f0d05  cmp     dword ptr [rbx+88h], 4
0x1400f0d0c  jz      short loc_1400F0D3D
0x1400f0d0e  mov     [rsi+8], edi
0x1400f0d11  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f0d17  nop
0x1400f0d18  lea     rax, ??_7TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable'
0x1400f0d1f  mov     [rsp+1C8h+var_198], rax
0x1400f0d24  lea     rcx, [rsp+1C8h+var_198]
0x1400f0d29  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f0d2e  lea     rcx, [rsp+1C8h+var_198]
0x1400f0d33  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f0d38  jmp     loc_1400F0E2C
0x1400f0d3d  mov     dword ptr [rbx+88h], 5
0x1400f0d47  mov     [rsi+8], edi
0x1400f0d4a  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f0d50  mov     rcx, [rbx+68h]
0x1400f0d54  mov     rax, [rcx]
0x1400f0d57  mov     r8, [rbx+70h]
0x1400f0d5b  mov     rdx, rbx
0x1400f0d5e  mov     rax, [rax+8]
0x1400f0d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f0d67  lea     r8, [rbx+28h]
0x1400f0d6b  mov     rdx, [rbx+8]
0x1400f0d6f  mov     rcx, rbx
0x1400f0d72  call    ?StartReceiveLoop@TransportRelay@@AEAAXPEAVTransport@@AEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; TransportRelay::StartReceiveLoop(Transport *,std::shared_ptr<TransportIoContext> const &)
0x1400f0d77  lea     r8, [rbx+38h]
0x1400f0d7b  mov     rdx, [rbx+18h]
0x1400f0d7f  mov     rcx, rbx
0x1400f0d82  call    ?StartReceiveLoop@TransportRelay@@AEAAXPEAVTransport@@AEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; TransportRelay::StartReceiveLoop(Transport *,std::shared_ptr<TransportIoContext> const &)
0x1400f0d87  lea     rcx, [rsp+1C8h+var_198]
0x1400f0d8c  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400f0d91  nop
0x1400f0d92  lea     rax, ??_7TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable'
0x1400f0d99  mov     [rsp+1C8h+var_198], rax
0x1400f0d9e  lea     rcx, [rsp+1C8h+var_198]
0x1400f0da3  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f0da8  lea     rcx, [rsp+1C8h+var_198]
0x1400f0dad  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f0db2  nop
0x1400f0db3  jmp     short loc_1400F0E2C
0x1400f0db5  test    r14b, r14b
0x1400f0db8  lea     r14, [rbx+0A0h]
0x1400f0dbf  lea     r15, ??_7TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable'
0x1400f0dc6  jz      loc_1400F0B90
0x1400f0dcc  mov     ecx, 12Ch; dwMilliseconds
0x1400f0dd1  call    cs:__imp_Sleep
0x1400f0dd7  lea     r14, [rbx+0A0h]
0x1400f0dde  lea     r15, ??_7TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable'
0x1400f0de5  jmp     loc_1400F0B90
0x1400f0dea  lea     rax, ??_7TransportRelay_ConnectWorker@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_ConnectWorker::`vftable'
0x1400f0df1  mov     [rsp+1C8h+var_198], rax
0x1400f0df6  lea     rcx, [rsp+1C8h+var_198]
0x1400f0dfb  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f0e00  lea     rcx, [rsp+1C8h+var_198]
0x1400f0e05  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f0e0a  jmp     short loc_1400F0E2C
0x1400f0e0c  mov     r8d, dword ptr [rsp+1C8h+var_1A8]
0x1400f0e11  test    r8d, r8d
0x1400f0e14  jns     short loc_1400F0E2C
0x1400f0e16  mov     rdx, [rsp+1C8h+var_1A0]
0x1400f0e1b  mov     rcx, [rdx+68h]
0x1400f0e1f  mov     rax, [rcx]
0x1400f0e22  mov     rax, [rax+10h]
0x1400f0e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f0e2b  nop
0x1400f0e2c  mov     rcx, [rsp+1C8h+var_30]
0x1400f0e34  xor     rcx, rsp; StackCookie
0x1400f0e37  call    __security_check_cookie
0x1400f0e3c  lea     r11, [rsp+1C8h+var_28]
0x1400f0e44  mov     rbx, [r11+40h]
0x1400f0e48  mov     rsi, [r11+48h]
0x1400f0e4c  mov     rsp, r11
0x1400f0e4f  pop     r15
0x1400f0e51  pop     r14
0x1400f0e53  pop     r13
0x1400f0e55  pop     r12
0x1400f0e57  pop     rdi
0x1400f0e58  retn
0x1400f0e59  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400f0e60  mov     edx, 0A01h; void *
0x1400f0e65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400f0e6b  mov     rcx, [rsp+1C8h]; this
0x1400f0e73  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\common\\transport"...
0x1400f0e7a  mov     edx, 163h; void *
0x1400f0e7f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400f0e84  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400f0e8b  mov     edx, 0A06h; void *
0x1400f0e90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400f0e96  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400f0e9d  mov     edx, 0A06h; void *
0x1400f0ea2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

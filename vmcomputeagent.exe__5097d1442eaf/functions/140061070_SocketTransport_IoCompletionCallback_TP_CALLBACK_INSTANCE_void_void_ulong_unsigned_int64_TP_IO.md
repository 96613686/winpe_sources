# SocketTransport::IoCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x140061070`
- end: `0x140061421`
- name: `?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `945`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x140009f8c`
- `0x14002e120`
- `0x14005d800`
- `0x14005f06c`
- `0x14005f364`
- `0x140060364`
- `0x140060654`
- `0x140061070`
- `0x140061548`
- `0x140061ab4`
- `0x14006265c`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400611f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400612a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140061350`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400611f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400612a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140061350`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140061179`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140061227`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400612c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140061179`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140061227`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400612c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006117f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006122d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400612ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006117f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006122d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400612ce`

## string_xrefs

- `0x1400610d0`: `SocketTransport_IoComplete`
- `0x14006140e`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SocketTransport::IoCompletionCallback(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PVOID *Overlapped,
        ULONG IoResult,
        ULONG_PTR NumberOfBytesTransferred,
        PTP_IO Io)
{
  PVOID *v9; // r13
  bool v10; // r14
  const char *v11; // r9
  ULONG_PTR v12; // r15
  __int64 v13; // rax
  volatile signed __int32 *v14; // rbx
  PVOID Ptr; // rcx
  void (__fastcall *v16)(PVOID, RTL_SRWLOCK *, __int128 *); // rax
  __int64 v17; // rax
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rax
  volatile signed __int32 *v20; // rbx
  const char *v21; // r9
  volatile signed __int32 *v22; // rbx
  RTL_SRWLOCK *v23; // [rsp+30h] [rbp-1D8h] BYREF
  volatile signed __int32 *v24; // [rsp+38h] [rbp-1D0h]
  PVOID *v25; // [rsp+40h] [rbp-1C8h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-1C0h]
  __int128 v27; // [rsp+50h] [rbp-1B8h] BYREF
  ULONG v28[4]; // [rsp+60h] [rbp-1A8h] BYREF
  _QWORD v29[42]; // [rsp+70h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v28[0] = IoResult;
  v23 = Context;
  v9 = Overlapped - 11;
  v25 = Overlapped - 11;
  v27 = 0;
  v10 = 0;
  memset_0(v29, 0, sizeof(v29));
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v29,
    "SocketTransport_IoComplete");
  try
  {
    v29[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_IoComplete::`vftable';
    ComputeService::Diagnostics::TraceProvider::SocketTransport_IoComplete::StartActivity<SocketTransport * &,TransportIoContext * &,enum TransportIoContextType &,unsigned long &,unsigned __int64 &>(
      (unsigned int)v29,
      (unsigned int)&v23,
      (unsigned int)&v25,
      (_DWORD)v9 + 16,
      (__int64)v28,
      (__int64)&NumberOfBytesTransferred);
    if ( *(Overlapped - 1) != Context )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x5BF,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        v11);
    *((_DWORD *)Overlapped - 10) = IoResult;
    v12 = NumberOfBytesTransferred;
    *((_DWORD *)Overlapped - 11) = NumberOfBytesTransferred;
    switch ( *((_DWORD *)Overlapped - 18) )
    {
      case 1:
        AcquireSRWLockExclusive(Context + 25);
        LODWORD(Context[26].Ptr) = GetCurrentThreadId();
        v23 = Context + 25;
        v19 = SocketTransport::MapRemove(Context, &v25, v9);
        std::shared_ptr<TransportIoContext>::operator=(&v27, v19);
        v20 = v26;
        if ( v26 )
        {
          if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
        SocketTransport::ProcessConnectCompletion((SocketTransport *)Context, IoResult);
        LODWORD(Context[26].Ptr) = 0;
        ReleaseSRWLockExclusive(Context + 25);
        (**(void (__fastcall ***)(PVOID, RTL_SRWLOCK *, __int128 *))Context[18].Ptr)(Context[18].Ptr, Context, &v27);
        goto LABEL_24;
      case 2:
        AcquireSRWLockExclusive(Context + 25);
        LODWORD(Context[26].Ptr) = GetCurrentThreadId();
        v17 = SocketTransport::MapRemove(Context, &v23, v9);
        std::shared_ptr<TransportIoContext>::operator=(&v27, v17);
        v18 = v24;
        if ( v24 )
        {
          if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
        Context[47].Ptr = (char *)Context[47].Ptr + v12;
        LODWORD(Context[26].Ptr) = 0;
        ReleaseSRWLockExclusive(Context + 25);
        Ptr = Context[18].Ptr;
        v16 = *(void (__fastcall **)(PVOID, RTL_SRWLOCK *, __int128 *))(*(_QWORD *)Ptr + 8LL);
        break;
      case 3:
        if ( !IoResult )
          v10 = (_DWORD)v12 == 0;
        AcquireSRWLockExclusive(Context + 25);
        LODWORD(Context[26].Ptr) = GetCurrentThreadId();
        v13 = SocketTransport::MapRemove(Context, &v23, v9);
        std::shared_ptr<TransportIoContext>::operator=(&v27, v13);
        v14 = v24;
        if ( v24 )
        {
          if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
        Context[46].Ptr = (char *)Context[46].Ptr + v12;
        LODWORD(Context[26].Ptr) = 0;
        ReleaseSRWLockExclusive(Context + 25);
        Ptr = Context[18].Ptr;
        v16 = *(void (__fastcall **)(PVOID, RTL_SRWLOCK *, __int128 *))(*(_QWORD *)Ptr + 16LL);
        break;
      default:
LABEL_24:
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
        v29[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_IoComplete::`vftable';
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v29);
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(v29);
        goto LABEL_35;
    }
    v16(Ptr, Context, &v27);
    goto LABEL_24;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x60A,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      v21);
  }
LABEL_35:
  if ( v10 )
    SocketTransport::GracefulDisconnect((SocketTransport *)Context);
  v22 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
  if ( *((_QWORD *)&v27 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
    if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
  }
}

```

## disassembly

```asm
0x140061070  push    rbx
0x140061072  push    rsi
0x140061073  push    rdi
0x140061074  push    r12
0x140061076  push    r13
0x140061078  push    r14
0x14006107a  push    r15
0x14006107c  sub     rsp, 1D0h
0x140061083  mov     rax, cs:__security_cookie
0x14006108a  xor     rax, rsp
0x14006108d  mov     [rsp+208h+var_48], rax
0x140061095  mov     r12d, r9d
0x140061098  mov     rsi, r8
0x14006109b  mov     rdi, rdx
0x14006109e  mov     [rsp+208h+var_1A8], r9d
0x1400610a3  mov     [rsp+208h+var_1D8], rdx
0x1400610a8  lea     r13, [r8-58h]
0x1400610ac  mov     [rsp+208h+var_1C8], r13
0x1400610b1  xorps   xmm1, xmm1
0x1400610b4  movdqu  [rsp+208h+var_1B8], xmm1
0x1400610ba  xor     r14b, r14b
0x1400610bd  xor     edx, edx; Val
0x1400610bf  mov     r8d, 150h; Size
0x1400610c5  lea     rcx, [rsp+208h+var_198]; void *
0x1400610ca  call    memset_0
0x1400610cf  nop
0x1400610d0  lea     rdx, aSockettranspor_1; "SocketTransport_IoComplete"
0x1400610d7  lea     rcx, [rsp+208h+var_198]
0x1400610dc  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400610e1  lea     rax, ??_7SocketTransport_IoComplete@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_IoComplete::`vftable'
0x1400610e8  mov     [rsp+208h+var_198], rax
0x1400610ed  lea     rax, [rsp+208h+NumberOfBytesTransferred]
0x1400610f5  mov     [rsp+208h+var_1E0], rax
0x1400610fa  lea     rax, [rsp+208h+var_1A8]
0x1400610ff  mov     [rsp+208h+var_1E8], rax
0x140061104  lea     r9, [r13+10h]
0x140061108  lea     r8, [rsp+208h+var_1C8]
0x14006110d  lea     rdx, [rsp+208h+var_1D8]
0x140061112  lea     rcx, [rsp+208h+var_198]
0x140061117  call    ??$StartActivity@AEAPEAVSocketTransport@@AEAPEAVTransportIoContext@@AEAW4TransportIoContextType@@AEAKAEA_K@SocketTransport_IoComplete@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAPEAVSocketTransport@@AEAPEAVTransportIoContext@@AEAW4TransportIoContextType@@AEAKAEA_K@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_IoComplete::StartActivity<SocketTransport * &,TransportIoContext * &,TransportIoContextType &,ulong &,unsigned __int64 &>(SocketTransport * &,TransportIoContext * &,TransportIoContextType &,ulong &,unsigned __int64 &)
0x14006111c  nop
0x14006111d  mov     rcx, [rsp+208h]; this
0x140061125  cmp     [rsi-8], rdi
0x140061129  jnz     loc_14006140E
0x14006112f  mov     [rsi-28h], r12d
0x140061133  mov     r15, [rsp+208h+NumberOfBytesTransferred]
0x14006113b  mov     [rsi-2Ch], r15d
0x14006113f  mov     ecx, [rsi-48h]
0x140061142  sub     ecx, 1
0x140061145  jz      loc_1400612BE
0x14006114b  sub     ecx, 1
0x14006114e  jz      loc_14006121D
0x140061154  cmp     ecx, 1
0x140061157  jnz     loc_140061370
0x14006115d  test    r12d, r12d
0x140061160  jnz     short loc_14006116F
0x140061162  movzx   r14d, r14b
0x140061166  mov     eax, ecx
0x140061168  test    r15d, r15d
0x14006116b  cmovz   r14d, ecx
0x14006116f  lea     rsi, [rdi+0C8h]
0x140061176  mov     rcx, rsi; SRWLock
0x140061179  call    cs:__imp_AcquireSRWLockExclusive
0x14006117f  call    cs:__imp_GetCurrentThreadId
0x140061185  mov     [rsi+8], eax
0x140061188  mov     r8, r13
0x14006118b  lea     rdx, [rsp+208h+var_1D8]
0x140061190  mov     rcx, rdi
0x140061193  call    ?MapRemove@SocketTransport@@AEAA?AV?$shared_ptr@VTransportIoContext@@@std@@PEAVTransportIoContext@@@Z; SocketTransport::MapRemove(TransportIoContext *)
0x140061198  mov     rdx, rax
0x14006119b  lea     rcx, [rsp+208h+var_1B8]
0x1400611a0  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x1400611a5  mov     rbx, [rsp+208h+var_1D0]
0x1400611aa  test    rbx, rbx
0x1400611ad  jz      short loc_1400611E6
0x1400611af  or      eax, 0FFFFFFFFh
0x1400611b2  lock xadd [rbx+8], eax
0x1400611b7  cmp     eax, 1
0x1400611ba  jnz     short loc_1400611E6
0x1400611bc  mov     rax, [rbx]
0x1400611bf  mov     rcx, rbx
0x1400611c2  mov     rax, [rax]
0x1400611c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400611ca  or      eax, 0FFFFFFFFh
0x1400611cd  lock xadd [rbx+0Ch], eax
0x1400611d2  cmp     eax, 1
0x1400611d5  jnz     short loc_1400611E6
0x1400611d7  mov     rax, [rbx]
0x1400611da  mov     rcx, rbx
0x1400611dd  mov     rax, [rax+8]
0x1400611e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400611e6  add     [rdi+170h], r15
0x1400611ed  mov     dword ptr [rsi+8], 0
0x1400611f4  mov     rcx, rsi; SRWLock
0x1400611f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400611fd  mov     rcx, [rdi+90h]
0x140061204  mov     rax, [rcx]
0x140061207  mov     rax, [rax+10h]
0x14006120b  mov     rdx, rdi
0x14006120e  lea     r8, [rsp+208h+var_1B8]
0x140061213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140061218  jmp     loc_140061370
0x14006121d  lea     rsi, [rdi+0C8h]
0x140061224  mov     rcx, rsi; SRWLock
0x140061227  call    cs:__imp_AcquireSRWLockExclusive
0x14006122d  call    cs:__imp_GetCurrentThreadId
0x140061233  mov     [rsi+8], eax
0x140061236  mov     r8, r13
0x140061239  lea     rdx, [rsp+208h+var_1D8]
0x14006123e  mov     rcx, rdi
0x140061241  call    ?MapRemove@SocketTransport@@AEAA?AV?$shared_ptr@VTransportIoContext@@@std@@PEAVTransportIoContext@@@Z; SocketTransport::MapRemove(TransportIoContext *)
0x140061246  mov     rdx, rax
0x140061249  lea     rcx, [rsp+208h+var_1B8]
0x14006124e  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x140061253  mov     rbx, [rsp+208h+var_1D0]
0x140061258  test    rbx, rbx
0x14006125b  jz      short loc_140061294
0x14006125d  or      eax, 0FFFFFFFFh
0x140061260  lock xadd [rbx+8], eax
0x140061265  cmp     eax, 1
0x140061268  jnz     short loc_140061294
0x14006126a  mov     rax, [rbx]
0x14006126d  mov     rcx, rbx
0x140061270  mov     rax, [rax]
0x140061273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140061278  or      eax, 0FFFFFFFFh
0x14006127b  lock xadd [rbx+0Ch], eax
0x140061280  cmp     eax, 1
0x140061283  jnz     short loc_140061294
0x140061285  mov     rax, [rbx]
0x140061288  mov     rcx, rbx
0x14006128b  mov     rax, [rax+8]
0x14006128f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140061294  add     [rdi+178h], r15
0x14006129b  mov     dword ptr [rsi+8], 0
0x1400612a2  mov     rcx, rsi; SRWLock
0x1400612a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1400612ab  mov     rcx, [rdi+90h]
0x1400612b2  mov     rax, [rcx]
0x1400612b5  mov     rax, [rax+8]
0x1400612b9  jmp     loc_14006120B
0x1400612be  lea     rsi, [rdi+0C8h]
0x1400612c5  mov     rcx, rsi; SRWLock
0x1400612c8  call    cs:__imp_AcquireSRWLockExclusive
0x1400612ce  call    cs:__imp_GetCurrentThreadId
0x1400612d4  mov     [rsi+8], eax
0x1400612d7  mov     [rsp+208h+var_1D8], rsi
0x1400612dc  mov     r8, r13
0x1400612df  lea     rdx, [rsp+208h+var_1C8]
0x1400612e4  mov     rcx, rdi
0x1400612e7  call    ?MapRemove@SocketTransport@@AEAA?AV?$shared_ptr@VTransportIoContext@@@std@@PEAVTransportIoContext@@@Z; SocketTransport::MapRemove(TransportIoContext *)
0x1400612ec  mov     rdx, rax
0x1400612ef  lea     rcx, [rsp+208h+var_1B8]
0x1400612f4  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x1400612f9  mov     rbx, [rsp+208h+var_1C0]
0x1400612fe  test    rbx, rbx
0x140061301  jz      short loc_14006133A
0x140061303  or      eax, 0FFFFFFFFh
0x140061306  lock xadd [rbx+8], eax
0x14006130b  cmp     eax, 1
0x14006130e  jnz     short loc_14006133A
0x140061310  mov     rax, [rbx]
0x140061313  mov     rcx, rbx
0x140061316  mov     rax, [rax]
0x140061319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006131e  or      eax, 0FFFFFFFFh
0x140061321  lock xadd [rbx+0Ch], eax
0x140061326  cmp     eax, 1
0x140061329  jnz     short loc_14006133A
0x14006132b  mov     rax, [rbx]
0x14006132e  mov     rcx, rbx
0x140061331  mov     rax, [rax+8]
0x140061335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006133a  mov     edx, r12d; unsigned int
0x14006133d  mov     rcx, rdi; this
0x140061340  call    ?ProcessConnectCompletion@SocketTransport@@AEAAXK@Z; SocketTransport::ProcessConnectCompletion(ulong)
0x140061345  nop
0x140061346  mov     dword ptr [rsi+8], 0
0x14006134d  mov     rcx, rsi; SRWLock
0x140061350  call    cs:__imp_ReleaseSRWLockExclusive
0x140061356  mov     rcx, [rdi+90h]
0x14006135d  mov     rax, [rcx]
0x140061360  lea     r8, [rsp+208h+var_1B8]
0x140061365  mov     rdx, rdi
0x140061368  mov     rax, [rax]
0x14006136b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140061370  lea     rcx, [rsp+208h+var_198]
0x140061375  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14006137a  nop
0x14006137b  lea     rax, ??_7SocketTransport_IoComplete@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_IoComplete::`vftable'
0x140061382  mov     [rsp+208h+var_198], rax
0x140061387  lea     rcx, [rsp+208h+var_198]
0x14006138c  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140061391  lea     rcx, [rsp+208h+var_198]
0x140061396  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14006139b  nop
0x14006139c  test    r14b, r14b
0x14006139f  jz      short loc_1400613AA
0x1400613a1  mov     rcx, rdi; this
0x1400613a4  call    ?GracefulDisconnect@SocketTransport@@AEAAXXZ; SocketTransport::GracefulDisconnect(void)
0x1400613a9  nop
0x1400613aa  mov     rbx, qword ptr [rsp+208h+var_1B8+8]
0x1400613af  test    rbx, rbx
0x1400613b2  jz      short loc_1400613EB
0x1400613b4  or      eax, 0FFFFFFFFh
0x1400613b7  lock xadd [rbx+8], eax
0x1400613bc  cmp     eax, 1
0x1400613bf  jnz     short loc_1400613EB
0x1400613c1  mov     rax, [rbx]
0x1400613c4  mov     rcx, rbx
0x1400613c7  mov     rax, [rax]
0x1400613ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400613cf  or      eax, 0FFFFFFFFh
0x1400613d2  lock xadd [rbx+0Ch], eax
0x1400613d7  cmp     eax, 1
0x1400613da  jnz     short loc_1400613EB
0x1400613dc  mov     rax, [rbx]
0x1400613df  mov     rcx, rbx
0x1400613e2  mov     rax, [rax+8]
0x1400613e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400613eb  mov     rcx, [rsp+208h+var_48]
0x1400613f3  xor     rcx, rsp; StackCookie
0x1400613f6  call    __security_check_cookie
0x1400613fb  add     rsp, 1D0h
0x140061402  pop     r15
0x140061404  pop     r14
0x140061406  pop     r13
0x140061408  pop     r12
0x14006140a  pop     rdi
0x14006140b  pop     rsi
0x14006140c  pop     rbx
0x14006140d  retn
0x14006140e  lea     r8, aOnecoreVmCompu_18; "onecore\\vm\\compute\\common\\transport"...
0x140061415  mov     edx, 5BFh; void *
0x14006141a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

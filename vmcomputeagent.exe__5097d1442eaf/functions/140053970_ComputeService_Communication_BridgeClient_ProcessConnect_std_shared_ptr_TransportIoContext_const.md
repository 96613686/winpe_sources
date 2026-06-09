# ComputeService::Communication::BridgeClient::ProcessConnect(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140053970`
- end: `0x140053b82`
- name: `?ProcessConnect@BridgeClient@Communication@ComputeService@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `530`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140053060`
- `0x140055b80`

## callees

- `0x1400016ec`
- `0x140005360`
- `0x140006098`
- `0x14000aeec`
- `0x140027760`
- `0x14002af9c`
- `0x140030fe4`
- `0x1400487ec`
- `0x140053970`
- `0x140053b88`
- `0x14005677c`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140053ae4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140053ae4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053a35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053a35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140053a17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140053a17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053a1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053a1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComputeService::Communication::BridgeClient::ProcessConnect(
        ComputeService::Communication::BridgeClient *this,
        __int64 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  _DWORD *v8; // rcx
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[42]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+190h] [rbp+90h] BYREF

  memset_0(v11, 0, sizeof(v11));
  v4 = *a2;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v11,
    "BridgeClient_ProcessConnect");
  v11[0] = &ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::`vftable';
  ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::StartActivity<unsigned long &>(v11, v4 + 48);
  while ( *(_DWORD *)(*a2 + 48) && *(_DWORD *)(*a2 + 48) != 10056 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 16LL))(
            *((_QWORD *)this + 3),
            a2) )
      goto LABEL_14;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 13);
  GetCurrentThreadId();
  *((_DWORD *)this + 30) = 2;
  *((_DWORD *)this + 28) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 13);
  if ( *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3)) + 8) == 2 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3));
    v6 = _RTDynamicCast_0(
           v5,
           0,
           &TransportConnectedPeer `RTTI Type Descriptor',
           &HyperVTransportConnectedPeer `RTTI Type Descriptor');
    *(_OWORD *)((char *)this + 280) = *(_OWORD *)(v6 + 16);
    *(_OWORD *)((char *)this + 296) = *(_OWORD *)(v6 + 32);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5), *((_QWORD *)this + 9));
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 3) + 32LL))(
         *((_QWORD *)this + 3),
         (char *)this + 72) )
  {
    ComputeService::Communication::BridgeClient::ProcessReceive((RTL_SRWLOCK *)this, (__int64 *)this + 9);
  }
  v10 = 1;
  v7 = *((_QWORD *)this + 23);
  if ( !v7 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 16LL))(v7, &v10);
  v8 = (_DWORD *)*((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *v8 > 5u )
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v8,
      (unsigned __int8 *)&word_140134D7E,
      (const GUID *)(v11[34] + 8LL),
      0,
      2u,
      &v12);
LABEL_14:
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11);
  v11[0] = &ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
  return wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(v11);
}

```

## disassembly

```asm
0x140053970  mov     [rsp-8+arg_10], rbx
0x140053975  mov     [rsp-8+arg_18], rsi
0x14005397a  push    rbp
0x14005397b  push    rdi
0x14005397c  push    r12
0x14005397e  lea     rbp, [rsp-0C0h]
0x140053986  sub     rsp, 1C0h
0x14005398d  mov     rax, cs:__security_cookie
0x140053994  xor     rax, rsp
0x140053997  mov     [rbp+0D0h+var_20], rax
0x14005399e  mov     rsi, rdx
0x1400539a1  mov     rdi, rcx
0x1400539a4  xor     edx, edx; Val
0x1400539a6  mov     r8d, 150h; Size
0x1400539ac  lea     rcx, [rsp+1D0h+var_190]; void *
0x1400539b1  call    memset_0
0x1400539b6  mov     rbx, [rsi]
0x1400539b9  lea     rdx, aBridgeclientPr; "BridgeClient_ProcessConnect"
0x1400539c0  lea     rcx, [rsp+1D0h+var_190]
0x1400539c5  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400539ca  lea     r12, ??_7BridgeClient_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::`vftable'
0x1400539d1  mov     [rsp+1D0h+var_190], r12
0x1400539d6  lea     rdx, [rbx+30h]
0x1400539da  lea     rcx, [rsp+1D0h+var_190]
0x1400539df  call    ??$StartActivity@AEAK@BridgeClient_ProcessConnect@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK@Z; ComputeService::Diagnostics::TraceProvider::BridgeClient_ProcessConnect::StartActivity<ulong &>(ulong &)
0x1400539e4  nop
0x1400539e5  mov     rax, [rsi]
0x1400539e8  cmp     dword ptr [rax+30h], 0
0x1400539ec  jz      short loc_140053A13
0x1400539ee  cmp     dword ptr [rax+30h], 2748h
0x1400539f5  jz      short loc_140053A13
0x1400539f7  mov     rcx, [rdi+18h]
0x1400539fb  mov     rax, [rcx]
0x1400539fe  mov     rdx, rsi
0x140053a01  mov     rax, [rax+10h]
0x140053a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053a0a  test    al, al
0x140053a0c  jnz     short loc_1400539E5
0x140053a0e  jmp     loc_140053B37
0x140053a13  lea     rcx, [rdi+68h]; SRWLock
0x140053a17  call    cs:__imp_AcquireSRWLockExclusive
0x140053a1d  call    cs:__imp_GetCurrentThreadId
0x140053a23  mov     dword ptr [rdi+78h], 2
0x140053a2a  mov     dword ptr [rdi+70h], 0
0x140053a31  lea     rcx, [rdi+68h]; SRWLock
0x140053a35  call    cs:__imp_ReleaseSRWLockExclusive
0x140053a3b  mov     rcx, [rdi+18h]
0x140053a3f  mov     rax, [rcx]
0x140053a42  mov     rax, [rax+38h]
0x140053a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053a4b  mov     esi, 1
0x140053a50  cmp     dword ptr [rax+8], 2
0x140053a54  jnz     short loc_140053A9A
0x140053a56  mov     rcx, [rdi+18h]
0x140053a5a  mov     rax, [rcx]
0x140053a5d  mov     rax, [rax+38h]
0x140053a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053a66  mov     rcx, rax
0x140053a69  mov     [rsp+1D0h+var_1B0], esi
0x140053a6d  lea     r9, ??_R0?AVHyperVTransportConnectedPeer@@@8; HyperVTransportConnectedPeer `RTTI Type Descriptor'
0x140053a74  lea     r8, ??_R0?AVTransportConnectedPeer@@@8; TransportConnectedPeer `RTTI Type Descriptor'
0x140053a7b  xor     edx, edx
0x140053a7d  call    __RTDynamicCast_0
0x140053a82  movups  xmm0, xmmword ptr [rax+10h]
0x140053a86  movdqu  xmmword ptr [rdi+118h], xmm0
0x140053a8e  movups  xmm1, xmmword ptr [rax+20h]
0x140053a92  movdqu  xmmword ptr [rdi+128h], xmm1
0x140053a9a  mov     rcx, [rdi+28h]
0x140053a9e  lea     rbx, [rdi+48h]
0x140053aa2  mov     rax, [rcx]
0x140053aa5  mov     rdx, [rbx]
0x140053aa8  mov     rax, [rax+8]
0x140053aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053ab1  mov     rcx, [rdi+18h]
0x140053ab5  mov     rax, [rcx]
0x140053ab8  mov     rdx, rbx
0x140053abb  mov     rax, [rax+20h]
0x140053abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053ac4  test    al, al
0x140053ac6  jz      short loc_140053AD3
0x140053ac8  mov     rdx, rbx
0x140053acb  mov     rcx, rdi; this
0x140053ace  call    ?ProcessReceive@BridgeClient@Communication@ComputeService@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; ComputeService::Communication::BridgeClient::ProcessReceive(std::shared_ptr<TransportIoContext> const &)
0x140053ad3  mov     [rsp+1D0h+var_198], rsi
0x140053ad8  mov     rcx, [rdi+0B8h]
0x140053adf  test    rcx, rcx
0x140053ae2  jnz     short loc_140053AEB
0x140053ae4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140053aea  int     3; Trap to Debugger
0x140053aeb  mov     rax, [rcx]
0x140053aee  lea     rdx, [rsp+1D0h+var_198]
0x140053af3  mov     rax, [rax+10h]
0x140053af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053afc  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140053b01  mov     rcx, [rax+8]; int
0x140053b05  mov     eax, [rcx]
0x140053b07  cmp     eax, 5
0x140053b0a  jbe     short loc_140053B37
0x140053b0c  mov     r8, [rbp+0D0h+var_80]
0x140053b10  add     r8, 8; int
0x140053b14  lea     rax, [rbp+0D0h+var_40]
0x140053b1b  mov     [rsp+1D0h+var_1A8], rax; PEVENT_DATA_DESCRIPTOR
0x140053b20  mov     [rsp+1D0h+var_1B0], 2; ULONG
0x140053b28  xor     r9d, r9d; int
0x140053b2b  lea     rdx, word_140134D7E; int
0x140053b32  call    _tlgWriteTransfer_EventWriteTransfer
0x140053b37  lea     rcx, [rsp+1D0h+var_190]
0x140053b3c  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140053b41  nop
0x140053b42  mov     [rsp+1D0h+var_190], r12
0x140053b47  lea     rcx, [rsp+1D0h+var_190]
0x140053b4c  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140053b51  lea     rcx, [rsp+1D0h+var_190]
0x140053b56  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140053b5b  mov     rcx, [rbp+0D0h+var_20]
0x140053b62  xor     rcx, rsp; StackCookie
0x140053b65  call    __security_check_cookie
0x140053b6a  lea     r11, [rsp+1D0h+var_10]
0x140053b72  mov     rbx, [r11+30h]
0x140053b76  mov     rsi, [r11+38h]
0x140053b7a  mov     rsp, r11
0x140053b7d  pop     r12
0x140053b7f  pop     rdi
0x140053b80  pop     rbp
0x140053b81  retn
```

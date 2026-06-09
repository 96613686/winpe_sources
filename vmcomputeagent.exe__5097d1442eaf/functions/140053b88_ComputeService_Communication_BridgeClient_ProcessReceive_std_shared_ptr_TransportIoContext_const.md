# ComputeService::Communication::BridgeClient::ProcessReceive(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140053b88`
- end: `0x140053de9`
- name: `?ProcessReceive@BridgeClient@Communication@ComputeService@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, __int64 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140053500`
- `0x140053970`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ea60`
- `0x140027760`
- `0x14002af9c`
- `0x140030fe4`
- `0x1400341ac`
- `0x1400488c8`
- `0x1400523f0`
- `0x140052aac`
- `0x140053518`
- `0x140053b88`
- `0x14005677c`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053c54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053d43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053c54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140053d43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140053c2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140053c2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053c35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140053c35`

## string_xrefs

- `0x140053dbc`: `onecore\vm\compute\common\bridge\MessageView.h`
- `0x140053d15`: `onecore\vm\compute\common\bridge\bridgeclient.cpp`
- `0x140053da4`: `onecore\vm\compute\common\bridge\bridgeclient.cpp`
- `0x140053dd7`: `onecore\vm\compute\common\bridge\bridgeclient.cpp`

## pseudocode

```c
__int64 __fastcall ComputeService::Communication::BridgeClient::ProcessReceive(RTL_SRWLOCK *this, __int64 *a2)
{
  __int64 v4; // rbx
  int Ptr; // eax
  RTL_SRWLOCK *v6; // rcx
  __int64 v7; // rdx
  const char *v8; // r9
  unsigned int v10; // [rsp+20h] [rbp-E0h]
  char *v11; // [rsp+28h] [rbp-D8h]
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h]
  _QWORD v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v15[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  memset_0(v15, 0, sizeof(v15));
  v4 = *a2;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "Bridge_Receive");
  v15[0] = &ComputeService::Diagnostics::TraceProvider::Bridge_Receive::`vftable';
  ComputeService::Diagnostics::TraceProvider::Bridge_Receive::StartActivity<_GUID &,_GUID &,unsigned long &,unsigned long &>(
    (unsigned int)v15,
    (_DWORD)this + 280,
    (_DWORD)this + 296,
    v4 + 48,
    v4 + 44);
  v13 = 257;
  v12 = this;
  while ( 1 )
  {
    AcquireSRWLockExclusive(this + 13);
    LODWORD(this[14].Ptr) = GetCurrentThreadId();
    Ptr = (int)this[15].Ptr;
    LODWORD(this[14].Ptr) = 0;
    v6 = this + 13;
    if ( Ptr != 2 )
      break;
    ReleaseSRWLockExclusive(v6);
    v7 = *a2;
    v8 = (const char *)*(unsigned int *)(*a2 + 48);
    if ( (_DWORD)v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x50F,
        (unsigned int)"onecore\\vm\\compute\\common\\bridge\\bridgeclient.cpp",
        v8,
        v10);
    if ( !*(_DWORD *)(v7 + 44) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x510,
        (unsigned int)"onecore\\vm\\compute\\common\\bridge\\bridgeclient.cpp",
        (const char *)0x80072746LL,
        v10);
    v14[3] = 1;
    memset(v14, 0, 24);
    if ( (*(unsigned __int8 (__fastcall **)(PVOID, __int64, _QWORD *))(*(_QWORD *)this[5].Ptr + 16LL))(
           this[5].Ptr,
           v7,
           v14) )
    {
      if ( !v14[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\vm\\compute\\common\\bridge\\MessageView.h",
          (const char *)0x8007139FLL,
          v10);
      if ( (*(_DWORD *)v14[0] & 0xF0000000) == 0x10000000 )
      {
        ComputeService::Communication::BridgeClient::OnRequestMessage(
          (ComputeService::Communication::BridgeClient *)this,
          (struct ComputeService::Communication::ReadonlyJsonMessageView *)v14);
      }
      else
      {
        LODWORD(v11) = *(_DWORD *)v14[0];
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x51C,
          (unsigned int)"onecore\\vm\\compute\\common\\bridge\\bridgeclient.cpp",
          (const char *)0xC0370111LL,
          (int)"Received unsupported message: %x",
          v11);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)this[3].Ptr + 32LL))(this[3].Ptr, a2) )
      goto LABEL_13;
  }
  ReleaseSRWLockExclusive(v6);
LABEL_13:
  BYTE1(v13) = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
  wil::details::ScopeExitFnGuard__lambda_03670d2194cd2d936bcd8b9805cf493f___::operator()(&v12);
  v15[0] = &ComputeService::Diagnostics::TraceProvider::Bridge_Receive::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
  return wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(v15);
}

```

## disassembly

```asm
0x140053b88  mov     [rsp-8+arg_10], rbx
0x140053b8d  mov     [rsp-8+arg_18], rsi
0x140053b92  push    rbp
0x140053b93  push    rdi
0x140053b94  push    r12
0x140053b96  lea     rbp, [rsp-0C0h]
0x140053b9e  sub     rsp, 1C0h
0x140053ba5  mov     rax, cs:__security_cookie
0x140053bac  xor     rax, rsp
0x140053baf  mov     [rbp+0D0h+var_20], rax
0x140053bb6  mov     rsi, rdx
0x140053bb9  mov     rdi, rcx
0x140053bbc  xor     edx, edx; Val
0x140053bbe  mov     r8d, 150h; Size
0x140053bc4  lea     rcx, [rsp+1D0h+var_170]; void *
0x140053bc9  call    memset_0
0x140053bce  mov     rbx, [rsi]
0x140053bd1  lea     rdx, aBridgeReceive; "Bridge_Receive"
0x140053bd8  lea     rcx, [rsp+1D0h+var_170]
0x140053bdd  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140053be2  lea     r12, ??_7Bridge_Receive@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::Bridge_Receive::`vftable'
0x140053be9  mov     [rsp+1D0h+var_170], r12
0x140053bee  lea     rax, [rbx+2Ch]
0x140053bf2  lea     r9, [rbx+30h]
0x140053bf6  lea     r8, [rdi+128h]
0x140053bfd  lea     rdx, [rdi+118h]
0x140053c04  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x140053c09  lea     rcx, [rsp+1D0h+var_170]
0x140053c0e  call    ??$StartActivity@AEAU_GUID@@AEAU1@AEAKAEAK@Bridge_Receive@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAU_GUID@@0AEAK1@Z; ComputeService::Diagnostics::TraceProvider::Bridge_Receive::StartActivity<_GUID &,_GUID &,ulong &,ulong &>(_GUID &,_GUID &,ulong &,ulong &)
0x140053c13  nop
0x140053c14  xorps   xmm0, xmm0
0x140053c17  movups  [rsp+1D0h+var_1A0], xmm0
0x140053c1c  mov     qword ptr [rsp+1D0h+var_1A0], rdi
0x140053c21  mov     word ptr [rsp+1D0h+var_1A0+8], 101h
0x140053c28  lea     rbx, [rdi+68h]
0x140053c2c  mov     rcx, rbx; SRWLock
0x140053c2f  call    cs:__imp_AcquireSRWLockExclusive
0x140053c35  call    cs:__imp_GetCurrentThreadId
0x140053c3b  mov     [rbx+8], eax
0x140053c3e  mov     eax, [rdi+78h]
0x140053c41  mov     dword ptr [rbx+8], 0
0x140053c48  mov     rcx, rbx; SRWLock
0x140053c4b  cmp     eax, 2
0x140053c4e  jnz     loc_140053D43
0x140053c54  call    cs:__imp_ReleaseSRWLockExclusive
0x140053c5a  mov     rdx, [rsi]
0x140053c5d  mov     r9d, [rdx+30h]; char *
0x140053c61  mov     rcx, [rbp+0D8h]; this
0x140053c68  test    r9d, r9d
0x140053c6b  jnz     loc_140053DA4
0x140053c71  mov     rcx, [rbp+0D8h]; this
0x140053c78  cmp     [rdx+2Ch], r9d
0x140053c7c  jz      loc_140053DD1
0x140053c82  mov     [rsp+1D0h+var_178], 1
0x140053c8b  mov     [rsp+1D0h+var_190], 0
0x140053c94  mov     [rsp+1D0h+var_188], 0
0x140053c9d  mov     [rsp+1D0h+var_180], 0
0x140053ca6  mov     rcx, [rdi+28h]
0x140053caa  mov     rax, [rcx]
0x140053cad  lea     r8, [rsp+1D0h+var_190]
0x140053cb2  mov     rax, [rax+10h]
0x140053cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053cbb  test    al, al
0x140053cbd  jz      short loc_140053D26
0x140053cbf  mov     rcx, [rsp+1D0h+var_190]
0x140053cc4  test    rcx, rcx
0x140053cc7  setz    al
0x140053cca  mov     r10, [rbp+0D8h]
0x140053cd1  test    al, al
0x140053cd3  jnz     loc_140053DB6
0x140053cd9  mov     edx, [rcx]
0x140053cdb  mov     eax, edx
0x140053cdd  and     eax, 0F0000000h
0x140053ce2  cmp     eax, 10000000h
0x140053ce7  jnz     short loc_140053CF8
0x140053ce9  lea     rdx, [rsp+1D0h+var_190]; struct ComputeService::Communication::ReadonlyJsonMessageView *
0x140053cee  mov     rcx, rdi; this
0x140053cf1  call    ?OnRequestMessage@BridgeClient@Communication@ComputeService@@AEAAXAEAVReadonlyJsonMessageView@23@@Z; ComputeService::Communication::BridgeClient::OnRequestMessage(ComputeService::Communication::ReadonlyJsonMessageView &)
0x140053cf6  jmp     short loc_140053D26
0x140053cf8  mov     rcx, [rbp+0D8h]; this
0x140053cff  mov     dword ptr [rsp+1D0h+var_1A8], edx; char *
0x140053d03  lea     rax, aReceivedUnsupp; "Received unsupported message: %x"
0x140053d0a  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x140053d0f  mov     r9d, 0C0370111h; char *
0x140053d15  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\common\\bridge\\b"...
0x140053d1c  mov     edx, 51Ch; void *
0x140053d21  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x140053d26  mov     rcx, [rdi+18h]
0x140053d2a  mov     rax, [rcx]
0x140053d2d  mov     rdx, rsi
0x140053d30  mov     rax, [rax+20h]
0x140053d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053d39  test    al, al
0x140053d3b  jnz     loc_140053C2C
0x140053d41  jmp     short loc_140053D49
0x140053d43  call    cs:__imp_ReleaseSRWLockExclusive
0x140053d49  mov     byte ptr [rsp+1D0h+var_1A0+9], 0
0x140053d4e  lea     rcx, [rsp+1D0h+var_170]
0x140053d53  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140053d58  nop
0x140053d59  lea     rcx, [rsp+1D0h+var_1A0]
0x140053d5e  call    wil__details__ScopeExitFnGuard__lambda_03670d2194cd2d936bcd8b9805cf493f_____operator__
0x140053d63  nop
0x140053d64  mov     [rsp+1D0h+var_170], r12
0x140053d69  lea     rcx, [rsp+1D0h+var_170]
0x140053d6e  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140053d73  lea     rcx, [rsp+1D0h+var_170]
0x140053d78  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140053d7d  mov     rcx, [rbp+0D0h+var_20]
0x140053d84  xor     rcx, rsp; StackCookie
0x140053d87  call    __security_check_cookie
0x140053d8c  lea     r11, [rsp+1D0h+var_10]
0x140053d94  mov     rbx, [r11+30h]
0x140053d98  mov     rsi, [r11+38h]
0x140053d9c  mov     rsp, r11
0x140053d9f  pop     r12
0x140053da1  pop     rdi
0x140053da2  pop     rbp
0x140053da3  retn
0x140053da4  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\common\\bridge\\b"...
0x140053dab  mov     edx, 50Fh; void *
0x140053db0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140053db6  mov     r9d, 8007139Fh; char *
0x140053dbc  lea     r8, aOnecoreVmCompu_39; "onecore\\vm\\compute\\common\\bridge\\M"...
0x140053dc3  mov     edx, 6Ah ; 'j'; void *
0x140053dc8  mov     rcx, r10; this
0x140053dcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140053dd1  mov     r9d, 80072746h; char *
0x140053dd7  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\common\\bridge\\b"...
0x140053dde  mov     edx, 510h; void *
0x140053de3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

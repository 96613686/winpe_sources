# ComputeService::Communication::BridgeClient::StartConnect(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140055b80`
- end: `0x140055d4a`
- name: `?StartConnect@BridgeClient@Communication@ComputeService@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `458`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004dbe0`
- `0x1400538d8`

## callees

- `0x140005360`
- `0x140006098`
- `0x140048a3c`
- `0x14004f238`
- `0x140053970`
- `0x140055b80`
- `0x1400569f0`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140055ccd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140055ce4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140055ccd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140055ce4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140055ca2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140055ca2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140055ca8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140055ca8`

## pseudocode

```c
void __fastcall ComputeService::Communication::BridgeClient::StartConnect(__int64 a1)
{
  __int128 v3; // [rsp+28h] [rbp-190h] BYREF
  void **v4; // [rsp+40h] [rbp-178h] BYREF
  int v5; // [rsp+48h] [rbp-170h] BYREF
  char v6; // [rsp+4Ch] [rbp-16Ch]
  int v7; // [rsp+70h] [rbp-148h] BYREF
  const char *v8; // [rsp+78h] [rbp-140h]
  __int64 v9; // [rsp+80h] [rbp-138h]
  char v10; // [rsp+88h] [rbp-130h]
  int v11; // [rsp+90h] [rbp-128h]
  _BYTE v12[152]; // [rsp+98h] [rbp-120h] BYREF
  __int128 v13; // [rsp+130h] [rbp-88h]
  int v14; // [rsp+140h] [rbp-78h]
  __int64 v15; // [rsp+148h] [rbp-70h]
  int *v16; // [rsp+150h] [rbp-68h]
  __int64 v17; // [rsp+158h] [rbp-60h]
  __int64 v18; // [rsp+160h] [rbp-58h]
  void ***v19; // [rsp+168h] [rbp-50h]
  __int64 v20; // [rsp+170h] [rbp-48h]
  int v21; // [rsp+178h] [rbp-40h]
  int *v22; // [rsp+180h] [rbp-38h]
  char v23; // [rsp+188h] [rbp-30h]

  memset_0(&v4, 0, 0x150u);
  v3 = 0;
  v5 = 0;
  v6 = 0;
  v10 = 0;
  v7 = 0;
  v8 = "Bridge_Connect";
  v9 = 0;
  v11 = 0;
  v13 = 0;
  memset_0(v12, 0, sizeof(v12));
  v14 = 1;
  v15 = 0;
  v16 = &v5;
  v17 = 0;
  v18 = 0;
  v19 = &v4;
  v20 = 0;
  v21 = 0;
  v22 = &v7;
  v23 = 0;
  v4 = &ComputeService::Diagnostics::TraceProvider::Bridge_Connect::`vftable';
  ComputeService::Diagnostics::TraceProvider::Bridge_Connect::StartActivity<_GUID>(&v4, &v3);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 104));
  *(_DWORD *)(a1 + 112) = GetCurrentThreadId();
  if ( *(_DWORD *)(a1 + 120) == 5 )
  {
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,6,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v4,
      2147947423LL);
    *(_DWORD *)(a1 + 112) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 104));
  }
  else
  {
    *(_QWORD *)(a1 + 120) = 1;
    *(_DWORD *)(a1 + 112) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 104));
    try
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24)) )
        ComputeService::Communication::BridgeClient::ProcessConnect((ComputeService::Communication::BridgeClient *)a1);
    }
    catch ( ... )
    {
      ComputeService::Communication::BridgeClient::OnTransportError((ComputeService::Communication::BridgeClient *)a1);
    }
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,6,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v4,
      0);
  }
  ComputeService::Diagnostics::TraceProvider::Bridge_Connect::~Bridge_Connect((ComputeService::Diagnostics::TraceProvider::Bridge_Connect *)&v4);
}

```

## disassembly

```asm
0x140055b80  mov     [rsp+arg_10], rbx
0x140055b85  push    rsi
0x140055b86  push    rdi
0x140055b87  push    r14
0x140055b89  sub     rsp, 1A0h
0x140055b90  mov     rax, cs:__security_cookie
0x140055b97  xor     rax, rsp
0x140055b9a  mov     [rsp+1B8h+var_28], rax
0x140055ba2  mov     rsi, rdx
0x140055ba5  mov     rdi, rcx
0x140055ba8  mov     [rsp+1B8h+var_198], rcx
0x140055bad  xor     edx, edx; Val
0x140055baf  mov     r8d, 150h; Size
0x140055bb5  lea     rcx, [rsp+1B8h+var_178]; void *
0x140055bba  call    memset_0
0x140055bbf  xorps   xmm0, xmm0
0x140055bc2  movups  [rsp+1B8h+var_190], xmm0
0x140055bc7  xor     r14d, r14d
0x140055bca  mov     [rsp+1B8h+var_170], r14d
0x140055bcf  mov     [rsp+1B8h+var_16C], r14b
0x140055bd4  mov     [rsp+1B8h+var_130], r14b
0x140055bdc  mov     [rsp+1B8h+var_148], r14d
0x140055be1  lea     rax, aBridgeConnect; "Bridge_Connect"
0x140055be8  mov     [rsp+1B8h+var_140], rax
0x140055bed  mov     [rsp+1B8h+var_138], r14
0x140055bf5  mov     [rsp+1B8h+var_128], r14d
0x140055bfd  movdqa  [rsp+1B8h+var_88], xmm0
0x140055c06  xor     edx, edx; Val
0x140055c08  mov     r8d, 98h; Size
0x140055c0e  lea     rcx, [rsp+1B8h+var_120]; void *
0x140055c16  call    memset_0
0x140055c1b  mov     [rsp+1B8h+var_78], 1
0x140055c26  xor     eax, eax
0x140055c28  mov     [rsp+1B8h+var_70], rax
0x140055c30  lea     rax, [rsp+1B8h+var_170]
0x140055c35  mov     [rsp+1B8h+var_68], rax
0x140055c3d  mov     [rsp+1B8h+var_60], r14
0x140055c45  mov     [rsp+1B8h+var_58], r14
0x140055c4d  lea     rax, [rsp+1B8h+var_178]
0x140055c52  mov     [rsp+1B8h+var_50], rax
0x140055c5a  mov     [rsp+1B8h+var_48], r14
0x140055c62  mov     [rsp+1B8h+var_40], r14d
0x140055c6a  lea     rax, [rsp+1B8h+var_148]
0x140055c6f  mov     [rsp+1B8h+var_38], rax
0x140055c77  mov     [rsp+1B8h+var_30], r14b
0x140055c7f  lea     rax, ??_7Bridge_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::Bridge_Connect::`vftable'
0x140055c86  mov     [rsp+1B8h+var_178], rax
0x140055c8b  lea     rdx, [rsp+1B8h+var_190]
0x140055c90  lea     rcx, [rsp+1B8h+var_178]
0x140055c95  call    ??$StartActivity@U_GUID@@@Bridge_Connect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAU_GUID@@@Z; ComputeService::Diagnostics::TraceProvider::Bridge_Connect::StartActivity<_GUID>(_GUID &&)
0x140055c9a  nop
0x140055c9b  lea     rbx, [rdi+68h]
0x140055c9f  mov     rcx, rbx; SRWLock
0x140055ca2  call    cs:__imp_AcquireSRWLockExclusive
0x140055ca8  call    cs:__imp_GetCurrentThreadId
0x140055cae  mov     [rbx+8], eax
0x140055cb1  cmp     dword ptr [rdi+78h], 5
0x140055cb5  jnz     short loc_140055CD5
0x140055cb7  mov     edx, 8007139Fh
0x140055cbc  lea     rcx, [rsp+1B8h+var_178]
0x140055cc1  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$05$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,6,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140055cc6  mov     [rbx+8], r14d
0x140055cca  mov     rcx, rbx; SRWLock
0x140055ccd  call    cs:__imp_ReleaseSRWLockExclusive
0x140055cd3  jmp     short loc_140055D1B
0x140055cd5  mov     qword ptr [rdi+78h], 1
0x140055cdd  mov     [rbx+8], r14d
0x140055ce1  mov     rcx, rbx; SRWLock
0x140055ce4  call    cs:__imp_ReleaseSRWLockExclusive
0x140055cea  nop
0x140055ceb  mov     rcx, [rdi+18h]
0x140055cef  mov     rax, [rcx]
0x140055cf2  mov     rdx, rsi
0x140055cf5  mov     rax, [rax+10h]
0x140055cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055cfe  test    al, al
0x140055d00  jz      short loc_140055D0E
0x140055d02  mov     rdx, rsi
0x140055d05  mov     rcx, rdi
0x140055d08  call    ?ProcessConnect@BridgeClient@Communication@ComputeService@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; ComputeService::Communication::BridgeClient::ProcessConnect(std::shared_ptr<TransportIoContext> const &)
0x140055d0d  nop
0x140055d0e  xor     edx, edx
0x140055d10  lea     rcx, [rsp+1B8h+var_178]
0x140055d15  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$05$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,6,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140055d1a  nop
0x140055d1b  lea     rcx, [rsp+1B8h+var_178]; this
0x140055d20  call    ??1Bridge_Connect@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::Bridge_Connect::~Bridge_Connect(void)
0x140055d25  nop
0x140055d26  mov     rcx, [rsp+1B8h+var_28]
0x140055d2e  xor     rcx, rsp; StackCookie
0x140055d31  call    __security_check_cookie
0x140055d36  mov     rbx, [rsp+1B8h+arg_10]
0x140055d3e  add     rsp, 1A0h
0x140055d45  pop     r14
0x140055d47  pop     rdi
0x140055d48  pop     rsi
0x140055d49  retn
```

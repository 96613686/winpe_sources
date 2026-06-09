# ComputeService::Management::BeginOperation_ModifySettingsImpl(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveServerOperation,std::unique_ptr<ComputeService::Management::ActivityHolder,std::default_delete<ComputeService::Management::ActivityHolder>>,std::shared_ptr<ComputeService::Management::StateOperationContext>)

- ea: `0x1400b983c`
- end: `0x1400b9c14`
- name: `?BeginOperation_ModifySettingsImpl@Management@ComputeService@@YA?AVActiveStateOperation@12@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveServerOperation@12@V?$unique_ptr@VActivityHolder@Management@ComputeService@@U?$default_delete@VActivityHolder@Management@ComputeService@@@std@@@5@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@5@@Z`
- size: `984`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14008b220`
- `0x14009be50`

## callees

- `0x140005360`
- `0x1400056fc`
- `0x1400083bc`
- `0x140009f8c`
- `0x14000ea60`
- `0x140034170`
- `0x14004199c`
- `0x1400b5918`
- `0x1400b6a1c`
- `0x1400b6f28`
- `0x1400b983c`
- `0x1400dc6e8`
- `0x1400e6de4`
- `0x1400e6f08`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1400b9939`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1400b9939`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9907`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9a83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9907`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400b9a83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b98cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b995b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b98cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400b995b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b9943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b9943`

## string_xrefs

- `0x1400b9c02`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400b9ba1`: `onecore\vm\compute\management\computeSystem\ComputeSystem.h`
- `0x1400b9b71`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`
- `0x1400b9b89`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`
- `0x1400b9bb9`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`
- `0x1400b9bec`: `onecore\vm\compute\management\shared\compute\basestatemachine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
ComputeService::Management::RundownReference *__fastcall ComputeService::Management::BeginOperation_ModifySettingsImpl(
        ComputeService::Management::RundownReference *a1,
        __int64 a2,
        RTL_SRWLOCK *a3,
        RTL_SRWLOCK *a4,
        RTL_SRWLOCK *a5)
{
  int v7; // r12d
  RTL_SRWLOCK *v9; // rax
  ComputeService::Management::RundownReference *v10; // rbx
  __int64 Ptr_low; // rdx
  PSRWLOCK v12; // rbx
  const char *v13; // r9
  RTL_SRWLOCK *v14; // rsi
  PSRWLOCK v15; // rbx
  __int64 v16; // rax
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *Ptr; // rbx
  volatile signed __int32 *v19; // rbx
  unsigned int v21; // eax
  int v22; // edx
  unsigned int v23; // eax
  int v24; // edx
  int v25; // [rsp+20h] [rbp-91h]
  char *v26; // [rsp+28h] [rbp-89h]
  int v27; // [rsp+50h] [rbp-61h] BYREF
  __int128 v28; // [rsp+58h] [rbp-59h] BYREF
  PSRWLOCK *v29; // [rsp+70h] [rbp-41h]
  char v30; // [rsp+78h] [rbp-39h]
  RTL_SRWLOCK *v31; // [rsp+80h] [rbp-31h]
  PSRWLOCK SRWLock[4]; // [rsp+88h] [rbp-29h] BYREF
  int CompareAddress; // [rsp+A8h] [rbp-9h] BYREF
  ComputeService::Management::RundownReference *v34; // [rsp+B0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]

  v7 = a2;
  v34 = a1;
  SRWLock[1] = a3;
  SRWLock[2] = a4;
  SRWLock[3] = a5;
  if ( *((_DWORD *)a3->Ptr + 6) != 9 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x556,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\basestatemachine.cpp",
      (const char *)0x80070057LL,
      v25);
  v9 = (RTL_SRWLOCK *)_RTDynamicCast_0(
                        *(_QWORD *)(*(_QWORD *)a2 + 8LL),
                        0,
                        &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
                        &ComputeService::Management::BaseStateMachine `RTTI Type Descriptor');
  v10 = (ComputeService::Management::RundownReference *)v9;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computeSystem\\ComputeSystem.h",
      (const char *)0x80004001LL,
      0);
  SRWLock[0] = v9;
  AcquireSRWLockExclusive(v9);
  v34 = v10;
  if ( BYTE5(SRWLock[0][19].Ptr) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56C,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\basestatemachine.cpp",
      (const char *)0xC0370107LL,
      0);
  Ptr_low = LODWORD(SRWLock[0][6].Ptr);
  if ( (_DWORD)Ptr_low != 2 && (unsigned int)(Ptr_low - 3) > 1 )
  {
    v23 = wil::verify_hresult<long>(3224830213LL, Ptr_low);
    LODWORD(v26) = v24;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x563,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\basestatemachine.cpp",
      (const char *)v23,
      (int)"state: %d",
      v26);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)v10);
  v29 = SRWLock;
  v30 = 1;
  v12 = SRWLock[0];
  while ( !_InterlockedExchange((volatile __int32 *)&v12[1], 0) )
  {
    CompareAddress = 0;
    if ( !WaitOnAddress(&v12[1], &CompareAddress, 4u, 0xFFFFFFFF) )
    {
      if ( GetLastError() != 1460 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xDBF,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v13);
      break;
    }
  }
  v14 = SRWLock[0];
  AcquireSRWLockExclusive(SRWLock[0]);
  v31 = v14;
  if ( LODWORD(SRWLock[0][6].Ptr) != 2 && (unsigned int)(LODWORD(SRWLock[0][6].Ptr) - 3) > 1 )
  {
    v21 = wil::verify_hresult<long>(3224830213LL, LODWORD(SRWLock[0][6].Ptr));
    LODWORD(v26) = v22;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x563,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\basestatemachine.cpp",
      (const char *)v21,
      (int)"state: %d",
      v26);
  }
  v34 = 0;
  ComputeService::Management::AcquireRundownReference(&v34, &SRWLock[0][2]);
  v30 = 0;
  CompareAddress = -1;
  v15 = SRWLock[0] + 6;
  v27 = 1;
  *(_QWORD *)&v28 = operator new(0x2A8u);
  v16 = std::_Ref_count_obj2_ComputeService::Management::StateOperation_::_Ref_count_obj2_ComputeService::Management::StateOperation__std::shared_ptr_ComputeService::Management::ComputeSystem__const___std::unique_ptr_ComputeService::Management::ActivityHolder_std::default_delete_ComputeService::Management::ActivityHolder____ComputeService::Management::RundownReferenceHolder_enum_ComputeService::Management::StateAction_enum_ComputeService::Management::SystemState___enum_ComputeService::Management::SystemState_ComputeService::Management::ActiveServerOperation_std::shared_ptr_ComputeService::Management::StateOperationContext___lambda_c65cea56f52a93d1c72f1dbbbf466c59___(
          v28,
          v7,
          (_DWORD)a4,
          (unsigned int)&v34,
          (__int64)&v27,
          (__int64)v15,
          (__int64)&CompareAddress,
          (__int64)a3,
          (__int64)a5);
  v28 = 0;
  std::shared_ptr<ComputeService::Management::StateOperation>::_Set_ptr_rep_and_enable_shared<ComputeService::Management::StateOperation>(
    &v28,
    (_QWORD *)(v16 + 16),
    v16);
  *(_DWORD *)(v28 + 432) = 15;
  ComputeService::Management::ActiveStateOperation::ActiveStateOperation(a1, &v28);
  v17 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  if ( *((_QWORD *)&v28 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  if ( v34 )
    ComputeService::Management::RundownReference::Exit(v34);
  if ( v14 )
    ReleaseSRWLockExclusive(v14);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)&a3[2]);
  Ptr = (volatile signed __int32 *)a3[1].Ptr;
  if ( Ptr )
  {
    if ( _InterlockedExchangeAdd(Ptr + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))Ptr)(Ptr);
      if ( _InterlockedExchangeAdd(Ptr + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Ptr + 8LL))(Ptr);
    }
  }
  if ( a4->Ptr )
    (**(void (__fastcall ***)(PVOID, __int64))a4->Ptr)(a4->Ptr, 1);
  v19 = (volatile signed __int32 *)a5[1].Ptr;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400b983c  push    rbp
0x1400b983e  push    rbx
0x1400b983f  push    rsi
0x1400b9840  push    rdi
0x1400b9841  push    r12
0x1400b9843  push    r13
0x1400b9845  push    r14
0x1400b9847  push    r15
0x1400b9849  lea     rbp, [rsp-17h]
0x1400b984e  sub     rsp, 0C8h
0x1400b9855  mov     rax, cs:__security_cookie
0x1400b985c  xor     rax, rsp
0x1400b985f  mov     [rbp+4Fh+var_48], rax
0x1400b9863  mov     r15, r9
0x1400b9866  mov     rdi, r8
0x1400b9869  mov     r12, rdx
0x1400b986c  mov     r14, rcx
0x1400b986f  mov     [rbp+4Fh+var_50], rcx
0x1400b9873  mov     [rbp+4Fh+var_70], r8
0x1400b9877  mov     [rbp+4Fh+var_68], r9
0x1400b987b  mov     r13, [rbp+4Fh+arg_20]
0x1400b987f  mov     [rbp+4Fh+var_60], r13
0x1400b9883  xor     esi, esi
0x1400b9885  mov     rcx, [rbp+57h]; this
0x1400b9889  mov     rax, [r8]
0x1400b988c  cmp     dword ptr [rax+18h], 9
0x1400b9890  jnz     loc_1400B9B83
0x1400b9896  mov     rcx, [rdx]
0x1400b9899  mov     [rsp+100h+var_E0], esi; int
0x1400b989d  lea     r9, ??_R0?AUBaseStateMachine@Management@ComputeService@@@8; ComputeService::Management::BaseStateMachine `RTTI Type Descriptor'
0x1400b98a4  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x1400b98ab  xor     edx, edx
0x1400b98ad  mov     rcx, [rcx+8]
0x1400b98b1  call    __RTDynamicCast_0
0x1400b98b6  mov     rbx, rax
0x1400b98b9  mov     rcx, [rbp+57h]; this
0x1400b98bd  test    rax, rax
0x1400b98c0  jz      loc_1400B9B9B
0x1400b98c6  mov     [rbp+4Fh+SRWLock], rax
0x1400b98ca  mov     rcx, rax; SRWLock
0x1400b98cd  call    cs:__imp_AcquireSRWLockExclusive
0x1400b98d3  mov     [rbp+4Fh+var_50], rbx
0x1400b98d7  mov     rcx, [rbp+57h]; this
0x1400b98db  mov     rdx, [rbp+4Fh+SRWLock]
0x1400b98df  cmp     [rdx+9Dh], sil
0x1400b98e6  jnz     loc_1400B9BB3
0x1400b98ec  mov     edx, [rdx+30h]
0x1400b98ef  mov     ecx, edx
0x1400b98f1  sub     ecx, 2
0x1400b98f4  jz      short loc_1400B9904
0x1400b98f6  sub     ecx, 1
0x1400b98f9  jz      short loc_1400B9904
0x1400b98fb  cmp     ecx, 1
0x1400b98fe  jnz     loc_1400B9BCB
0x1400b9904  mov     rcx, rbx; SRWLock
0x1400b9907  call    cs:__imp_ReleaseSRWLockExclusive
0x1400b990d  lea     rax, [rbp+4Fh+SRWLock]
0x1400b9911  mov     [rbp+4Fh+var_90], rax
0x1400b9915  mov     [rbp+4Fh+var_88], 1
0x1400b9919  mov     rbx, [rbp+4Fh+SRWLock]
0x1400b991d  mov     eax, esi
0x1400b991f  xchg    eax, [rbx+8]
0x1400b9922  test    eax, eax
0x1400b9924  jnz     short loc_1400B9954
0x1400b9926  mov     [rbp+4Fh+CompareAddress], esi
0x1400b9929  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400b992d  lea     r8d, [rax+4]; AddressSize
0x1400b9931  lea     rdx, [rbp+4Fh+CompareAddress]; CompareAddress
0x1400b9935  lea     rcx, [rbx+8]; Address
0x1400b9939  call    cs:__imp_WaitOnAddress
0x1400b993f  test    eax, eax
0x1400b9941  jnz     short loc_1400B991D
0x1400b9943  call    cs:__imp_GetLastError
0x1400b9949  cmp     eax, 5B4h
0x1400b994e  jnz     loc_1400B9BFE
0x1400b9954  mov     rsi, [rbp+4Fh+SRWLock]
0x1400b9958  mov     rcx, rsi; SRWLock
0x1400b995b  call    cs:__imp_AcquireSRWLockExclusive
0x1400b9961  mov     [rbp+4Fh+var_80], rsi
0x1400b9965  mov     r8, [rbp+4Fh+SRWLock]
0x1400b9969  mov     edx, [r8+30h]
0x1400b996d  mov     ecx, edx
0x1400b996f  sub     ecx, 2
0x1400b9972  jz      short loc_1400B9982
0x1400b9974  sub     ecx, 1
0x1400b9977  jz      short loc_1400B9982
0x1400b9979  cmp     ecx, 1
0x1400b997c  jnz     loc_1400B9B50
0x1400b9982  mov     [rbp+4Fh+var_50], 0
0x1400b998a  lea     rdx, [r8+10h]
0x1400b998e  lea     rcx, [rbp+4Fh+var_50]
0x1400b9992  call    ?AcquireRundownReference@Management@ComputeService@@YA?AVRundownReferenceHolder@12@PEAVRundownReference@12@@Z; ComputeService::Management::AcquireRundownReference(ComputeService::Management::RundownReference *)
0x1400b9997  nop
0x1400b9998  mov     [rbp+4Fh+var_88], 0
0x1400b999c  mov     [rbp+4Fh+CompareAddress], 0FFFFFFFFh
0x1400b99a3  mov     rbx, [rbp+4Fh+SRWLock]
0x1400b99a7  add     rbx, 30h ; '0'
0x1400b99ab  mov     [rbp+4Fh+var_B0], 1
0x1400b99b2  mov     ecx, 2A8h; Size
0x1400b99b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b99bc  mov     qword ptr [rbp+4Fh+var_A8], rax
0x1400b99c0  mov     [rsp+100h+var_C0], r13
0x1400b99c5  mov     [rsp+100h+var_C8], rdi
0x1400b99ca  lea     rcx, [rbp+4Fh+CompareAddress]
0x1400b99ce  mov     [rsp+100h+var_D0], rcx
0x1400b99d3  mov     [rsp+100h+var_D8], rbx
0x1400b99d8  lea     rcx, [rbp+4Fh+var_B0]
0x1400b99dc  mov     qword ptr [rsp+100h+var_E0], rcx
0x1400b99e1  lea     r9, [rbp+4Fh+var_50]
0x1400b99e5  mov     r8, r15
0x1400b99e8  mov     rdx, r12
0x1400b99eb  mov     rcx, rax
0x1400b99ee  call    std___Ref_count_obj2_ComputeService__Management__StateOperation____Ref_count_obj2_ComputeService__Management__StateOperation__std__shared_ptr_ComputeService__Management__ComputeSystem__const___std__unique_ptr_ComputeService__Management__ActivityHolder_std__default_delete_ComputeService__Management__ActivityHolder____ComputeService__Management__RundownReferenceHolder_enum_ComputeService__Management__StateAction_enum_ComputeService__Management__SystemState___enum_ComputeService__Management__SystemState_ComputeService__Management__ActiveServerOperation_std__shared_ptr_ComputeService__Management__StateOperationContext___lambda_c65cea56f52a93d1c72f1dbbbf466c59___
0x1400b99f3  xorps   xmm1, xmm1
0x1400b99f6  movdqu  [rbp+4Fh+var_A8], xmm1
0x1400b99fb  lea     rdx, [rax+10h]
0x1400b99ff  mov     r8, rax
0x1400b9a02  lea     rcx, [rbp+4Fh+var_A8]
0x1400b9a06  call    ??$_Set_ptr_rep_and_enable_shared@VStateOperation@Management@ComputeService@@@?$shared_ptr@VStateOperation@Management@ComputeService@@@std@@AEAAXQEAVStateOperation@Management@ComputeService@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<ComputeService::Management::StateOperation>::_Set_ptr_rep_and_enable_shared<ComputeService::Management::StateOperation>(ComputeService::Management::StateOperation * const,std::_Ref_count_base * const)
0x1400b9a0b  nop
0x1400b9a0c  mov     rax, qword ptr [rbp+4Fh+var_A8]
0x1400b9a10  mov     dword ptr [rax+1B0h], 0Fh
0x1400b9a1a  lea     rdx, [rbp+4Fh+var_A8]
0x1400b9a1e  mov     rcx, r14
0x1400b9a21  call    ??0ActiveStateOperation@Management@ComputeService@@QEAA@AEBV?$shared_ptr@VStateOperation@Management@ComputeService@@@std@@@Z; ComputeService::Management::ActiveStateOperation::ActiveStateOperation(std::shared_ptr<ComputeService::Management::StateOperation> const &)
0x1400b9a26  nop
0x1400b9a27  mov     rbx, qword ptr [rbp+4Fh+var_A8+8]
0x1400b9a2b  or      r12d, 0FFFFFFFFh
0x1400b9a2f  test    rbx, rbx
0x1400b9a32  jz      short loc_1400B9A6C
0x1400b9a34  mov     eax, r12d
0x1400b9a37  lock xadd [rbx+8], eax
0x1400b9a3c  add     eax, r12d
0x1400b9a3f  jnz     short loc_1400B9A6C
0x1400b9a41  mov     rax, [rbx]
0x1400b9a44  mov     rcx, rbx
0x1400b9a47  mov     rax, [rax]
0x1400b9a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9a4f  mov     eax, r12d
0x1400b9a52  lock xadd [rbx+0Ch], eax
0x1400b9a57  add     eax, r12d
0x1400b9a5a  jnz     short loc_1400B9A6C
0x1400b9a5c  mov     rax, [rbx]
0x1400b9a5f  mov     rcx, rbx
0x1400b9a62  mov     rax, [rax+8]
0x1400b9a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9a6b  nop
0x1400b9a6c  mov     rcx, [rbp+4Fh+var_50]; this
0x1400b9a70  test    rcx, rcx
0x1400b9a73  jz      short loc_1400B9A7B
0x1400b9a75  call    ?Exit@RundownReference@Management@ComputeService@@QEAAXXZ; ComputeService::Management::RundownReference::Exit(void)
0x1400b9a7a  nop
0x1400b9a7b  test    rsi, rsi
0x1400b9a7e  jz      short loc_1400B9A8A
0x1400b9a80  mov     rcx, rsi; SRWLock
0x1400b9a83  call    cs:__imp_ReleaseSRWLockExclusive
0x1400b9a89  nop
0x1400b9a8a  lea     rcx, [rdi+10h]; this
0x1400b9a8e  call    ??1RetireServerOperation@Management@ComputeService@@QEAA@XZ; ComputeService::Management::RetireServerOperation::~RetireServerOperation(void)
0x1400b9a93  mov     rbx, [rdi+8]
0x1400b9a97  test    rbx, rbx
0x1400b9a9a  jz      short loc_1400B9AD4
0x1400b9a9c  mov     eax, r12d
0x1400b9a9f  lock xadd [rbx+8], eax
0x1400b9aa4  add     eax, r12d
0x1400b9aa7  jnz     short loc_1400B9AD4
0x1400b9aa9  mov     rax, [rbx]
0x1400b9aac  mov     rcx, rbx
0x1400b9aaf  mov     rax, [rax]
0x1400b9ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9ab7  mov     eax, r12d
0x1400b9aba  lock xadd [rbx+0Ch], eax
0x1400b9abf  add     eax, r12d
0x1400b9ac2  jnz     short loc_1400B9AD4
0x1400b9ac4  mov     rax, [rbx]
0x1400b9ac7  mov     rcx, rbx
0x1400b9aca  mov     rax, [rax+8]
0x1400b9ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9ad3  nop
0x1400b9ad4  mov     rcx, [r15]
0x1400b9ad7  test    rcx, rcx
0x1400b9ada  jz      short loc_1400B9AED
0x1400b9adc  mov     rax, [rcx]
0x1400b9adf  mov     edx, 1
0x1400b9ae4  mov     rax, [rax]
0x1400b9ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9aec  nop
0x1400b9aed  mov     rbx, [r13+8]
0x1400b9af1  test    rbx, rbx
0x1400b9af4  jz      short loc_1400B9B2D
0x1400b9af6  mov     eax, r12d
0x1400b9af9  lock xadd [rbx+8], eax
0x1400b9afe  add     eax, r12d
0x1400b9b01  jnz     short loc_1400B9B2D
0x1400b9b03  mov     rax, [rbx]
0x1400b9b06  mov     rcx, rbx
0x1400b9b09  mov     rax, [rax]
0x1400b9b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9b11  mov     edx, r12d
0x1400b9b14  lock xadd [rbx+0Ch], edx
0x1400b9b19  add     edx, r12d
0x1400b9b1c  jnz     short loc_1400B9B2D
0x1400b9b1e  mov     rdx, [rbx]
0x1400b9b21  mov     rcx, rbx
0x1400b9b24  mov     rax, [rdx+8]
0x1400b9b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b9b2d  mov     rax, r14
0x1400b9b30  mov     rcx, [rbp+4Fh+var_48]
0x1400b9b34  xor     rcx, rsp; StackCookie
0x1400b9b37  call    __security_check_cookie
0x1400b9b3c  add     rsp, 0C8h
0x1400b9b43  pop     r15
0x1400b9b45  pop     r14
0x1400b9b47  pop     r13
0x1400b9b49  pop     r12
0x1400b9b4b  pop     rdi
0x1400b9b4c  pop     rsi
0x1400b9b4d  pop     rbx
0x1400b9b4e  pop     rbp
0x1400b9b4f  retn
0x1400b9b50  mov     ecx, 0C0370105h
0x1400b9b55  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400b9b5a  mov     r9d, eax; char *
0x1400b9b5d  mov     rcx, [rbp+57h]; this
0x1400b9b61  mov     dword ptr [rsp+100h+var_D8], edx; char *
0x1400b9b65  lea     rax, aStateD; "state: %d"
0x1400b9b6c  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1400b9b71  lea     r8, aOnecoreVmCompu_34; "onecore\\vm\\compute\\management\\share"...
0x1400b9b78  mov     edx, 563h; void *
0x1400b9b7d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400b9b83  mov     r9d, 80070057h; char *
0x1400b9b89  lea     r8, aOnecoreVmCompu_34; "onecore\\vm\\compute\\management\\share"...
0x1400b9b90  mov     edx, 556h; void *
0x1400b9b95  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400b9b9b  mov     r9d, 80004001h; char *
0x1400b9ba1  lea     r8, aOnecoreVmCompu_32; "onecore\\vm\\compute\\management\\compu"...
0x1400b9ba8  mov     edx, 5Dh ; ']'; void *
0x1400b9bad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b9bb3  mov     r9d, 0C0370107h; char *
0x1400b9bb9  lea     r8, aOnecoreVmCompu_34; "onecore\\vm\\compute\\management\\share"...
0x1400b9bc0  mov     edx, 56Ch; void *
0x1400b9bc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b9bcb  mov     ecx, 0C0370105h
0x1400b9bd0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400b9bd5  mov     r9d, eax; char *
0x1400b9bd8  mov     rcx, [rbp+57h]; this
0x1400b9bdc  mov     dword ptr [rsp+100h+var_D8], edx; char *
0x1400b9be0  lea     rax, aStateD; "state: %d"
0x1400b9be7  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1400b9bec  lea     r8, aOnecoreVmCompu_34; "onecore\\vm\\compute\\management\\share"...
0x1400b9bf3  mov     edx, 563h; void *
0x1400b9bf8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400b9bfe  mov     rcx, [rbp+57h]; this
0x1400b9c02  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400b9c09  mov     edx, 0DBFh; void *
0x1400b9c0e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

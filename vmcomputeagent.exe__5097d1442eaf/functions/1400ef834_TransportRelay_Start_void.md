# TransportRelay::Start(void *)

- ea: `0x1400ef834`
- end: `0x1400efb98`
- name: `?Start@TransportRelay@@QEAAXPEAX@Z`
- size: `868`
- prototype: `void __fastcall(PVOID pv, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400f1f44`

## callees

- `0x1400056c4`
- `0x140006098`
- `0x1400068e0`
- `0x14000ddac`
- `0x14002e120`
- `0x1400341ac`
- `0x14003aa4c`
- `0x14004b95c`
- `0x140052990`
- `0x1400ef834`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400ef883`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400ef883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ef84e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ef84e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400efb36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400efb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400efb23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400efb23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400efb2e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400efb2e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400efb57`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400efb0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400efb0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ef854`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ef854`

## string_xrefs

- `0x1400efb66`: `onecore\vm\compute\common\transport\transportrelay.cpp`
- `0x1400efb86`: `onecore\vm\compute\common\transport\transportrelay.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TransportRelay::Start(RTL_SRWLOCK *pv, void *a2)
{
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rax
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rax
  TransportIoContext **v10; // r14
  volatile signed __int32 *v11; // rbx
  unsigned int Ptr; // ebx
  void *v13; // rsi
  unsigned __int64 v14; // rdx
  char *v15; // rax
  void *v16; // rcx
  __int64 v17; // rax
  TransportIoContext **v18; // r14
  volatile signed __int32 *v19; // rbx
  unsigned int v20; // ebx
  void *v21; // rsi
  unsigned __int64 v22; // rdx
  char *v23; // rax
  void *v24; // rcx
  struct _TP_WORK *ThreadpoolWork; // rsi
  const char *v26; // r9
  struct _TP_WORK *v27; // rbp
  DWORD LastError; // ebx
  unsigned int v29; // [rsp+20h] [rbp-68h]
  RTL_SRWLOCK *v30; // [rsp+30h] [rbp-58h] BYREF
  volatile signed __int32 *v31; // [rsp+38h] [rbp-50h]
  char v32; // [rsp+40h] [rbp-48h] BYREF
  char v33; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = pv + 15;
  AcquireSRWLockExclusive(pv + 15);
  LODWORD(v4[1].Ptr) = GetCurrentThreadId();
  v30 = v4;
  if ( LODWORD(pv[17].Ptr) != 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\transportrelay.cpp",
      (const char *)0x139F,
      v29);
  LODWORD(pv[17].Ptr) = 4;
  LODWORD(v4[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v4);
  v5 = std::make_shared<TransportIoContext,>(&v30);
  std::shared_ptr<TransportIoContext>::operator=(&pv[18], v5);
  v6 = v31;
  if ( v31 )
  {
    if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = std::make_shared<TransportIoContext,>(&v30);
  std::shared_ptr<TransportIoContext>::operator=(&pv[20], v7);
  v8 = v31;
  if ( v31 )
  {
    if ( !_InterlockedDecrement(v31 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)pv[18].Ptr + 56,
    1);
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)pv[20].Ptr + 56,
    1);
  v9 = std::make_shared<TransportIoContext,>(&v30);
  v10 = (TransportIoContext **)&pv[5];
  std::shared_ptr<TransportIoContext>::operator=(&pv[5], v9);
  v11 = v31;
  if ( v31 )
  {
    if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  TransportIoContext::Clear(*v10);
  Ptr = (unsigned int)pv[11].Ptr;
  v13 = operator new[](Ptr);
  memset_0(v13, 0, Ptr);
  v15 = (char *)*v10 + 24;
  if ( v15 == &v32 )
  {
    if ( v13 )
    {
      v16 = v13;
LABEL_19:
      operator delete(v16, v14);
    }
  }
  else
  {
    v16 = *(void **)v15;
    *(_QWORD *)v15 = v13;
    if ( v16 )
      goto LABEL_19;
  }
  *((_DWORD *)*v10 + 8) = pv[11].Ptr;
  *((_DWORD *)*v10 + 10) = *((_DWORD *)*v10 + 8);
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)*v10 + 56,
    1);
  v17 = std::make_shared<TransportIoContext,>(&v30);
  v18 = (TransportIoContext **)&pv[7];
  std::shared_ptr<TransportIoContext>::operator=(&pv[7], v17);
  v19 = v31;
  if ( v31 )
  {
    if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  TransportIoContext::Clear(*v18);
  v20 = (unsigned int)pv[11].Ptr;
  v21 = operator new[](v20);
  memset_0(v21, 0, v20);
  v23 = (char *)*v18 + 24;
  if ( v23 == &v33 )
  {
    if ( !v21 )
      goto LABEL_30;
    v24 = v21;
  }
  else
  {
    v24 = *(void **)v23;
    *(_QWORD *)v23 = v21;
    if ( !v24 )
      goto LABEL_30;
  }
  operator delete(v24, v22);
LABEL_30:
  *((_DWORD *)*v18 + 8) = pv[11].Ptr;
  *((_DWORD *)*v18 + 10) = *((_DWORD *)*v18 + 8);
  _create___event_t_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__Uerr_exception_policy_2__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)*v18 + 56,
    1);
  pv[14].Ptr = a2;
  ThreadpoolWork = CreateThreadpoolWork(TransportRelay::WorkerThread, pv, 0);
  v27 = (struct _TP_WORK *)pv[22].Ptr;
  if ( v27 )
  {
    LastError = GetLastError();
    CloseThreadpoolWork(v27);
    SetLastError(LastError);
  }
  pv[22].Ptr = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\transportrelay.cpp",
      v26);
  SubmitThreadpoolWork(ThreadpoolWork);
}

```

## disassembly

```asm
0x1400ef834  push    rbx
0x1400ef836  push    rbp
0x1400ef837  push    rsi
0x1400ef838  push    rdi
0x1400ef839  push    r14
0x1400ef83b  push    r15
0x1400ef83d  sub     rsp, 58h
0x1400ef841  mov     rbp, rdx
0x1400ef844  mov     rdi, rcx
0x1400ef847  lea     rbx, [rcx+78h]
0x1400ef84b  mov     rcx, rbx; SRWLock
0x1400ef84e  call    cs:__imp_AcquireSRWLockExclusive
0x1400ef854  call    cs:__imp_GetCurrentThreadId
0x1400ef85a  mov     [rbx+8], eax
0x1400ef85d  mov     [rsp+88h+var_58], rbx
0x1400ef862  cmp     dword ptr [rdi+88h], 3
0x1400ef869  jnz     loc_1400EFB78
0x1400ef86f  mov     dword ptr [rdi+88h], 4
0x1400ef879  mov     dword ptr [rbx+8], 0
0x1400ef880  mov     rcx, rbx; SRWLock
0x1400ef883  call    cs:__imp_ReleaseSRWLockExclusive
0x1400ef889  lea     rcx, [rsp+88h+var_58]
0x1400ef88e  call    ??$make_shared@VTransportIoContext@@$$V@std@@YA?AV?$shared_ptr@VTransportIoContext@@@0@XZ; std::make_shared<TransportIoContext,>(void)
0x1400ef893  lea     r14, [rdi+90h]
0x1400ef89a  mov     rdx, rax
0x1400ef89d  mov     rcx, r14
0x1400ef8a0  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x1400ef8a5  or      r15d, 0FFFFFFFFh
0x1400ef8a9  mov     rbx, [rsp+88h+var_50]
0x1400ef8ae  test    rbx, rbx
0x1400ef8b1  jz      short loc_1400EF8EA
0x1400ef8b3  mov     eax, r15d
0x1400ef8b6  lock xadd [rbx+8], eax
0x1400ef8bb  add     eax, r15d
0x1400ef8be  jnz     short loc_1400EF8EA
0x1400ef8c0  mov     rax, [rbx]
0x1400ef8c3  mov     rcx, rbx
0x1400ef8c6  mov     rax, [rax]
0x1400ef8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef8ce  mov     eax, r15d
0x1400ef8d1  lock xadd [rbx+0Ch], eax
0x1400ef8d6  add     eax, r15d
0x1400ef8d9  jnz     short loc_1400EF8EA
0x1400ef8db  mov     rax, [rbx]
0x1400ef8de  mov     rcx, rbx
0x1400ef8e1  mov     rax, [rax+8]
0x1400ef8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef8ea  lea     rcx, [rsp+88h+var_58]
0x1400ef8ef  call    ??$make_shared@VTransportIoContext@@$$V@std@@YA?AV?$shared_ptr@VTransportIoContext@@@0@XZ; std::make_shared<TransportIoContext,>(void)
0x1400ef8f4  lea     rsi, [rdi+0A0h]
0x1400ef8fb  mov     rdx, rax
0x1400ef8fe  mov     rcx, rsi
0x1400ef901  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x1400ef906  mov     rbx, [rsp+88h+var_50]
0x1400ef90b  test    rbx, rbx
0x1400ef90e  jz      short loc_1400EF947
0x1400ef910  mov     eax, r15d
0x1400ef913  lock xadd [rbx+8], eax
0x1400ef918  add     eax, r15d
0x1400ef91b  jnz     short loc_1400EF947
0x1400ef91d  mov     rax, [rbx]
0x1400ef920  mov     rcx, rbx
0x1400ef923  mov     rax, [rax]
0x1400ef926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef92b  mov     eax, r15d
0x1400ef92e  lock xadd [rbx+0Ch], eax
0x1400ef933  add     eax, r15d
0x1400ef936  jnz     short loc_1400EF947
0x1400ef938  mov     rax, [rbx]
0x1400ef93b  mov     rcx, rbx
0x1400ef93e  mov     rax, [rax+8]
0x1400ef942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef947  mov     rcx, [r14]
0x1400ef94a  add     rcx, 38h ; '8'
0x1400ef94e  mov     edx, 1
0x1400ef953  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400ef958  mov     rcx, [rsi]
0x1400ef95b  add     rcx, 38h ; '8'
0x1400ef95f  mov     edx, 1
0x1400ef964  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400ef969  lea     rcx, [rsp+88h+var_58]
0x1400ef96e  call    ??$make_shared@VTransportIoContext@@$$V@std@@YA?AV?$shared_ptr@VTransportIoContext@@@0@XZ; std::make_shared<TransportIoContext,>(void)
0x1400ef973  lea     r14, [rdi+28h]
0x1400ef977  mov     rdx, rax
0x1400ef97a  mov     rcx, r14
0x1400ef97d  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x1400ef982  mov     rbx, [rsp+88h+var_50]
0x1400ef987  test    rbx, rbx
0x1400ef98a  jz      short loc_1400EF9C3
0x1400ef98c  mov     eax, r15d
0x1400ef98f  lock xadd [rbx+8], eax
0x1400ef994  add     eax, r15d
0x1400ef997  jnz     short loc_1400EF9C3
0x1400ef999  mov     rax, [rbx]
0x1400ef99c  mov     rcx, rbx
0x1400ef99f  mov     rax, [rax]
0x1400ef9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef9a7  mov     eax, r15d
0x1400ef9aa  lock xadd [rbx+0Ch], eax
0x1400ef9af  add     eax, r15d
0x1400ef9b2  jnz     short loc_1400EF9C3
0x1400ef9b4  mov     rax, [rbx]
0x1400ef9b7  mov     rcx, rbx
0x1400ef9ba  mov     rax, [rax+8]
0x1400ef9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ef9c3  mov     rcx, [r14]; this
0x1400ef9c6  call    ?Clear@TransportIoContext@@QEAAXXZ; TransportIoContext::Clear(void)
0x1400ef9cb  mov     ebx, [rdi+58h]
0x1400ef9ce  mov     ecx, ebx; unsigned __int64
0x1400ef9d0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400ef9d5  mov     rsi, rax
0x1400ef9d8  mov     r8d, ebx; Size
0x1400ef9db  xor     edx, edx; Val
0x1400ef9dd  mov     rcx, rax; void *
0x1400ef9e0  call    memset_0
0x1400ef9e5  mov     rax, [r14]
0x1400ef9e8  add     rax, 18h
0x1400ef9ec  lea     rcx, [rsp+88h+var_48]
0x1400ef9f1  cmp     rax, rcx
0x1400ef9f4  jz      short loc_1400EFA03
0x1400ef9f6  mov     rcx, [rax]
0x1400ef9f9  mov     [rax], rsi
0x1400ef9fc  test    rcx, rcx
0x1400ef9ff  jz      short loc_1400EFA10
0x1400efa01  jmp     short loc_1400EFA0B
0x1400efa03  test    rsi, rsi
0x1400efa06  jz      short loc_1400EFA10
0x1400efa08  mov     rcx, rsi; void *
0x1400efa0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400efa10  mov     rcx, [r14]
0x1400efa13  mov     eax, [rdi+58h]
0x1400efa16  mov     [rcx+20h], eax
0x1400efa19  mov     rcx, [r14]
0x1400efa1c  mov     eax, [rcx+20h]
0x1400efa1f  mov     [rcx+28h], eax
0x1400efa22  mov     rcx, [r14]
0x1400efa25  add     rcx, 38h ; '8'
0x1400efa29  mov     edx, 1
0x1400efa2e  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400efa33  lea     rcx, [rsp+88h+var_58]
0x1400efa38  call    ??$make_shared@VTransportIoContext@@$$V@std@@YA?AV?$shared_ptr@VTransportIoContext@@@0@XZ; std::make_shared<TransportIoContext,>(void)
0x1400efa3d  lea     r14, [rdi+38h]
0x1400efa41  mov     rdx, rax
0x1400efa44  mov     rcx, r14
0x1400efa47  call    ??4?$shared_ptr@VTransportIoContext@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<TransportIoContext>::operator=(std::shared_ptr<TransportIoContext> &&)
0x1400efa4c  mov     rbx, [rsp+88h+var_50]
0x1400efa51  test    rbx, rbx
0x1400efa54  jz      short loc_1400EFA8D
0x1400efa56  mov     eax, r15d
0x1400efa59  lock xadd [rbx+8], eax
0x1400efa5e  add     eax, r15d
0x1400efa61  jnz     short loc_1400EFA8D
0x1400efa63  mov     rax, [rbx]
0x1400efa66  mov     rcx, rbx
0x1400efa69  mov     rax, [rax]
0x1400efa6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400efa71  mov     eax, r15d
0x1400efa74  lock xadd [rbx+0Ch], eax
0x1400efa79  add     eax, r15d
0x1400efa7c  jnz     short loc_1400EFA8D
0x1400efa7e  mov     rax, [rbx]
0x1400efa81  mov     rcx, rbx
0x1400efa84  mov     rax, [rax+8]
0x1400efa88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400efa8d  mov     rcx, [r14]; this
0x1400efa90  call    ?Clear@TransportIoContext@@QEAAXXZ; TransportIoContext::Clear(void)
0x1400efa95  mov     ebx, [rdi+58h]
0x1400efa98  mov     ecx, ebx; unsigned __int64
0x1400efa9a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400efa9f  mov     rsi, rax
0x1400efaa2  mov     r8d, ebx; Size
0x1400efaa5  xor     edx, edx; Val
0x1400efaa7  mov     rcx, rax; void *
0x1400efaaa  call    memset_0
0x1400efaaf  mov     rax, [r14]
0x1400efab2  add     rax, 18h
0x1400efab6  lea     rcx, [rsp+88h+var_40]
0x1400efabb  cmp     rax, rcx
0x1400efabe  jz      short loc_1400EFACD
0x1400efac0  mov     rcx, [rax]
0x1400efac3  mov     [rax], rsi
0x1400efac6  test    rcx, rcx
0x1400efac9  jz      short loc_1400EFADA
0x1400efacb  jmp     short loc_1400EFAD5
0x1400efacd  test    rsi, rsi
0x1400efad0  jz      short loc_1400EFADA
0x1400efad2  mov     rcx, rsi; void *
0x1400efad5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400efada  mov     rcx, [r14]
0x1400efadd  mov     eax, [rdi+58h]
0x1400efae0  mov     [rcx+20h], eax
0x1400efae3  mov     rcx, [r14]
0x1400efae6  mov     eax, [rcx+20h]
0x1400efae9  mov     [rcx+28h], eax
0x1400efaec  mov     rcx, [r14]
0x1400efaef  add     rcx, 38h ; '8'
0x1400efaf3  mov     edx, 1
0x1400efaf8  call    ?create@?$event_t@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@Uerr_exception_policy@2@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400efafd  mov     [rdi+70h], rbp
0x1400efb01  xor     r8d, r8d; pcbe
0x1400efb04  mov     rdx, rdi; pv
0x1400efb07  lea     rcx, ?WorkerThread@TransportRelay@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1400efb0e  call    cs:__imp_CreateThreadpoolWork
0x1400efb14  mov     rsi, rax
0x1400efb17  mov     rbp, [rdi+0B0h]
0x1400efb1e  test    rbp, rbp
0x1400efb21  jz      short loc_1400EFB3C
0x1400efb23  call    cs:__imp_GetLastError
0x1400efb29  mov     ebx, eax
0x1400efb2b  mov     rcx, rbp; pwk
0x1400efb2e  call    cs:__imp_CloseThreadpoolWork
0x1400efb34  mov     ecx, ebx; dwErrCode
0x1400efb36  call    cs:__imp_SetLastError
0x1400efb3c  mov     [rdi+0B0h], rsi
0x1400efb43  test    rsi, rsi
0x1400efb46  jz      short loc_1400EFB5E
0x1400efb48  mov     rcx, rsi
0x1400efb4b  add     rsp, 58h
0x1400efb4f  pop     r15
0x1400efb51  pop     r14
0x1400efb53  pop     rdi
0x1400efb54  pop     rsi
0x1400efb55  pop     rbp
0x1400efb56  pop     rbx
0x1400efb57  jmp     cs:__imp_SubmitThreadpoolWork
0x1400efb5e  mov     rcx, [rsp+88h]; this
0x1400efb66  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\common\\transport"...
0x1400efb6d  mov     edx, 102h; void *
0x1400efb72  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400efb78  mov     rcx, [rsp+88h]; this
0x1400efb80  mov     r9d, 139Fh; char *
0x1400efb86  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\common\\transport"...
0x1400efb8d  mov     edx, 0DAh; void *
0x1400efb92  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

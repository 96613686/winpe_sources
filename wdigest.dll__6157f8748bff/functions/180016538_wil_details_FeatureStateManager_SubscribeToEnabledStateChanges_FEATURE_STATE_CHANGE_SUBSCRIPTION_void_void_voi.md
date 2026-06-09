# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180016538`
- end: `0x1800165f3`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180016a80`

## callees

- `0x180011354`
- `0x180012014`
- `0x180016538`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016568`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016568`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800165e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800165e0`

## string_xrefs

- `0x18001658e`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rdi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    if ( this[18].Ptr
      || ((NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification,
           this[18].Ptr = 0,
           NtDllProcedureAddress)
       || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
           (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0)
        ? (v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))NtDllProcedureAddress)(
                   _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
                   this,
                   0,
                   &this[18]))
        : (v10 = -1073741511),
          !v10) )
    {
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x180016538  push    rbx
0x18001653a  push    rbp
0x18001653b  push    rsi
0x18001653c  push    rdi
0x18001653d  push    r14
0x18001653f  push    r15
0x180016541  sub     rsp, 38h
0x180016545  mov     qword ptr [rdx], 0
0x18001654c  mov     rbp, r9
0x18001654f  cmp     byte ptr [rcx], 0
0x180016552  mov     r15, r8
0x180016555  mov     r14, rdx
0x180016558  mov     rbx, rcx
0x18001655b  jz      loc_1800165E6
0x180016561  lea     rdi, [rcx+20h]
0x180016565  mov     rcx, rdi; SRWLock
0x180016568  call    cs:__imp_AcquireSRWLockExclusive
0x18001656e  lea     rsi, [rbx+90h]
0x180016575  cmp     qword ptr [rsi], 0
0x180016579  jnz     short loc_1800165C6
0x18001657b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180016582  mov     qword ptr [rsi], 0
0x180016589  test    rax, rax
0x18001658c  jnz     short loc_1800165AD
0x18001658e  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180016595  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001659a  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800165a1  test    rax, rax
0x1800165a4  jnz     short loc_1800165AD
0x1800165a6  mov     eax, 0C0000139h
0x1800165ab  jmp     short loc_1800165C2
0x1800165ad  mov     r9, rsi
0x1800165b0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800165b7  xor     r8d, r8d
0x1800165ba  mov     rdx, rbx
0x1800165bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165c2  test    eax, eax
0x1800165c4  jnz     short loc_1800165D8
0x1800165c6  lea     rcx, [rbx+48h]; this
0x1800165ca  mov     r9, rbp; void *
0x1800165cd  mov     r8, r15; void (*)(void *)
0x1800165d0  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800165d3  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800165d8  test    rdi, rdi
0x1800165db  jz      short loc_1800165E6
0x1800165dd  mov     rcx, rdi; SRWLock
0x1800165e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800165e6  add     rsp, 38h
0x1800165ea  pop     r15
0x1800165ec  pop     r14
0x1800165ee  pop     rdi
0x1800165ef  pop     rsi
0x1800165f0  pop     rbp
0x1800165f1  pop     rbx
0x1800165f2  retn
```

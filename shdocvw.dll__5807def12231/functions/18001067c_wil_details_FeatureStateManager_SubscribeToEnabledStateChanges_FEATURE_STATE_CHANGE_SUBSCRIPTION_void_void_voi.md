# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001067c`
- end: `0x180010737`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `187`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180010930`

## callees

- `0x180003530`
- `0x180004b90`
- `0x18001067c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800106ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800106ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010724`

## string_xrefs

- `0x1800106d2`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001067c  push    rbx
0x18001067e  push    rbp
0x18001067f  push    rsi
0x180010680  push    rdi
0x180010681  push    r14
0x180010683  push    r15
0x180010685  sub     rsp, 38h
0x180010689  mov     qword ptr [rdx], 0
0x180010690  mov     rbp, r9
0x180010693  cmp     byte ptr [rcx], 0
0x180010696  mov     r15, r8
0x180010699  mov     r14, rdx
0x18001069c  mov     rbx, rcx
0x18001069f  jz      loc_18001072A
0x1800106a5  lea     rdi, [rcx+20h]
0x1800106a9  mov     rcx, rdi; SRWLock
0x1800106ac  call    cs:__imp_AcquireSRWLockExclusive
0x1800106b2  lea     rsi, [rbx+90h]
0x1800106b9  cmp     qword ptr [rsi], 0
0x1800106bd  jnz     short loc_18001070A
0x1800106bf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800106c6  mov     qword ptr [rsi], 0
0x1800106cd  test    rax, rax
0x1800106d0  jnz     short loc_1800106F1
0x1800106d2  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800106d9  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800106de  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800106e5  test    rax, rax
0x1800106e8  jnz     short loc_1800106F1
0x1800106ea  mov     eax, 0C0000139h
0x1800106ef  jmp     short loc_180010706
0x1800106f1  mov     r9, rsi
0x1800106f4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800106fb  xor     r8d, r8d
0x1800106fe  mov     rdx, rbx
0x180010701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010706  test    eax, eax
0x180010708  jnz     short loc_18001071C
0x18001070a  lea     rcx, [rbx+48h]; this
0x18001070e  mov     r9, rbp; void *
0x180010711  mov     r8, r15; void (*)(void *)
0x180010714  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180010717  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001071c  test    rdi, rdi
0x18001071f  jz      short loc_18001072A
0x180010721  mov     rcx, rdi; SRWLock
0x180010724  call    cs:__imp_ReleaseSRWLockExclusive
0x18001072a  add     rsp, 38h
0x18001072e  pop     r15
0x180010730  pop     r14
0x180010732  pop     rdi
0x180010733  pop     rsi
0x180010734  pop     rbp
0x180010735  pop     rbx
0x180010736  retn
```

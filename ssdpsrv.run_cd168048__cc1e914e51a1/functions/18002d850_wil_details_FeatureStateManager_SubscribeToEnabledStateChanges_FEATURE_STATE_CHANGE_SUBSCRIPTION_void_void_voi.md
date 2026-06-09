# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002d850`
- end: `0x18002d91e`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `206`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002df40`

## callees

- `0x180024d20`
- `0x18002d850`
- `0x18002da24`
- `0x18002e5fc`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d885`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d885`

## string_xrefs

- `0x18002d8b6`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v10; // eax
  RTL_SRWLOCK *v11; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    v11 = v8;
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18002d850  mov     [rsp+arg_8], rbx
0x18002d855  mov     [rsp+arg_10], rbp
0x18002d85a  push    rsi
0x18002d85b  push    rdi
0x18002d85c  push    r14
0x18002d85e  sub     rsp, 30h
0x18002d862  mov     qword ptr [rdx], 0
0x18002d869  mov     rbp, r9
0x18002d86c  cmp     byte ptr [rcx], 0
0x18002d86f  mov     r14, r8
0x18002d872  mov     rsi, rdx
0x18002d875  mov     rdi, rcx
0x18002d878  jz      loc_18002D90A
0x18002d87e  lea     rbx, [rcx+20h]
0x18002d882  mov     rcx, rbx; SRWLock
0x18002d885  call    cs:__imp_AcquireSRWLockExclusive
0x18002d88c  nop     dword ptr [rax+rax+00h]
0x18002d891  mov     [rsp+48h+arg_0], rbx
0x18002d896  lea     rbx, [rdi+90h]
0x18002d89d  cmp     qword ptr [rbx], 0
0x18002d8a1  jnz     short loc_18002D8EE
0x18002d8a3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002d8aa  mov     qword ptr [rbx], 0
0x18002d8b1  test    rax, rax
0x18002d8b4  jnz     short loc_18002D8D5
0x18002d8b6  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002d8bd  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002d8c2  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002d8c9  test    rax, rax
0x18002d8cc  jnz     short loc_18002D8D5
0x18002d8ce  mov     eax, 0C0000139h
0x18002d8d3  jmp     short loc_18002D8EA
0x18002d8d5  mov     r9, rbx
0x18002d8d8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002d8df  xor     r8d, r8d
0x18002d8e2  mov     rdx, rdi
0x18002d8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8ea  test    eax, eax
0x18002d8ec  jnz     short loc_18002D900
0x18002d8ee  lea     rcx, [rdi+48h]; this
0x18002d8f2  mov     r9, rbp; void *
0x18002d8f5  mov     r8, r14; void (*)(void *)
0x18002d8f8  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002d8fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002d900  lea     rcx, [rsp+48h+arg_0]
0x18002d905  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002d90a  mov     rbx, [rsp+48h+arg_8]
0x18002d90f  mov     rbp, [rsp+48h+arg_10]
0x18002d914  add     rsp, 30h
0x18002d918  pop     r14
0x18002d91a  pop     rdi
0x18002d91b  pop     rsi
0x18002d91c  retn
```

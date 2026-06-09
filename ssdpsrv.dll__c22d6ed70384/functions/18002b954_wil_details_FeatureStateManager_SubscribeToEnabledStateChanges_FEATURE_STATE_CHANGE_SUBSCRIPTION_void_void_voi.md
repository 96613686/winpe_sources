# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002b954`
- end: `0x18002ba1b`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bfc0`

## callees

- `0x1800232a8`
- `0x18002b954`
- `0x18002bb18`
- `0x18002c630`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b989`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b989`

## string_xrefs

- `0x18002b9b4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002b954  mov     [rsp+arg_8], rbx
0x18002b959  mov     [rsp+arg_10], rbp
0x18002b95e  push    rsi
0x18002b95f  push    rdi
0x18002b960  push    r14
0x18002b962  sub     rsp, 30h
0x18002b966  mov     qword ptr [rdx], 0
0x18002b96d  mov     rbp, r9
0x18002b970  cmp     byte ptr [rcx], 0
0x18002b973  mov     r14, r8
0x18002b976  mov     rsi, rdx
0x18002b979  mov     rdi, rcx
0x18002b97c  jz      loc_18002BA08
0x18002b982  lea     rbx, [rcx+20h]
0x18002b986  mov     rcx, rbx; SRWLock
0x18002b989  call    cs:__imp_AcquireSRWLockExclusive
0x18002b98f  mov     [rsp+48h+arg_0], rbx
0x18002b994  lea     rbx, [rdi+90h]
0x18002b99b  cmp     qword ptr [rbx], 0
0x18002b99f  jnz     short loc_18002B9EC
0x18002b9a1  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002b9a8  mov     qword ptr [rbx], 0
0x18002b9af  test    rax, rax
0x18002b9b2  jnz     short loc_18002B9D3
0x18002b9b4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002b9bb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b9c0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002b9c7  test    rax, rax
0x18002b9ca  jnz     short loc_18002B9D3
0x18002b9cc  mov     eax, 0C0000139h
0x18002b9d1  jmp     short loc_18002B9E8
0x18002b9d3  mov     r9, rbx
0x18002b9d6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002b9dd  xor     r8d, r8d
0x18002b9e0  mov     rdx, rdi
0x18002b9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9e8  test    eax, eax
0x18002b9ea  jnz     short loc_18002B9FE
0x18002b9ec  lea     rcx, [rdi+48h]; this
0x18002b9f0  mov     r9, rbp; void *
0x18002b9f3  mov     r8, r14; void (*)(void *)
0x18002b9f6  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002b9f9  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002b9fe  lea     rcx, [rsp+48h+arg_0]
0x18002ba03  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ba08  mov     rbx, [rsp+48h+arg_8]
0x18002ba0d  mov     rbp, [rsp+48h+arg_10]
0x18002ba12  add     rsp, 30h
0x18002ba16  pop     r14
0x18002ba18  pop     rdi
0x18002ba19  pop     rsi
0x18002ba1a  retn
```

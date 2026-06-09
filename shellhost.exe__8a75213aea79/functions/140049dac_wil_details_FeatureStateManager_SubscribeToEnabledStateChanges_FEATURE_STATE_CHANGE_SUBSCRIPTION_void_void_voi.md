# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140049dac`
- end: `0x140049e73`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14004a2c0`

## callees

- `0x14000a814`
- `0x140049dac`
- `0x140049f70`
- `0x14004b6e0`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140049de1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140049de1`

## string_xrefs

- `0x140049e0c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140049dac  mov     [rsp+arg_8], rbx
0x140049db1  mov     [rsp+arg_10], rbp
0x140049db6  push    rsi
0x140049db7  push    rdi
0x140049db8  push    r14
0x140049dba  sub     rsp, 30h
0x140049dbe  mov     qword ptr [rdx], 0
0x140049dc5  mov     rbp, r9
0x140049dc8  cmp     byte ptr [rcx], 0
0x140049dcb  mov     r14, r8
0x140049dce  mov     rsi, rdx
0x140049dd1  mov     rdi, rcx
0x140049dd4  jz      loc_140049E60
0x140049dda  lea     rbx, [rcx+20h]
0x140049dde  mov     rcx, rbx; SRWLock
0x140049de1  call    cs:__imp_AcquireSRWLockExclusive
0x140049de7  mov     [rsp+48h+arg_0], rbx
0x140049dec  lea     rbx, [rdi+90h]
0x140049df3  cmp     qword ptr [rbx], 0
0x140049df7  jnz     short loc_140049E44
0x140049df9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140049e00  mov     qword ptr [rbx], 0
0x140049e07  test    rax, rax
0x140049e0a  jnz     short loc_140049E2B
0x140049e0c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140049e13  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140049e18  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140049e1f  test    rax, rax
0x140049e22  jnz     short loc_140049E2B
0x140049e24  mov     eax, 0C0000139h
0x140049e29  jmp     short loc_140049E40
0x140049e2b  mov     r9, rbx
0x140049e2e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140049e35  xor     r8d, r8d
0x140049e38  mov     rdx, rdi
0x140049e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049e40  test    eax, eax
0x140049e42  jnz     short loc_140049E56
0x140049e44  lea     rcx, [rdi+48h]; this
0x140049e48  mov     r9, rbp; void *
0x140049e4b  mov     r8, r14; void (*)(void *)
0x140049e4e  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140049e51  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140049e56  lea     rcx, [rsp+48h+arg_0]
0x140049e5b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140049e60  mov     rbx, [rsp+48h+arg_8]
0x140049e65  mov     rbp, [rsp+48h+arg_10]
0x140049e6a  add     rsp, 30h
0x140049e6e  pop     r14
0x140049e70  pop     rdi
0x140049e71  pop     rsi
0x140049e72  retn
```

# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18002bb6c`
- end: `0x18002bc33`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bf50`

## callees

- `0x18001f5f0`
- `0x180022d58`
- `0x18002bb6c`
- `0x18002bd30`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bba1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bba1`

## string_xrefs

- `0x18002bbcc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002bb6c  mov     [rsp+arg_8], rbx
0x18002bb71  mov     [rsp+arg_10], rbp
0x18002bb76  push    rsi
0x18002bb77  push    rdi
0x18002bb78  push    r14
0x18002bb7a  sub     rsp, 30h
0x18002bb7e  mov     qword ptr [rdx], 0
0x18002bb85  mov     rbp, r9
0x18002bb88  cmp     byte ptr [rcx], 0
0x18002bb8b  mov     r14, r8
0x18002bb8e  mov     rsi, rdx
0x18002bb91  mov     rdi, rcx
0x18002bb94  jz      loc_18002BC20
0x18002bb9a  lea     rbx, [rcx+20h]
0x18002bb9e  mov     rcx, rbx; SRWLock
0x18002bba1  call    cs:__imp_AcquireSRWLockExclusive
0x18002bba7  mov     [rsp+48h+arg_0], rbx
0x18002bbac  lea     rbx, [rdi+90h]
0x18002bbb3  cmp     qword ptr [rbx], 0
0x18002bbb7  jnz     short loc_18002BC04
0x18002bbb9  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002bbc0  mov     qword ptr [rbx], 0
0x18002bbc7  test    rax, rax
0x18002bbca  jnz     short loc_18002BBEB
0x18002bbcc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002bbd3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002bbd8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002bbdf  test    rax, rax
0x18002bbe2  jnz     short loc_18002BBEB
0x18002bbe4  mov     eax, 0C0000139h
0x18002bbe9  jmp     short loc_18002BC00
0x18002bbeb  mov     r9, rbx
0x18002bbee  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18002bbf5  xor     r8d, r8d
0x18002bbf8  mov     rdx, rdi
0x18002bbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc00  test    eax, eax
0x18002bc02  jnz     short loc_18002BC16
0x18002bc04  lea     rcx, [rdi+48h]; this
0x18002bc08  mov     r9, rbp; void *
0x18002bc0b  mov     r8, r14; void (*)(void *)
0x18002bc0e  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002bc11  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18002bc16  lea     rcx, [rsp+48h+arg_0]
0x18002bc1b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bc20  mov     rbx, [rsp+48h+arg_8]
0x18002bc25  mov     rbp, [rsp+48h+arg_10]
0x18002bc2a  add     rsp, 30h
0x18002bc2e  pop     r14
0x18002bc30  pop     rdi
0x18002bc31  pop     rsi
0x18002bc32  retn
```

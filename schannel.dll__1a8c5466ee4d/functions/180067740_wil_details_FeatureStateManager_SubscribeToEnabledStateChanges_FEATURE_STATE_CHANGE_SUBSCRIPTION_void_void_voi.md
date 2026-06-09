# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180067740`
- end: `0x180067807`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `199`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180067b00`

## callees

- `0x18004621c`
- `0x180049d34`
- `0x18004b974`
- `0x180067740`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180067775`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180067775`

## string_xrefs

- `0x1800677a0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180067740  mov     [rsp+arg_8], rbx
0x180067745  mov     [rsp+arg_10], rbp
0x18006774a  push    rsi
0x18006774b  push    rdi
0x18006774c  push    r14
0x18006774e  sub     rsp, 30h
0x180067752  mov     qword ptr [rdx], 0
0x180067759  mov     rbp, r9
0x18006775c  cmp     byte ptr [rcx], 0
0x18006775f  mov     r14, r8
0x180067762  mov     rsi, rdx
0x180067765  mov     rdi, rcx
0x180067768  jz      loc_1800677F4
0x18006776e  lea     rbx, [rcx+20h]
0x180067772  mov     rcx, rbx; SRWLock
0x180067775  call    cs:__imp_AcquireSRWLockExclusive
0x18006777b  mov     [rsp+48h+arg_0], rbx
0x180067780  lea     rbx, [rdi+90h]
0x180067787  cmp     qword ptr [rbx], 0
0x18006778b  jnz     short loc_1800677D8
0x18006778d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180067794  mov     qword ptr [rbx], 0
0x18006779b  test    rax, rax
0x18006779e  jnz     short loc_1800677BF
0x1800677a0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800677a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800677ac  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800677b3  test    rax, rax
0x1800677b6  jnz     short loc_1800677BF
0x1800677b8  mov     eax, 0C0000139h
0x1800677bd  jmp     short loc_1800677D4
0x1800677bf  mov     r9, rbx
0x1800677c2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800677c9  xor     r8d, r8d
0x1800677cc  mov     rdx, rdi
0x1800677cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800677d4  test    eax, eax
0x1800677d6  jnz     short loc_1800677EA
0x1800677d8  lea     rcx, [rdi+48h]; this
0x1800677dc  mov     r9, rbp; void *
0x1800677df  mov     r8, r14; void (*)(void *)
0x1800677e2  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800677e5  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800677ea  lea     rcx, [rsp+48h+arg_0]
0x1800677ef  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800677f4  mov     rbx, [rsp+48h+arg_8]
0x1800677f9  mov     rbp, [rsp+48h+arg_10]
0x1800677fe  add     rsp, 30h
0x180067802  pop     r14
0x180067804  pop     rdi
0x180067805  pop     rsi
0x180067806  retn
```

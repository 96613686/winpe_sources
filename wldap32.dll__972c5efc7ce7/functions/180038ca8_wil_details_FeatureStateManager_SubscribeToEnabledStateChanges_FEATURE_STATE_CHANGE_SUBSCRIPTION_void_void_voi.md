# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180038ca8`
- end: `0x180038d76`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `206`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180039330`

## callees

- `0x18002b440`
- `0x180031a10`
- `0x180038ca8`
- `0x180038e7c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038cdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038cdd`

## string_xrefs

- `0x180038d0e`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180038ca8  mov     [rsp+arg_8], rbx
0x180038cad  mov     [rsp+arg_10], rbp
0x180038cb2  push    rsi
0x180038cb3  push    rdi
0x180038cb4  push    r14
0x180038cb6  sub     rsp, 30h
0x180038cba  mov     qword ptr [rdx], 0
0x180038cc1  mov     rbp, r9
0x180038cc4  cmp     byte ptr [rcx], 0
0x180038cc7  mov     r14, r8
0x180038cca  mov     rsi, rdx
0x180038ccd  mov     rdi, rcx
0x180038cd0  jz      loc_180038D62
0x180038cd6  lea     rbx, [rcx+20h]
0x180038cda  mov     rcx, rbx; SRWLock
0x180038cdd  call    cs:__imp_AcquireSRWLockExclusive
0x180038ce4  nop     dword ptr [rax+rax+00h]
0x180038ce9  mov     [rsp+48h+arg_0], rbx
0x180038cee  lea     rbx, [rdi+90h]
0x180038cf5  cmp     qword ptr [rbx], 0
0x180038cf9  jnz     short loc_180038D46
0x180038cfb  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180038d02  mov     qword ptr [rbx], 0
0x180038d09  test    rax, rax
0x180038d0c  jnz     short loc_180038D2D
0x180038d0e  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180038d15  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180038d1a  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180038d21  test    rax, rax
0x180038d24  jnz     short loc_180038D2D
0x180038d26  mov     eax, 0C0000139h
0x180038d2b  jmp     short loc_180038D42
0x180038d2d  mov     r9, rbx
0x180038d30  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180038d37  xor     r8d, r8d
0x180038d3a  mov     rdx, rdi
0x180038d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d42  test    eax, eax
0x180038d44  jnz     short loc_180038D58
0x180038d46  lea     rcx, [rdi+48h]; this
0x180038d4a  mov     r9, rbp; void *
0x180038d4d  mov     r8, r14; void (*)(void *)
0x180038d50  mov     rdx, rsi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180038d53  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180038d58  lea     rcx, [rsp+48h+arg_0]
0x180038d5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180038d62  mov     rbx, [rsp+48h+arg_8]
0x180038d67  mov     rbp, [rsp+48h+arg_10]
0x180038d6c  add     rsp, 30h
0x180038d70  pop     r14
0x180038d72  pop     rdi
0x180038d73  pop     rsi
0x180038d74  retn
```

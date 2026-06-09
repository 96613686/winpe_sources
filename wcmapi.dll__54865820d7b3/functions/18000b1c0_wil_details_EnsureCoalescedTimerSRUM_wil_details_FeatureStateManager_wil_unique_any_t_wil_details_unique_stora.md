# `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000b1c0`
- end: `0x18000b22a`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `106`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000b1c0`
- `0x18000bf04`
- `0x180010ff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b1d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b1d9`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  char *v4; // rbx
  char *v5; // [rsp+20h] [rbp-18h] BYREF

  if ( *Context )
  {
    v4 = Context + 40;
    AcquireSRWLockExclusive((PSRWLOCK)Context + 5);
    v5 = v4;
    if ( *((_QWORD *)Context + 30) - *((_QWORD *)Context + 29) >= 0xCu )
    {
      wil_details_WriteSRUMWnfUsageBuffer((__int64 *)Context + 29);
      *((_QWORD *)Context + 30) = *((_QWORD *)Context + 29);
    }
    Context[64] = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  }
}

```

## disassembly

```asm
0x18000b1c0  mov     [rsp+arg_0], rbx
0x18000b1c5  push    rdi
0x18000b1c6  sub     rsp, 30h
0x18000b1ca  cmp     byte ptr [rdx], 0
0x18000b1cd  mov     rdi, rdx
0x18000b1d0  jz      short loc_18000B21E
0x18000b1d2  lea     rbx, [rdx+28h]
0x18000b1d6  mov     rcx, rbx; SRWLock
0x18000b1d9  call    cs:__imp_AcquireSRWLockExclusive
0x18000b1e0  nop     dword ptr [rax+rax+00h]
0x18000b1e5  mov     [rsp+38h+var_18], rbx
0x18000b1ea  lea     rbx, [rdi+0E8h]
0x18000b1f1  mov     rax, [rbx+8]
0x18000b1f5  sub     rax, [rbx]
0x18000b1f8  cmp     rax, 0Ch
0x18000b1fc  jb      short loc_18000B210
0x18000b1fe  mov     rcx, rbx
0x18000b201  call    ?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z; wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)
0x18000b206  mov     rax, [rbx]
0x18000b209  mov     [rdi+0F0h], rax
0x18000b210  lea     rcx, [rsp+38h+var_18]
0x18000b215  mov     byte ptr [rdi+40h], 0
0x18000b219  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b21e  mov     rbx, [rsp+38h+arg_0]
0x18000b223  add     rsp, 30h
0x18000b227  pop     rdi
0x18000b228  retn
```

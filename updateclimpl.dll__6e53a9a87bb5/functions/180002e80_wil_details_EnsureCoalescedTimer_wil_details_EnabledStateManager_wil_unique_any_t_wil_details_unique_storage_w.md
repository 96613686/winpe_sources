# `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180002e80`
- end: `0x180002ec4`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `68`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002e80`
- `0x180003020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002e99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002e99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002eb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002eb3`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rbx

  if ( LOBYTE(Context->Ptr) )
  {
    v4 = Context + 1;
    AcquireSRWLockExclusive(Context + 1);
    wil::details::EnabledStateManager::RecordCachedUsageUnderLock((wil::details::EnabledStateManager *)Context);
    LOBYTE(Context[3].Ptr) = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x180002e80  mov     [rsp+arg_0], rbx
0x180002e85  push    rdi
0x180002e86  sub     rsp, 20h
0x180002e8a  cmp     byte ptr [rdx], 0
0x180002e8d  mov     rdi, rdx
0x180002e90  jz      short loc_180002EB9
0x180002e92  lea     rbx, [rdx+8]
0x180002e96  mov     rcx, rbx; SRWLock
0x180002e99  call    cs:__imp_AcquireSRWLockExclusive
0x180002e9f  mov     rcx, rdi; this
0x180002ea2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180002ea7  mov     byte ptr [rdi+18h], 0
0x180002eab  test    rbx, rbx
0x180002eae  jz      short loc_180002EB9
0x180002eb0  mov     rcx, rbx; SRWLock
0x180002eb3  call    cs:__imp_ReleaseSRWLockExclusive
0x180002eb9  mov     rbx, [rsp+28h+arg_0]
0x180002ebe  add     rsp, 20h
0x180002ec2  pop     rdi
0x180002ec3  retn
```

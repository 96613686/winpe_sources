# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000a280`
- end: `0x18000a2ff`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `127`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a280`
- `0x18000c344`
- `0x18000d9a0`
- `0x18000e0f4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a299`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a299`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rdi

  if ( *Context )
  {
    v4 = (RTL_SRWLOCK *)(Context + 32);
    AcquireSRWLockExclusive((PSRWLOCK)Context + 4);
    Context[65] = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)Context) )
    {
      wil::details_abi::SubscriptionList::OnSignaled(
        (LPCRITICAL_SECTION)(*((_QWORD *)Context + 3) + 200LL),
        *((PSRWLOCK *)Context + 3));
      wil::details_abi::FeatureStateData::RecordUsage(*((PSRWLOCK *)Context + 3));
    }
  }
}

```

## disassembly

```asm
0x18000a280  mov     [rsp+arg_0], rbx
0x18000a285  push    rdi
0x18000a286  sub     rsp, 20h
0x18000a28a  cmp     byte ptr [rdx], 0
0x18000a28d  mov     rbx, rdx
0x18000a290  jz      short loc_18000A2F4
0x18000a292  lea     rdi, [rdx+20h]
0x18000a296  mov     rcx, rdi; SRWLock
0x18000a299  call    cs:__imp_AcquireSRWLockExclusive
0x18000a29f  mov     byte ptr [rbx+41h], 0
0x18000a2a3  test    rdi, rdi
0x18000a2a6  jz      short loc_18000A2B1
0x18000a2a8  mov     rcx, rdi; SRWLock
0x18000a2ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a2b1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a2b8  jnz     short loc_18000A2F4
0x18000a2ba  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a2c1  test    rax, rax
0x18000a2c4  jz      short loc_18000A2CF
0x18000a2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2cb  test    al, al
0x18000a2cd  jnz     short loc_18000A2F4
0x18000a2cf  mov     rcx, rbx; this
0x18000a2d2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a2d7  test    al, al
0x18000a2d9  jz      short loc_18000A2F4
0x18000a2db  mov     rdx, [rbx+18h]; SRWLock
0x18000a2df  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a2e6  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000a2eb  mov     rcx, [rbx+18h]; SRWLock
0x18000a2ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a2f4  mov     rbx, [rsp+28h+arg_0]
0x18000a2f9  add     rsp, 20h
0x18000a2fd  pop     rdi
0x18000a2fe  retn
```

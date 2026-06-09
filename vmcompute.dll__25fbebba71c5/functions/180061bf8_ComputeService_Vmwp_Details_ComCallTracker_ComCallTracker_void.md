# ComputeService::Vmwp::Details::ComCallTracker::~ComCallTracker(void)

- ea: `0x180061bf8`
- end: `0x180061c6c`
- name: `??1ComCallTracker@Details@Vmwp@ComputeService@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(ComputeService::Vmwp::Details::ComCallTracker *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800619b0`
- `0x180080fe5`

## callees

- `0x18000eb30`
- `0x180061bf8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180061c59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180061c59`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180061c36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180061c36`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180061c4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180061c4a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180061c10`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180061c10`

## pseudocode

```c
void __fastcall ComputeService::Vmwp::Details::ComCallTracker::~ComCallTracker(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rbx

  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this,
    0);
  if ( *((_DWORD *)this + 2) )
  {
    CoDisableCallCancellation(0);
    *((_DWORD *)this + 2) = 0;
  }
  v2 = *this;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
}

```

## disassembly

```asm
0x180061bf8  push    rbx
0x180061bfa  sub     rsp, 20h
0x180061bfe  xor     edx, edx
0x180061c00  mov     rbx, rcx
0x180061c03  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180061c08  cmp     dword ptr [rbx+8], 0
0x180061c0c  jz      short loc_180061C23
0x180061c0e  xor     ecx, ecx; pReserved
0x180061c10  call    cs:__imp_CoDisableCallCancellation
0x180061c17  nop     dword ptr [rax+rax+00h]
0x180061c1c  mov     dword ptr [rbx+8], 0
0x180061c23  mov     rbx, [rbx]
0x180061c26  test    rbx, rbx
0x180061c29  jz      short loc_180061C65
0x180061c2b  xor     r9d, r9d; msWindowLength
0x180061c2e  xor     r8d, r8d; msPeriod
0x180061c31  xor     edx, edx; pftDueTime
0x180061c33  mov     rcx, rbx; pti
0x180061c36  call    cs:__imp_SetThreadpoolTimer
0x180061c3d  nop     dword ptr [rax+rax+00h]
0x180061c42  mov     edx, 1; fCancelPendingCallbacks
0x180061c47  mov     rcx, rbx; pti
0x180061c4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180061c51  nop     dword ptr [rax+rax+00h]
0x180061c56  mov     rcx, rbx; pti
0x180061c59  call    cs:__imp_CloseThreadpoolTimer
0x180061c60  nop     dword ptr [rax+rax+00h]
0x180061c65  add     rsp, 20h
0x180061c69  pop     rbx
0x180061c6a  retn
```

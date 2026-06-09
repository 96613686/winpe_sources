# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(void)

- ea: `0x180006770`
- end: `0x1800067bf`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180081045`

## callees

- `0x180006770`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800067ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800067ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006789`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006789`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000679d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000679d`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>(
        PTP_TIMER *a1)
{
  struct _TP_TIMER *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolTimer(*a1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
  }
}

```

## disassembly

```asm
0x180006770  push    rbx
0x180006772  sub     rsp, 20h
0x180006776  mov     rbx, [rcx]
0x180006779  test    rbx, rbx
0x18000677c  jz      short loc_1800067B8
0x18000677e  xor     r9d, r9d; msWindowLength
0x180006781  xor     r8d, r8d; msPeriod
0x180006784  xor     edx, edx; pftDueTime
0x180006786  mov     rcx, rbx; pti
0x180006789  call    cs:__imp_SetThreadpoolTimer
0x180006790  nop     dword ptr [rax+rax+00h]
0x180006795  mov     edx, 1; fCancelPendingCallbacks
0x18000679a  mov     rcx, rbx; pti
0x18000679d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800067a4  nop     dword ptr [rax+rax+00h]
0x1800067a9  mov     rcx, rbx; pti
0x1800067ac  call    cs:__imp_CloseThreadpoolTimer
0x1800067b3  nop     dword ptr [rax+rax+00h]
0x1800067b8  add     rsp, 20h
0x1800067bc  pop     rbx
0x1800067bd  retn
```

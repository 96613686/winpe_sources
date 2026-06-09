# ThreadpoolTimerHelper::Cancel(void)

- ea: `0x180006fa4`
- end: `0x18000700a`
- name: `?Cancel@ThreadpoolTimerHelper@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ThreadpoolTimerHelper *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006f3c`
- `0x1800633c8`
- `0x180074358`
- `0x1800743c0`
- `0x180074428`
- `0x180074490`

## callees

- `0x180006fa4`
- `0x180007010`
- `0x18000e1c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fbf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006fd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006fd1`

## pseudocode

```c
void __fastcall ThreadpoolTimerHelper::Cancel(ThreadpoolTimerHelper *this)
{
  int v2; // ebx
  std::_Ref_count_base *v3; // rcx

  if ( *(_QWORD *)this )
  {
    v2 = *(_DWORD *)(*((_QWORD *)this + 1) + 64LL);
    if ( GetCurrentThreadId() != v2 )
      WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)this, 1);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      this,
      0);
    *((_QWORD *)this + 1) = 0;
    v3 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v3 )
      std::_Ref_count_base::_Decref(v3);
  }
}

```

## disassembly

```asm
0x180006fa4  mov     [rsp+arg_0], rbx
0x180006fa9  push    rdi
0x180006faa  sub     rsp, 20h
0x180006fae  cmp     qword ptr [rcx], 0
0x180006fb2  mov     rdi, rcx
0x180006fb5  jz      short loc_180006FFF
0x180006fb7  mov     rax, [rcx+8]
0x180006fbb  mov     ebx, [rax+40h]
0x180006fbe  nop
0x180006fbf  call    cs:__imp_GetCurrentThreadId
0x180006fc5  cmp     eax, ebx
0x180006fc7  jz      short loc_180006FD7
0x180006fc9  mov     rcx, [rdi]; pti
0x180006fcc  mov     edx, 1; fCancelPendingCallbacks
0x180006fd1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006fd7  xor     edx, edx
0x180006fd9  mov     rcx, rdi
0x180006fdc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006fe1  mov     qword ptr [rdi+8], 0
0x180006fe9  mov     rcx, [rdi+10h]; this
0x180006fed  mov     qword ptr [rdi+10h], 0
0x180006ff5  test    rcx, rcx
0x180006ff8  jz      short loc_180006FFF
0x180006ffa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180006fff  mov     rbx, [rsp+28h+arg_0]
0x180007004  add     rsp, 20h
0x180007008  pop     rdi
0x180007009  retn
```

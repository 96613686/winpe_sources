# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180010920`
- end: `0x1800109f0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `208`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000ad50`

## callees

- `0x18000e5c0`
- `0x18000f35c`
- `0x18000f9f8`
- `0x180010920`
- `0x180010f28`
- `0x180010f48`
- `0x180011060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001094f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001094f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800109ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800109ac`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char v10; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x180010920  push    rbx
0x180010922  push    rbp
0x180010923  push    rsi
0x180010924  push    rdi
0x180010925  sub     rsp, 38h
0x180010929  mov     eax, [rcx]
0x18001092b  mov     rsi, r8
0x18001092e  mov     ebp, edx
0x180010930  mov     rbx, rcx
0x180010933  test    eax, eax
0x180010935  jz      loc_1800109E7
0x18001093b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180010940  test    al, al
0x180010942  jnz     loc_1800109E7
0x180010948  lea     rdi, [rbx+8]
0x18001094c  mov     rcx, rdi; SRWLock
0x18001094f  call    cs:__imp_AcquireSRWLockExclusive
0x180010955  mov     eax, [rbx]
0x180010957  test    eax, eax
0x180010959  jz      short loc_1800109D9
0x18001095b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180010960  test    al, al
0x180010962  jnz     short loc_1800109D9
0x180010964  xor     eax, eax
0x180010966  mov     [rsp+58h+var_38], ebp
0x18001096a  lea     rcx, [rbx+20h]; this
0x18001096e  mov     [rsp+58h+var_34], eax
0x180010972  lea     rdx, [rsp+58h+var_38]; void *
0x180010977  mov     [rsp+58h+var_30], rsi
0x18001097c  lea     r8d, [rax+10h]; unsigned __int64
0x180010980  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010985  cmp     byte ptr [rbx+18h], 0
0x180010989  jnz     short loc_1800109D9
0x18001098b  lea     rsi, [rbx+10h]
0x18001098f  cmp     qword ptr [rsi], 0
0x180010993  jnz     short loc_1800109C7
0x180010995  lea     rcx, [rsp+58h+arg_0]; this
0x18001099a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001099f  xor     r8d, r8d; pcbe
0x1800109a2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800109a9  mov     rdx, rbx; pv
0x1800109ac  call    cs:__imp_CreateThreadpoolTimer
0x1800109b2  mov     rdx, rax
0x1800109b5  mov     rcx, rsi
0x1800109b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800109bd  lea     rcx, [rsp+58h+arg_0]; this
0x1800109c2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800109c7  mov     r8d, 493E0h
0x1800109cd  lea     rdx, [rbx+18h]
0x1800109d1  mov     rcx, rsi
0x1800109d4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800109d9  test    rdi, rdi
0x1800109dc  jz      short loc_1800109E7
0x1800109de  mov     rcx, rdi; SRWLock
0x1800109e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800109e7  add     rsp, 38h
0x1800109eb  pop     rdi
0x1800109ec  pop     rsi
0x1800109ed  pop     rbp
0x1800109ee  pop     rbx
0x1800109ef  retn
```

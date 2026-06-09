# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180026614`
- end: `0x1800266f5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `225`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800030b0`
- `0x1800036a0`
- `0x180003834`
- `0x1800039c0`
- `0x180003dd0`
- `0x180004110`
- `0x180004930`

## callees

- `0x18000c90c`
- `0x180012f24`
- `0x180012f68`
- `0x180016abc`
- `0x180026614`
- `0x180026858`
- `0x180026878`
- `0x180032b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800266de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800266de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800266a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800266a7`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-10h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::AcquireSRWLockExclusive(&SRWLock, pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(pv + 16, pv + 24, 300000);
        }
      }
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
}

```

## disassembly

```asm
0x180026614  mov     [rsp+arg_8], rbx
0x180026619  mov     [rsp+arg_10], rsi
0x18002661e  push    rdi
0x18002661f  sub     rsp, 30h
0x180026623  mov     rdi, r8
0x180026626  mov     esi, edx
0x180026628  mov     rbx, rcx
0x18002662b  mov     eax, [rcx]
0x18002662d  test    eax, eax
0x18002662f  jz      loc_1800266E5
0x180026635  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002663a  test    al, al
0x18002663c  jnz     loc_1800266E5
0x180026642  lea     rdx, [rbx+8]
0x180026646  lea     rcx, [rsp+38h+SRWLock]
0x18002664b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180026650  mov     eax, [rbx]
0x180026652  test    eax, eax
0x180026654  jz      short loc_1800266D4
0x180026656  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002665b  test    al, al
0x18002665d  jnz     short loc_1800266D4
0x18002665f  mov     [rsp+38h+var_18], esi
0x180026663  xor     eax, eax
0x180026665  mov     [rsp+38h+var_14], eax
0x180026669  mov     [rsp+38h+var_10], rdi
0x18002666e  lea     rcx, [rbx+20h]; this
0x180026672  lea     r8d, [rax+10h]; unsigned __int64
0x180026676  lea     rdx, [rsp+38h+var_18]; void *
0x18002667b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026680  cmp     byte ptr [rbx+18h], 0
0x180026684  jnz     short loc_1800266D4
0x180026686  lea     rdi, [rbx+10h]
0x18002668a  cmp     qword ptr [rdi], 0
0x18002668e  jnz     short loc_1800266C2
0x180026690  lea     rcx, [rsp+38h+arg_18]; this
0x180026695  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002669a  xor     r8d, r8d; pcbe
0x18002669d  mov     rdx, rbx; pv
0x1800266a0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800266a7  call    cs:__imp_CreateThreadpoolTimer
0x1800266ad  mov     rdx, rax
0x1800266b0  mov     rcx, rdi
0x1800266b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800266b8  lea     rcx, [rsp+38h+arg_18]; this
0x1800266bd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800266c2  mov     r8d, 493E0h
0x1800266c8  lea     rdx, [rbx+18h]
0x1800266cc  mov     rcx, rdi
0x1800266cf  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800266d4  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800266d9  test    rcx, rcx
0x1800266dc  jz      short loc_1800266E5
0x1800266de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800266e4  nop
0x1800266e5  mov     rbx, [rsp+38h+arg_8]
0x1800266ea  mov     rsi, [rsp+38h+arg_10]
0x1800266ef  add     rsp, 30h
0x1800266f3  pop     rdi
0x1800266f4  retn
```

# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180016420`
- end: `0x18001650a`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016ba4`

## callees

- `0x18000bd50`
- `0x18000bf04`
- `0x18000c264`
- `0x18000ccb8`
- `0x18000ecf8`
- `0x180010dd4`
- `0x180010ef4`
- `0x180016420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016452`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016452`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800164be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800164be`

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
  RTL_SRWLOCK *v10; // [rsp+30h] [rbp-28h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v10 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180016420  mov     [rsp+arg_18], rbx
0x180016425  push    rbp
0x180016426  push    rsi
0x180016427  push    rdi
0x180016428  sub     rsp, 40h
0x18001642c  mov     rbp, r8
0x18001642f  mov     esi, edx
0x180016431  mov     rdi, rcx
0x180016434  mov     eax, [rcx]
0x180016436  test    eax, eax
0x180016438  jz      loc_1800164FC
0x18001643e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180016443  test    al, al
0x180016445  jnz     loc_1800164FC
0x18001644b  lea     rbx, [rdi+8]
0x18001644f  mov     rcx, rbx; SRWLock
0x180016452  call    cs:__imp_AcquireSRWLockExclusive
0x180016459  nop     dword ptr [rax+rax+00h]
0x18001645e  mov     [rsp+58h+var_28], rbx
0x180016463  mov     eax, [rdi]
0x180016465  test    eax, eax
0x180016467  jz      loc_1800164F1
0x18001646d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180016472  test    al, al
0x180016474  jnz     short loc_1800164F1
0x180016476  mov     [rsp+58h+var_38], esi
0x18001647a  xor     eax, eax
0x18001647c  mov     [rsp+58h+var_34], eax
0x180016480  mov     [rsp+58h+var_30], rbp
0x180016485  lea     rcx, [rdi+30h]; this
0x180016489  lea     r8d, [rax+10h]; unsigned __int64
0x18001648d  lea     rdx, [rsp+58h+var_38]; void *
0x180016492  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016497  cmp     byte ptr [rdi+18h], 0
0x18001649b  jnz     short loc_1800164F1
0x18001649d  lea     rbx, [rdi+10h]
0x1800164a1  cmp     qword ptr [rbx], 0
0x1800164a5  jnz     short loc_1800164DF
0x1800164a7  lea     rcx, [rsp+58h+var_38]; this
0x1800164ac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800164b1  xor     r8d, r8d; pcbe
0x1800164b4  mov     rdx, rdi; pv
0x1800164b7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800164be  call    cs:__imp_CreateThreadpoolTimer
0x1800164c5  nop     dword ptr [rax+rax+00h]
0x1800164ca  mov     rdx, rax
0x1800164cd  mov     rcx, rbx
0x1800164d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800164d5  lea     rcx, [rsp+58h+var_38]; this
0x1800164da  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800164df  mov     r8d, 493E0h
0x1800164e5  lea     rdx, [rdi+18h]
0x1800164e9  mov     rcx, rbx
0x1800164ec  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800164f1  lea     rcx, [rsp+58h+var_28]
0x1800164f6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800164fb  nop
0x1800164fc  mov     rbx, [rsp+58h+arg_18]
0x180016501  add     rsp, 40h
0x180016505  pop     rdi
0x180016506  pop     rsi
0x180016507  pop     rbp
0x180016508  retn
```

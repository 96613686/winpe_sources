# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003af20`
- end: `0x18003b009`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `233`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003ae00`

## callees

- `0x180032698`
- `0x180032a30`
- `0x180032b0c`
- `0x180032bb4`
- `0x180033f08`
- `0x180033f2c`
- `0x180033f50`
- `0x18003af20`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18003afbe`
- `KERNEL32!CreateThreadpoolTimer` at `0x18003afbe`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003af52`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003af52`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], Source, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18003af20  mov     [rsp+arg_8], rbx
0x18003af25  push    rbp
0x18003af26  push    rsi
0x18003af27  push    rdi
0x18003af28  sub     rsp, 30h
0x18003af2c  mov     eax, [rcx]
0x18003af2e  mov     rsi, r8
0x18003af31  mov     ebp, edx
0x18003af33  mov     rdi, rcx
0x18003af36  test    eax, eax
0x18003af38  jz      loc_18003AFFB
0x18003af3e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003af43  test    al, al
0x18003af45  jnz     loc_18003AFFB
0x18003af4b  lea     rbx, [rdi+8]
0x18003af4f  mov     rcx, rbx; SRWLock
0x18003af52  call    cs:__imp_AcquireSRWLockExclusive
0x18003af59  nop     dword ptr [rax+rax+00h]
0x18003af5e  mov     eax, [rdi]
0x18003af60  mov     [rsp+48h+arg_18], rbx
0x18003af65  test    eax, eax
0x18003af67  jz      loc_18003AFF1
0x18003af6d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003af72  test    al, al
0x18003af74  jnz     short loc_18003AFF1
0x18003af76  xor     eax, eax
0x18003af78  mov     [rsp+48h+Source], ebp
0x18003af7c  lea     rcx, [rdi+30h]; this
0x18003af80  mov     [rsp+48h+var_24], eax
0x18003af84  lea     rdx, [rsp+48h+Source]; Source
0x18003af89  mov     [rsp+48h+var_20], rsi
0x18003af8e  lea     r8d, [rax+10h]; SourceSize
0x18003af92  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003af97  cmp     byte ptr [rdi+18h], 0
0x18003af9b  jnz     short loc_18003AFF1
0x18003af9d  lea     rbx, [rdi+10h]
0x18003afa1  cmp     qword ptr [rbx], 0
0x18003afa5  jnz     short loc_18003AFDF
0x18003afa7  lea     rcx, [rsp+48h+arg_0]; this
0x18003afac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003afb1  xor     r8d, r8d; pcbe
0x18003afb4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003afbb  mov     rdx, rdi; pv
0x18003afbe  call    cs:__imp_CreateThreadpoolTimer
0x18003afc5  nop     dword ptr [rax+rax+00h]
0x18003afca  mov     rdx, rax
0x18003afcd  mov     rcx, rbx
0x18003afd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003afd5  lea     rcx, [rsp+48h+arg_0]; this
0x18003afda  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003afdf  mov     r8d, 493E0h
0x18003afe5  lea     rdx, [rdi+18h]
0x18003afe9  mov     rcx, rbx
0x18003afec  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003aff1  lea     rcx, [rsp+48h+arg_18]
0x18003aff6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003affb  mov     rbx, [rsp+48h+arg_8]
0x18003b000  add     rsp, 30h
0x18003b004  pop     rdi
0x18003b005  pop     rsi
0x18003b006  pop     rbp
0x18003b007  retn
```

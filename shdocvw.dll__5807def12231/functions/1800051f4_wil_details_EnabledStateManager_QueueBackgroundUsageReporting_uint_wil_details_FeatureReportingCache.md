# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800051f4`
- end: `0x1800052c5`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000f6a8`

## callees

- `0x180003b30`
- `0x180003c60`
- `0x1800042f0`
- `0x1800051f4`
- `0x180005540`
- `0x180005560`
- `0x180005590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005223`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005223`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800052b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800052b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005280`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005280`

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
0x1800051f4  push    rbx
0x1800051f6  push    rbp
0x1800051f7  push    rsi
0x1800051f8  push    rdi
0x1800051f9  sub     rsp, 38h
0x1800051fd  mov     rsi, r8
0x180005200  mov     ebp, edx
0x180005202  mov     rbx, rcx
0x180005205  mov     eax, [rcx]
0x180005207  test    eax, eax
0x180005209  jz      loc_1800052BC
0x18000520f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180005214  test    al, al
0x180005216  jnz     loc_1800052BC
0x18000521c  lea     rdi, [rbx+8]
0x180005220  mov     rcx, rdi; SRWLock
0x180005223  call    cs:__imp_AcquireSRWLockExclusive
0x180005229  mov     eax, [rbx]
0x18000522b  test    eax, eax
0x18000522d  jz      short loc_1800052AD
0x18000522f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180005234  test    al, al
0x180005236  jnz     short loc_1800052AD
0x180005238  mov     [rsp+58h+var_38], ebp
0x18000523c  xor     eax, eax
0x18000523e  mov     [rsp+58h+var_34], eax
0x180005242  mov     [rsp+58h+var_30], rsi
0x180005247  lea     rcx, [rbx+20h]; this
0x18000524b  lea     r8d, [rax+10h]; unsigned __int64
0x18000524f  lea     rdx, [rsp+58h+var_38]; void *
0x180005254  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005259  cmp     byte ptr [rbx+18h], 0
0x18000525d  jnz     short loc_1800052AD
0x18000525f  lea     rsi, [rbx+10h]
0x180005263  cmp     qword ptr [rsi], 0
0x180005267  jnz     short loc_18000529B
0x180005269  lea     rcx, [rsp+58h+arg_0]; this
0x18000526e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005273  xor     r8d, r8d; pcbe
0x180005276  mov     rdx, rbx; pv
0x180005279  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005280  call    cs:__imp_CreateThreadpoolTimer
0x180005286  mov     rdx, rax
0x180005289  mov     rcx, rsi
0x18000528c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005291  lea     rcx, [rsp+58h+arg_0]; this
0x180005296  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000529b  mov     r8d, 493E0h
0x1800052a1  lea     rdx, [rbx+18h]
0x1800052a5  mov     rcx, rsi
0x1800052a8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800052ad  test    rdi, rdi
0x1800052b0  jz      short loc_1800052BC
0x1800052b2  mov     rcx, rdi; SRWLock
0x1800052b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800052bb  nop
0x1800052bc  add     rsp, 38h
0x1800052c0  pop     rdi
0x1800052c1  pop     rsi
0x1800052c2  pop     rbp
0x1800052c3  pop     rbx
0x1800052c4  retn
```

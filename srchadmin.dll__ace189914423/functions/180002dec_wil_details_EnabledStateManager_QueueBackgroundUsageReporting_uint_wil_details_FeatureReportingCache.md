# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180002dec`
- end: `0x180002ebd`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `209`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800161cc`

## callees

- `0x180002dec`
- `0x180003138`
- `0x180003158`
- `0x18000317c`
- `0x1800031c0`
- `0x180003770`
- `0x18000c644`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002e1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002e1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002ead`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002ead`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002e78`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002e78`

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
0x180002dec  push    rbx
0x180002dee  push    rbp
0x180002def  push    rsi
0x180002df0  push    rdi
0x180002df1  sub     rsp, 38h
0x180002df5  mov     rsi, r8
0x180002df8  mov     ebp, edx
0x180002dfa  mov     rbx, rcx
0x180002dfd  mov     eax, [rcx]
0x180002dff  test    eax, eax
0x180002e01  jz      loc_180002EB4
0x180002e07  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180002e0c  test    al, al
0x180002e0e  jnz     loc_180002EB4
0x180002e14  lea     rdi, [rbx+8]
0x180002e18  mov     rcx, rdi; SRWLock
0x180002e1b  call    cs:__imp_AcquireSRWLockExclusive
0x180002e21  mov     eax, [rbx]
0x180002e23  test    eax, eax
0x180002e25  jz      short loc_180002EA5
0x180002e27  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180002e2c  test    al, al
0x180002e2e  jnz     short loc_180002EA5
0x180002e30  mov     [rsp+58h+var_38], ebp
0x180002e34  xor     eax, eax
0x180002e36  mov     [rsp+58h+var_34], eax
0x180002e3a  mov     [rsp+58h+var_30], rsi
0x180002e3f  lea     rcx, [rbx+20h]; this
0x180002e43  lea     r8d, [rax+10h]; unsigned __int64
0x180002e47  lea     rdx, [rsp+58h+var_38]; void *
0x180002e4c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180002e51  cmp     byte ptr [rbx+18h], 0
0x180002e55  jnz     short loc_180002EA5
0x180002e57  lea     rsi, [rbx+10h]
0x180002e5b  cmp     qword ptr [rsi], 0
0x180002e5f  jnz     short loc_180002E93
0x180002e61  lea     rcx, [rsp+58h+arg_0]; this
0x180002e66  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180002e6b  xor     r8d, r8d; pcbe
0x180002e6e  mov     rdx, rbx; pv
0x180002e71  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180002e78  call    cs:__imp_CreateThreadpoolTimer
0x180002e7e  mov     rdx, rax
0x180002e81  mov     rcx, rsi
0x180002e84  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180002e89  lea     rcx, [rsp+58h+arg_0]; this
0x180002e8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180002e93  mov     r8d, 493E0h
0x180002e99  lea     rdx, [rbx+18h]
0x180002e9d  mov     rcx, rsi
0x180002ea0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180002ea5  test    rdi, rdi
0x180002ea8  jz      short loc_180002EB4
0x180002eaa  mov     rcx, rdi; SRWLock
0x180002ead  call    cs:__imp_ReleaseSRWLockExclusive
0x180002eb3  nop
0x180002eb4  add     rsp, 38h
0x180002eb8  pop     rdi
0x180002eb9  pop     rsi
0x180002eba  pop     rbp
0x180002ebb  pop     rbx
0x180002ebc  retn
```

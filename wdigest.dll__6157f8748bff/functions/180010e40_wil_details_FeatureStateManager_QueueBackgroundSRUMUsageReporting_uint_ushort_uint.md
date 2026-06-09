# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180010e40`
- end: `0x180010f21`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `225`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180016a00`

## callees

- `0x18000e5c0`
- `0x18000f35c`
- `0x18000f9f8`
- `0x180010e40`
- `0x180010f28`
- `0x180010f48`
- `0x180011060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010f08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010f08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010ed3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010ed3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int16 v10; // [rsp+24h] [rbp-24h]
  __int16 v11; // [rsp+26h] [rbp-22h]
  int v12; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = a2;
    v11 = 0;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v9, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x180010e40  mov     [rsp+arg_8], rbx
0x180010e45  mov     [rsp+arg_10], rbp
0x180010e4a  push    rsi
0x180010e4b  push    rdi
0x180010e4c  push    r14
0x180010e4e  sub     rsp, 30h
0x180010e52  cmp     byte ptr [rcx], 0
0x180010e55  mov     edi, r9d
0x180010e58  movzx   ebp, r8w
0x180010e5c  mov     r14d, edx
0x180010e5f  mov     rbx, rcx
0x180010e62  jz      loc_180010F0E
0x180010e68  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180010e6d  test    al, al
0x180010e6f  jnz     loc_180010F0E
0x180010e75  lea     rsi, [rbx+28h]
0x180010e79  mov     rcx, rsi; SRWLock
0x180010e7c  call    cs:__imp_AcquireSRWLockExclusive
0x180010e82  xor     eax, eax
0x180010e84  mov     [rsp+48h+var_28], r14d
0x180010e89  lea     rcx, [rbx+0E8h]; this
0x180010e90  mov     [rsp+48h+var_22], ax
0x180010e95  lea     rdx, [rsp+48h+var_28]; void *
0x180010e9a  mov     [rsp+48h+var_24], bp
0x180010e9f  mov     [rsp+48h+var_20], edi
0x180010ea3  lea     r8d, [rax+0Ch]; unsigned __int64
0x180010ea7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010eac  cmp     byte ptr [rbx+40h], 0
0x180010eb0  jnz     short loc_180010F00
0x180010eb2  lea     rdi, [rbx+38h]
0x180010eb6  cmp     qword ptr [rdi], 0
0x180010eba  jnz     short loc_180010EEE
0x180010ebc  lea     rcx, [rsp+48h+arg_0]; this
0x180010ec1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180010ec6  xor     r8d, r8d; pcbe
0x180010ec9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180010ed0  mov     rdx, rbx; pv
0x180010ed3  call    cs:__imp_CreateThreadpoolTimer
0x180010ed9  mov     rdx, rax
0x180010edc  mov     rcx, rdi
0x180010edf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180010ee4  lea     rcx, [rsp+48h+arg_0]; this
0x180010ee9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180010eee  mov     r8d, 1388h
0x180010ef4  lea     rdx, [rbx+40h]
0x180010ef8  mov     rcx, rdi
0x180010efb  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180010f00  test    rsi, rsi
0x180010f03  jz      short loc_180010F0E
0x180010f05  mov     rcx, rsi; SRWLock
0x180010f08  call    cs:__imp_ReleaseSRWLockExclusive
0x180010f0e  mov     rbx, [rsp+48h+arg_8]
0x180010f13  mov     rbp, [rsp+48h+arg_10]
0x180010f18  add     rsp, 30h
0x180010f1c  pop     r14
0x180010f1e  pop     rdi
0x180010f1f  pop     rsi
0x180010f20  retn
```

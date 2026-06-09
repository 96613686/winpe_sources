# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001c7a0`
- end: `0x18001c922`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `386`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dc2c`

## callees

- `0x180008bfc`
- `0x18001c7a0`
- `0x18001eff4`
- `0x18001f0ec`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c901`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c8b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c884`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c89f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c89f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c8e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c8e9`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v6; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v11 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 48), 0x10u) )
      {
        memcpy_s(
          *((void *const *)pv + 7),
          (*((_QWORD *)pv + 8) - *((_QWORD *)pv + 7)) & -(__int64)(*((_QWORD *)pv + 7) < *((_QWORD *)pv + 8)),
          Source,
          0x10u);
        *((_QWORD *)pv + 7) += 16LL;
      }
      if ( !pv[24] )
      {
        v6 = (struct _TP_TIMER **)(pv + 16);
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v9 = *v6;
        if ( *v6 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
          pv[24] = 1;
        }
      }
    }
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x18001c7a0  mov     [rsp+arg_8], rbx
0x18001c7a5  mov     [rsp+arg_10], rbp
0x18001c7aa  push    rsi
0x18001c7ab  push    rdi
0x18001c7ac  push    r14
0x18001c7ae  sub     rsp, 30h
0x18001c7b2  mov     rbx, r8
0x18001c7b5  mov     ebp, edx
0x18001c7b7  mov     rdi, rcx
0x18001c7ba  mov     eax, [rcx]
0x18001c7bc  test    eax, eax
0x18001c7be  jz      loc_18001C90E
0x18001c7c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c7cb  jnz     loc_18001C90E
0x18001c7d1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c7d8  test    rax, rax
0x18001c7db  jz      short loc_18001C7EA
0x18001c7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7e2  test    al, al
0x18001c7e4  jnz     loc_18001C90E
0x18001c7ea  lea     rsi, [rdi+8]
0x18001c7ee  mov     rcx, rsi; SRWLock
0x18001c7f1  call    cs:__imp_AcquireSRWLockExclusive
0x18001c7f8  nop     dword ptr [rax+rax+00h]
0x18001c7fd  mov     eax, [rdi]
0x18001c7ff  test    eax, eax
0x18001c801  jz      loc_18001C8F9
0x18001c807  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c80e  jnz     loc_18001C8F9
0x18001c814  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c81b  test    rax, rax
0x18001c81e  jz      short loc_18001C82D
0x18001c820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c825  test    al, al
0x18001c827  jnz     loc_18001C8F9
0x18001c82d  mov     [rsp+48h+Source], ebp
0x18001c831  xor     eax, eax
0x18001c833  mov     [rsp+48h+var_24], eax
0x18001c837  mov     [rsp+48h+var_20], rbx
0x18001c83c  lea     ebp, [rax+10h]
0x18001c83f  mov     edx, ebp; unsigned __int64
0x18001c841  lea     rcx, [rdi+30h]; this
0x18001c845  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001c84a  test    al, al
0x18001c84c  jz      short loc_18001C874
0x18001c84e  mov     rcx, [rdi+38h]; Destination
0x18001c852  mov     rax, [rdi+40h]
0x18001c856  sub     rax, rcx
0x18001c859  cmp     rcx, [rdi+40h]
0x18001c85d  sbb     rdx, rdx
0x18001c860  and     rdx, rax; DestinationSize
0x18001c863  mov     r9d, ebp; SourceSize
0x18001c866  lea     r8, [rsp+48h+Source]; Source
0x18001c86b  call    memcpy_s
0x18001c870  add     [rdi+38h], rbp
0x18001c874  cmp     byte ptr [rdi+18h], 0
0x18001c878  jnz     short loc_18001C8F9
0x18001c87a  lea     r14, [rdi+10h]
0x18001c87e  cmp     qword ptr [r14], 0
0x18001c882  jnz     short loc_18001C8C4
0x18001c884  call    cs:__imp_GetLastError
0x18001c88b  nop     dword ptr [rax+rax+00h]
0x18001c890  mov     ebx, eax
0x18001c892  xor     r8d, r8d; pcbe
0x18001c895  mov     rdx, rdi; pv
0x18001c898  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c89f  call    cs:__imp_CreateThreadpoolTimer
0x18001c8a6  nop     dword ptr [rax+rax+00h]
0x18001c8ab  mov     rdx, rax
0x18001c8ae  mov     rcx, r14
0x18001c8b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c8b6  mov     ecx, ebx; dwErrCode
0x18001c8b8  call    cs:__imp_SetLastError
0x18001c8bf  nop     dword ptr [rax+rax+00h]
0x18001c8c4  mov     rcx, [r14]; pti
0x18001c8c7  test    rcx, rcx
0x18001c8ca  jz      short loc_18001C8F9
0x18001c8cc  mov     rax, 0FFFFFFFF4D2FA200h
0x18001c8d6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001c8db  mov     r9d, 124F8h; msWindowLength
0x18001c8e1  xor     r8d, r8d; msPeriod
0x18001c8e4  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001c8e9  call    cs:__imp_SetThreadpoolTimer
0x18001c8f0  nop     dword ptr [rax+rax+00h]
0x18001c8f5  mov     byte ptr [rdi+18h], 1
0x18001c8f9  test    rsi, rsi
0x18001c8fc  jz      short loc_18001C90E
0x18001c8fe  mov     rcx, rsi; SRWLock
0x18001c901  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c908  nop     dword ptr [rax+rax+00h]
0x18001c90d  nop
0x18001c90e  mov     rbx, [rsp+48h+arg_8]
0x18001c913  mov     rbp, [rsp+48h+arg_10]
0x18001c918  add     rsp, 30h
0x18001c91c  pop     r14
0x18001c91e  pop     rdi
0x18001c91f  pop     rsi
0x18001c920  retn
```

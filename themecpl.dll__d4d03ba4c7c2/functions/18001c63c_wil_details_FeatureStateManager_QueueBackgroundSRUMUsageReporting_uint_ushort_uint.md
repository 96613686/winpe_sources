# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001c63c`
- end: `0x18001c798`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001eb20`

## callees

- `0x180008bfc`
- `0x18001c63c`
- `0x18001eff4`
- `0x18001f0ec`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c691`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c691`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c777`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c777`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c734`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c700`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c71b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c71b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c75f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c75f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 232), 0xCu) )
    {
      memcpy_s(
        *((void *const *)pv + 30),
        (*((_QWORD *)pv + 31) - *((_QWORD *)pv + 30)) & -(__int64)(*((_QWORD *)pv + 30) < *((_QWORD *)pv + 31)),
        &Source,
        0xCu);
      *((_QWORD *)pv + 30) += 12LL;
    }
    if ( !pv[64] )
    {
      v8 = (struct _TP_TIMER **)(pv + 56);
      if ( !*((_QWORD *)pv + 7) )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)pv + 7,
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        pv[64] = 1;
      }
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x18001c63c  mov     [rsp+arg_8], rbx
0x18001c641  mov     [rsp+arg_10], rbp
0x18001c646  push    rsi
0x18001c647  push    rdi
0x18001c648  push    r14
0x18001c64a  sub     rsp, 30h
0x18001c64e  mov     ebx, r9d
0x18001c651  movzx   esi, r8w
0x18001c655  mov     r14d, edx
0x18001c658  mov     rdi, rcx
0x18001c65b  cmp     byte ptr [rcx], 0
0x18001c65e  jz      loc_18001C784
0x18001c664  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c66b  jnz     loc_18001C784
0x18001c671  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c678  test    rax, rax
0x18001c67b  jz      short loc_18001C68A
0x18001c67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c682  test    al, al
0x18001c684  jnz     loc_18001C784
0x18001c68a  lea     rbp, [rdi+28h]
0x18001c68e  mov     rcx, rbp; SRWLock
0x18001c691  call    cs:__imp_AcquireSRWLockExclusive
0x18001c698  nop     dword ptr [rax+rax+00h]
0x18001c69d  xor     eax, eax
0x18001c69f  mov     [rsp+48h+var_22], ax
0x18001c6a4  mov     [rsp+48h+Source], r14d
0x18001c6a9  mov     [rsp+48h+var_24], si
0x18001c6ae  mov     [rsp+48h+var_20], ebx
0x18001c6b2  lea     rbx, [rdi+0E8h]
0x18001c6b9  lea     esi, [rax+0Ch]
0x18001c6bc  mov     edx, esi; unsigned __int64
0x18001c6be  mov     rcx, rbx; this
0x18001c6c1  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001c6c6  test    al, al
0x18001c6c8  jz      short loc_18001C6F0
0x18001c6ca  mov     rcx, [rbx+8]; Destination
0x18001c6ce  mov     rax, [rbx+10h]
0x18001c6d2  sub     rax, rcx
0x18001c6d5  cmp     rcx, [rbx+10h]
0x18001c6d9  sbb     rdx, rdx
0x18001c6dc  and     rdx, rax; DestinationSize
0x18001c6df  mov     r9d, esi; SourceSize
0x18001c6e2  lea     r8, [rsp+48h+Source]; Source
0x18001c6e7  call    memcpy_s
0x18001c6ec  add     [rbx+8], rsi
0x18001c6f0  cmp     byte ptr [rdi+40h], 0
0x18001c6f4  jnz     short loc_18001C76F
0x18001c6f6  lea     rsi, [rdi+38h]
0x18001c6fa  cmp     qword ptr [rsi], 0
0x18001c6fe  jnz     short loc_18001C740
0x18001c700  call    cs:__imp_GetLastError
0x18001c707  nop     dword ptr [rax+rax+00h]
0x18001c70c  mov     ebx, eax
0x18001c70e  xor     r8d, r8d; pcbe
0x18001c711  mov     rdx, rdi; pv
0x18001c714  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c71b  call    cs:__imp_CreateThreadpoolTimer
0x18001c722  nop     dword ptr [rax+rax+00h]
0x18001c727  mov     rdx, rax
0x18001c72a  mov     rcx, rsi
0x18001c72d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c732  mov     ecx, ebx; dwErrCode
0x18001c734  call    cs:__imp_SetLastError
0x18001c73b  nop     dword ptr [rax+rax+00h]
0x18001c740  mov     rcx, [rsi]; pti
0x18001c743  test    rcx, rcx
0x18001c746  jz      short loc_18001C76F
0x18001c748  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001c751  mov     r9d, 4E2h; msWindowLength
0x18001c757  xor     r8d, r8d; msPeriod
0x18001c75a  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001c75f  call    cs:__imp_SetThreadpoolTimer
0x18001c766  nop     dword ptr [rax+rax+00h]
0x18001c76b  mov     byte ptr [rdi+40h], 1
0x18001c76f  test    rbp, rbp
0x18001c772  jz      short loc_18001C784
0x18001c774  mov     rcx, rbp; SRWLock
0x18001c777  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c77e  nop     dword ptr [rax+rax+00h]
0x18001c783  nop
0x18001c784  mov     rbx, [rsp+48h+arg_8]
0x18001c789  mov     rbp, [rsp+48h+arg_10]
0x18001c78e  add     rsp, 30h
0x18001c792  pop     r14
0x18001c794  pop     rdi
0x18001c795  pop     rsi
0x18001c796  retn
```

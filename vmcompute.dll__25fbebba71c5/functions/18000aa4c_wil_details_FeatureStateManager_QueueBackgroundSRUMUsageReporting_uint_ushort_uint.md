# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000aa4c`
- end: `0x18000abb4`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `360`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e120`

## callees

- `0x180002f50`
- `0x18000aa4c`
- `0x18000ea2c`
- `0x18000eb30`
- `0x18000f3c4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aaa8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aaa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab4b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ab76`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ab76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ab32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ab32`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        DWORD a2,
        unsigned __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  __int64 Source; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h]

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    LODWORD(Source) = a2;
    HIDWORD(Source) = a3;
    v13 = a4;
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
        Source = -50000000;
        SetThreadpoolTimer(v11, (PFILETIME)&Source, 0, 0x4E2u);
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
0x18000aa4c  push    rbx
0x18000aa4e  push    rbp
0x18000aa4f  push    rsi
0x18000aa50  push    rdi
0x18000aa51  push    r14
0x18000aa53  sub     rsp, 40h
0x18000aa57  mov     rax, cs:__security_cookie
0x18000aa5e  xor     rax, rsp
0x18000aa61  mov     [rsp+68h+var_38], rax
0x18000aa66  mov     r14d, r9d
0x18000aa69  movzx   esi, r8w
0x18000aa6d  mov     ebx, edx
0x18000aa6f  mov     rdi, rcx
0x18000aa72  cmp     byte ptr [rcx], 0
0x18000aa75  jz      loc_18000AB9B
0x18000aa7b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000aa82  jnz     loc_18000AB9B
0x18000aa88  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aa8f  test    rax, rax
0x18000aa92  jz      short loc_18000AAA1
0x18000aa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa99  test    al, al
0x18000aa9b  jnz     loc_18000AB9B
0x18000aaa1  lea     rbp, [rdi+28h]
0x18000aaa5  mov     rcx, rbp; SRWLock
0x18000aaa8  call    cs:__imp_AcquireSRWLockExclusive
0x18000aaaf  nop     dword ptr [rax+rax+00h]
0x18000aab4  xor     eax, eax
0x18000aab6  mov     word ptr [rsp+68h+Source+6], ax
0x18000aabb  mov     dword ptr [rsp+68h+Source], ebx
0x18000aabf  mov     word ptr [rsp+68h+Source+4], si
0x18000aac4  mov     [rsp+68h+var_40], r14d
0x18000aac9  lea     rbx, [rdi+0E8h]
0x18000aad0  lea     esi, [rax+0Ch]
0x18000aad3  mov     edx, esi; unsigned __int64
0x18000aad5  mov     rcx, rbx; this
0x18000aad8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000aadd  test    al, al
0x18000aadf  jz      short loc_18000AB07
0x18000aae1  mov     rcx, [rbx+8]; Destination
0x18000aae5  mov     rax, [rbx+10h]
0x18000aae9  sub     rax, rcx
0x18000aaec  cmp     rcx, [rbx+10h]
0x18000aaf0  sbb     rdx, rdx
0x18000aaf3  and     rdx, rax; DestinationSize
0x18000aaf6  mov     r9d, esi; SourceSize
0x18000aaf9  lea     r8, [rsp+68h+Source]; Source
0x18000aafe  call    memcpy_s
0x18000ab03  add     [rbx+8], rsi
0x18000ab07  cmp     byte ptr [rdi+40h], 0
0x18000ab0b  jnz     short loc_18000AB86
0x18000ab0d  lea     rsi, [rdi+38h]
0x18000ab11  cmp     qword ptr [rsi], 0
0x18000ab15  jnz     short loc_18000AB57
0x18000ab17  call    cs:__imp_GetLastError
0x18000ab1e  nop     dword ptr [rax+rax+00h]
0x18000ab23  mov     ebx, eax
0x18000ab25  xor     r8d, r8d; pcbe
0x18000ab28  mov     rdx, rdi; pv
0x18000ab2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ab32  call    cs:__imp_CreateThreadpoolTimer
0x18000ab39  nop     dword ptr [rax+rax+00h]
0x18000ab3e  mov     rdx, rax
0x18000ab41  mov     rcx, rsi
0x18000ab44  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ab49  mov     ecx, ebx; dwErrCode
0x18000ab4b  call    cs:__imp_SetLastError
0x18000ab52  nop     dword ptr [rax+rax+00h]
0x18000ab57  mov     rcx, [rsi]; pti
0x18000ab5a  test    rcx, rcx
0x18000ab5d  jz      short loc_18000AB86
0x18000ab5f  mov     [rsp+68h+Source], 0FFFFFFFFFD050F80h
0x18000ab68  mov     r9d, 4E2h; msWindowLength
0x18000ab6e  xor     r8d, r8d; msPeriod
0x18000ab71  lea     rdx, [rsp+68h+Source]; pftDueTime
0x18000ab76  call    cs:__imp_SetThreadpoolTimer
0x18000ab7d  nop     dword ptr [rax+rax+00h]
0x18000ab82  mov     byte ptr [rdi+40h], 1
0x18000ab86  test    rbp, rbp
0x18000ab89  jz      short loc_18000AB9B
0x18000ab8b  mov     rcx, rbp; SRWLock
0x18000ab8e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab95  nop     dword ptr [rax+rax+00h]
0x18000ab9a  nop
0x18000ab9b  mov     rcx, [rsp+68h+var_38]
0x18000aba0  xor     rcx, rsp; StackCookie
0x18000aba3  call    __security_check_cookie
0x18000aba8  add     rsp, 40h
0x18000abac  pop     r14
0x18000abae  pop     rdi
0x18000abaf  pop     rsi
0x18000abb0  pop     rbp
0x18000abb1  pop     rbx
0x18000abb2  retn
```

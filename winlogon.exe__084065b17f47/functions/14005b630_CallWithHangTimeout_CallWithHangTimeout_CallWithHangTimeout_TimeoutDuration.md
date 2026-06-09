# CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)

- ea: `0x14005b630`
- end: `0x14005b7f8`
- name: `??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z`
- size: `456`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `38`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400060d0`
- `0x1400106bc`
- `0x140015a48`
- `0x1400176f8`
- `0x140033894`
- `0x140036200`
- `0x140047370`
- `0x14004c400`
- `0x14004d980`
- `0x14004ddc8`
- `0x14004e770`
- `0x1400500f0`
- `0x1400505c4`
- `0x1400516a0`
- `0x140052c20`
- `0x14005b81c`
- `0x14005d310`
- `0x1400619c0`
- `0x1400625d0`
- `0x140062e20`
- `0x140063660`
- `0x140063a00`
- `0x140063ba0`
- `0x140063f80`
- `0x1400643e0`
- `0x1400647e0`
- `0x140064ce0`
- `0x140065950`
- `0x14006de20`
- `0x14006e220`
- `0x140077060`
- `0x140079d50`
- `0x140084aa0`
- `0x140084e20`
- `0x1400858e0`
- `0x1400872a8`
- `0x1400877f0`
- `0x14008be98`

## callees

- `0x140053ad0`
- `0x140053b38`
- `0x14005b630`
- `0x14005c7e8`
- `0x14005c834`
- `0x14005d664`
- `0x14005d698`
- `0x14005d714`
- `0x14005d800`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005b7d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14005b7d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14005b6d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14005b6d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14005b74b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14005b74b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005b64f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005b64f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005b646`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005b646`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14005b67d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14005b67d`

## string_xrefs

- `0x14005b7c9`: `verifier.dll`

## pseudocode

```c
_DWORD *__fastcall CallWithHangTimeout::CallWithHangTimeout(_DWORD *a1, int a2)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v5; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v7; // r9
  struct _TP_TIMER *v8; // rcx
  __int64 v9; // rax
  bool v11; // al
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)a1 = 0;
  a1[2] = GetCurrentThreadId();
  a1[3] = GetCurrentProcessId();
  *((_QWORD *)a1 + 2) = 0;
  a1[6] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl'::`2'::impl);
  if ( !IsDebuggerPresent() && !CallWithHangTimeout::IsTargetBeingDebugged() )
  {
    ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v5 = *ThreadLocalStoragePointer;
    if ( __TSS0__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
    {
      Init_thread_header(&__TSS0__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA);
      if ( __TSS0__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA == -1 )
      {
        v11 = (NtCurrentPeb()->NtGlobalFlag & 0x100) != 0 && GetModuleHandleW(L"verifier.dll");
        `CallWithHangTimeout::CallWithHangTimeout'::`2'::s_isAppVerifierEnabled = v11;
        Init_thread_footer(&__TSS0__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA);
      }
    }
    if ( __TSS1__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA > *(_DWORD *)(v5 + 4) )
    {
      Init_thread_header(&__TSS1__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA);
      if ( __TSS1__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA == -1 )
      {
        `CallWithHangTimeout::CallWithHangTimeout'::`2'::s_timeoutOverride = 10000
                                                                           * CallWithHangTimeout::GetTimeoutOverride();
        Init_thread_footer(&__TSS1__1___0CallWithHangTimeout__QEAA_W4TimeoutDuration_1__Z_4HA);
      }
    }
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_fe166ee785c77a0b82d43104ca244eaa_::_lambda_invoker_cdecl_, a1, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      a1,
      ThreadpoolTimer);
    if ( !*(_QWORD *)a1 )
      wil::details::in1diag3::_Log_NullAlloc(
        retaddr,
        (void *)0x3A,
        (unsigned int)"OneCoreUap\\Internal\\DS\\inc\\winlogon/CallWithHangTimeout.h",
        v7);
    v8 = *(struct _TP_TIMER **)a1;
    if ( *(_QWORD *)a1 )
    {
      v9 = `CallWithHangTimeout::CallWithHangTimeout'::`2'::s_timeoutOverride;
      if ( !`CallWithHangTimeout::CallWithHangTimeout'::`2'::s_timeoutOverride )
      {
        v9 = 300000000;
        if ( a2 != 1 )
          v9 = 100000000;
        if ( `CallWithHangTimeout::CallWithHangTimeout'::`2'::s_isAppVerifierEnabled )
          v9 *= 4;
      }
      pftDueTime = (struct _FILETIME)-v9;
      SetThreadpoolTimer(v8, &pftDueTime, 0, 0x3E8u);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14005b630  push    rbx
0x14005b632  push    rsi
0x14005b633  push    rdi
0x14005b634  push    r14
0x14005b636  sub     rsp, 28h
0x14005b63a  mov     esi, edx
0x14005b63c  mov     qword ptr [rcx], 0
0x14005b643  mov     rbx, rcx
0x14005b646  call    cs:__imp_GetCurrentThreadId
0x14005b64c  mov     [rbx+8], eax
0x14005b64f  call    cs:__imp_GetCurrentProcessId
0x14005b655  mov     [rbx+0Ch], eax
0x14005b658  xor     eax, eax
0x14005b65a  mov     [rbx+10h], rax
0x14005b65e  mov     [rbx+18h], eax
0x14005b661  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl(void)'::`2'::impl
0x14005b668  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(void)
0x14005b66d  test    al, al
0x14005b66f  jnz     short loc_14005B67D
0x14005b671  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::GetImpl(void)'::`2'::impl
0x14005b678  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnDWMCallouts2>::__private_IsEnabled(void)
0x14005b67d  call    cs:__imp_IsDebuggerPresent
0x14005b683  test    eax, eax
0x14005b685  jnz     loc_14005B751
0x14005b68b  call    ?IsTargetBeingDebugged@CallWithHangTimeout@@CA_NXZ; CallWithHangTimeout::IsTargetBeingDebugged(void)
0x14005b690  test    al, al
0x14005b692  jnz     loc_14005B751
0x14005b698  mov     rax, gs:58h
0x14005b6a1  mov     r14d, 4
0x14005b6a7  mov     rdi, [rax]
0x14005b6aa  mov     eax, [r14+rdi]
0x14005b6ae  cmp     cs:?$TSS0@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA, eax
0x14005b6b4  jg      loc_14005B79B
0x14005b6ba  mov     eax, [r14+rdi]
0x14005b6be  cmp     cs:?$TSS1@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA, eax
0x14005b6c4  jg      loc_14005B75E
0x14005b6ca  xor     r8d, r8d; pcbe
0x14005b6cd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_fe166ee785c77a0b82d43104ca244eaa_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14005b6d4  mov     rdx, rbx; pv
0x14005b6d7  call    cs:__imp_CreateThreadpoolTimer
0x14005b6dd  mov     rdx, rax
0x14005b6e0  mov     rcx, rbx
0x14005b6e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14005b6e8  cmp     qword ptr [rbx], 0
0x14005b6ec  jnz     short loc_14005B704
0x14005b6ee  mov     rcx, [rsp+48h]; this
0x14005b6f3  lea     r8, aOnecoreuapInte_5; "OneCoreUap\\Internal\\DS\\inc\\winlogon"...
0x14005b6fa  mov     edx, 3Ah ; ':'; void *
0x14005b6ff  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x14005b704  mov     rcx, [rbx]; pti
0x14005b707  test    rcx, rcx
0x14005b70a  jz      short loc_14005B751
0x14005b70c  mov     rax, cs:?s_timeoutOverride@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4_KA; unsigned __int64 `CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)'::`2'::s_timeoutOverride
0x14005b713  test    rax, rax
0x14005b716  jnz     short loc_14005B735
0x14005b718  cmp     esi, 1
0x14005b71b  mov     eax, 11E1A300h
0x14005b720  mov     edx, 5F5E100h
0x14005b725  cmovnz  eax, edx
0x14005b728  cmp     cs:?s_isAppVerifierEnabled@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4_NA, 0; bool `CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)'::`2'::s_isAppVerifierEnabled
0x14005b72f  jz      short loc_14005B735
0x14005b731  shl     rax, 2
0x14005b735  neg     rax
0x14005b738  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x14005b73d  mov     r9d, 3E8h; msWindowLength
0x14005b743  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x14005b748  xor     r8d, r8d; msPeriod
0x14005b74b  call    cs:__imp_SetThreadpoolTimer
0x14005b751  mov     rax, rbx
0x14005b754  add     rsp, 28h
0x14005b758  pop     r14
0x14005b75a  pop     rdi
0x14005b75b  pop     rsi
0x14005b75c  pop     rbx
0x14005b75d  retn
0x14005b75e  lea     rcx, ?$TSS1@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA
0x14005b765  call    _Init_thread_header
0x14005b76a  cmp     cs:?$TSS1@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA, 0FFFFFFFFh
0x14005b771  jnz     loc_14005B6CA
0x14005b777  call    ?GetTimeoutOverride@CallWithHangTimeout@@CA_KXZ; CallWithHangTimeout::GetTimeoutOverride(void)
0x14005b77c  imul    rdx, rax, 2710h
0x14005b783  lea     rcx, ?$TSS1@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA
0x14005b78a  mov     cs:?s_timeoutOverride@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4_KA, rdx; unsigned __int64 `CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)'::`2'::s_timeoutOverride
0x14005b791  call    _Init_thread_footer
0x14005b796  jmp     loc_14005B6CA
0x14005b79b  lea     rcx, ?$TSS0@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA
0x14005b7a2  call    _Init_thread_header
0x14005b7a7  cmp     cs:?$TSS0@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA, 0FFFFFFFFh
0x14005b7ae  jnz     loc_14005B6BA
0x14005b7b4  mov     rax, gs:60h
0x14005b7bd  test    dword ptr [rax+0BCh], 100h
0x14005b7c7  jz      short loc_14005B7DF
0x14005b7c9  lea     rcx, aVerifierDll; "verifier.dll"
0x14005b7d0  call    cs:__imp_GetModuleHandleW
0x14005b7d6  test    rax, rax
0x14005b7d9  jz      short loc_14005B7DF
0x14005b7db  mov     al, 1
0x14005b7dd  jmp     short loc_14005B7E1
0x14005b7df  xor     al, al
0x14005b7e1  lea     rcx, ?$TSS0@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4HA
0x14005b7e8  mov     cs:?s_isAppVerifierEnabled@?1???0CallWithHangTimeout@@QEAA@W4TimeoutDuration@1@@Z@4_NA, al; bool `CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)'::`2'::s_isAppVerifierEnabled
0x14005b7ee  call    _Init_thread_footer
0x14005b7f3  jmp     loc_14005B6BA
```

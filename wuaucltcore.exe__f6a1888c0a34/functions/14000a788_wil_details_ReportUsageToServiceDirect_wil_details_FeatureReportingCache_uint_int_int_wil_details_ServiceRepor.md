# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000a788`
- end: `0x14000a993`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x14000a99c`

## callees

- `0x140004b40`
- `0x14000a314`
- `0x14000a63c`
- `0x14000a788`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a86b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a917`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a86b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a832`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a832`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a8cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v12; // rax
  __m128i v13; // xmm1
  unsigned int v14; // ebx
  unsigned __int64 v15; // r8
  __int64 v16; // r8
  void (__fastcall *v17)(_QWORD, _QWORD, __int64, _QWORD); // rax
  int v18; // edi
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(_QWORD, __int64, _QWORD, _QWORD); // rax
  bool v22; // zf
  _DWORD v24[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v25; // [rsp+38h] [rbp-70h]
  __m128i v26; // [rsp+40h] [rbp-68h]
  __int64 v27; // [rsp+60h] [rbp-48h]
  _BYTE v28[64]; // [rsp+68h] [rbp-40h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v28, a1, a5);
  v13 = *(__m128i *)v12;
  v26 = *(__m128i *)v12;
  v27 = *(_QWORD *)(v12 + 16);
  v14 = 0;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
  {
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
    v13 = v26;
  }
  if ( _mm_cvtsi128_si32(v13) && wil::details::g_enabledStateManager && !wil::details::g_processShutdownInProgress )
  {
    if ( !wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v24[0] = a2;
      v24[1] = 0;
      v25 = a1;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002E5C0, v24, v15);
      wil::details::EnabledStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)&wil::details::g_enabledStateManager);
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v13 = v26;
  }
  v16 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 4));
  if ( (_DWORD)v16 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 8)), v16, 0);
    }
  }
  v18 = v27;
  if ( !(_DWORD)v27 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_14002E5B8 )
    {
      qword_14002E5B8 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_14002E5B8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    v21 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(a2, v20, 0, 0);
    }
  }
  v22 = v18 == 0;
  if ( !v18 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v16) = a8;
      g_wil_details_realtimeFeatureUsageHook(a2, a5, v16);
    }
    v22 = 1;
  }
  LOBYTE(v14) = v22;
  return v14;
}

```

## disassembly

```asm
0x14000a788  mov     [rsp+arg_10], rbx
0x14000a78d  push    rbp
0x14000a78e  push    rsi
0x14000a78f  push    rdi
0x14000a790  push    r14
0x14000a792  push    r15
0x14000a794  sub     rsp, 80h
0x14000a79b  mov     r15d, r9d
0x14000a79e  mov     r14d, r8d
0x14000a7a1  mov     ebp, edx
0x14000a7a3  mov     rdi, rcx
0x14000a7a6  mov     esi, [rsp+0A8h+arg_20]
0x14000a7ad  mov     r8d, esi
0x14000a7b0  mov     rdx, rcx
0x14000a7b3  lea     rcx, [rsp+0A8h+var_40]
0x14000a7b8  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000a7bd  movups  xmm1, xmmword ptr [rax]
0x14000a7c0  movups  [rsp+0A8h+var_68], xmm1
0x14000a7c5  movsd   xmm0, qword ptr [rax+10h]
0x14000a7ca  movsd   [rsp+0A8h+var_48], xmm0
0x14000a7d0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000a7d7  xor     ebx, ebx
0x14000a7d9  test    rax, rax
0x14000a7dc  jz      short loc_14000A7FE
0x14000a7de  test    esi, esi
0x14000a7e0  jz      short loc_14000A7EA
0x14000a7e2  lea     ecx, [rsi-64h]
0x14000a7e5  cmp     ecx, 31h ; '1'
0x14000a7e8  ja      short loc_14000A7FE
0x14000a7ea  mov     r8d, 1
0x14000a7f0  mov     edx, esi
0x14000a7f2  mov     ecx, ebp
0x14000a7f4  call    _guard_dispatch_icall
0x14000a7f9  movups  xmm1, [rsp+0A8h+var_68]
0x14000a7fe  movd    eax, xmm1
0x14000a802  test    eax, eax
0x14000a804  jz      short loc_14000A876
0x14000a806  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000a80c  jz      short loc_14000A876
0x14000a80e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x14000a814  jnz     short loc_14000A876
0x14000a816  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a81d  test    rax, rax
0x14000a820  jz      short loc_14000A82B
0x14000a822  call    _guard_dispatch_icall
0x14000a827  test    al, al
0x14000a829  jnz     short loc_14000A871
0x14000a82b  lea     rcx, SRWLock; SRWLock
0x14000a832  call    cs:__imp_AcquireSRWLockExclusive
0x14000a838  mov     [rsp+0A8h+var_78], ebp
0x14000a83c  xor     eax, eax
0x14000a83e  mov     [rsp+0A8h+var_74], eax
0x14000a842  mov     [rsp+0A8h+var_70], rdi
0x14000a847  lea     rdx, [rsp+0A8h+var_78]; void *
0x14000a84c  lea     rcx, qword_14002E5C0; this
0x14000a853  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000a858  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000a85f  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::EnsureTimerUnderLock(void)
0x14000a864  lea     rcx, SRWLock; SRWLock
0x14000a86b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a871  movups  xmm1, [rsp+0A8h+var_68]
0x14000a876  movdqa  xmm0, xmm1
0x14000a87a  psrldq  xmm0, 4
0x14000a87f  movd    r8d, xmm0
0x14000a884  test    r8d, r8d
0x14000a887  jz      short loc_14000A8B4
0x14000a889  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000a890  test    rax, rax
0x14000a893  jnz     short loc_14000A8A1
0x14000a895  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000a89c  test    rax, rax
0x14000a89f  jz      short loc_14000A8B4
0x14000a8a1  psrldq  xmm1, 8
0x14000a8a6  xor     r9d, r9d
0x14000a8a9  movd    edx, xmm1
0x14000a8ad  mov     ecx, ebp
0x14000a8af  call    _guard_dispatch_icall
0x14000a8b4  mov     edi, dword ptr [rsp+0A8h+var_48]
0x14000a8b8  test    edi, edi
0x14000a8ba  jnz     short loc_14000A91E
0x14000a8bc  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000a8c2  jz      short loc_14000A91E
0x14000a8c4  lea     rcx, SRWLock; SRWLock
0x14000a8cb  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8d1  cmp     cs:qword_14002E5B8, rbx
0x14000a8d8  jnz     short loc_14000A910
0x14000a8da  mov     cs:qword_14002E5B8, rbx
0x14000a8e1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000a8e8  test    rax, rax
0x14000a8eb  jnz     short loc_14000A8F9
0x14000a8ed  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000a8f4  test    rax, rax
0x14000a8f7  jz      short loc_14000A910
0x14000a8f9  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000a8fd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x14000a904  lea     rcx, qword_14002E5B8
0x14000a90b  call    _guard_dispatch_icall
0x14000a910  lea     rcx, SRWLock; SRWLock
0x14000a917  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a91d  nop
0x14000a91e  test    r14d, r14d
0x14000a921  jz      short loc_14000A954
0x14000a923  mov     edx, esi
0x14000a925  bts     edx, 1Fh
0x14000a929  test    r15d, r15d
0x14000a92c  cmovz   edx, esi
0x14000a92f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000a936  test    rax, rax
0x14000a939  jnz     short loc_14000A947
0x14000a93b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000a942  test    rax, rax
0x14000a945  jz      short loc_14000A954
0x14000a947  xor     r9d, r9d
0x14000a94a  xor     r8d, r8d
0x14000a94d  mov     ecx, ebp
0x14000a94f  call    _guard_dispatch_icall
0x14000a954  test    edi, edi
0x14000a956  jnz     short loc_14000A977
0x14000a958  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000a95f  test    rax, rax
0x14000a962  jz      short loc_14000A975
0x14000a964  mov     r8b, [rsp+0A8h+arg_38]
0x14000a96c  mov     edx, esi
0x14000a96e  mov     ecx, ebp
0x14000a970  call    _guard_dispatch_icall
0x14000a975  test    edi, edi
0x14000a977  setz    bl
0x14000a97a  mov     eax, ebx
0x14000a97c  mov     rbx, [rsp+0A8h+arg_10]
0x14000a984  add     rsp, 80h
0x14000a98b  pop     r15
0x14000a98d  pop     r14
0x14000a98f  pop     rdi
0x14000a990  pop     rsi
0x14000a991  pop     rbp
0x14000a992  retn
```

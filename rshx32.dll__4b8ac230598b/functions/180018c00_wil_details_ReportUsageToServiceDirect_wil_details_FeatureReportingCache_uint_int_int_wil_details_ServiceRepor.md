# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180018c00`
- end: `0x180018d9e`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180018ac8`

## callees

- `0x180018770`
- `0x180018c00`
- `0x1800195a8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018d17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018d17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018ccb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018ccb`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // r8
  unsigned int v12; // ebp
  int v13; // r15d
  unsigned int v14; // esi
  unsigned int v15; // r13d
  int v16; // r12d
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v19)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = 1;
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v14 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180028CA0 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_180028CA0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180028CA0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(a2, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v12;
}

```

## disassembly

```asm
0x180018c00  mov     rax, rsp
0x180018c03  mov     [rax+8], rbx
0x180018c07  mov     [rax+20h], r9d
0x180018c0b  mov     [rax+18h], r8d
0x180018c0f  push    rbp
0x180018c10  push    rsi
0x180018c11  push    rdi
0x180018c12  push    r12
0x180018c14  push    r13
0x180018c16  push    r14
0x180018c18  push    r15
0x180018c1a  sub     rsp, 50h
0x180018c1e  mov     ebx, [rsp+88h+arg_20]
0x180018c25  mov     edi, edx
0x180018c27  mov     rdx, rcx
0x180018c2a  mov     r14, rcx
0x180018c2d  lea     rcx, [rax-58h]
0x180018c31  mov     r8d, ebx
0x180018c34  call    wil_details_FeatureReporting_RecordUsageInCache
0x180018c39  mov     ebp, 1
0x180018c3e  mov     r15d, [rax]
0x180018c41  mov     esi, [rax+4]
0x180018c44  mov     r13d, [rax+8]
0x180018c48  mov     r12d, [rax+10h]
0x180018c4c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180018c53  test    rax, rax
0x180018c56  jz      short loc_180018C70
0x180018c58  test    ebx, ebx
0x180018c5a  jz      short loc_180018C64
0x180018c5c  lea     ecx, [rbx-64h]
0x180018c5f  cmp     ecx, 31h ; '1'
0x180018c62  ja      short loc_180018C70
0x180018c64  mov     r8d, ebp
0x180018c67  mov     edx, ebx
0x180018c69  mov     ecx, edi
0x180018c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c70  test    r15d, r15d
0x180018c73  jz      short loc_180018C86
0x180018c75  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x180018c78  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180018c7f  mov     edx, edi; unsigned int
0x180018c81  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x180018c86  xor     r14d, r14d
0x180018c89  test    esi, esi
0x180018c8b  jz      short loc_180018CB5
0x180018c8d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180018c94  test    rax, rax
0x180018c97  jnz     short loc_180018CA5
0x180018c99  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180018ca0  test    rax, rax
0x180018ca3  jz      short loc_180018CB5
0x180018ca5  xor     r9d, r9d
0x180018ca8  mov     r8d, esi
0x180018cab  mov     edx, r13d
0x180018cae  mov     ecx, edi
0x180018cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cb5  test    r12d, r12d
0x180018cb8  jnz     short loc_180018D1D
0x180018cba  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018cc0  test    eax, eax
0x180018cc2  jz      short loc_180018D1D
0x180018cc4  lea     rcx, SRWLock; SRWLock
0x180018ccb  call    cs:__imp_AcquireSRWLockExclusive
0x180018cd1  cmp     cs:qword_180028CA0, r14
0x180018cd8  jnz     short loc_180018D10
0x180018cda  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180018ce1  mov     cs:qword_180028CA0, r14
0x180018ce8  test    rax, rax
0x180018ceb  jnz     short loc_180018CF9
0x180018ced  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180018cf4  test    rax, rax
0x180018cf7  jz      short loc_180018D10
0x180018cf9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018cfd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180018d04  lea     rcx, qword_180028CA0
0x180018d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d10  lea     rcx, SRWLock; SRWLock
0x180018d17  call    cs:__imp_ReleaseSRWLockExclusive
0x180018d1d  cmp     [rsp+88h+arg_10], r14d
0x180018d25  jz      short loc_180018D5D
0x180018d27  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180018d2e  mov     edx, ebx
0x180018d30  bts     edx, 1Fh
0x180018d34  cmp     [rsp+88h+arg_18], r14d
0x180018d3c  cmovz   edx, ebx
0x180018d3f  test    rax, rax
0x180018d42  jnz     short loc_180018D50
0x180018d44  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180018d4b  test    rax, rax
0x180018d4e  jz      short loc_180018D5D
0x180018d50  xor     r9d, r9d
0x180018d53  xor     r8d, r8d
0x180018d56  mov     ecx, edi
0x180018d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d5d  test    r12d, r12d
0x180018d60  jnz     short loc_180018D81
0x180018d62  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180018d69  test    rax, rax
0x180018d6c  jz      short loc_180018D84
0x180018d6e  mov     r8b, [rsp+88h+arg_38]
0x180018d76  mov     edx, ebx
0x180018d78  mov     ecx, edi
0x180018d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d7f  jmp     short loc_180018D84
0x180018d81  mov     ebp, r14d
0x180018d84  mov     rbx, [rsp+88h+arg_0]
0x180018d8c  mov     eax, ebp
0x180018d8e  add     rsp, 50h
0x180018d92  pop     r15
0x180018d94  pop     r14
0x180018d96  pop     r13
0x180018d98  pop     r12
0x180018d9a  pop     rdi
0x180018d9b  pop     rsi
0x180018d9c  pop     rbp
0x180018d9d  retn
```

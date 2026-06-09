# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000b708`
- end: `0x14000b8a6`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000b5d0`

## callees

- `0x14000a2f8`
- `0x14000b708`
- `0x14000c910`
- `0x140016010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b7d3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b7d3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b81f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b81f`

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
    if ( !qword_1400214C0 )
    {
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1400214C0 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1400214C0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x14000b708  mov     rax, rsp
0x14000b70b  mov     [rax+8], rbx
0x14000b70f  mov     [rax+20h], r9d
0x14000b713  mov     [rax+18h], r8d
0x14000b717  push    rbp
0x14000b718  push    rsi
0x14000b719  push    rdi
0x14000b71a  push    r12
0x14000b71c  push    r13
0x14000b71e  push    r14
0x14000b720  push    r15
0x14000b722  sub     rsp, 50h
0x14000b726  mov     ebx, [rsp+88h+arg_20]
0x14000b72d  mov     edi, edx
0x14000b72f  mov     rdx, rcx
0x14000b732  mov     r14, rcx
0x14000b735  lea     rcx, [rax-58h]
0x14000b739  mov     r8d, ebx
0x14000b73c  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000b741  mov     ebp, 1
0x14000b746  mov     r15d, [rax]
0x14000b749  mov     esi, [rax+4]
0x14000b74c  mov     r13d, [rax+8]
0x14000b750  mov     r12d, [rax+10h]
0x14000b754  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000b75b  test    rax, rax
0x14000b75e  jz      short loc_14000B778
0x14000b760  test    ebx, ebx
0x14000b762  jz      short loc_14000B76C
0x14000b764  lea     ecx, [rbx-64h]
0x14000b767  cmp     ecx, 31h ; '1'
0x14000b76a  ja      short loc_14000B778
0x14000b76c  mov     r8d, ebp
0x14000b76f  mov     edx, ebx
0x14000b771  mov     ecx, edi
0x14000b773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b778  test    r15d, r15d
0x14000b77b  jz      short loc_14000B78E
0x14000b77d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x14000b780  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000b787  mov     edx, edi; unsigned int
0x14000b789  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000b78e  xor     r14d, r14d
0x14000b791  test    esi, esi
0x14000b793  jz      short loc_14000B7BD
0x14000b795  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000b79c  test    rax, rax
0x14000b79f  jnz     short loc_14000B7AD
0x14000b7a1  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000b7a8  test    rax, rax
0x14000b7ab  jz      short loc_14000B7BD
0x14000b7ad  xor     r9d, r9d
0x14000b7b0  mov     r8d, esi
0x14000b7b3  mov     edx, r13d
0x14000b7b6  mov     ecx, edi
0x14000b7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7bd  test    r12d, r12d
0x14000b7c0  jnz     short loc_14000B825
0x14000b7c2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000b7c8  test    eax, eax
0x14000b7ca  jz      short loc_14000B825
0x14000b7cc  lea     rcx, SRWLock; SRWLock
0x14000b7d3  call    cs:__imp_AcquireSRWLockExclusive
0x14000b7d9  cmp     cs:qword_1400214C0, r14
0x14000b7e0  jnz     short loc_14000B818
0x14000b7e2  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000b7e9  mov     cs:qword_1400214C0, r14
0x14000b7f0  test    rax, rax
0x14000b7f3  jnz     short loc_14000B801
0x14000b7f5  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000b7fc  test    rax, rax
0x14000b7ff  jz      short loc_14000B818
0x14000b801  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b805  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x14000b80c  lea     rcx, qword_1400214C0
0x14000b813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b818  lea     rcx, SRWLock; SRWLock
0x14000b81f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b825  cmp     [rsp+88h+arg_10], r14d
0x14000b82d  jz      short loc_14000B865
0x14000b82f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000b836  mov     edx, ebx
0x14000b838  bts     edx, 1Fh
0x14000b83c  cmp     [rsp+88h+arg_18], r14d
0x14000b844  cmovz   edx, ebx
0x14000b847  test    rax, rax
0x14000b84a  jnz     short loc_14000B858
0x14000b84c  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000b853  test    rax, rax
0x14000b856  jz      short loc_14000B865
0x14000b858  xor     r9d, r9d
0x14000b85b  xor     r8d, r8d
0x14000b85e  mov     ecx, edi
0x14000b860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b865  test    r12d, r12d
0x14000b868  jnz     short loc_14000B889
0x14000b86a  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000b871  test    rax, rax
0x14000b874  jz      short loc_14000B88C
0x14000b876  mov     r8b, [rsp+88h+arg_38]
0x14000b87e  mov     edx, ebx
0x14000b880  mov     ecx, edi
0x14000b882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b887  jmp     short loc_14000B88C
0x14000b889  mov     ebp, r14d
0x14000b88c  mov     rbx, [rsp+88h+arg_0]
0x14000b894  mov     eax, ebp
0x14000b896  add     rsp, 50h
0x14000b89a  pop     r15
0x14000b89c  pop     r14
0x14000b89e  pop     r13
0x14000b8a0  pop     r12
0x14000b8a2  pop     rdi
0x14000b8a3  pop     rsi
0x14000b8a4  pop     rbp
0x14000b8a5  retn
```

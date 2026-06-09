# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000c948`
- end: `0x18000cae7`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c810`

## callees

- `0x18000b114`
- `0x18000c948`
- `0x180012270`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ca5f`

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
  int v12; // r15d
  unsigned int v13; // esi
  unsigned int v14; // r12d
  int v15; // r13d
  unsigned int v16; // ebp
  void (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v19; // rdx
  void (__fastcall *v20)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5);
  v12 = *v10;
  v13 = v10[1];
  v14 = v10[2];
  v15 = v10[4];
  v16 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      a2,
      a1);
  if ( v13 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180047480 )
    {
      qword_180047480 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180047480, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = a5;
    LODWORD(v19) = a5 | 0x80000000;
    if ( !a4 )
      v19 = a5;
    v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(a2, v19, 0, 0);
    }
  }
  if ( v15 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v11) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v11);
  }
  return v16;
}

```

## disassembly

```asm
0x18000c948  mov     rax, rsp
0x18000c94b  mov     [rax+8], rbx
0x18000c94f  mov     [rax+20h], r9d
0x18000c953  mov     [rax+18h], r8d
0x18000c957  push    rbp
0x18000c958  push    rsi
0x18000c959  push    rdi
0x18000c95a  push    r12
0x18000c95c  push    r13
0x18000c95e  push    r14
0x18000c960  push    r15
0x18000c962  sub     rsp, 50h
0x18000c966  mov     edi, edx
0x18000c968  mov     r14, rcx
0x18000c96b  mov     ebx, [rsp+88h+arg_20]
0x18000c972  mov     r8d, ebx
0x18000c975  mov     rdx, rcx
0x18000c978  lea     rcx, [rax-58h]
0x18000c97c  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000c981  mov     r15d, [rax]
0x18000c984  mov     esi, [rax+4]
0x18000c987  mov     r12d, [rax+8]
0x18000c98b  mov     r13d, [rax+10h]
0x18000c98f  mov     ebp, 1
0x18000c994  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c99b  test    rax, rax
0x18000c99e  jz      short loc_18000C9B8
0x18000c9a0  test    ebx, ebx
0x18000c9a2  jz      short loc_18000C9AC
0x18000c9a4  lea     ecx, [rbx-64h]
0x18000c9a7  cmp     ecx, 31h ; '1'
0x18000c9aa  ja      short loc_18000C9B8
0x18000c9ac  mov     r8d, ebp
0x18000c9af  mov     edx, ebx
0x18000c9b1  mov     ecx, edi
0x18000c9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9b8  test    r15d, r15d
0x18000c9bb  jz      short loc_18000C9CE
0x18000c9bd  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000c9c0  mov     edx, edi; unsigned int
0x18000c9c2  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c9c9  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c9ce  xor     r14d, r14d
0x18000c9d1  test    esi, esi
0x18000c9d3  jz      short loc_18000C9FD
0x18000c9d5  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c9dc  test    rax, rax
0x18000c9df  jnz     short loc_18000C9ED
0x18000c9e1  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c9e8  test    rax, rax
0x18000c9eb  jz      short loc_18000C9FD
0x18000c9ed  xor     r9d, r9d
0x18000c9f0  mov     r8d, esi
0x18000c9f3  mov     edx, r12d
0x18000c9f6  mov     ecx, edi
0x18000c9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9fd  test    r13d, r13d
0x18000ca00  jnz     short loc_18000CA66
0x18000ca02  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ca08  test    eax, eax
0x18000ca0a  jz      short loc_18000CA66
0x18000ca0c  lea     rcx, SRWLock; SRWLock
0x18000ca13  call    cs:__imp_AcquireSRWLockExclusive
0x18000ca19  cmp     cs:qword_180047480, r14
0x18000ca20  jnz     short loc_18000CA58
0x18000ca22  mov     cs:qword_180047480, r14
0x18000ca29  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ca30  test    rax, rax
0x18000ca33  jnz     short loc_18000CA41
0x18000ca35  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ca3c  test    rax, rax
0x18000ca3f  jz      short loc_18000CA58
0x18000ca41  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ca45  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000ca4c  lea     rcx, qword_180047480
0x18000ca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca58  lea     rcx, SRWLock; SRWLock
0x18000ca5f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca65  nop
0x18000ca66  cmp     [rsp+88h+arg_10], r14d
0x18000ca6e  jz      short loc_18000CAA6
0x18000ca70  mov     edx, ebx
0x18000ca72  bts     edx, 1Fh
0x18000ca76  cmp     [rsp+88h+arg_18], r14d
0x18000ca7e  cmovz   edx, ebx
0x18000ca81  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ca88  test    rax, rax
0x18000ca8b  jnz     short loc_18000CA99
0x18000ca8d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ca94  test    rax, rax
0x18000ca97  jz      short loc_18000CAA6
0x18000ca99  xor     r9d, r9d
0x18000ca9c  xor     r8d, r8d
0x18000ca9f  mov     ecx, edi
0x18000caa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caa6  test    r13d, r13d
0x18000caa9  jnz     short loc_18000CACA
0x18000caab  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000cab2  test    rax, rax
0x18000cab5  jz      short loc_18000CACD
0x18000cab7  mov     r8b, [rsp+88h+arg_38]
0x18000cabf  mov     edx, ebx
0x18000cac1  mov     ecx, edi
0x18000cac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cac8  jmp     short loc_18000CACD
0x18000caca  mov     ebp, r14d
0x18000cacd  mov     eax, ebp
0x18000cacf  mov     rbx, [rsp+88h+arg_0]
0x18000cad7  add     rsp, 50h
0x18000cadb  pop     r15
0x18000cadd  pop     r14
0x18000cadf  pop     r13
0x18000cae1  pop     r12
0x18000cae3  pop     rdi
0x18000cae4  pop     rsi
0x18000cae5  pop     rbp
0x18000cae6  retn
```

# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000a1b8`
- end: `0x18000a34b`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a0e0`

## callees

- `0x180008c50`
- `0x18000a1b8`
- `0x18000bc50`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a27f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a27f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  int *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r14d
  unsigned int v14; // edi
  unsigned int v15; // r15d
  int v16; // r12d
  unsigned int v17; // esi
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(__int64, __int64, _QWORD, _QWORD); // rax
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = *v10;
  v14 = v10[1];
  v15 = v10[2];
  v16 = v10[4];
  v17 = 1;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(16372493, a5, 1);
  if ( v13 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v14 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(16372493, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180015898 )
    {
      qword_180015898 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_180015898, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
    v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(16372493, v20, 0, 0);
    }
  }
  if ( v16 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(16372493, a5, v12);
  }
  return v17;
}

```

## disassembly

```asm
0x18000a1b8  mov     [rsp+arg_18], r9d
0x18000a1bd  push    rbx
0x18000a1be  push    rbp
0x18000a1bf  push    rsi
0x18000a1c0  push    rdi
0x18000a1c1  push    r12
0x18000a1c3  push    r13
0x18000a1c5  push    r14
0x18000a1c7  push    r15
0x18000a1c9  sub     rsp, 58h
0x18000a1cd  mov     r13d, r8d
0x18000a1d0  mov     rbp, rcx
0x18000a1d3  mov     ebx, [rsp+98h+arg_20]
0x18000a1da  mov     r8d, ebx
0x18000a1dd  mov     rdx, rcx
0x18000a1e0  lea     rcx, [rsp+98h+var_68]
0x18000a1e5  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000a1ea  mov     r14d, [rax]
0x18000a1ed  mov     edi, [rax+4]
0x18000a1f0  mov     r15d, [rax+8]
0x18000a1f4  mov     r12d, [rax+10h]
0x18000a1f8  mov     esi, 1
0x18000a1fd  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000a204  test    rax, rax
0x18000a207  jz      short loc_18000A224
0x18000a209  test    ebx, ebx
0x18000a20b  jz      short loc_18000A215
0x18000a20d  lea     ecx, [rbx-64h]
0x18000a210  cmp     ecx, 31h ; '1'
0x18000a213  ja      short loc_18000A224
0x18000a215  mov     r8d, esi
0x18000a218  mov     edx, ebx
0x18000a21a  mov     ecx, 0F9D30Dh
0x18000a21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a224  test    r14d, r14d
0x18000a227  jz      short loc_18000A238
0x18000a229  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x18000a22c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000a233  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000a238  xor     ebp, ebp
0x18000a23a  test    edi, edi
0x18000a23c  jz      short loc_18000A269
0x18000a23e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000a245  test    rax, rax
0x18000a248  jnz     short loc_18000A256
0x18000a24a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000a251  test    rax, rax
0x18000a254  jz      short loc_18000A269
0x18000a256  xor     r9d, r9d
0x18000a259  mov     r8d, edi
0x18000a25c  mov     edx, r15d
0x18000a25f  mov     ecx, 0F9D30Dh
0x18000a264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a269  test    r12d, r12d
0x18000a26c  jnz     short loc_18000A2D2
0x18000a26e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a274  test    eax, eax
0x18000a276  jz      short loc_18000A2D2
0x18000a278  lea     rcx, SRWLock; SRWLock
0x18000a27f  call    cs:__imp_AcquireSRWLockExclusive
0x18000a285  cmp     cs:qword_180015898, rbp
0x18000a28c  jnz     short loc_18000A2C4
0x18000a28e  mov     cs:qword_180015898, rbp
0x18000a295  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000a29c  test    rax, rax
0x18000a29f  jnz     short loc_18000A2AD
0x18000a2a1  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000a2a8  test    rax, rax
0x18000a2ab  jz      short loc_18000A2C4
0x18000a2ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a2b1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000a2b8  lea     rcx, qword_180015898
0x18000a2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2c4  lea     rcx, SRWLock; SRWLock
0x18000a2cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a2d1  nop
0x18000a2d2  test    r13d, r13d
0x18000a2d5  jz      short loc_18000A30F
0x18000a2d7  mov     edx, ebx
0x18000a2d9  bts     edx, 1Fh
0x18000a2dd  cmp     [rsp+98h+arg_18], ebp
0x18000a2e4  cmovz   edx, ebx
0x18000a2e7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000a2ee  test    rax, rax
0x18000a2f1  jnz     short loc_18000A2FF
0x18000a2f3  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000a2fa  test    rax, rax
0x18000a2fd  jz      short loc_18000A30F
0x18000a2ff  xor     r9d, r9d
0x18000a302  xor     r8d, r8d
0x18000a305  mov     ecx, 0F9D30Dh
0x18000a30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a30f  test    r12d, r12d
0x18000a312  jnz     short loc_18000A336
0x18000a314  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000a31b  test    rax, rax
0x18000a31e  jz      short loc_18000A338
0x18000a320  mov     r8b, [rsp+98h+arg_38]
0x18000a328  mov     edx, ebx
0x18000a32a  mov     ecx, 0F9D30Dh
0x18000a32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a334  jmp     short loc_18000A338
0x18000a336  mov     esi, ebp
0x18000a338  mov     eax, esi
0x18000a33a  add     rsp, 58h
0x18000a33e  pop     r15
0x18000a340  pop     r14
0x18000a342  pop     r13
0x18000a344  pop     r12
0x18000a346  pop     rdi
0x18000a347  pop     rsi
0x18000a348  pop     rbp
0x18000a349  pop     rbx
0x18000a34a  retn
```

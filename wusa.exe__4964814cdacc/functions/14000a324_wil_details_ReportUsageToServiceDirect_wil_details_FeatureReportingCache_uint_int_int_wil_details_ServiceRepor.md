# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x14000a324`
- end: `0x14000a4b6`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000a24c`

## callees

- `0x140008d70`
- `0x14000a324`
- `0x14000cbe0`
- `0x140015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a3eb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a3eb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a437`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a437`

## pseudocode

```c
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
  unsigned int v13; // esi
  int v14; // r14d
  unsigned int v15; // edi
  unsigned int v16; // r12d
  int v17; // r15d
  void (__fastcall *v18)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v20)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v21; // rdx
  _BYTE v23[104]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v23, a1, a5);
  v13 = 1;
  v14 = *v10;
  v15 = v10[1];
  v16 = v10[2];
  v17 = v10[4];
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(58674884, a5, 1);
  if ( v14 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v11,
      a1);
  if ( v15 )
  {
    v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v18 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v18(58674884, v16, v15, 0);
    }
  }
  if ( !v17 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_140020438 )
    {
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_140020438 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_140020438, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v20 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v21 = a5;
    LODWORD(v21) = a5 | 0x80000000;
    if ( !a4 )
      v21 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v20 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v20(58674884, v21, 0, 0);
    }
  }
  if ( v17 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v12) = a8;
    g_wil_details_realtimeFeatureUsageHook(58674884, a5, v12);
  }
  return v13;
}

```

## disassembly

```asm
0x14000a324  mov     [rsp+arg_18], r9d
0x14000a329  push    rbx
0x14000a32a  push    rbp
0x14000a32b  push    rsi
0x14000a32c  push    rdi
0x14000a32d  push    r12
0x14000a32f  push    r13
0x14000a331  push    r14
0x14000a333  push    r15
0x14000a335  sub     rsp, 58h
0x14000a339  mov     ebx, [rsp+98h+arg_20]
0x14000a340  mov     r13d, r8d
0x14000a343  mov     rbp, rcx
0x14000a346  mov     rdx, rcx
0x14000a349  mov     r8d, ebx
0x14000a34c  lea     rcx, [rsp+98h+var_68]
0x14000a351  call    wil_details_FeatureReporting_RecordUsageInCache
0x14000a356  mov     esi, 1
0x14000a35b  mov     r14d, [rax]
0x14000a35e  mov     edi, [rax+4]
0x14000a361  mov     r12d, [rax+8]
0x14000a365  mov     r15d, [rax+10h]
0x14000a369  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x14000a370  test    rax, rax
0x14000a373  jz      short loc_14000A390
0x14000a375  test    ebx, ebx
0x14000a377  jz      short loc_14000A381
0x14000a379  lea     ecx, [rbx-64h]
0x14000a37c  cmp     ecx, 31h ; '1'
0x14000a37f  ja      short loc_14000A390
0x14000a381  mov     r8d, esi
0x14000a384  mov     edx, ebx
0x14000a386  mov     ecx, 37F4EC4h
0x14000a38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a390  test    r14d, r14d
0x14000a393  jz      short loc_14000A3A4
0x14000a395  mov     r8, rbp; struct wil_details_FeatureReportingCache *
0x14000a398  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x14000a39f  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000a3a4  xor     ebp, ebp
0x14000a3a6  test    edi, edi
0x14000a3a8  jz      short loc_14000A3D5
0x14000a3aa  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000a3b1  test    rax, rax
0x14000a3b4  jnz     short loc_14000A3C2
0x14000a3b6  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000a3bd  test    rax, rax
0x14000a3c0  jz      short loc_14000A3D5
0x14000a3c2  xor     r9d, r9d
0x14000a3c5  mov     r8d, edi
0x14000a3c8  mov     edx, r12d
0x14000a3cb  mov     ecx, 37F4EC4h
0x14000a3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3d5  test    r15d, r15d
0x14000a3d8  jnz     short loc_14000A43D
0x14000a3da  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000a3e0  test    eax, eax
0x14000a3e2  jz      short loc_14000A43D
0x14000a3e4  lea     rcx, SRWLock; SRWLock
0x14000a3eb  call    cs:__imp_AcquireSRWLockExclusive
0x14000a3f1  cmp     cs:qword_140020438, rbp
0x14000a3f8  jnz     short loc_14000A430
0x14000a3fa  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000a401  mov     cs:qword_140020438, rbp
0x14000a408  test    rax, rax
0x14000a40b  jnz     short loc_14000A419
0x14000a40d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x14000a414  test    rax, rax
0x14000a417  jz      short loc_14000A430
0x14000a419  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000a41d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x14000a424  lea     rcx, qword_140020438
0x14000a42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a430  lea     rcx, SRWLock; SRWLock
0x14000a437  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a43d  test    r13d, r13d
0x14000a440  jz      short loc_14000A47A
0x14000a442  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000a449  mov     edx, ebx
0x14000a44b  bts     edx, 1Fh
0x14000a44f  cmp     [rsp+98h+arg_18], ebp
0x14000a456  cmovz   edx, ebx
0x14000a459  test    rax, rax
0x14000a45c  jnz     short loc_14000A46A
0x14000a45e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000a465  test    rax, rax
0x14000a468  jz      short loc_14000A47A
0x14000a46a  xor     r9d, r9d
0x14000a46d  xor     r8d, r8d
0x14000a470  mov     ecx, 37F4EC4h
0x14000a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a47a  test    r15d, r15d
0x14000a47d  jnz     short loc_14000A4A1
0x14000a47f  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000a486  test    rax, rax
0x14000a489  jz      short loc_14000A4A3
0x14000a48b  mov     r8b, [rsp+98h+arg_38]
0x14000a493  mov     edx, ebx
0x14000a495  mov     ecx, 37F4EC4h
0x14000a49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a49f  jmp     short loc_14000A4A3
0x14000a4a1  mov     esi, ebp
0x14000a4a3  mov     eax, esi
0x14000a4a5  add     rsp, 58h
0x14000a4a9  pop     r15
0x14000a4ab  pop     r14
0x14000a4ad  pop     r13
0x14000a4af  pop     r12
0x14000a4b1  pop     rdi
0x14000a4b2  pop     rsi
0x14000a4b3  pop     rbp
0x14000a4b4  pop     rbx
0x14000a4b5  retn
```

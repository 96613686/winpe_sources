# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000b418`
- end: `0x18000b5b7`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b2e0`

## callees

- `0x180009b54`
- `0x18000b418`
- `0x18000e3e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b52f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b52f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4e3`

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
    if ( !qword_180021780 )
    {
      qword_180021780 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180021780, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000b418  mov     rax, rsp
0x18000b41b  mov     [rax+8], rbx
0x18000b41f  mov     [rax+20h], r9d
0x18000b423  mov     [rax+18h], r8d
0x18000b427  push    rbp
0x18000b428  push    rsi
0x18000b429  push    rdi
0x18000b42a  push    r12
0x18000b42c  push    r13
0x18000b42e  push    r14
0x18000b430  push    r15
0x18000b432  sub     rsp, 50h
0x18000b436  mov     edi, edx
0x18000b438  mov     r14, rcx
0x18000b43b  mov     ebx, [rsp+88h+arg_20]
0x18000b442  mov     r8d, ebx
0x18000b445  mov     rdx, rcx
0x18000b448  lea     rcx, [rax-58h]
0x18000b44c  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000b451  mov     r15d, [rax]
0x18000b454  mov     esi, [rax+4]
0x18000b457  mov     r12d, [rax+8]
0x18000b45b  mov     r13d, [rax+10h]
0x18000b45f  mov     ebp, 1
0x18000b464  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000b46b  test    rax, rax
0x18000b46e  jz      short loc_18000B488
0x18000b470  test    ebx, ebx
0x18000b472  jz      short loc_18000B47C
0x18000b474  lea     ecx, [rbx-64h]
0x18000b477  cmp     ecx, 31h ; '1'
0x18000b47a  ja      short loc_18000B488
0x18000b47c  mov     r8d, ebp
0x18000b47f  mov     edx, ebx
0x18000b481  mov     ecx, edi
0x18000b483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b488  test    r15d, r15d
0x18000b48b  jz      short loc_18000B49E
0x18000b48d  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000b490  mov     edx, edi; unsigned int
0x18000b492  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000b499  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000b49e  xor     r14d, r14d
0x18000b4a1  test    esi, esi
0x18000b4a3  jz      short loc_18000B4CD
0x18000b4a5  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000b4ac  test    rax, rax
0x18000b4af  jnz     short loc_18000B4BD
0x18000b4b1  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000b4b8  test    rax, rax
0x18000b4bb  jz      short loc_18000B4CD
0x18000b4bd  xor     r9d, r9d
0x18000b4c0  mov     r8d, esi
0x18000b4c3  mov     edx, r12d
0x18000b4c6  mov     ecx, edi
0x18000b4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4cd  test    r13d, r13d
0x18000b4d0  jnz     short loc_18000B536
0x18000b4d2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b4d8  test    eax, eax
0x18000b4da  jz      short loc_18000B536
0x18000b4dc  lea     rcx, SRWLock; SRWLock
0x18000b4e3  call    cs:__imp_AcquireSRWLockExclusive
0x18000b4e9  cmp     cs:qword_180021780, r14
0x18000b4f0  jnz     short loc_18000B528
0x18000b4f2  mov     cs:qword_180021780, r14
0x18000b4f9  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000b500  test    rax, rax
0x18000b503  jnz     short loc_18000B511
0x18000b505  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000b50c  test    rax, rax
0x18000b50f  jz      short loc_18000B528
0x18000b511  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b515  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000b51c  lea     rcx, qword_180021780
0x18000b523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b528  lea     rcx, SRWLock; SRWLock
0x18000b52f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b535  nop
0x18000b536  cmp     [rsp+88h+arg_10], r14d
0x18000b53e  jz      short loc_18000B576
0x18000b540  mov     edx, ebx
0x18000b542  bts     edx, 1Fh
0x18000b546  cmp     [rsp+88h+arg_18], r14d
0x18000b54e  cmovz   edx, ebx
0x18000b551  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000b558  test    rax, rax
0x18000b55b  jnz     short loc_18000B569
0x18000b55d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000b564  test    rax, rax
0x18000b567  jz      short loc_18000B576
0x18000b569  xor     r9d, r9d
0x18000b56c  xor     r8d, r8d
0x18000b56f  mov     ecx, edi
0x18000b571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b576  test    r13d, r13d
0x18000b579  jnz     short loc_18000B59A
0x18000b57b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000b582  test    rax, rax
0x18000b585  jz      short loc_18000B59D
0x18000b587  mov     r8b, [rsp+88h+arg_38]
0x18000b58f  mov     edx, ebx
0x18000b591  mov     ecx, edi
0x18000b593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b598  jmp     short loc_18000B59D
0x18000b59a  mov     ebp, r14d
0x18000b59d  mov     eax, ebp
0x18000b59f  mov     rbx, [rsp+88h+arg_0]
0x18000b5a7  add     rsp, 50h
0x18000b5ab  pop     r15
0x18000b5ad  pop     r14
0x18000b5af  pop     r13
0x18000b5b1  pop     r12
0x18000b5b3  pop     rdi
0x18000b5b4  pop     rsi
0x18000b5b5  pop     rbp
0x18000b5b6  retn
```

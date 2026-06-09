# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180015740`
- end: `0x1800158df`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180015608`

## callees

- `0x180014dd4`
- `0x180015740`
- `0x180017d8c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001580b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001580b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015857`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015857`

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
    if ( !qword_180034710 )
    {
      qword_180034710 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180034710, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x180015740  mov     rax, rsp
0x180015743  mov     [rax+8], rbx
0x180015747  mov     [rax+20h], r9d
0x18001574b  mov     [rax+18h], r8d
0x18001574f  push    rbp
0x180015750  push    rsi
0x180015751  push    rdi
0x180015752  push    r12
0x180015754  push    r13
0x180015756  push    r14
0x180015758  push    r15
0x18001575a  sub     rsp, 50h
0x18001575e  mov     edi, edx
0x180015760  mov     r14, rcx
0x180015763  mov     ebx, [rsp+88h+arg_20]
0x18001576a  mov     r8d, ebx
0x18001576d  mov     rdx, rcx
0x180015770  lea     rcx, [rax-58h]
0x180015774  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015779  mov     r15d, [rax]
0x18001577c  mov     esi, [rax+4]
0x18001577f  mov     r12d, [rax+8]
0x180015783  mov     r13d, [rax+10h]
0x180015787  mov     ebp, 1
0x18001578c  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180015793  test    rax, rax
0x180015796  jz      short loc_1800157B0
0x180015798  test    ebx, ebx
0x18001579a  jz      short loc_1800157A4
0x18001579c  lea     ecx, [rbx-64h]
0x18001579f  cmp     ecx, 31h ; '1'
0x1800157a2  ja      short loc_1800157B0
0x1800157a4  mov     r8d, ebp
0x1800157a7  mov     edx, ebx
0x1800157a9  mov     ecx, edi
0x1800157ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157b0  test    r15d, r15d
0x1800157b3  jz      short loc_1800157C6
0x1800157b5  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x1800157b8  mov     edx, edi; unsigned int
0x1800157ba  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800157c1  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x1800157c6  xor     r14d, r14d
0x1800157c9  test    esi, esi
0x1800157cb  jz      short loc_1800157F5
0x1800157cd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800157d4  test    rax, rax
0x1800157d7  jnz     short loc_1800157E5
0x1800157d9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800157e0  test    rax, rax
0x1800157e3  jz      short loc_1800157F5
0x1800157e5  xor     r9d, r9d
0x1800157e8  mov     r8d, esi
0x1800157eb  mov     edx, r12d
0x1800157ee  mov     ecx, edi
0x1800157f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f5  test    r13d, r13d
0x1800157f8  jnz     short loc_18001585E
0x1800157fa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015800  test    eax, eax
0x180015802  jz      short loc_18001585E
0x180015804  lea     rcx, SRWLock; SRWLock
0x18001580b  call    cs:__imp_AcquireSRWLockExclusive
0x180015811  cmp     cs:qword_180034710, r14
0x180015818  jnz     short loc_180015850
0x18001581a  mov     cs:qword_180034710, r14
0x180015821  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180015828  test    rax, rax
0x18001582b  jnz     short loc_180015839
0x18001582d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180015834  test    rax, rax
0x180015837  jz      short loc_180015850
0x180015839  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001583d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180015844  lea     rcx, qword_180034710
0x18001584b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015850  lea     rcx, SRWLock; SRWLock
0x180015857  call    cs:__imp_ReleaseSRWLockExclusive
0x18001585d  nop
0x18001585e  cmp     [rsp+88h+arg_10], r14d
0x180015866  jz      short loc_18001589E
0x180015868  mov     edx, ebx
0x18001586a  bts     edx, 1Fh
0x18001586e  cmp     [rsp+88h+arg_18], r14d
0x180015876  cmovz   edx, ebx
0x180015879  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015880  test    rax, rax
0x180015883  jnz     short loc_180015891
0x180015885  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001588c  test    rax, rax
0x18001588f  jz      short loc_18001589E
0x180015891  xor     r9d, r9d
0x180015894  xor     r8d, r8d
0x180015897  mov     ecx, edi
0x180015899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001589e  test    r13d, r13d
0x1800158a1  jnz     short loc_1800158C2
0x1800158a3  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x1800158aa  test    rax, rax
0x1800158ad  jz      short loc_1800158C5
0x1800158af  mov     r8b, [rsp+88h+arg_38]
0x1800158b7  mov     edx, ebx
0x1800158b9  mov     ecx, edi
0x1800158bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158c0  jmp     short loc_1800158C5
0x1800158c2  mov     ebp, r14d
0x1800158c5  mov     eax, ebp
0x1800158c7  mov     rbx, [rsp+88h+arg_0]
0x1800158cf  add     rsp, 50h
0x1800158d3  pop     r15
0x1800158d5  pop     r14
0x1800158d7  pop     r13
0x1800158d9  pop     r12
0x1800158db  pop     rdi
0x1800158dc  pop     rsi
0x1800158dd  pop     rbp
0x1800158de  retn
```

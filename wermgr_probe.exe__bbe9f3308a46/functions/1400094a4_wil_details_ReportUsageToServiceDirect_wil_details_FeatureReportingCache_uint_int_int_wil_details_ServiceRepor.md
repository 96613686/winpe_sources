# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1400094a4`
- end: `0x140009643`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000936c`

## callees

- `0x140008fe8`
- `0x1400094a4`
- `0x14000f484`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400095bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400095bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000956f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000956f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    if ( !qword_14002C490 )
    {
      qword_14002C490 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_14002C490, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x1400094a4  mov     rax, rsp
0x1400094a7  mov     [rax+8], rbx
0x1400094ab  mov     [rax+20h], r9d
0x1400094af  mov     [rax+18h], r8d
0x1400094b3  push    rbp
0x1400094b4  push    rsi
0x1400094b5  push    rdi
0x1400094b6  push    r12
0x1400094b8  push    r13
0x1400094ba  push    r14
0x1400094bc  push    r15
0x1400094be  sub     rsp, 50h
0x1400094c2  mov     edi, edx
0x1400094c4  mov     r14, rcx
0x1400094c7  mov     ebx, [rsp+88h+arg_20]
0x1400094ce  mov     r8d, ebx
0x1400094d1  mov     rdx, rcx
0x1400094d4  lea     rcx, [rax-58h]
0x1400094d8  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400094dd  mov     r15d, [rax]
0x1400094e0  mov     esi, [rax+4]
0x1400094e3  mov     r12d, [rax+8]
0x1400094e7  mov     r13d, [rax+10h]
0x1400094eb  mov     ebp, 1
0x1400094f0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x1400094f7  test    rax, rax
0x1400094fa  jz      short loc_140009514
0x1400094fc  test    ebx, ebx
0x1400094fe  jz      short loc_140009508
0x140009500  lea     ecx, [rbx-64h]
0x140009503  cmp     ecx, 31h ; '1'
0x140009506  ja      short loc_140009514
0x140009508  mov     r8d, ebp
0x14000950b  mov     edx, ebx
0x14000950d  mov     ecx, edi
0x14000950f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009514  test    r15d, r15d
0x140009517  jz      short loc_14000952A
0x140009519  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x14000951c  mov     edx, edi; unsigned int
0x14000951e  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x140009525  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x14000952a  xor     r14d, r14d
0x14000952d  test    esi, esi
0x14000952f  jz      short loc_140009559
0x140009531  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140009538  test    rax, rax
0x14000953b  jnz     short loc_140009549
0x14000953d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140009544  test    rax, rax
0x140009547  jz      short loc_140009559
0x140009549  xor     r9d, r9d
0x14000954c  mov     r8d, esi
0x14000954f  mov     edx, r12d
0x140009552  mov     ecx, edi
0x140009554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009559  test    r13d, r13d
0x14000955c  jnz     short loc_1400095C2
0x14000955e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009564  test    eax, eax
0x140009566  jz      short loc_1400095C2
0x140009568  lea     rcx, SRWLock; SRWLock
0x14000956f  call    cs:__imp_AcquireSRWLockExclusive
0x140009575  cmp     cs:qword_14002C490, r14
0x14000957c  jnz     short loc_1400095B4
0x14000957e  mov     cs:qword_14002C490, r14
0x140009585  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x14000958c  test    rax, rax
0x14000958f  jnz     short loc_14000959D
0x140009591  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x140009598  test    rax, rax
0x14000959b  jz      short loc_1400095B4
0x14000959d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400095a1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x1400095a8  lea     rcx, qword_14002C490
0x1400095af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095b4  lea     rcx, SRWLock; SRWLock
0x1400095bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1400095c1  nop
0x1400095c2  cmp     [rsp+88h+arg_10], r14d
0x1400095ca  jz      short loc_140009602
0x1400095cc  mov     edx, ebx
0x1400095ce  bts     edx, 1Fh
0x1400095d2  cmp     [rsp+88h+arg_18], r14d
0x1400095da  cmovz   edx, ebx
0x1400095dd  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400095e4  test    rax, rax
0x1400095e7  jnz     short loc_1400095F5
0x1400095e9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400095f0  test    rax, rax
0x1400095f3  jz      short loc_140009602
0x1400095f5  xor     r9d, r9d
0x1400095f8  xor     r8d, r8d
0x1400095fb  mov     ecx, edi
0x1400095fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009602  test    r13d, r13d
0x140009605  jnz     short loc_140009626
0x140009607  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x14000960e  test    rax, rax
0x140009611  jz      short loc_140009629
0x140009613  mov     r8b, [rsp+88h+arg_38]
0x14000961b  mov     edx, ebx
0x14000961d  mov     ecx, edi
0x14000961f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009624  jmp     short loc_140009629
0x140009626  mov     ebp, r14d
0x140009629  mov     eax, ebp
0x14000962b  mov     rbx, [rsp+88h+arg_0]
0x140009633  add     rsp, 50h
0x140009637  pop     r15
0x140009639  pop     r14
0x14000963b  pop     r13
0x14000963d  pop     r12
0x14000963f  pop     rdi
0x140009640  pop     rsi
0x140009641  pop     rbp
0x140009642  retn
```

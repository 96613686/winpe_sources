# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000a498`
- end: `0x18000a63f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a358`
- `0x180014f00`

## callees

- `0x18000800c`
- `0x18000a498`
- `0x18000d440`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a56b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a56b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a5b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a5b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
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

  v10 = (int *)wil_details_FeatureReporting_RecordUsageInCache(&v22, a1, a5, a6);
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
    if ( !qword_1800234F0 )
    {
      qword_1800234F0 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_1800234F0, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18000a498  mov     rax, rsp
0x18000a49b  mov     [rax+8], rbx
0x18000a49f  mov     [rax+20h], r9d
0x18000a4a3  mov     [rax+18h], r8d
0x18000a4a7  push    rbp
0x18000a4a8  push    rsi
0x18000a4a9  push    rdi
0x18000a4aa  push    r12
0x18000a4ac  push    r13
0x18000a4ae  push    r14
0x18000a4b0  push    r15
0x18000a4b2  sub     rsp, 50h
0x18000a4b6  mov     ebx, edx
0x18000a4b8  mov     r14, rcx
0x18000a4bb  mov     r9d, [rsp+88h+arg_28]
0x18000a4c3  mov     edi, [rsp+88h+arg_20]
0x18000a4ca  mov     r8d, edi
0x18000a4cd  mov     rdx, rcx
0x18000a4d0  lea     rcx, [rax-58h]
0x18000a4d4  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000a4d9  mov     r15d, [rax]
0x18000a4dc  mov     esi, [rax+4]
0x18000a4df  mov     r12d, [rax+8]
0x18000a4e3  mov     r13d, [rax+10h]
0x18000a4e7  mov     ebp, 1
0x18000a4ec  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000a4f3  test    rax, rax
0x18000a4f6  jz      short loc_18000A510
0x18000a4f8  test    edi, edi
0x18000a4fa  jz      short loc_18000A504
0x18000a4fc  lea     ecx, [rdi-64h]
0x18000a4ff  cmp     ecx, 31h ; '1'
0x18000a502  ja      short loc_18000A510
0x18000a504  mov     r8d, ebp
0x18000a507  mov     edx, edi
0x18000a509  mov     ecx, ebx
0x18000a50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a510  test    r15d, r15d
0x18000a513  jz      short loc_18000A526
0x18000a515  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18000a518  mov     edx, ebx; unsigned int
0x18000a51a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000a521  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000a526  xor     r14d, r14d
0x18000a529  test    esi, esi
0x18000a52b  jz      short loc_18000A555
0x18000a52d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000a534  test    rax, rax
0x18000a537  jnz     short loc_18000A545
0x18000a539  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000a540  test    rax, rax
0x18000a543  jz      short loc_18000A555
0x18000a545  xor     r9d, r9d
0x18000a548  mov     r8d, esi
0x18000a54b  mov     edx, r12d
0x18000a54e  mov     ecx, ebx
0x18000a550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a555  test    r13d, r13d
0x18000a558  jnz     short loc_18000A5BE
0x18000a55a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a560  test    eax, eax
0x18000a562  jz      short loc_18000A5BE
0x18000a564  lea     rcx, SRWLock; SRWLock
0x18000a56b  call    cs:__imp_AcquireSRWLockExclusive
0x18000a571  cmp     cs:qword_1800234F0, r14
0x18000a578  jnz     short loc_18000A5B0
0x18000a57a  mov     cs:qword_1800234F0, r14
0x18000a581  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000a588  test    rax, rax
0x18000a58b  jnz     short loc_18000A599
0x18000a58d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000a594  test    rax, rax
0x18000a597  jz      short loc_18000A5B0
0x18000a599  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a59d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000a5a4  lea     rcx, qword_1800234F0
0x18000a5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b0  lea     rcx, SRWLock; SRWLock
0x18000a5b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a5bd  nop
0x18000a5be  cmp     [rsp+88h+arg_10], r14d
0x18000a5c6  jz      short loc_18000A5FE
0x18000a5c8  mov     edx, edi
0x18000a5ca  bts     edx, 1Fh
0x18000a5ce  cmp     [rsp+88h+arg_18], r14d
0x18000a5d6  cmovz   edx, edi
0x18000a5d9  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000a5e0  test    rax, rax
0x18000a5e3  jnz     short loc_18000A5F1
0x18000a5e5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000a5ec  test    rax, rax
0x18000a5ef  jz      short loc_18000A5FE
0x18000a5f1  xor     r9d, r9d
0x18000a5f4  xor     r8d, r8d
0x18000a5f7  mov     ecx, ebx
0x18000a5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fe  test    r13d, r13d
0x18000a601  jnz     short loc_18000A622
0x18000a603  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000a60a  test    rax, rax
0x18000a60d  jz      short loc_18000A625
0x18000a60f  mov     r8b, [rsp+88h+arg_38]
0x18000a617  mov     edx, edi
0x18000a619  mov     ecx, ebx
0x18000a61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a620  jmp     short loc_18000A625
0x18000a622  mov     ebp, r14d
0x18000a625  mov     eax, ebp
0x18000a627  mov     rbx, [rsp+88h+arg_0]
0x18000a62f  add     rsp, 50h
0x18000a633  pop     r15
0x18000a635  pop     r14
0x18000a637  pop     r13
0x18000a639  pop     r12
0x18000a63b  pop     rdi
0x18000a63c  pop     rsi
0x18000a63d  pop     rbp
0x18000a63e  retn
```

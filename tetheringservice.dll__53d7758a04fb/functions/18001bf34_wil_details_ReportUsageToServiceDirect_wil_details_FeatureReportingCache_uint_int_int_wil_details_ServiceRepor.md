# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18001bf34`
- end: `0x18001c0d3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001bdfc`

## callees

- `0x18001b554`
- `0x18001bf34`
- `0x180021c90`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c04b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c04b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bfff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bfff`

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
    if ( !qword_180041A00 )
    {
      qword_180041A00 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180041A00, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x18001bf34  mov     rax, rsp
0x18001bf37  mov     [rax+8], rbx
0x18001bf3b  mov     [rax+20h], r9d
0x18001bf3f  mov     [rax+18h], r8d
0x18001bf43  push    rbp
0x18001bf44  push    rsi
0x18001bf45  push    rdi
0x18001bf46  push    r12
0x18001bf48  push    r13
0x18001bf4a  push    r14
0x18001bf4c  push    r15
0x18001bf4e  sub     rsp, 50h
0x18001bf52  mov     edi, edx
0x18001bf54  mov     r14, rcx
0x18001bf57  mov     ebx, [rsp+88h+arg_20]
0x18001bf5e  mov     r8d, ebx
0x18001bf61  mov     rdx, rcx
0x18001bf64  lea     rcx, [rax-58h]
0x18001bf68  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001bf6d  mov     r15d, [rax]
0x18001bf70  mov     esi, [rax+4]
0x18001bf73  mov     r12d, [rax+8]
0x18001bf77  mov     r13d, [rax+10h]
0x18001bf7b  mov     ebp, 1
0x18001bf80  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18001bf87  test    rax, rax
0x18001bf8a  jz      short loc_18001BFA4
0x18001bf8c  test    ebx, ebx
0x18001bf8e  jz      short loc_18001BF98
0x18001bf90  lea     ecx, [rbx-64h]
0x18001bf93  cmp     ecx, 31h ; '1'
0x18001bf96  ja      short loc_18001BFA4
0x18001bf98  mov     r8d, ebp
0x18001bf9b  mov     edx, ebx
0x18001bf9d  mov     ecx, edi
0x18001bf9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfa4  test    r15d, r15d
0x18001bfa7  jz      short loc_18001BFBA
0x18001bfa9  mov     r8, r14; struct wil_details_FeatureReportingCache *
0x18001bfac  mov     edx, edi; unsigned int
0x18001bfae  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18001bfb5  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18001bfba  xor     r14d, r14d
0x18001bfbd  test    esi, esi
0x18001bfbf  jz      short loc_18001BFE9
0x18001bfc1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001bfc8  test    rax, rax
0x18001bfcb  jnz     short loc_18001BFD9
0x18001bfcd  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001bfd4  test    rax, rax
0x18001bfd7  jz      short loc_18001BFE9
0x18001bfd9  xor     r9d, r9d
0x18001bfdc  mov     r8d, esi
0x18001bfdf  mov     edx, r12d
0x18001bfe2  mov     ecx, edi
0x18001bfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfe9  test    r13d, r13d
0x18001bfec  jnz     short loc_18001C052
0x18001bfee  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001bff4  test    eax, eax
0x18001bff6  jz      short loc_18001C052
0x18001bff8  lea     rcx, SRWLock; SRWLock
0x18001bfff  call    cs:__imp_AcquireSRWLockExclusive
0x18001c005  cmp     cs:qword_180041A00, r14
0x18001c00c  jnz     short loc_18001C044
0x18001c00e  mov     cs:qword_180041A00, r14
0x18001c015  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001c01c  test    rax, rax
0x18001c01f  jnz     short loc_18001C02D
0x18001c021  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001c028  test    rax, rax
0x18001c02b  jz      short loc_18001C044
0x18001c02d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c031  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18001c038  lea     rcx, qword_180041A00
0x18001c03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c044  lea     rcx, SRWLock; SRWLock
0x18001c04b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c051  nop
0x18001c052  cmp     [rsp+88h+arg_10], r14d
0x18001c05a  jz      short loc_18001C092
0x18001c05c  mov     edx, ebx
0x18001c05e  bts     edx, 1Fh
0x18001c062  cmp     [rsp+88h+arg_18], r14d
0x18001c06a  cmovz   edx, ebx
0x18001c06d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18001c074  test    rax, rax
0x18001c077  jnz     short loc_18001C085
0x18001c079  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18001c080  test    rax, rax
0x18001c083  jz      short loc_18001C092
0x18001c085  xor     r9d, r9d
0x18001c088  xor     r8d, r8d
0x18001c08b  mov     ecx, edi
0x18001c08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c092  test    r13d, r13d
0x18001c095  jnz     short loc_18001C0B6
0x18001c097  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18001c09e  test    rax, rax
0x18001c0a1  jz      short loc_18001C0B9
0x18001c0a3  mov     r8b, [rsp+88h+arg_38]
0x18001c0ab  mov     edx, ebx
0x18001c0ad  mov     ecx, edi
0x18001c0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0b4  jmp     short loc_18001C0B9
0x18001c0b6  mov     ebp, r14d
0x18001c0b9  mov     eax, ebp
0x18001c0bb  mov     rbx, [rsp+88h+arg_0]
0x18001c0c3  add     rsp, 50h
0x18001c0c7  pop     r15
0x18001c0c9  pop     r14
0x18001c0cb  pop     r13
0x18001c0cd  pop     r12
0x18001c0cf  pop     rdi
0x18001c0d0  pop     rsi
0x18001c0d1  pop     rbp
0x18001c0d2  retn
```

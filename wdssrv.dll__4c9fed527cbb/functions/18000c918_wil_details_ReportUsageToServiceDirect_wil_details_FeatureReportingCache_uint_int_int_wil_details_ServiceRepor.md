# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000c918`
- end: `0x18000cae3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c83c`

## callees

- `0x18000afb4`
- `0x18000c918`
- `0x18000f554`
- `0x18001d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ca0a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ca0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ca5e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ca5e`

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
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // esi
  __m128i v14; // xmm1
  __int64 v15; // xmm0_8
  __int64 v16; // r8
  void (__fastcall *v17)(__int64, _QWORD, __int64, _QWORD); // rax
  void (__fastcall *v18)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  void (__fastcall *v19)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v20; // rdx
  __m128i v22; // [rsp+30h] [rbp-58h]
  __int64 v23; // [rsp+58h] [rbp-30h] BYREF

  v11 = wil_details_FeatureReporting_RecordUsageInCache(&v23, a1, a5);
  v13 = 1;
  v14 = *(__m128i *)v11;
  v15 = *(_QWORD *)(v11 + 16);
  v22 = *(__m128i *)v11;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(52965666, a5, 1);
  if ( _mm_cvtsi128_si32(v14) )
  {
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
      v12,
      a1);
    v14 = v22;
  }
  v16 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v14, 4));
  if ( (_DWORD)v16 )
  {
    v17 = (void (__fastcall *)(__int64, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(__int64, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(52965666, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v14, 8)), v16, 0);
    }
  }
  if ( !(_DWORD)v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180028350 )
    {
      qword_180028350 = 0;
      v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v18 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v18(&qword_180028350, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( a3 )
  {
    v19 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    v20 = a5;
    LODWORD(v20) = a5 | 0x80000000;
    if ( !a4 )
      v20 = a5;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v19 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v19(52965666, v20, 0, 0);
    }
  }
  if ( (_DWORD)v15 )
  {
    return 0;
  }
  else if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v16) = a8;
    g_wil_details_realtimeFeatureUsageHook(52965666, a5, v16);
  }
  return v13;
}

```

## disassembly

```asm
0x18000c918  mov     rax, rsp
0x18000c91b  mov     [rax+8], rbx
0x18000c91f  mov     [rax+10h], rbp
0x18000c923  mov     [rax+18h], rsi
0x18000c927  push    rdi
0x18000c928  push    r12
0x18000c92a  push    r14
0x18000c92c  sub     rsp, 70h
0x18000c930  mov     ebx, [rsp+88h+arg_20]
0x18000c937  mov     ebp, r8d
0x18000c93a  mov     rdi, rcx
0x18000c93d  mov     rdx, rcx
0x18000c940  mov     r8d, ebx
0x18000c943  lea     rcx, [rax-30h]
0x18000c947  mov     r14d, r9d
0x18000c94a  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000c94f  mov     esi, 1
0x18000c954  mov     r12d, 3283122h
0x18000c95a  movups  xmm1, xmmword ptr [rax]
0x18000c95d  movsd   xmm0, qword ptr [rax+10h]
0x18000c962  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000c969  movsd   [rsp+88h+var_38], xmm0
0x18000c96f  movups  [rsp+88h+var_58], xmm1
0x18000c974  test    rax, rax
0x18000c977  jz      short loc_18000C997
0x18000c979  test    ebx, ebx
0x18000c97b  jz      short loc_18000C985
0x18000c97d  lea     ecx, [rbx-64h]
0x18000c980  cmp     ecx, 31h ; '1'
0x18000c983  ja      short loc_18000C997
0x18000c985  mov     r8d, esi
0x18000c988  mov     edx, ebx
0x18000c98a  mov     ecx, r12d
0x18000c98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c992  movups  xmm1, [rsp+88h+var_58]
0x18000c997  movd    eax, xmm1
0x18000c99b  test    eax, eax
0x18000c99d  jz      short loc_18000C9B3
0x18000c99f  mov     r8, rdi; struct wil_details_FeatureReportingCache *
0x18000c9a2  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000c9a9  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000c9ae  movups  xmm1, [rsp+88h+var_58]
0x18000c9b3  movdqa  xmm0, xmm1
0x18000c9b7  psrldq  xmm0, 4
0x18000c9bc  movd    r8d, xmm0
0x18000c9c1  test    r8d, r8d
0x18000c9c4  jz      short loc_18000C9F2
0x18000c9c6  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000c9cd  test    rax, rax
0x18000c9d0  jnz     short loc_18000C9DE
0x18000c9d2  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000c9d9  test    rax, rax
0x18000c9dc  jz      short loc_18000C9F2
0x18000c9de  psrldq  xmm1, 8
0x18000c9e3  xor     r9d, r9d
0x18000c9e6  movd    edx, xmm1
0x18000c9ea  mov     ecx, r12d
0x18000c9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f2  mov     edi, dword ptr [rsp+88h+var_38]
0x18000c9f6  test    edi, edi
0x18000c9f8  jnz     short loc_18000CA6A
0x18000c9fa  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, dil; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ca01  jz      short loc_18000CA6A
0x18000ca03  lea     rcx, SRWLock; SRWLock
0x18000ca0a  call    cs:__imp_AcquireSRWLockExclusive
0x18000ca11  nop     dword ptr [rax+rax+00h]
0x18000ca16  cmp     cs:qword_180028350, 0
0x18000ca1e  jnz     short loc_18000CA57
0x18000ca20  and     cs:qword_180028350, 0
0x18000ca28  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ca2f  test    rax, rax
0x18000ca32  jnz     short loc_18000CA40
0x18000ca34  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ca3b  test    rax, rax
0x18000ca3e  jz      short loc_18000CA57
0x18000ca40  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ca44  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000ca4b  lea     rcx, qword_180028350
0x18000ca52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca57  lea     rcx, SRWLock; SRWLock
0x18000ca5e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ca65  nop     dword ptr [rax+rax+00h]
0x18000ca6a  test    ebp, ebp
0x18000ca6c  jz      short loc_18000CAA0
0x18000ca6e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ca75  mov     edx, ebx
0x18000ca77  bts     edx, 1Fh
0x18000ca7b  test    r14d, r14d
0x18000ca7e  cmovz   edx, ebx
0x18000ca81  test    rax, rax
0x18000ca84  jnz     short loc_18000CA92
0x18000ca86  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ca8d  test    rax, rax
0x18000ca90  jz      short loc_18000CAA0
0x18000ca92  xor     r9d, r9d
0x18000ca95  xor     r8d, r8d
0x18000ca98  mov     ecx, r12d
0x18000ca9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caa0  test    edi, edi
0x18000caa2  jnz     short loc_18000CAC4
0x18000caa4  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000caab  test    rax, rax
0x18000caae  jz      short loc_18000CAC6
0x18000cab0  mov     r8b, [rsp+88h+arg_38]
0x18000cab8  mov     edx, ebx
0x18000caba  mov     ecx, r12d
0x18000cabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cac2  jmp     short loc_18000CAC6
0x18000cac4  xor     esi, esi
0x18000cac6  lea     r11, [rsp+88h+var_18]
0x18000cacb  mov     eax, esi
0x18000cacd  mov     rbx, [r11+20h]
0x18000cad1  mov     rbp, [r11+28h]
0x18000cad5  mov     rsi, [r11+30h]
0x18000cad9  mov     rsp, r11
0x18000cadc  pop     r14
0x18000cade  pop     r12
0x18000cae0  pop     rdi
0x18000cae1  retn
```

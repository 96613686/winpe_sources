# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180003248`
- end: `0x180003453`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `523`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000345c`

## callees

- `0x180002ba4`
- `0x180002ecc`
- `0x180003248`
- `0x180003744`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800032f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000338b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800032f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000338b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000332b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800033d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000332b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800033d7`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v12; // rax
  __m128i v13; // xmm1
  unsigned int v14; // ebx
  unsigned __int64 v15; // r8
  __int64 v16; // r8
  void (__fastcall *v17)(_QWORD, _QWORD, __int64, _QWORD); // rax
  int v18; // edi
  void (__fastcall *v19)(__int64 *, void (*)(), __int64); // rax
  __int64 v20; // rdx
  void (__fastcall *v21)(_QWORD, __int64, _QWORD, _QWORD); // rax
  bool v22; // zf
  _DWORD v24[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v25; // [rsp+38h] [rbp-70h]
  __m128i v26; // [rsp+40h] [rbp-68h]
  __int64 v27; // [rsp+60h] [rbp-48h]
  _BYTE v28[64]; // [rsp+68h] [rbp-40h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v28, a1, a5);
  v13 = *(__m128i *)v12;
  v26 = *(__m128i *)v12;
  v27 = *(_QWORD *)(v12 + 16);
  v14 = 0;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
  {
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
    v13 = v26;
  }
  if ( _mm_cvtsi128_si32(v13) && wil::details::g_enabledStateManager && !wil::details::g_processShutdownInProgress )
  {
    if ( !wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v24[0] = a2;
      v24[1] = 0;
      v25 = a1;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001F200, v24, v15);
      wil::details::EnabledStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)&wil::details::g_enabledStateManager);
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v13 = v26;
  }
  v16 = (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 4));
  if ( (_DWORD)v16 )
  {
    v17 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v17 = (void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v17(a2, (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v13, 8)), v16, 0);
    }
  }
  v18 = v27;
  if ( !(_DWORD)v27 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_18001F1F8 )
    {
      qword_18001F1F8 = 0;
      v19 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, void (*)(), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_18001F1F8, `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_, -1);
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
    v21 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v21 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v21(a2, v20, 0, 0);
    }
  }
  v22 = v18 == 0;
  if ( !v18 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v16) = a8;
      g_wil_details_realtimeFeatureUsageHook(a2, a5, v16);
    }
    v22 = 1;
  }
  LOBYTE(v14) = v22;
  return v14;
}

```

## disassembly

```asm
0x180003248  mov     [rsp+arg_10], rbx
0x18000324d  push    rbp
0x18000324e  push    rsi
0x18000324f  push    rdi
0x180003250  push    r14
0x180003252  push    r15
0x180003254  sub     rsp, 80h
0x18000325b  mov     r15d, r9d
0x18000325e  mov     r14d, r8d
0x180003261  mov     ebp, edx
0x180003263  mov     rdi, rcx
0x180003266  mov     esi, [rsp+0A8h+arg_20]
0x18000326d  mov     r8d, esi
0x180003270  mov     rdx, rcx
0x180003273  lea     rcx, [rsp+0A8h+var_40]
0x180003278  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000327d  movups  xmm1, xmmword ptr [rax]
0x180003280  movups  [rsp+0A8h+var_68], xmm1
0x180003285  movsd   xmm0, qword ptr [rax+10h]
0x18000328a  movsd   [rsp+0A8h+var_48], xmm0
0x180003290  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180003297  xor     ebx, ebx
0x180003299  test    rax, rax
0x18000329c  jz      short loc_1800032BE
0x18000329e  test    esi, esi
0x1800032a0  jz      short loc_1800032AA
0x1800032a2  lea     ecx, [rsi-64h]
0x1800032a5  cmp     ecx, 31h ; '1'
0x1800032a8  ja      short loc_1800032BE
0x1800032aa  mov     r8d, 1
0x1800032b0  mov     edx, esi
0x1800032b2  mov     ecx, ebp
0x1800032b4  call    _guard_dispatch_icall
0x1800032b9  movups  xmm1, [rsp+0A8h+var_68]
0x1800032be  movd    eax, xmm1
0x1800032c2  test    eax, eax
0x1800032c4  jz      short loc_180003336
0x1800032c6  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800032cc  jz      short loc_180003336
0x1800032ce  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x1800032d4  jnz     short loc_180003336
0x1800032d6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800032dd  test    rax, rax
0x1800032e0  jz      short loc_1800032EB
0x1800032e2  call    _guard_dispatch_icall
0x1800032e7  test    al, al
0x1800032e9  jnz     short loc_180003331
0x1800032eb  lea     rcx, SRWLock; SRWLock
0x1800032f2  call    cs:__imp_AcquireSRWLockExclusive
0x1800032f8  mov     [rsp+0A8h+var_78], ebp
0x1800032fc  xor     eax, eax
0x1800032fe  mov     [rsp+0A8h+var_74], eax
0x180003302  mov     [rsp+0A8h+var_70], rdi
0x180003307  lea     rdx, [rsp+0A8h+var_78]; void *
0x18000330c  lea     rcx, qword_18001F200; this
0x180003313  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180003318  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000331f  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::EnsureTimerUnderLock(void)
0x180003324  lea     rcx, SRWLock; SRWLock
0x18000332b  call    cs:__imp_ReleaseSRWLockExclusive
0x180003331  movups  xmm1, [rsp+0A8h+var_68]
0x180003336  movdqa  xmm0, xmm1
0x18000333a  psrldq  xmm0, 4
0x18000333f  movd    r8d, xmm0
0x180003344  test    r8d, r8d
0x180003347  jz      short loc_180003374
0x180003349  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180003350  test    rax, rax
0x180003353  jnz     short loc_180003361
0x180003355  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000335c  test    rax, rax
0x18000335f  jz      short loc_180003374
0x180003361  psrldq  xmm1, 8
0x180003366  xor     r9d, r9d
0x180003369  movd    edx, xmm1
0x18000336d  mov     ecx, ebp
0x18000336f  call    _guard_dispatch_icall
0x180003374  mov     edi, dword ptr [rsp+0A8h+var_48]
0x180003378  test    edi, edi
0x18000337a  jnz     short loc_1800033DE
0x18000337c  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003382  jz      short loc_1800033DE
0x180003384  lea     rcx, SRWLock; SRWLock
0x18000338b  call    cs:__imp_AcquireSRWLockExclusive
0x180003391  cmp     cs:qword_18001F1F8, rbx
0x180003398  jnz     short loc_1800033D0
0x18000339a  mov     cs:qword_18001F1F8, rbx
0x1800033a1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800033a8  test    rax, rax
0x1800033ab  jnz     short loc_1800033B9
0x1800033ad  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800033b4  test    rax, rax
0x1800033b7  jz      short loc_1800033D0
0x1800033b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800033bd  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z; `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x1800033c4  lea     rcx, qword_18001F1F8
0x1800033cb  call    _guard_dispatch_icall
0x1800033d0  lea     rcx, SRWLock; SRWLock
0x1800033d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800033dd  nop
0x1800033de  test    r14d, r14d
0x1800033e1  jz      short loc_180003414
0x1800033e3  mov     edx, esi
0x1800033e5  bts     edx, 1Fh
0x1800033e9  test    r15d, r15d
0x1800033ec  cmovz   edx, esi
0x1800033ef  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800033f6  test    rax, rax
0x1800033f9  jnz     short loc_180003407
0x1800033fb  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180003402  test    rax, rax
0x180003405  jz      short loc_180003414
0x180003407  xor     r9d, r9d
0x18000340a  xor     r8d, r8d
0x18000340d  mov     ecx, ebp
0x18000340f  call    _guard_dispatch_icall
0x180003414  test    edi, edi
0x180003416  jnz     short loc_180003437
0x180003418  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000341f  test    rax, rax
0x180003422  jz      short loc_180003435
0x180003424  mov     r8b, [rsp+0A8h+arg_38]
0x18000342c  mov     edx, esi
0x18000342e  mov     ecx, ebp
0x180003430  call    _guard_dispatch_icall
0x180003435  test    edi, edi
0x180003437  setz    bl
0x18000343a  mov     eax, ebx
0x18000343c  mov     rbx, [rsp+0A8h+arg_10]
0x180003444  add     rsp, 80h
0x18000344b  pop     r15
0x18000344d  pop     r14
0x18000344f  pop     rdi
0x180003450  pop     rsi
0x180003451  pop     rbp
0x180003452  retn
```

# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180016a98`
- end: `0x180016ca3`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180016cac`

## callees

- `0x180010418`
- `0x180016624`
- `0x18001694c`
- `0x180016a98`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016bdb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016bdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  void (__fastcall *v19)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
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
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004DDF0, v24, v15);
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
    if ( !qword_18004DDE8 )
    {
      qword_18004DDE8 = 0;
      v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v19 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v19(&qword_18004DDE8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
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
0x180016a98  mov     [rsp+arg_10], rbx
0x180016a9d  push    rbp
0x180016a9e  push    rsi
0x180016a9f  push    rdi
0x180016aa0  push    r14
0x180016aa2  push    r15
0x180016aa4  sub     rsp, 80h
0x180016aab  mov     r15d, r9d
0x180016aae  mov     r14d, r8d
0x180016ab1  mov     ebp, edx
0x180016ab3  mov     rdi, rcx
0x180016ab6  mov     esi, [rsp+0A8h+arg_20]
0x180016abd  mov     r8d, esi
0x180016ac0  mov     rdx, rcx
0x180016ac3  lea     rcx, [rsp+0A8h+var_40]
0x180016ac8  call    wil_details_FeatureReporting_RecordUsageInCache
0x180016acd  movups  xmm1, xmmword ptr [rax]
0x180016ad0  movups  [rsp+0A8h+var_68], xmm1
0x180016ad5  movsd   xmm0, qword ptr [rax+10h]
0x180016ada  movsd   [rsp+0A8h+var_48], xmm0
0x180016ae0  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180016ae7  xor     ebx, ebx
0x180016ae9  test    rax, rax
0x180016aec  jz      short loc_180016B0E
0x180016aee  test    esi, esi
0x180016af0  jz      short loc_180016AFA
0x180016af2  lea     ecx, [rsi-64h]
0x180016af5  cmp     ecx, 31h ; '1'
0x180016af8  ja      short loc_180016B0E
0x180016afa  mov     r8d, 1
0x180016b00  mov     edx, esi
0x180016b02  mov     ecx, ebp
0x180016b04  call    _guard_dispatch_icall
0x180016b09  movups  xmm1, [rsp+0A8h+var_68]
0x180016b0e  movd    eax, xmm1
0x180016b12  test    eax, eax
0x180016b14  jz      short loc_180016B86
0x180016b16  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016b1c  jz      short loc_180016B86
0x180016b1e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x180016b24  jnz     short loc_180016B86
0x180016b26  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016b2d  test    rax, rax
0x180016b30  jz      short loc_180016B3B
0x180016b32  call    _guard_dispatch_icall
0x180016b37  test    al, al
0x180016b39  jnz     short loc_180016B81
0x180016b3b  lea     rcx, SRWLock; SRWLock
0x180016b42  call    cs:__imp_AcquireSRWLockExclusive
0x180016b48  mov     [rsp+0A8h+var_78], ebp
0x180016b4c  xor     eax, eax
0x180016b4e  mov     [rsp+0A8h+var_74], eax
0x180016b52  mov     [rsp+0A8h+var_70], rdi
0x180016b57  lea     rdx, [rsp+0A8h+var_78]; void *
0x180016b5c  lea     rcx, qword_18004DDF0; this
0x180016b63  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016b68  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180016b6f  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::EnsureTimerUnderLock(void)
0x180016b74  lea     rcx, SRWLock; SRWLock
0x180016b7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180016b81  movups  xmm1, [rsp+0A8h+var_68]
0x180016b86  movdqa  xmm0, xmm1
0x180016b8a  psrldq  xmm0, 4
0x180016b8f  movd    r8d, xmm0
0x180016b94  test    r8d, r8d
0x180016b97  jz      short loc_180016BC4
0x180016b99  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180016ba0  test    rax, rax
0x180016ba3  jnz     short loc_180016BB1
0x180016ba5  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180016bac  test    rax, rax
0x180016baf  jz      short loc_180016BC4
0x180016bb1  psrldq  xmm1, 8
0x180016bb6  xor     r9d, r9d
0x180016bb9  movd    edx, xmm1
0x180016bbd  mov     ecx, ebp
0x180016bbf  call    _guard_dispatch_icall
0x180016bc4  mov     edi, dword ptr [rsp+0A8h+var_48]
0x180016bc8  test    edi, edi
0x180016bca  jnz     short loc_180016C2E
0x180016bcc  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, bl; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016bd2  jz      short loc_180016C2E
0x180016bd4  lea     rcx, SRWLock; SRWLock
0x180016bdb  call    cs:__imp_AcquireSRWLockExclusive
0x180016be1  cmp     cs:qword_18004DDE8, rbx
0x180016be8  jnz     short loc_180016C20
0x180016bea  mov     cs:qword_18004DDE8, rbx
0x180016bf1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180016bf8  test    rax, rax
0x180016bfb  jnz     short loc_180016C09
0x180016bfd  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180016c04  test    rax, rax
0x180016c07  jz      short loc_180016C20
0x180016c09  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016c0d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180016c14  lea     rcx, qword_18004DDE8
0x180016c1b  call    _guard_dispatch_icall
0x180016c20  lea     rcx, SRWLock; SRWLock
0x180016c27  call    cs:__imp_ReleaseSRWLockExclusive
0x180016c2d  nop
0x180016c2e  test    r14d, r14d
0x180016c31  jz      short loc_180016C64
0x180016c33  mov     edx, esi
0x180016c35  bts     edx, 1Fh
0x180016c39  test    r15d, r15d
0x180016c3c  cmovz   edx, esi
0x180016c3f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180016c46  test    rax, rax
0x180016c49  jnz     short loc_180016C57
0x180016c4b  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180016c52  test    rax, rax
0x180016c55  jz      short loc_180016C64
0x180016c57  xor     r9d, r9d
0x180016c5a  xor     r8d, r8d
0x180016c5d  mov     ecx, ebp
0x180016c5f  call    _guard_dispatch_icall
0x180016c64  test    edi, edi
0x180016c66  jnz     short loc_180016C87
0x180016c68  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180016c6f  test    rax, rax
0x180016c72  jz      short loc_180016C85
0x180016c74  mov     r8b, [rsp+0A8h+arg_38]
0x180016c7c  mov     edx, esi
0x180016c7e  mov     ecx, ebp
0x180016c80  call    _guard_dispatch_icall
0x180016c85  test    edi, edi
0x180016c87  setz    bl
0x180016c8a  mov     eax, ebx
0x180016c8c  mov     rbx, [rsp+0A8h+arg_10]
0x180016c94  add     rsp, 80h
0x180016c9b  pop     r15
0x180016c9d  pop     r14
0x180016c9f  pop     rdi
0x180016ca0  pop     rsi
0x180016ca1  pop     rbp
0x180016ca2  retn
```

# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180005e90`
- end: `0x1800062c8`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `1080`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180005220`
- `0x180006ed0`
- `0x180027340`

## callees

- `0x180005e90`
- `0x18002d704`
- `0x1800340e4`
- `0x180042010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006035`
- `msvcrt!memcpy_s` at `0x1800060ba`
- `msvcrt!memcpy_s` at `0x180006035`
- `msvcrt!memcpy_s` at `0x1800060ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006241`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006241`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000604e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000604e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000605c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000605c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006113`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006010`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006081`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006145`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006154`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006010`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006081`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006145`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006154`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800060fe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800060fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006134`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006134`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000613d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000613d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006126`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006183`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006126`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006183`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int v8; // r15d
  int *v11; // rax
  __int64 v12; // rcx
  int v13; // ebx
  unsigned int v14; // r13d
  unsigned int v15; // r14d
  int v16; // esi
  __int64 v17; // rcx
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // rdx
  void *v20; // r10
  unsigned __int64 v21; // rbx
  DWORD LastError; // esi
  unsigned __int64 v23; // r14
  char *v24; // rax
  char *v25; // rbx
  signed __int64 v26; // rdi
  void *v27; // r15
  HANDLE ProcessHeap; // rax
  rsize_t v29; // rdx
  struct _TP_TIMER *v30; // rcx
  DWORD v31; // esi
  struct _TP_TIMER *ThreadpoolTimer; // r14
  struct _TP_TIMER *v33; // rdi
  DWORD v34; // ebx
  void (__fastcall *v35)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v36)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v37; // rdx
  void (__fastcall *v38)(_QWORD, __int64, _QWORD, _QWORD); // rax
  unsigned int v40; // [rsp+30h] [rbp-78h]
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-70h] BYREF
  _DWORD Source[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v43; // [rsp+48h] [rbp-60h]
  char v44[88]; // [rsp+50h] [rbp-58h] BYREF
  int v47; // [rsp+E0h] [rbp+38h]

  v8 = a3;
  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v44, a1, a5, a6);
  v13 = *v11;
  v14 = v11[1];
  v15 = v11[2];
  v40 = v15;
  v16 = v11[4];
  v47 = v16;
  if ( g_wil_details_RecordSRUMFeatureUsage )
  {
    if ( !a5 || (v12 = a5 - 100, (unsigned int)v12 <= 0x31) )
      g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  }
  if ( v13
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v12)) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v17) )
    {
LABEL_33:
      ReleaseSRWLockExclusive(&SRWLock);
      goto LABEL_34;
    }
    Source[0] = a2;
    Source[1] = 0;
    v43 = a1;
    v18 = qword_180054500;
    v19 = qword_180054500 - (_QWORD)::Source;
    v20 = Destination;
    if ( (_BYTE *)Destination - (_BYTE *)::Source + 16 >= (unsigned __int64)(qword_180054500 - (_QWORD)::Source) )
    {
      v21 = 16;
      if ( 2 * v19 > 0x10 )
        v21 = 2 * v19;
      if ( v19 < v21 )
      {
        LastError = GetLastError();
        v23 = (v21 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v24 = (char *)wil::details::ProcessHeapAlloc(0, v23);
        v25 = v24;
        if ( !v24 )
        {
          SetLastError(LastError);
LABEL_26:
          if ( !byte_1800544E8 )
          {
            v30 = pti;
            if ( pti )
              goto LABEL_31;
            v31 = GetLastError();
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                &wil::details::g_enabledStateManager,
                                0);
            v33 = pti;
            if ( pti )
            {
              v34 = GetLastError();
              SetThreadpoolTimer(v33, 0, 0, 0);
              WaitForThreadpoolTimerCallbacks(v33, 1);
              CloseThreadpoolTimer(v33);
              SetLastError(v34);
            }
            pti = ThreadpoolTimer;
            SetLastError(v31);
            v30 = pti;
            if ( pti )
            {
LABEL_31:
              pftDueTime = (struct _FILETIME)-3000000000LL;
              SetThreadpoolTimer(v30, &pftDueTime, 0, 0x124F8u);
              byte_1800544E8 = 1;
            }
          }
          v16 = v47;
          v15 = v40;
          goto LABEL_33;
        }
        v26 = (_BYTE *)Destination - (_BYTE *)::Source;
        memcpy_s(v24, v23, ::Source, (_BYTE *)Destination - (_BYTE *)::Source);
        v27 = lpMem;
        lpMem = v25;
        if ( v27 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v27);
        }
        ::Source = v25;
        Destination = &v25[v26];
        qword_180054500 = (__int64)&v25[v23];
        SetLastError(LastError);
        v18 = qword_180054500;
        v20 = Destination;
        v8 = a3;
      }
    }
    v29 = 0;
    if ( (unsigned __int64)v20 < v18 )
      v29 = v18 - (_QWORD)v20;
    memcpy_s(v20, v29, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_26;
  }
LABEL_34:
  if ( v14 )
  {
    v35 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v35 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v35(a2, v15, v14, 0);
    }
  }
  if ( !v16 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180054538 )
    {
      qword_180054538 = 0;
      v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v36 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v36(&qword_180054538, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v8 )
  {
    v37 = a5;
    LODWORD(v37) = a5 | 0x80000000;
    if ( !a4 )
      v37 = a5;
    v38 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v38 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v38(a2, v37, 0, 0);
    }
  }
  if ( v16 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
    g_wil_details_realtimeFeatureUsageHook(a2, a5, a8);
  return 1;
}

```

## disassembly

```asm
0x180005e90  mov     [rsp+arg_0], rbx
0x180005e95  mov     [rsp+arg_18], r9d
0x180005e9a  mov     [rsp+arg_10], r8d
0x180005e9f  push    rbp
0x180005ea0  push    rsi
0x180005ea1  push    rdi
0x180005ea2  push    r12
0x180005ea4  push    r13
0x180005ea6  push    r14
0x180005ea8  push    r15
0x180005eaa  sub     rsp, 70h
0x180005eae  mov     r15d, r8d
0x180005eb1  mov     r12d, edx
0x180005eb4  mov     rdi, rcx
0x180005eb7  mov     r9d, [rsp+0A8h+arg_28]
0x180005ebf  mov     ebp, [rsp+0A8h+arg_20]
0x180005ec6  mov     r8d, ebp
0x180005ec9  mov     rdx, rcx
0x180005ecc  lea     rcx, [rsp+0A8h+var_58]
0x180005ed1  call    wil_details_FeatureReporting_RecordUsageInCache
0x180005ed6  mov     ebx, [rax]
0x180005ed8  mov     r13d, [rax+4]
0x180005edc  mov     r14d, [rax+8]
0x180005ee0  mov     [rsp+0A8h+var_78], r14d
0x180005ee5  mov     esi, [rax+10h]
0x180005ee8  mov     [rsp+0A8h+arg_30], esi
0x180005eef  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180005ef6  test    rax, rax
0x180005ef9  jz      short loc_180005F17
0x180005efb  test    ebp, ebp
0x180005efd  jz      short loc_180005F07
0x180005eff  lea     ecx, [rbp-64h]
0x180005f02  cmp     ecx, 31h ; '1'
0x180005f05  ja      short loc_180005F17
0x180005f07  mov     r8d, 1
0x180005f0d  mov     edx, ebp
0x180005f0f  mov     ecx, r12d
0x180005f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f17  test    ebx, ebx
0x180005f19  jz      loc_1800061AA
0x180005f1f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005f25  test    eax, eax
0x180005f27  jz      loc_1800061AA
0x180005f2d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005f34  jnz     loc_1800061AA
0x180005f3a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005f41  test    rax, rax
0x180005f44  jz      short loc_180005F53
0x180005f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f4b  test    al, al
0x180005f4d  jnz     loc_1800061AA
0x180005f53  lea     rcx, SRWLock; SRWLock
0x180005f5a  call    cs:__imp_AcquireSRWLockExclusive
0x180005f60  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005f66  test    eax, eax
0x180005f68  jz      loc_18000619C
0x180005f6e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005f75  jnz     loc_18000619C
0x180005f7b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005f82  test    rax, rax
0x180005f85  jz      short loc_180005F94
0x180005f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8c  test    al, al
0x180005f8e  jnz     loc_18000619C
0x180005f94  mov     [rsp+0A8h+Source], r12d
0x180005f99  xor     eax, eax
0x180005f9b  mov     [rsp+0A8h+var_64], eax
0x180005f9f  mov     [rsp+0A8h+var_60], rdi
0x180005fa4  mov     r8, cs:qword_180054500
0x180005fab  mov     rdx, r8
0x180005fae  sub     rdx, cs:Source
0x180005fb5  mov     r10, cs:Destination
0x180005fbc  mov     rax, r10
0x180005fbf  sub     rax, cs:Source
0x180005fc6  add     rax, 10h
0x180005fca  cmp     rax, rdx
0x180005fcd  jb      loc_18000609D
0x180005fd3  lea     rax, [rdx+rdx]
0x180005fd7  mov     ebx, 10h
0x180005fdc  cmp     rax, rbx
0x180005fdf  cmova   rbx, rax
0x180005fe3  cmp     rdx, rbx
0x180005fe6  jnb     loc_18000609D
0x180005fec  call    cs:__imp_GetLastError
0x180005ff2  mov     esi, eax
0x180005ff4  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180005ff8  lea     r14, [rbx+40h]
0x180005ffc  mov     rdx, r14; dwBytes
0x180005fff  xor     ecx, ecx; dwFlags
0x180006001  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006006  mov     rbx, rax
0x180006009  test    rax, rax
0x18000600c  jnz     short loc_18000601B
0x18000600e  mov     ecx, esi; dwErrCode
0x180006010  call    cs:__imp_SetLastError
0x180006016  jmp     loc_1800060C8
0x18000601b  mov     r8, cs:Source; Source
0x180006022  mov     rdi, cs:Destination
0x180006029  sub     rdi, r8
0x18000602c  mov     r9, rdi; SourceSize
0x18000602f  mov     rdx, r14; DestinationSize
0x180006032  mov     rcx, rbx; Destination
0x180006035  call    cs:__imp_memcpy_s
0x18000603b  mov     r15, cs:lpMem
0x180006042  mov     cs:lpMem, rbx
0x180006049  test    r15, r15
0x18000604c  jz      short loc_180006062
0x18000604e  call    cs:__imp_GetProcessHeap
0x180006054  mov     rcx, rax; hHeap
0x180006057  mov     r8, r15; lpMem
0x18000605a  xor     edx, edx; dwFlags
0x18000605c  call    cs:__imp_HeapFree
0x180006062  mov     cs:Source, rbx
0x180006069  lea     rax, [rdi+rbx]
0x18000606d  mov     cs:Destination, rax
0x180006074  lea     rax, [r14+rbx]
0x180006078  mov     cs:qword_180054500, rax
0x18000607f  mov     ecx, esi; dwErrCode
0x180006081  call    cs:__imp_SetLastError
0x180006087  mov     r8, cs:qword_180054500
0x18000608e  mov     r10, cs:Destination
0x180006095  mov     r15d, [rsp+0A8h+arg_10]
0x18000609d  mov     rax, r8
0x1800060a0  sub     rax, r10
0x1800060a3  xor     edx, edx
0x1800060a5  cmp     r10, r8
0x1800060a8  cmovb   rdx, rax; DestinationSize
0x1800060ac  mov     r9d, 10h; SourceSize
0x1800060b2  lea     r8, [rsp+0A8h+Source]; Source
0x1800060b7  mov     rcx, r10; Destination
0x1800060ba  call    cs:__imp_memcpy_s
0x1800060c0  add     cs:Destination, 10h
0x1800060c8  cmp     cs:byte_1800544E8, 0
0x1800060cf  jnz     loc_180006190
0x1800060d5  mov     rcx, cs:pti
0x1800060dc  test    rcx, rcx
0x1800060df  jnz     loc_180006166
0x1800060e5  call    cs:__imp_GetLastError
0x1800060eb  mov     esi, eax
0x1800060ed  xor     r8d, r8d; pcbe
0x1800060f0  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800060f7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800060fe  call    cs:__imp_CreateThreadpoolTimer
0x180006104  mov     r14, rax
0x180006107  mov     rdi, cs:pti
0x18000610e  test    rdi, rdi
0x180006111  jz      short loc_18000614B
0x180006113  call    cs:__imp_GetLastError
0x180006119  mov     ebx, eax
0x18000611b  xor     r9d, r9d; msWindowLength
0x18000611e  xor     r8d, r8d; msPeriod
0x180006121  xor     edx, edx; pftDueTime
0x180006123  mov     rcx, rdi; pti
0x180006126  call    cs:__imp_SetThreadpoolTimer
0x18000612c  mov     edx, 1; fCancelPendingCallbacks
0x180006131  mov     rcx, rdi; pti
0x180006134  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000613a  mov     rcx, rdi; pti
0x18000613d  call    cs:__imp_CloseThreadpoolTimer
0x180006143  mov     ecx, ebx; dwErrCode
0x180006145  call    cs:__imp_SetLastError
0x18000614b  mov     cs:pti, r14
0x180006152  mov     ecx, esi; dwErrCode
0x180006154  call    cs:__imp_SetLastError
0x18000615a  mov     rcx, cs:pti; pti
0x180006161  test    rcx, rcx
0x180006164  jz      short loc_180006190
0x180006166  mov     rax, 0FFFFFFFF4D2FA200h
0x180006170  mov     qword ptr [rsp+0A8h+pftDueTime.dwLowDateTime], rax
0x180006175  mov     r9d, 124F8h; msWindowLength
0x18000617b  xor     r8d, r8d; msPeriod
0x18000617e  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x180006183  call    cs:__imp_SetThreadpoolTimer
0x180006189  mov     cs:byte_1800544E8, 1
0x180006190  mov     esi, [rsp+0A8h+arg_30]
0x180006197  mov     r14d, [rsp+0A8h+var_78]
0x18000619c  lea     rcx, SRWLock; SRWLock
0x1800061a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800061a9  nop
0x1800061aa  test    r13d, r13d
0x1800061ad  jz      short loc_1800061D8
0x1800061af  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800061b6  test    rax, rax
0x1800061b9  jnz     short loc_1800061C7
0x1800061bb  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800061c2  test    rax, rax
0x1800061c5  jz      short loc_1800061D8
0x1800061c7  xor     r9d, r9d
0x1800061ca  mov     r8d, r13d
0x1800061cd  mov     edx, r14d
0x1800061d0  mov     ecx, r12d
0x1800061d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d8  test    esi, esi
0x1800061da  jnz     short loc_180006248
0x1800061dc  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800061e2  test    eax, eax
0x1800061e4  jz      short loc_180006248
0x1800061e6  lea     rcx, SRWLock; SRWLock
0x1800061ed  call    cs:__imp_AcquireSRWLockExclusive
0x1800061f3  cmp     cs:qword_180054538, 0
0x1800061fb  jnz     short loc_18000623A
0x1800061fd  mov     cs:qword_180054538, 0
0x180006208  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000620f  test    rax, rax
0x180006212  jnz     short loc_180006220
0x180006214  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000621b  test    rax, rax
0x18000621e  jz      short loc_18000623A
0x180006220  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180006227  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000622e  lea     rcx, qword_180054538
0x180006235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000623a  lea     rcx, SRWLock; SRWLock
0x180006241  call    cs:__imp_ReleaseSRWLockExclusive
0x180006247  nop
0x180006248  test    r15d, r15d
0x18000624b  jz      short loc_180006284
0x18000624d  mov     edx, ebp
0x18000624f  bts     edx, 1Fh
0x180006253  cmp     [rsp+0A8h+arg_18], 0
0x18000625b  cmovz   edx, ebp
0x18000625e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180006265  test    rax, rax
0x180006268  jnz     short loc_180006276
0x18000626a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006271  test    rax, rax
0x180006274  jz      short loc_180006284
0x180006276  xor     r9d, r9d
0x180006279  xor     r8d, r8d
0x18000627c  mov     ecx, r12d
0x18000627f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006284  test    esi, esi
0x180006286  jnz     short loc_1800062AE
0x180006288  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000628f  test    rax, rax
0x180006292  jz      short loc_1800062A7
0x180006294  movzx   r8d, [rsp+0A8h+arg_38]
0x18000629d  mov     edx, ebp
0x18000629f  mov     ecx, r12d
0x1800062a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a7  mov     eax, 1
0x1800062ac  jmp     short loc_1800062B0
0x1800062ae  xor     eax, eax
0x1800062b0  mov     rbx, [rsp+0A8h+arg_0]
0x1800062b8  add     rsp, 70h
0x1800062bc  pop     r15
0x1800062be  pop     r14
0x1800062c0  pop     r13
0x1800062c2  pop     r12
0x1800062c4  pop     rdi
0x1800062c5  pop     rsi
0x1800062c6  pop     rbp
0x1800062c7  retn
```

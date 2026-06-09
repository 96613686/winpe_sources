# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180086e70`
- end: `0x1800871ca`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `858`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callees

- `0x180009e78`
- `0x180032164`
- `0x180032220`
- `0x1800325d0`
- `0x1800335c0`
- `0x1800336dc`
- `0x180086e70`
- `0x1800b30d2`
- `0x1800b3128`
- `0x1800b8a98`
- `0x18010b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180087063`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180087092`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180087063`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180087092`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086fc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087035`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008712d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008713c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086fc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087035`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008712d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008713c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800870cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800870fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800870cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800870fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087002`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087010`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180086f3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180086f3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180087179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180087179`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800870e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800870e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180087125`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180087125`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008711c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008711c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008710e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180087165`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008710e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180087165`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, unsigned int a2, unsigned int a3)
{
  unsigned int v4; // ebx
  DWORD v5; // esi
  __int64 v6; // rcx
  __int128 v7; // kr00_16
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  DWORD LastError; // esi
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r8
  char *v13; // rax
  char *v14; // rbx
  signed __int64 v15; // r14
  void *v16; // rbp
  HANDLE ProcessHeap; // rax
  size_t v18; // r8
  struct _TP_TIMER *v19; // rcx
  DWORD v20; // esi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v22; // rdi
  struct _TP_TIMER *v23; // rbp
  DWORD v24; // ebx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  v4 = a2 & 0x7FFFFFFF;
  v5 = (unsigned int)this;
  if ( !(_DWORD)this && !a3 && !v4 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18014FE58[25], qword_18014FE58);
      wil::details_abi::FeatureStateData::RecordUsage((wil::details_abi::FeatureStateData *)qword_18014FE58);
    }
    return;
  }
  if ( (a2 & 0x40000000) == 0 )
  {
    if ( a3 || v4 == 254 )
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    else
      wil_RtlStagingConfig_RecordFeatureUsage(this, v4, a2 >> 31);
    return;
  }
  if ( !wil::details::g_featureStateManager
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(&stru_18014FE68);
  v7 = *(_OWORD *)&xmmword_18014FF30;
  v8 = (_BYTE *)*(&xmmword_18014FF30 + 1) - (_BYTE *)Source;
  pftDueTime.dwLowDateTime = v5;
  pftDueTime.dwHighDateTime = (unsigned __int16)v4;
  if ( (_BYTE *)xmmword_18014FF30 - (_BYTE *)Source + 12 >= (unsigned __int64)((_BYTE *)*(&xmmword_18014FF30 + 1)
                                                                             - (_BYTE *)Source) )
  {
    v9 = 12;
    if ( 2 * v8 > 0xC )
      v9 = 2 * v8;
    if ( v8 < v9 )
    {
      LastError = GetLastError();
      v11 = (v9 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v13 = (char *)wil::details::ProcessHeapAlloc(0, v11, v12);
      v14 = v13;
      if ( !v13 )
      {
        SetLastError(LastError);
        goto LABEL_32;
      }
      v15 = (_BYTE *)xmmword_18014FF30 - (_BYTE *)Source;
      memcpy_s(v13, v11, Source, (_BYTE *)xmmword_18014FF30 - (_BYTE *)Source);
      v16 = qword_18014FF40;
      qword_18014FF40 = v14;
      if ( v16 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v16);
      }
      Source = v14;
      xmmword_18014FF30 = &v14[v15];
      *(&xmmword_18014FF30 + 1) = &v14[v11];
      SetLastError(LastError);
      v7 = *(_OWORD *)&xmmword_18014FF30;
    }
  }
  v18 = 0;
  if ( (unsigned __int64)v7 < *((_QWORD *)&v7 + 1) )
    v18 = *((_QWORD *)&v7 + 1) - v7;
  if ( !(_QWORD)v7 )
  {
    *(_DWORD *)_o__errno(v6, v8, v18) = 22;
LABEL_30:
    invalid_parameter_noinfo();
    goto LABEL_31;
  }
  if ( v18 < 0xC )
  {
    memset_0((void *)v7, 0, v18);
    *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    goto LABEL_30;
  }
  *(struct _FILETIME *)v7 = pftDueTime;
  *(_DWORD *)(v7 + 8) = a3;
LABEL_31:
  xmmword_18014FF30 = (char *)xmmword_18014FF30 + 12;
LABEL_32:
  if ( !(_BYTE)word_18014FE80 )
  {
    v19 = pti;
    if ( pti )
      goto LABEL_37;
    v20 = GetLastError();
    ThreadpoolTimer = CreateThreadpoolTimer(
                        _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                        &wil::details::g_featureStateManager,
                        0);
    v22 = pti;
    v23 = ThreadpoolTimer;
    if ( pti )
    {
      v24 = GetLastError();
      SetThreadpoolTimer(v22, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v22, 1);
      CloseThreadpoolTimer(v22);
      SetLastError(v24);
    }
    pti = v23;
    SetLastError(v20);
    v19 = pti;
    if ( pti )
    {
LABEL_37:
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v19, &pftDueTime, 0, 0x4E2u);
      LOBYTE(word_18014FE80) = 1;
    }
  }
  ReleaseSRWLockExclusive(&stru_18014FE68);
}

```

## disassembly

```asm
0x180086e70  push    rbx
0x180086e72  push    rsi
0x180086e73  push    rdi
0x180086e74  sub     rsp, 30h
0x180086e78  mov     ebx, edx
0x180086e7a  mov     edi, r8d
0x180086e7d  btr     ebx, 1Fh
0x180086e81  mov     esi, ecx
0x180086e83  test    ecx, ecx
0x180086e85  jnz     short loc_180086EF0
0x180086e87  test    r8d, r8d
0x180086e8a  jnz     short loc_180086EF0
0x180086e8c  test    ebx, ebx
0x180086e8e  jnz     short loc_180086EF0
0x180086e90  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x180086e96  jnz     loc_1800871C2
0x180086e9c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180086ea3  test    rax, rax
0x180086ea6  jz      short loc_180086EB5
0x180086ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ead  test    al, al
0x180086eaf  jnz     loc_1800871C2
0x180086eb5  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180086ebc  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180086ec1  test    al, al
0x180086ec3  jz      loc_1800871C2
0x180086ec9  mov     rdx, cs:qword_18014FE58; SRWLock
0x180086ed0  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180086ed7  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180086edc  mov     rcx, cs:qword_18014FE58; this
0x180086ee3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180086ee8  add     rsp, 30h
0x180086eec  pop     rdi
0x180086eed  pop     rsi
0x180086eee  pop     rbx
0x180086eef  retn
0x180086ef0  bt      ebx, 1Eh
0x180086ef4  jnb     loc_18008718C
0x180086efa  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180086f01  jz      loc_1800871C2
0x180086f07  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180086f0e  jnz     loc_1800871C2
0x180086f14  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180086f1b  test    rax, rax
0x180086f1e  jz      short loc_180086F2D
0x180086f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f25  test    al, al
0x180086f27  jnz     loc_1800871C2
0x180086f2d  mov     [rsp+48h+arg_0], rbp
0x180086f32  lea     rcx, stru_18014FE68; SRWLock
0x180086f39  mov     [rsp+48h+arg_10], r15
0x180086f3e  call    cs:__imp_AcquireSRWLockExclusive
0x180086f44  mov     r9, qword ptr cs:xmmword_18014FF30
0x180086f4b  xor     eax, eax
0x180086f4d  mov     r10, qword ptr cs:xmmword_18014FF30+8
0x180086f54  mov     word ptr [rsp+48h+pftDueTime.dwHighDateTime+2], ax
0x180086f59  mov     rdx, r10
0x180086f5c  sub     rdx, cs:Source
0x180086f63  mov     rax, r9
0x180086f66  sub     rax, cs:Source
0x180086f6d  add     rax, 0Ch
0x180086f71  mov     [rsp+48h+pftDueTime.dwLowDateTime], esi
0x180086f75  mov     word ptr [rsp+48h+pftDueTime.dwHighDateTime], bx
0x180086f7a  cmp     rax, rdx
0x180086f7d  jb      loc_18008704E
0x180086f83  lea     rax, [rdx+rdx]
0x180086f87  mov     ebx, 0Ch
0x180086f8c  cmp     rax, rbx
0x180086f8f  cmova   rbx, rax
0x180086f93  cmp     rdx, rbx
0x180086f96  jnb     loc_18008704E
0x180086f9c  call    cs:__imp_GetLastError
0x180086fa2  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180086fa6  xor     ecx, ecx; dwFlags
0x180086fa8  mov     esi, eax
0x180086faa  lea     r15, [rbx+40h]
0x180086fae  mov     rdx, r15; dwBytes
0x180086fb1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180086fb6  mov     rbx, rax
0x180086fb9  test    rax, rax
0x180086fbc  jnz     short loc_180086FCB
0x180086fbe  mov     ecx, esi; dwErrCode
0x180086fc0  call    cs:__imp_SetLastError
0x180086fc6  jmp     loc_1800870AB
0x180086fcb  mov     r8, cs:Source; Source
0x180086fd2  mov     rdx, r15; DestinationSize
0x180086fd5  mov     [rsp+48h+arg_8], r14
0x180086fda  mov     rcx, rbx; Destination
0x180086fdd  mov     r14, qword ptr cs:xmmword_18014FF30
0x180086fe4  sub     r14, r8
0x180086fe7  mov     r9, r14; SourceSize
0x180086fea  call    memcpy_s
0x180086fef  mov     rbp, cs:qword_18014FF40
0x180086ff6  mov     cs:qword_18014FF40, rbx
0x180086ffd  test    rbp, rbp
0x180087000  jz      short loc_180087016
0x180087002  call    cs:__imp_GetProcessHeap
0x180087008  mov     r8, rbp; lpMem
0x18008700b  xor     edx, edx; dwFlags
0x18008700d  mov     rcx, rax; hHeap
0x180087010  call    cs:__imp_HeapFree
0x180087016  lea     rax, [r14+rbx]
0x18008701a  mov     cs:Source, rbx
0x180087021  mov     qword ptr cs:xmmword_18014FF30, rax
0x180087028  mov     ecx, esi; dwErrCode
0x18008702a  lea     rax, [r15+rbx]
0x18008702e  mov     qword ptr cs:xmmword_18014FF30+8, rax
0x180087035  call    cs:__imp_SetLastError
0x18008703b  mov     r10, qword ptr cs:xmmword_18014FF30+8
0x180087042  mov     r9, qword ptr cs:xmmword_18014FF30
0x180087049  mov     r14, [rsp+48h+arg_8]
0x18008704e  xor     r8d, r8d
0x180087051  mov     rax, r10
0x180087054  sub     rax, r9
0x180087057  cmp     r9, r10
0x18008705a  cmovb   r8, rax; Size
0x18008705e  test    r9, r9
0x180087061  jnz     short loc_180087071
0x180087063  call    cs:__imp__o__errno
0x180087069  mov     dword ptr [rax], 16h
0x18008706f  jmp     short loc_18008709E
0x180087071  cmp     r8, 0Ch
0x180087075  jb      short loc_180087088
0x180087077  movsd   xmm0, qword ptr [rsp+48h+pftDueTime.dwLowDateTime]
0x18008707d  movsd   qword ptr [r9], xmm0
0x180087082  mov     [r9+8], edi
0x180087086  jmp     short loc_1800870A3
0x180087088  xor     edx, edx; Val
0x18008708a  mov     rcx, r9; void *
0x18008708d  call    memset_0
0x180087092  call    cs:__imp__o__errno
0x180087098  mov     dword ptr [rax], 22h ; '"'
0x18008709e  call    _invalid_parameter_noinfo
0x1800870a3  add     qword ptr cs:xmmword_18014FF30, 0Ch
0x1800870ab  cmp     byte ptr cs:word_18014FE80, 0
0x1800870b2  mov     r15, [rsp+48h+arg_10]
0x1800870b7  jnz     loc_180087172
0x1800870bd  mov     rcx, cs:pti
0x1800870c4  test    rcx, rcx
0x1800870c7  jnz     loc_18008714E
0x1800870cd  call    cs:__imp_GetLastError
0x1800870d3  xor     r8d, r8d; pcbe
0x1800870d6  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800870dd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800870e4  mov     esi, eax
0x1800870e6  call    cs:__imp_CreateThreadpoolTimer
0x1800870ec  mov     rdi, cs:pti
0x1800870f3  mov     rbp, rax
0x1800870f6  test    rdi, rdi
0x1800870f9  jz      short loc_180087133
0x1800870fb  call    cs:__imp_GetLastError
0x180087101  xor     r9d, r9d; msWindowLength
0x180087104  xor     r8d, r8d; msPeriod
0x180087107  xor     edx, edx; pftDueTime
0x180087109  mov     rcx, rdi; pti
0x18008710c  mov     ebx, eax
0x18008710e  call    cs:__imp_SetThreadpoolTimer
0x180087114  mov     edx, 1; fCancelPendingCallbacks
0x180087119  mov     rcx, rdi; pti
0x18008711c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180087122  mov     rcx, rdi; pti
0x180087125  call    cs:__imp_CloseThreadpoolTimer
0x18008712b  mov     ecx, ebx; dwErrCode
0x18008712d  call    cs:__imp_SetLastError
0x180087133  mov     ecx, esi; dwErrCode
0x180087135  mov     cs:pti, rbp
0x18008713c  call    cs:__imp_SetLastError
0x180087142  mov     rcx, cs:pti; pti
0x180087149  test    rcx, rcx
0x18008714c  jz      short loc_180087172
0x18008714e  mov     r9d, 4E2h; msWindowLength
0x180087154  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18008715d  xor     r8d, r8d; msPeriod
0x180087160  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180087165  call    cs:__imp_SetThreadpoolTimer
0x18008716b  mov     byte ptr cs:word_18014FE80, 1
0x180087172  lea     rcx, stru_18014FE68; SRWLock
0x180087179  call    cs:__imp_ReleaseSRWLockExclusive
0x18008717f  mov     rbp, [rsp+48h+arg_0]
0x180087184  add     rsp, 30h
0x180087188  pop     rdi
0x180087189  pop     rsi
0x18008718a  pop     rbx
0x18008718b  retn
0x18008718c  test    r8d, r8d
0x18008718f  jnz     short loc_1800871AE
0x180087191  cmp     ebx, 0FEh
0x180087197  jz      short loc_1800871AE
0x180087199  shr     edx, 1Fh
0x18008719c  mov     r8d, edx
0x18008719f  mov     edx, ebx
0x1800871a1  call    wil_RtlStagingConfig_RecordFeatureUsage
0x1800871a6  add     rsp, 30h
0x1800871aa  pop     rdi
0x1800871ab  pop     rsi
0x1800871ac  pop     rbx
0x1800871ad  retn
0x1800871ae  mov     r9, rdi
0x1800871b1  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800871b8  mov     r8d, ebx
0x1800871bb  mov     edx, esi
0x1800871bd  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800871c2  add     rsp, 30h
0x1800871c6  pop     rdi
0x1800871c7  pop     rsi
0x1800871c8  pop     rbx
0x1800871c9  retn
```

# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001c330`
- end: `0x18001c60b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `731`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180002aa0`
- `0x180004790`
- `0x1800051b0`
- `0x18000537c`
- `0x180005600`
- `0x180013f00`
- `0x18001c330`
- `0x180026cc8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c3f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c5b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c3f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c5b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c484`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c39a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c39a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c525`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c570`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c3fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c570`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c541`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c599`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c541`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c599`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c510`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c510`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c558`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c558`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c54f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c54f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, unsigned int a2, unsigned int a3)
{
  int v4; // ebp
  unsigned int v5; // ebx
  PSRWLOCK v6; // rdx
  DWORD v7; // edi
  RTL_SRWLOCK *Shared; // rbx
  struct _TP_TIMER *v9; // rcx
  DWORD LastError; // ebp
  struct _TP_TIMER *ThreadpoolTimer; // r14
  struct _TP_TIMER *v12; // rsi
  DWORD v13; // [rsp+2Ch] [rbp-5Ch]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-50h]
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp-48h]

  v4 = (int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v5 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      if ( wil::details::g_featureStateManager
        && !wil::details::g_processShutdownInProgress
        && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this)) )
      {
        AcquireSRWLockExclusive(&stru_18005A3A0);
        v16 = &stru_18005A3A0;
        LODWORD(SRWLock) = v4;
        HIDWORD(SRWLock) = (unsigned __int16)v5;
        v15 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&xmmword_18005A460, &SRWLock, 0xCu);
        if ( !(_BYTE)word_18005A3B8 )
        {
          v9 = pti;
          if ( pti )
            goto LABEL_27;
          LastError = GetLastError();
          LOBYTE(SRWLock) = 0;
          HIDWORD(SRWLock) = LastError;
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                              &wil::details::g_featureStateManager,
                              0);
          v12 = pti;
          if ( pti )
          {
            v13 = GetLastError();
            SetThreadpoolTimer(v12, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v12, 1);
            CloseThreadpoolTimer(v12);
            SetLastError(v13);
          }
          pti = ThreadpoolTimer;
          SetLastError(LastError);
          v9 = pti;
          if ( pti )
          {
LABEL_27:
            SRWLock = (PSRWLOCK)-50000000LL;
            SetThreadpoolTimer(v9, (PFILETIME)&SRWLock, 0, 0x4E2u);
            LOBYTE(word_18005A3B8) = 1;
          }
        }
        ReleaseSRWLockExclusive(&stru_18005A3A0);
      }
    }
    else if ( a3 || v5 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v5,
        a3,
        0);
    }
    else
    {
      wil_RtlStagingConfig_RecordFeatureUsage(this, v5, a2 >> 31);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress
          || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this)) )
  {
    v6 = xmmword_18005A390;
    if ( xmmword_18005A390 )
      goto LABEL_16;
    v7 = GetLastError();
    if ( xmmword_18005A390 )
      Shared = 0;
    else
      Shared = (RTL_SRWLOCK *)wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(&off_18005A380);
    wil::srwlock::lock_exclusive(&(&xmmword_18005A390)[1], &SRWLock);
    if ( !xmmword_18005A390 )
      xmmword_18005A390 = Shared;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    SetLastError(v7);
    v6 = xmmword_18005A390;
    if ( xmmword_18005A390 )
    {
LABEL_16:
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&v6[25], v6);
      wil::details_abi::FeatureStateData::RecordUsage(xmmword_18005A390);
    }
  }
}

```

## disassembly

```asm
0x18001c330  push    rbx
0x18001c332  push    rbp
0x18001c333  push    rsi
0x18001c334  push    rdi
0x18001c335  push    r14
0x18001c337  push    r15
0x18001c339  sub     rsp, 58h
0x18001c33d  mov     esi, r8d
0x18001c340  mov     ebp, ecx
0x18001c342  mov     [rsp+88h+var_68], 0
0x18001c34a  mov     ebx, edx
0x18001c34c  btr     ebx, 1Fh
0x18001c350  test    ecx, ecx
0x18001c352  jnz     loc_18001C439
0x18001c358  test    r8d, r8d
0x18001c35b  jnz     loc_18001C439
0x18001c361  test    ebx, ebx
0x18001c363  jnz     loc_18001C439
0x18001c369  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x18001c36f  jnz     loc_18001C5FE
0x18001c375  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c37c  test    rax, rax
0x18001c37f  jz      short loc_18001C38E
0x18001c381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c386  test    al, al
0x18001c388  jnz     loc_18001C5FE
0x18001c38e  mov     rdx, qword ptr cs:xmmword_18005A390
0x18001c395  test    rdx, rdx
0x18001c398  jnz     short loc_18001C414
0x18001c39a  call    cs:__imp_GetLastError
0x18001c3a0  mov     edi, eax
0x18001c3a2  mov     [rsp+88h+var_60], 0
0x18001c3a7  mov     [rsp+88h+var_5C], eax
0x18001c3ab  cmp     qword ptr cs:xmmword_18005A390, 0
0x18001c3b3  jz      short loc_18001C3B9
0x18001c3b5  xor     ebx, ebx
0x18001c3b7  jmp     short loc_18001C3C8
0x18001c3b9  lea     rcx, off_18005A380; "WilStaging_02"
0x18001c3c0  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x18001c3c5  mov     rbx, rax
0x18001c3c8  lea     rdx, [rsp+88h+SRWLock]
0x18001c3cd  lea     rcx, xmmword_18005A390+8
0x18001c3d4  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18001c3d9  nop
0x18001c3da  cmp     qword ptr cs:xmmword_18005A390, 0
0x18001c3e2  jnz     short loc_18001C3EB
0x18001c3e4  mov     qword ptr cs:xmmword_18005A390, rbx
0x18001c3eb  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x18001c3f0  test    rcx, rcx
0x18001c3f3  jz      short loc_18001C3FC
0x18001c3f5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c3fb  nop
0x18001c3fc  mov     ecx, edi; dwErrCode
0x18001c3fe  call    cs:__imp_SetLastError
0x18001c404  mov     rdx, qword ptr cs:xmmword_18005A390; SRWLock
0x18001c40b  test    rdx, rdx
0x18001c40e  jz      loc_18001C5FE
0x18001c414  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001c41b  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001c420  mov     rcx, qword ptr cs:xmmword_18005A390; SRWLock
0x18001c427  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001c42c  add     rsp, 58h
0x18001c430  pop     r15
0x18001c432  pop     r14
0x18001c434  pop     rdi
0x18001c435  pop     rsi
0x18001c436  pop     rbp
0x18001c437  pop     rbx
0x18001c438  retn
0x18001c439  bt      ebx, 1Eh
0x18001c43d  jnb     loc_18001C5C3
0x18001c443  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001c44a  jz      loc_18001C5FE
0x18001c450  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c457  jnz     loc_18001C5FE
0x18001c45d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c464  test    rax, rax
0x18001c467  jz      short loc_18001C476
0x18001c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c46e  test    al, al
0x18001c470  jnz     loc_18001C5FE
0x18001c476  btr     ebx, 1Eh
0x18001c47a  lea     r15, stru_18005A3A0
0x18001c481  mov     rcx, r15; SRWLock
0x18001c484  call    cs:__imp_AcquireSRWLockExclusive
0x18001c48a  mov     [rsp+88h+var_48], r15
0x18001c48f  mov     edi, 8
0x18001c494  mov     [rsp+88h+var_68], edi
0x18001c498  and     edi, 0FFFFFFF7h
0x18001c49b  mov     [rsp+88h+var_68], edi
0x18001c49f  or      edi, 4
0x18001c4a2  mov     [rsp+88h+var_68], edi
0x18001c4a6  xor     eax, eax
0x18001c4a8  mov     word ptr [rsp+88h+SRWLock+6], ax
0x18001c4ad  mov     dword ptr [rsp+88h+SRWLock], ebp
0x18001c4b1  mov     word ptr [rsp+88h+SRWLock+4], bx
0x18001c4b6  mov     [rsp+88h+var_50], esi
0x18001c4ba  mov     r8d, 0Ch; unsigned __int64
0x18001c4c0  lea     rdx, [rsp+88h+SRWLock]; void *
0x18001c4c5  lea     rcx, xmmword_18005A460; this
0x18001c4cc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001c4d1  cmp     byte ptr cs:word_18005A3B8, 0
0x18001c4d8  jnz     loc_18001C5A6
0x18001c4de  mov     rcx, cs:pti
0x18001c4e5  test    rcx, rcx
0x18001c4e8  jnz     loc_18001C582
0x18001c4ee  call    cs:__imp_GetLastError
0x18001c4f4  mov     ebp, eax
0x18001c4f6  mov     byte ptr [rsp+88h+SRWLock], 0
0x18001c4fb  mov     dword ptr [rsp+88h+SRWLock+4], eax
0x18001c4ff  xor     r8d, r8d; pcbe
0x18001c502  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001c509  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c510  call    cs:__imp_CreateThreadpoolTimer
0x18001c516  mov     r14, rax
0x18001c519  mov     rsi, cs:pti
0x18001c520  test    rsi, rsi
0x18001c523  jz      short loc_18001C567
0x18001c525  call    cs:__imp_GetLastError
0x18001c52b  mov     ebx, eax
0x18001c52d  mov     [rsp+88h+var_60], 0
0x18001c532  mov     [rsp+88h+var_5C], eax
0x18001c536  xor     r9d, r9d; msWindowLength
0x18001c539  xor     r8d, r8d; msPeriod
0x18001c53c  xor     edx, edx; pftDueTime
0x18001c53e  mov     rcx, rsi; pti
0x18001c541  call    cs:__imp_SetThreadpoolTimer
0x18001c547  mov     edx, 1; fCancelPendingCallbacks
0x18001c54c  mov     rcx, rsi; pti
0x18001c54f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c555  mov     rcx, rsi; pti
0x18001c558  call    cs:__imp_CloseThreadpoolTimer
0x18001c55e  nop
0x18001c55f  mov     ecx, ebx; dwErrCode
0x18001c561  call    cs:__imp_SetLastError
0x18001c567  mov     cs:pti, r14
0x18001c56e  mov     ecx, ebp; dwErrCode
0x18001c570  call    cs:__imp_SetLastError
0x18001c576  mov     rcx, cs:pti; pti
0x18001c57d  test    rcx, rcx
0x18001c580  jz      short loc_18001C5A6
0x18001c582  mov     [rsp+88h+SRWLock], 0FFFFFFFFFD050F80h
0x18001c58b  mov     r9d, 4E2h; msWindowLength
0x18001c591  xor     r8d, r8d; msPeriod
0x18001c594  lea     rdx, [rsp+88h+SRWLock]; pftDueTime
0x18001c599  call    cs:__imp_SetThreadpoolTimer
0x18001c59f  mov     byte ptr cs:word_18005A3B8, 1
0x18001c5a6  and     edi, 0FFFFFFFBh
0x18001c5a9  mov     [rsp+88h+var_68], edi
0x18001c5ad  mov     rcx, r15; SRWLock
0x18001c5b0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c5b6  add     rsp, 58h
0x18001c5ba  pop     r15
0x18001c5bc  pop     r14
0x18001c5be  pop     rdi
0x18001c5bf  pop     rsi
0x18001c5c0  pop     rbp
0x18001c5c1  pop     rbx
0x18001c5c2  retn
0x18001c5c3  test    r8d, r8d
0x18001c5c6  jnz     short loc_18001C5EA
0x18001c5c8  cmp     ebx, 0FEh
0x18001c5ce  jz      short loc_18001C5EA
0x18001c5d0  shr     edx, 1Fh
0x18001c5d3  mov     r8d, edx
0x18001c5d6  mov     edx, ebx
0x18001c5d8  call    wil_RtlStagingConfig_RecordFeatureUsage
0x18001c5dd  add     rsp, 58h
0x18001c5e1  pop     r15
0x18001c5e3  pop     r14
0x18001c5e5  pop     rdi
0x18001c5e6  pop     rsi
0x18001c5e7  pop     rbp
0x18001c5e8  pop     rbx
0x18001c5e9  retn
0x18001c5ea  mov     r9, rsi
0x18001c5ed  mov     r8d, ebx
0x18001c5f0  mov     edx, ebp
0x18001c5f2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001c5f9  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001c5fe  add     rsp, 58h
0x18001c602  pop     r15
0x18001c604  pop     r14
0x18001c606  pop     rdi
0x18001c607  pop     rsi
0x18001c608  pop     rbp
0x18001c609  pop     rbx
0x18001c60a  retn
```

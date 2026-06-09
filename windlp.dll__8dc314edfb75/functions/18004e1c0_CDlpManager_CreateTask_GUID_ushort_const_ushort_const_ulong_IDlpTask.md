# CDlpManager::CreateTask(_GUID,ushort const *,ushort const *,ulong,IDlpTask * *)

- ea: `0x18004e1c0`
- end: `0x18004e853`
- name: `?CreateTask@CDlpManager@@UEAAJU_GUID@@PEBG1KPEAPEAVIDlpTask@@@Z`
- size: `1683`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _GUID *, unsigned __int16 *, OLECHAR *, unsigned int, struct IDlpTask **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x1800475b0`
- `0x180049ba8`
- `0x18004d6f0`
- `0x18004e1c0`
- `0x180061dec`
- `0x180064ae8`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004e7b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e7b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e7c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e7c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e7d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e7d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e227`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e833`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e833`

## string_xrefs

- `0x18004e2a2`: `CDlpManager::CreateTask`
- `0x18004e4aa`: `CDlpManager::CreateTask`
- `0x18004e611`: `CDlpManager::CreateTask`
- `0x18004e792`: `CreateTask: Error serializing state!  [0x%x]`
- `0x18004e53a`: `CreateTask: Name = [%s], WorkingPath = [%s%s], TransportId = [%s], Flags = [0x%X]`

## pseudocode

```c
__int64 __fastcall CDlpManager::CreateTask(
        struct _RTL_CRITICAL_SECTION *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        OLECHAR *a4,
        unsigned int a5,
        struct IDlpTask **a6)
{
  enum WINDLP_STATE *v10; // rdx
  struct CDlpTask *v11; // r14
  __int64 v12; // r13
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  BSTR v23; // rdi
  __int64 v24; // rax
  int *v25; // rcx
  int *v26; // r9
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // eax
  struct CDlpTask *v30; // rcx
  struct CDlpTask *v31; // rax
  __int64 v32; // rax
  HANDLE ProcessHeap; // rax
  __int64 v35; // [rsp+20h] [rbp-99h]
  __int64 v36; // [rsp+28h] [rbp-91h]
  struct CDlpTask *v37; // [rsp+40h] [rbp-79h] BYREF
  __int64 v38; // [rsp+48h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-69h] BYREF
  struct CDlpTask *v40; // [rsp+58h] [rbp-61h] BYREF
  __int64 v41; // [rsp+60h] [rbp-59h] BYREF
  __int128 v42; // [rsp+70h] [rbp-49h] BYREF
  struct IDlpTask **v43; // [rsp+80h] [rbp-39h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp-31h]
  void **v45; // [rsp+90h] [rbp-29h]
  ULONG_PTR *p_SpinCount; // [rsp+98h] [rbp-21h]
  __int64 v47; // [rsp+A0h] [rbp-19h]
  __int64 v48; // [rsp+A8h] [rbp-11h]
  __int64 v49; // [rsp+B0h] [rbp-9h]

  *(_QWORD *)&v42 = a2;
  v43 = a6;
  v48 = 0;
  p_SpinCount = &this[4].SpinCount;
  v45 = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  lpCriticalSection = this + 5;
  EnterCriticalSection(this + 5);
  v47 = 1;
  v11 = 0;
  v37 = 0;
  v40 = 0;
  v41 = 0;
  v12 = 0;
  v38 = 0;
  bstrString = 0;
  v49 = 0;
  if ( !a6 )
  {
    v13 = -2147024809;
    if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
      goto LABEL_70;
    v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
    v15 = 0;
    if ( !v14 )
      goto LABEL_7;
    LODWORD(v36) = -2147024809;
    LODWORD(v35) = 612;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v13 = CDlpManager::CheckInitialized((CDlpManager *)this, v10);
    if ( v13 >= 0 )
    {
      if ( !a3 || *a3 )
      {
        if ( a4
          || (v13 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, BSTR *))this->DebugInfo[5].ProcessLocksList.Blink)(
                      this,
                      &bstrString),
              v13 >= 0) )
        {
          v17 = CDlpHelpersT<CEmptyType>::GuidToSString(a2, 0, &v38);
          v13 = v17;
          if ( v17 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
          v18 = this + 2;
          v19 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
          if ( v13 < 0 )
          {
            if ( v19 )
            {
              v20 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
              v21 = 0;
              if ( v20 )
              {
                v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
                        v20,
                        4,
                        L"%s(%d): Result = 0x%X",
                        L"CDlpManager::CreateTask",
                        629,
                        v13);
                v21 = (unsigned int)v22;
                if ( v22 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v22);
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v21);
            }
            v12 = v38;
            goto LABEL_70;
          }
          v12 = v38;
          if ( v19 )
          {
            v23 = a4;
            if ( !a4 )
              v23 = bstrString;
            v24 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
            v25 = &dword_180084C74;
            if ( !a4 )
              v25 = (int *)L"(inherited) ";
            v26 = (int *)a3;
            if ( !a3 )
              v26 = &dword_180084C74;
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v24,
              2,
              L"CreateTask: Name = [%s], WorkingPath = [%s%s], TransportId = [%s], Flags = [0x%X]",
              v26,
              v25,
              v23,
              v12,
              0);
          }
          if ( !a3
            || (*(unsigned int (__fastcall **)(struct _RTL_CRITICAL_SECTION *, unsigned __int16 *, __int64 *))&this->DebugInfo[5].Type)(
                 this,
                 a3,
                 &v41) == -2147023728 )
          {
            v13 = CDlpTask::CreateInstance((struct IDlpManagerInternal *)this, this[13].RecursionCount, &v37);
            if ( v13 < 0 )
            {
              if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2) )
              {
                v27 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
                v28 = 0;
                if ( v27 )
                {
                  LODWORD(v36) = v13;
                  LODWORD(v35) = 649;
                  v29 = CDlpLogT<CEmptyType>::DlpLogFormat(
                          v27,
                          4,
                          L"%s(%d): Result = 0x%X",
                          L"CDlpManager::CreateTask",
                          v35,
                          v36);
                  v28 = (unsigned int)v29;
                  if ( v29 < 0 )
                    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v29);
                }
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v28);
              }
              v11 = v37;
              goto LABEL_70;
            }
            v42 = *(_OWORD *)v42;
            v11 = v37;
            v13 = CDlpTask::Initialize(v37, &v42, a3, a4, 0, 1);
            if ( v13 >= 0 )
            {
              if ( v11 )
              {
                v40 = v11;
                v30 = v11;
              }
              else
              {
                v40 = 0;
                v30 = 0;
              }
              (*(void (__fastcall **)(struct CDlpTask *))(*(_QWORD *)v30 + 8LL))(v30);
              v13 = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
                      (__int64)&this[13].LockCount,
                      (__int64 *)&v40);
              if ( v13 >= 0 )
              {
                v31 = v11;
                v11 = 0;
                v37 = 0;
                *v43 = v31;
                v13 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, _QWORD))&this->DebugInfo[5].Flags)(
                        this,
                        0);
                if ( v13 < 0 )
                {
                  if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2) )
                  {
                    v32 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
                    CDlpLogT<CEmptyType>::DlpLogFormat(
                      v32,
                      4,
                      L"CreateTask: Error serializing state!  [0x%x]",
                      (unsigned int)v13);
                  }
                  v13 = 0;
                }
                goto LABEL_70;
              }
              if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2) )
                goto LABEL_70;
              v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
              v15 = 0;
              if ( !v14 )
                goto LABEL_7;
              LODWORD(v36) = v13;
              LODWORD(v35) = 663;
            }
            else
            {
              if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2) )
                goto LABEL_70;
              v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
              v15 = 0;
              if ( !v14 )
                goto LABEL_7;
              LODWORD(v36) = v13;
              LODWORD(v35) = 657;
            }
          }
          else
          {
            v13 = -2147024713;
            if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2) )
              goto LABEL_70;
            v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v18->DebugInfo->ProcessLocksList.Flink)(this + 2);
            v15 = 0;
            if ( !v14 )
              goto LABEL_7;
            LODWORD(v36) = -2147024713;
            LODWORD(v35) = 642;
          }
        }
        else
        {
          if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
            goto LABEL_70;
          v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
          v15 = 0;
          if ( !v14 )
            goto LABEL_7;
          LODWORD(v36) = v13;
          LODWORD(v35) = 626;
        }
      }
      else
      {
        v13 = -2147024809;
        if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
          goto LABEL_70;
        v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
        v15 = 0;
        if ( !v14 )
          goto LABEL_7;
        LODWORD(v36) = -2147024809;
        LODWORD(v35) = 621;
      }
    }
    else
    {
      if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
        goto LABEL_70;
      v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
      v15 = 0;
      if ( !v14 )
        goto LABEL_7;
      LODWORD(v36) = v13;
      LODWORD(v35) = 617;
    }
LABEL_5:
    v16 = CDlpLogT<CEmptyType>::DlpLogFormat(v14, 4, L"%s(%d): Result = 0x%X", L"CDlpManager::CreateTask", v35, v36);
    v15 = (unsigned int)v16;
    if ( v16 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    goto LABEL_7;
  }
  v13 = -2147024809;
  if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
  {
    v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
    v15 = 0;
    if ( v14 )
    {
      LODWORD(v36) = -2147024809;
      LODWORD(v35) = 613;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
  }
LABEL_70:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v12 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v40 )
    (*(void (__fastcall **)(struct CDlpTask *))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v11 )
    (*(void (__fastcall **)(struct CDlpTask *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( (_DWORD)v47 )
  {
    LeaveCriticalSection(lpCriticalSection);
    LODWORD(v47) = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004e1c0  push    rbp
0x18004e1c2  push    rbx
0x18004e1c3  push    rsi
0x18004e1c4  push    rdi
0x18004e1c5  push    r12
0x18004e1c7  push    r13
0x18004e1c9  push    r14
0x18004e1cb  push    r15
0x18004e1cd  lea     rbp, [rsp-0Fh]
0x18004e1d2  sub     rsp, 0C8h
0x18004e1d9  mov     r12, r9
0x18004e1dc  mov     r15, r8
0x18004e1df  mov     rbx, rdx
0x18004e1e2  mov     qword ptr [rbp+47h+var_90], rdx
0x18004e1e6  mov     rsi, rcx
0x18004e1e9  mov     rdi, [rbp+47h+arg_28]
0x18004e1ed  mov     [rbp+47h+var_80], rdi
0x18004e1f1  mov     [rbp+47h+var_58], 0
0x18004e1f9  xorps   xmm0, xmm0
0x18004e1fc  xor     eax, eax
0x18004e1fe  movups  [rbp+47h+var_70], xmm0
0x18004e202  mov     [rbp+47h+var_60], rax
0x18004e206  lea     rax, [rcx+0C0h]
0x18004e20d  mov     qword ptr [rbp+47h+var_70+8], rax
0x18004e211  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x18004e218  mov     qword ptr [rbp+47h+var_70], rcx
0x18004e21c  add     rax, 8
0x18004e220  mov     [rbp+47h+lpCriticalSection], rax
0x18004e224  mov     rcx, rax; lpCriticalSection
0x18004e227  call    cs:__imp_EnterCriticalSection
0x18004e22d  mov     dword ptr [rbp+47h+var_60], 1
0x18004e234  xor     eax, eax
0x18004e236  mov     r14d, eax
0x18004e239  mov     [rbp+47h+var_C0], rax
0x18004e23d  mov     [rbp+47h+var_A8], rax
0x18004e241  mov     [rbp+47h+var_A0], rax
0x18004e245  mov     r13d, eax
0x18004e248  mov     [rbp+47h+var_B8], rax
0x18004e24c  mov     [rbp+47h+bstrString], rax
0x18004e250  mov     [rbp+47h+var_50], rax
0x18004e254  test    rdi, rdi
0x18004e257  jnz     short loc_18004E2D2
0x18004e259  mov     ebx, 80070057h
0x18004e25e  mov     edi, ebx
0x18004e260  mov     rax, [rsi+50h]
0x18004e264  lea     rcx, [rsi+50h]
0x18004e268  mov     rax, [rax+10h]
0x18004e26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e271  xor     r15d, r15d
0x18004e274  test    rax, rax
0x18004e277  jz      loc_18004E7A6
0x18004e27d  mov     rax, [rsi+50h]
0x18004e281  lea     rcx, [rsi+50h]
0x18004e285  mov     rax, [rax+10h]
0x18004e289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e28e  mov     ecx, r15d
0x18004e291  test    rax, rax
0x18004e294  jz      short loc_18004E2C8
0x18004e296  mov     dword ptr [rsp+100h+var_D8], ebx
0x18004e29a  mov     dword ptr [rsp+100h+var_E0], 264h
0x18004e2a2  lea     r9, aCdlpmanagerCre_2; "CDlpManager::CreateTask"
0x18004e2a9  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004e2b0  mov     edx, 4
0x18004e2b5  mov     rcx, rax
0x18004e2b8  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004e2bd  test    eax, eax
0x18004e2bf  mov     ecx, eax
0x18004e2c1  jns     short loc_18004E2C8
0x18004e2c3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004e2c8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004e2cd  jmp     loc_18004E7A6
0x18004e2d2  cmp     [rbp+47h+arg_20], eax
0x18004e2d5  jz      short loc_18004E322
0x18004e2d7  mov     ebx, 80070057h
0x18004e2dc  mov     edi, ebx
0x18004e2de  mov     rax, [rsi+50h]
0x18004e2e2  lea     rcx, [rsi+50h]
0x18004e2e6  mov     rax, [rax+10h]
0x18004e2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2ef  xor     r15d, r15d
0x18004e2f2  test    rax, rax
0x18004e2f5  jz      loc_18004E7A6
0x18004e2fb  mov     rax, [rsi+50h]
0x18004e2ff  lea     rcx, [rsi+50h]
0x18004e303  mov     rax, [rax+10h]
0x18004e307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e30c  mov     ecx, r15d
0x18004e30f  test    rax, rax
0x18004e312  jz      short loc_18004E2C8
0x18004e314  mov     dword ptr [rsp+100h+var_D8], ebx
0x18004e318  mov     dword ptr [rsp+100h+var_E0], 265h
0x18004e320  jmp     short loc_18004E2A2
0x18004e322  mov     rcx, rsi; this
0x18004e325  call    ?CheckInitialized@CDlpManager@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpManager::CheckInitialized(WINDLP_STATE *)
0x18004e32a  mov     edi, eax
0x18004e32c  xor     eax, eax
0x18004e32e  test    edi, edi
0x18004e330  jns     short loc_18004E37D
0x18004e332  mov     rcx, [rsi+50h]
0x18004e336  mov     rax, [rcx+10h]
0x18004e33a  lea     rcx, [rsi+50h]
0x18004e33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e343  xor     r15d, r15d
0x18004e346  test    rax, rax
0x18004e349  jz      loc_18004E7A6
0x18004e34f  mov     rax, [rsi+50h]
0x18004e353  lea     rcx, [rsi+50h]
0x18004e357  mov     rax, [rax+10h]
0x18004e35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e360  mov     ecx, r15d
0x18004e363  test    rax, rax
0x18004e366  jz      loc_18004E2C8
0x18004e36c  mov     dword ptr [rsp+100h+var_D8], edi
0x18004e370  mov     dword ptr [rsp+100h+var_E0], 269h
0x18004e378  jmp     loc_18004E2A2
0x18004e37d  test    r15, r15
0x18004e380  jz      short loc_18004E3DA
0x18004e382  cmp     [r15], ax
0x18004e386  jnz     short loc_18004E3DA
0x18004e388  mov     ebx, 80070057h
0x18004e38d  mov     edi, ebx
0x18004e38f  mov     rax, [rsi+50h]
0x18004e393  lea     rcx, [rsi+50h]
0x18004e397  mov     rax, [rax+10h]
0x18004e39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3a0  xor     r15d, r15d
0x18004e3a3  test    rax, rax
0x18004e3a6  jz      loc_18004E7A6
0x18004e3ac  mov     rax, [rsi+50h]
0x18004e3b0  lea     rcx, [rsi+50h]
0x18004e3b4  mov     rax, [rax+10h]
0x18004e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3bd  mov     ecx, r15d
0x18004e3c0  test    rax, rax
0x18004e3c3  jz      loc_18004E2C8
0x18004e3c9  mov     dword ptr [rsp+100h+var_D8], ebx
0x18004e3cd  mov     dword ptr [rsp+100h+var_E0], 26Dh
0x18004e3d5  jmp     loc_18004E2A2
0x18004e3da  test    r12, r12
0x18004e3dd  jnz     short loc_18004E446
0x18004e3df  mov     rax, [rsi]
0x18004e3e2  lea     rdx, [rbp+47h+bstrString]
0x18004e3e6  mov     rcx, rsi
0x18004e3e9  mov     rax, [rax+108h]
0x18004e3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3f5  mov     edi, eax
0x18004e3f7  test    eax, eax
0x18004e3f9  jns     short loc_18004E446
0x18004e3fb  mov     rax, [rsi+50h]
0x18004e3ff  lea     rcx, [rsi+50h]
0x18004e403  mov     rax, [rax+10h]
0x18004e407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e40c  xor     r15d, r15d
0x18004e40f  test    rax, rax
0x18004e412  jz      loc_18004E7A6
0x18004e418  mov     rax, [rsi+50h]
0x18004e41c  lea     rcx, [rsi+50h]
0x18004e420  mov     rax, [rax+10h]
0x18004e424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e429  mov     ecx, r15d
0x18004e42c  test    rax, rax
0x18004e42f  jz      loc_18004E2C8
0x18004e435  mov     dword ptr [rsp+100h+var_D8], edi
0x18004e439  mov     dword ptr [rsp+100h+var_E0], 272h
0x18004e441  jmp     loc_18004E2A2
0x18004e446  lea     r8, [rbp+47h+var_B8]
0x18004e44a  xor     edx, edx
0x18004e44c  mov     rcx, rbx
0x18004e44f  call    ?GuidToSString@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBU_GUID@@HPEAPEAG@Z; CDlpHelpersT<CEmptyType>::GuidToSString(_GUID const *,int,ushort * *)
0x18004e454  mov     edi, eax
0x18004e456  test    eax, eax
0x18004e458  jns     short loc_18004E461
0x18004e45a  mov     ecx, eax
0x18004e45c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004e461  mov     ecx, edi
0x18004e463  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004e468  lea     rbx, [rsi+50h]
0x18004e46c  mov     rax, [rbx]
0x18004e46f  mov     rax, [rax+10h]
0x18004e473  mov     rcx, rbx
0x18004e476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e47b  test    edi, edi
0x18004e47d  jns     short loc_18004E4DD
0x18004e47f  xor     r15d, r15d
0x18004e482  test    rax, rax
0x18004e485  jz      short loc_18004E4D4
0x18004e487  mov     rax, [rbx]
0x18004e48a  mov     rcx, rbx
0x18004e48d  mov     rax, [rax+10h]
0x18004e491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e496  mov     ecx, r15d
0x18004e499  test    rax, rax
0x18004e49c  jz      short loc_18004E4CF
0x18004e49e  mov     dword ptr [rsp+100h+var_D8], edi
0x18004e4a2  mov     dword ptr [rsp+100h+var_E0], 275h
0x18004e4aa  lea     r9, aCdlpmanagerCre_2; "CDlpManager::CreateTask"
0x18004e4b1  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004e4b8  lea     edx, [r15+4]
0x18004e4bc  mov     rcx, rax
0x18004e4bf  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004e4c4  mov     ecx, eax
0x18004e4c6  test    eax, eax
0x18004e4c8  jns     short loc_18004E4CF
0x18004e4ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004e4cf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004e4d4  mov     r13, [rbp+47h+var_B8]
0x18004e4d8  jmp     loc_18004E7A6
0x18004e4dd  mov     r13, [rbp+47h+var_B8]
0x18004e4e1  test    rax, rax
0x18004e4e4  jz      short loc_18004E54E
0x18004e4e6  test    r12, r12
0x18004e4e9  mov     rdi, r12
0x18004e4ec  jnz     short loc_18004E4F2
0x18004e4ee  mov     rdi, [rbp+47h+bstrString]
0x18004e4f2  mov     rax, [rbx]
0x18004e4f5  mov     rcx, rbx
0x18004e4f8  mov     rax, [rax+10h]
0x18004e4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e501  lea     rdx, aInherited; "(inherited) "
0x18004e508  lea     r8, dword_180084C74
0x18004e50f  mov     rcx, r8
0x18004e512  test    r12, r12
0x18004e515  cmovz   rcx, rdx
0x18004e519  mov     r9, r15
0x18004e51c  test    r15, r15
0x18004e51f  cmovz   r9, r8
0x18004e523  mov     [rsp+100h+var_C8], 0
0x18004e52b  mov     [rsp+100h+var_D0], r13
0x18004e530  mov     [rsp+100h+var_D8], rdi
0x18004e535  mov     [rsp+100h+var_E0], rcx
0x18004e53a  lea     r8, aCreatetaskName; "CreateTask: Name = [%s], WorkingPath = "...
0x18004e541  mov     edx, 2
0x18004e546  mov     rcx, rax
0x18004e549  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004e54e  test    r15, r15
0x18004e551  jz      short loc_18004E5BF
0x18004e553  mov     rax, [rsi]
0x18004e556  lea     r8, [rbp+47h+var_A0]
0x18004e55a  mov     rdx, r15
0x18004e55d  mov     rcx, rsi
0x18004e560  mov     rax, [rax+0F0h]
0x18004e567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e56c  cmp     eax, 80070490h
0x18004e571  jz      short loc_18004E5BF
0x18004e573  mov     edi, 800700B7h
0x18004e578  mov     rax, [rbx]
0x18004e57b  mov     rcx, rbx
0x18004e57e  mov     rax, [rax+10h]
0x18004e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e587  xor     r15d, r15d
0x18004e58a  test    rax, rax
0x18004e58d  jz      loc_18004E7A6
0x18004e593  mov     rax, [rbx]
0x18004e596  mov     rcx, rbx
0x18004e599  mov     rax, [rax+10h]
0x18004e59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5a2  mov     ecx, r15d
0x18004e5a5  test    rax, rax
0x18004e5a8  jz      loc_18004E2C8
0x18004e5ae  mov     dword ptr [rsp+100h+var_D8], edi
0x18004e5b2  mov     dword ptr [rsp+100h+var_E0], 282h
0x18004e5ba  jmp     loc_18004E2A2
0x18004e5bf  lea     r8, [rbp+47h+var_C0]; struct CDlpTask **
0x18004e5c3  mov     edx, [rsi+214h]; unsigned int
0x18004e5c9  mov     rcx, rsi; struct IDlpManagerInternal *
0x18004e5cc  call    ?CreateInstance@CDlpTask@@SAJPEAVIDlpManagerInternal@@KPEAPEAV1@@Z; CDlpTask::CreateInstance(IDlpManagerInternal *,ulong,CDlpTask * *)
0x18004e5d1  mov     edi, eax
0x18004e5d3  test    eax, eax
0x18004e5d5  jns     short loc_18004E644
0x18004e5d7  mov     rax, [rbx]
0x18004e5da  mov     rcx, rbx
0x18004e5dd  mov     rax, [rax+10h]
0x18004e5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5e6  xor     r15d, r15d
0x18004e5e9  test    rax, rax
0x18004e5ec  jz      short loc_18004E63B
0x18004e5ee  mov     rax, [rbx]
0x18004e5f1  mov     rcx, rbx
0x18004e5f4  mov     rax, [rax+10h]
0x18004e5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5fd  mov     ecx, r15d
0x18004e600  test    rax, rax
0x18004e603  jz      short loc_18004E636
0x18004e605  mov     dword ptr [rsp+100h+var_D8], edi
0x18004e609  mov     dword ptr [rsp+100h+var_E0], 289h
0x18004e611  lea     r9, aCdlpmanagerCre_2; "CDlpManager::CreateTask"
0x18004e618  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004e61f  lea     edx, [r15+4]
0x18004e623  mov     rcx, rax
0x18004e626  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004e62b  mov     ecx, eax
0x18004e62d  test    eax, eax
0x18004e62f  jns     short loc_18004E636
0x18004e631  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004e636  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004e63b  mov     r14, [rbp+47h+var_C0]
0x18004e63f  jmp     loc_18004E7A6
0x18004e644  mov     rax, qword ptr [rbp+47h+var_90]
0x18004e648  movups  xmm0, xmmword ptr [rax]
0x18004e64b  movdqu  [rbp+47h+var_90], xmm0
  ... truncated ...
```

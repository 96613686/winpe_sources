# SchedulerManager::ThreadEntryPoint(void *)

- ea: `0x10042b6f0`
- end: `0x10042ba54`
- name: `?ThreadEntryPoint@SchedulerManager@@SAIPEAX@Z`
- size: `868`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x100405d90`
- `0x100405df0`
- `0x10042b250`
- `0x10042b620`
- `0x10042b6f0`
- `0x100435af0`
- `0x1004360f0`
- `0x10043e700`
- `0x100456850`
- `0x100473970`
- `0x100473b80`
- `0x100473dc0`
- `0x100475070`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10042b9fc`
- `KERNEL32!WaitForSingleObject` at `0x10046f64a`
- `KERNEL32!WaitForSingleObject` at `0x10042b9fc`
- `KERNEL32!WaitForSingleObject` at `0x10046f64a`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10046f6ed`
- `KERNEL32!GetThreadIOPendingFlag` at `0x10046f6ed`
- `KERNEL32!GetCurrentThreadId` at `0x10046f713`
- `KERNEL32!GetCurrentThreadId` at `0x10046f713`
- `KERNEL32!SetEvent` at `0x10042b9e7`
- `KERNEL32!SetEvent` at `0x10046f82e`
- `KERNEL32!SetEvent` at `0x10042b9e7`
- `KERNEL32!SetEvent` at `0x10046f82e`
- `KERNEL32!GetCurrentThread` at `0x10042b804`
- `KERNEL32!GetCurrentThread` at `0x10042b804`
- `KERNEL32!QueryPerformanceCounter` at `0x10046f50c`
- `KERNEL32!QueryPerformanceCounter` at `0x10046f54b`
- `KERNEL32!QueryPerformanceCounter` at `0x10046f50c`
- `KERNEL32!QueryPerformanceCounter` at `0x10046f54b`
- `KERNEL32!CloseHandle` at `0x10046f77a`
- `KERNEL32!CloseHandle` at `0x10046f77a`
- `KERNEL32!GetLastError` at `0x10042b82c`
- `KERNEL32!GetLastError` at `0x10046f787`
- `KERNEL32!GetLastError` at `0x10042b82c`
- `KERNEL32!GetLastError` at `0x10046f787`
- `ADVAPI32!OpenThreadToken` at `0x10042b81e`
- `ADVAPI32!OpenThreadToken` at `0x10042b81e`
- `ADVAPI32!ImpersonateSelf` at `0x10042b84a`
- `ADVAPI32!ImpersonateSelf` at `0x10042b84a`
- `ADVAPI32!RevertToSelf` at `0x10042b858`
- `ADVAPI32!RevertToSelf` at `0x10042b858`
- `VCRUNTIME140!_set_se_translator` at `0x10042b7dc`
- `VCRUNTIME140!_set_se_translator` at `0x10042b7dc`
- `VCRUNTIME140!set_unexpected` at `0x10042b7f6`
- `VCRUNTIME140!set_unexpected` at `0x10042b7f6`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x10042b7e9`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x10042b7e9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046f5be`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10046f5be`

## string_xrefs

- `0x10046f71b`: `OS Error :Exiting worker %u with pending IO in ThreadEntryPoint\n`
- `0x10046f75a`: `Sql\DkTemp\sos\include\worker_ext.inl`
- `0x10046f7a3`: `Sql\DkTemp\sos\include\worker_ext.inl`
- `0x10046f748`: `Impersonation token unexpectedly found on newly created thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SchedulerManager::ThreadEntryPoint(volatile signed __int32 *Parameter)
{
  __int64 v2; // rdi
  __int64 v3; // r13
  __int64 v4; // rbx
  __int64 v5; // rax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  LPVOID v8; // r8
  unsigned int v9; // r14d
  __int64 v10; // r9
  unsigned int v11; // ecx
  __int64 v12; // rbx
  struct Worker *v13; // rcx
  __int64 v14; // r15
  DWORD v15; // eax
  DWORD v16; // ebx
  int v17; // edx
  LARGE_INTEGER v18; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v20; // r14
  __int64 v21; // rdx
  LARGE_INTEGER v22; // rax
  LONGLONG v23; // rax
  int v24; // r8d
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rdx
  void (*v30)(const wchar_t *, ...); // rbx
  DWORD CurrentThreadId; // eax
  DWORD v33; // eax
  void (*v34)(const wchar_t *, ...); // rax
  __int64 v35; // [rsp+30h] [rbp-D8h]
  int v36; // [rsp+48h] [rbp-C0h]
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-B8h] BYREF
  LARGE_INTEGER v38; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A8h]
  __int64 v40; // [rsp+70h] [rbp-98h]
  void (*v41)(const wchar_t *, ...); // [rsp+78h] [rbp-90h]
  _BYTE v42[16]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v43[24]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v44[96]; // [rsp+A8h] [rbp-60h] BYREF
  WINBOOL IOIsPending; // [rsp+110h] [rbp+8h] BYREF
  unsigned int v46; // [rsp+118h] [rbp+10h] BYREF
  __int64 v47; // [rsp+120h] [rbp+18h]
  void *TokenHandle; // [rsp+128h] [rbp+20h] BYREF

  v40 = -2;
  v35 = (unsigned int)SystemThread_TlsOffset
      + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v2 = v35;
  v39 = v35;
  v3 = v35;
  v47 = v35;
  v36 = 0;
  if ( (SOS_OS_sm_osProcessStatus & 1) == 0 )
  {
    v18.QuadPart = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( qword_1007143D8
      || _InterlockedCompareExchange64((volatile signed __int64 *)&qword_1007143D8, UniqueThread_low, 0) )
    {
      v20 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
            + (unsigned int)SystemThread_TlsOffset;
        if ( v21 && *(_QWORD *)(v21 + 272) == v21 )
          v20 = *(_QWORD *)(v21 + 256);
        if ( v20 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&PerformanceCount);
            v18 = PerformanceCount;
          }
          else
          {
            v18.QuadPart = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( (qword_1007149B5 & 0x800000) == 0 )
        Spinlock<15,1,268435714>::SpinToAcquireWithExponentialBackoff((SpinlockBase *)&qword_1007143D8);
      else
        Spinlock<15,1,268435714>::SpinToAcquireOptimistic((SpinlockBase *)&qword_1007143D8);
      if ( v20 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v38);
          v22 = v38;
        }
        else
        {
          v22.QuadPart = MEMORY[0x7FFE0008];
        }
        if ( v22.QuadPart < (unsigned __int64)v18.QuadPart )
          v23 = 0;
        else
          v23 = v22.QuadPart - v18.QuadPart;
        *(_QWORD *)(v20 + 3192) += v23;
      }
    }
    v36 = 1;
  }
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
     + (unsigned int)SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  *(_DWORD *)(v5 + 616) &= ~0x200u;
  *(_DWORD *)(v35 + 264) |= 0x10u;
  if ( v36 )
  {
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v24 = rand();
      if ( v24 == 5 * (v24 / 5) )
        Spinlock<15,1,268435714>::UpdateStatSnapshot();
    }
    qword_1007143D8 = 0;
  }
  if ( SOS_OS::sm_SetThreadStackGuarantee )
  {
    v46 = 0x10000;
    SOS_OS::sm_SetThreadStackGuarantee(&v46);
  }
  _set_se_translator(SOS_SEHTranslator);
  set_terminate(ex_terminator);
  set_unexpected(ex_terminator);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    if ( TokenHandle )
    {
      utassert_fail(
        1u,
        "FALSE",
        "Sql\\DkTemp\\sos\\include\\worker_ext.inl",
        235,
        "Impersonation token unexpectedly found on newly created thread");
      CloseHandle(TokenHandle);
      goto LABEL_60;
    }
  }
  else
  {
    LastError = GetLastError();
    TokenHandle = 0;
    if ( LastError != 1008 && LastError != 1309 )
      goto LABEL_60;
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    if ( !RevertToSelf() )
    {
      v33 = GetLastError();
      utassert_fail(
        1u,
        "revertResult",
        "Sql\\DkTemp\\sos\\include\\worker_ext.inl",
        215,
        "RevertToSelf failed: %d",
        v33);
    }
    v9 = 0;
  }
  else
  {
    v9 = 0x80000000;
  }
  LODWORD(v47) = v9;
  if ( v9 )
    goto LABEL_61;
  if ( !*(_QWORD *)(v35 + 296) )
  {
    SystemThread::CreateThreadHandle((SystemThread *)v35);
    if ( !*(_QWORD *)(v35 + 296) )
    {
LABEL_60:
      v9 = 0x80000000;
LABEL_61:
      _InterlockedDecrement(Parameter + 48);
      v14 = v35;
      goto LABEL_62;
    }
  }
  v10 = *(unsigned __int16 *)(*((_QWORD *)Parameter + 35) + 160LL);
  v11 = 0;
  if ( (_DWORD)SOS_PublicGlobals::sm_cpuCount )
  {
    while ( 1 )
    {
      v8 = SOS_PublicGlobals::sm_CPUInfo;
      if ( *((_WORD *)SOS_PublicGlobals::sm_CPUInfo + 16 * v11) == (_WORD)v10 )
        break;
      if ( ++v11 >= (unsigned int)SOS_PublicGlobals::sm_cpuCount )
        goto LABEL_18;
    }
    *(_DWORD *)(v35 + 216) = *((_DWORD *)SOS_PublicGlobals::sm_CPUInfo + 8 * v11 + 1);
  }
LABEL_18:
  TList<SOS_Node,SystemThread,184,TListSLock>::AppendElem(*((_QWORD *)Parameter + 35) + 64LL, v35, v8, v10);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v44, 0, 0, 0, (int (*)(int, int, int, int, char *))ReportAndBackoutHandler, 0);
    SystemThreadDispatcher::ProcessWorker((SystemThreadDispatcher *)(Parameter + 48), (struct SystemThread *)v35);
    ExcHandler::~ExcHandler((ExcHandler *)v44);
  }
  catch ( SQLError v43 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v42, (const struct SQLError *)v43);
      v34 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v34 = SOS_OS_LogUnlocalizedRoutine;
      v41 = v34;
      v34(L"OS Error :Terminating system thread due to exception in ProcessWorker\n");
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v42);
    }
    catch ( ShortStackException )
    {
    }
    v2 = v39;
    v9 = v47;
    v3 = v39;
  }
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  v13 = *(struct Worker **)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(struct Worker **)(v12 + 256);
  }
  if ( *((_DWORD *)v13 + 139) )
    ExceptionPostCatchActions(v13);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 208), 0xFFFFFFFF) != 1 )
    goto LABEL_83;
  if ( !*(_QWORD *)(v3 + 192) )
  {
    *(_QWORD *)(v35 + 248) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                           + (unsigned int)SystemThread_TlsOffset;
    SetEvent(*(HANDLE *)(v35 + 320));
LABEL_83:
    v14 = v35;
    goto LABEL_26;
  }
  v14 = v35;
  TList<SOS_Node,SystemThread,184,TListSLock>::RemoveElem(*(_QWORD *)(v3 + 200) + 64LL, v35);
  *(_QWORD *)(v35 + 248) = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                         + (unsigned int)SystemThread_TlsOffset;
  SetEvent(*(HANDLE *)(v35 + 320));
  do
  {
LABEL_26:
    v15 = WaitForSingleObject(*(HANDLE *)(v2 + 320), 0xFFFFFFFF);
    v16 = v15;
    if ( *(_QWORD *)(v2 + 248) || (v17 = 1, v15 == 192) )
      v17 = 0;
    SystemThread::LogSpuriousEvent((SystemThread *)v2, v17, v15);
  }
  while ( !*(_QWORD *)(v2 + 248) && !v16 );
LABEL_62:
  v25 = *(_QWORD *)(v2 + 256);
  if ( !*(_QWORD *)(v25 + 608) )
  {
    if ( (SOS_OS_sm_osProcessStatus & 1) == 0 )
    {
      WaitForSingleObject(SOS_OS_BootEvent, 0xFFFFFFFF);
      v25 = *(_QWORD *)(v14 + 256);
    }
    if ( !*(_QWORD *)(v25 + 608) )
    {
      v26 = qword_100714178;
      if ( qword_100714178 )
      {
        if ( (*(_BYTE *)(qword_100714178 + 1568) & 0x10) == 0 )
        {
          v27 = *(_QWORD *)(qword_100714178 + 184);
          if ( v27 )
          {
            v28 = *(_QWORD *)(v27 + 3696);
            *(_DWORD *)(v2 + 216) = *(_DWORD *)(v27 + 3536);
            *(_QWORD *)(v25 + 992) = v26;
            *(_QWORD *)(v25 + 608) = v27;
            *(_QWORD *)(v25 + 1000) = v28;
            *(_DWORD *)(v25 + 76) = *(_DWORD *)(v27 + 3536);
            v29 = *(_QWORD *)(v25 + 600);
            *(_QWORD *)(v29 + 160) = v27;
            *(_QWORD *)(v29 + 168) = *(_QWORD *)(v27 + 5192);
          }
        }
      }
    }
  }
  if ( !v9 )
  {
    IOIsPending = 0;
    if ( GetThreadIOPendingFlag(*(HANDLE *)(v2 + 296), &IOIsPending) )
    {
      if ( IOIsPending )
      {
        v30 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
        if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
          v30 = SOS_OS_LogUnlocalizedRoutine;
        CurrentThreadId = GetCurrentThreadId();
        v30(L"OS Error :Exiting worker %u with pending IO in ThreadEntryPoint\n", CurrentThreadId);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10042b6f0  push    rbx
0x10042b6f2  push    rsi
0x10042b6f3  push    rdi
0x10042b6f4  push    r12
0x10042b6f6  push    r13
0x10042b6f8  push    r14
0x10042b6fa  push    r15
0x10042b6fc  sub     rsp, 0D0h
0x10042b703  mov     [rsp+108h+var_98], 0FFFFFFFFFFFFFFFEh
0x10042b70c  mov     r12, rcx
0x10042b70f  mov     r8, gs:58h
0x10042b718  mov     eax, cs:_tls_index
0x10042b71e  mov     edx, cs:SystemThread_TlsOffset
0x10042b724  mov     rax, [r8+rax*8]
0x10042b728  add     rax, rdx
0x10042b72b  mov     [rsp+108h+var_D8], rax
0x10042b730  mov     [rsp+108h+var_D0], rax
0x10042b735  mov     rdi, rax
0x10042b738  mov     [rsp+108h+var_A8], rax
0x10042b73d  mov     r13, rax
0x10042b740  mov     [rsp+108h+arg_10], rax
0x10042b748  mov     rax, [rsp+108h+arg_10]
0x10042b750  lea     rcx, qword_1007143D8
0x10042b757  mov     [rsp+108h+var_C8], rcx
0x10042b75c  xor     esi, esi
0x10042b75e  mov     [rsp+108h+var_C0], esi
0x10042b762  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x10042b769  jz      loc_10046F48E
0x10042b76f  mov     rcx, gs:58h
0x10042b778  mov     eax, cs:_tls_index
0x10042b77e  mov     ebx, cs:SystemThread_TlsOffset
0x10042b784  add     rbx, [rcx+rax*8]
0x10042b788  mov     rax, [rbx+100h]
0x10042b78f  test    rax, rax
0x10042b792  jz      loc_10046F5A1
0x10042b798  and     dword ptr [rax+268h], 0FFFFFDFFh
0x10042b7a2  or      dword ptr [rdi+108h], 10h
0x10042b7a9  cmp     [rsp+108h+var_C0], 0
0x10042b7ae  jnz     loc_10046F5B5
0x10042b7b4  mov     rax, cs:?sm_SetThreadStackGuarantee@SOS_OS@@0P6AHPEAK@ZEA; int (*SOS_OS::sm_SetThreadStackGuarantee)(ulong *)
0x10042b7bb  test    rax, rax
0x10042b7be  jz      short loc_10042B7D5
0x10042b7c0  mov     [rsp+108h+arg_8], 10000h
0x10042b7cb  lea     rcx, [rsp+108h+arg_8]
0x10042b7d3  call    rax ; int (*SOS_OS::sm_SetThreadStackGuarantee)(ulong *)
0x10042b7d5  lea     rcx, ?SOS_SEHTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SOS_SEHTranslator(uint,_EXCEPTION_POINTERS *)
0x10042b7dc  call    cs:__imp__set_se_translator
0x10042b7e2  lea     rcx, ?ex_terminator@@YAXXZ; ex_terminator(void)
0x10042b7e9  call    cs:__imp_set_terminate
0x10042b7ef  lea     rcx, ?ex_terminator@@YAXXZ; ex_terminator(void)
0x10042b7f6  call    cs:__imp_set_unexpected
0x10042b7fc  mov     [rsp+108h+TokenHandle], rsi
0x10042b804  call    cs:__imp_GetCurrentThread
0x10042b80a  mov     rcx, rax; ThreadHandle
0x10042b80d  lea     r9, [rsp+108h+TokenHandle]; TokenHandle
0x10042b815  mov     edx, 0Ch; DesiredAccess
0x10042b81a  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x10042b81e  call    cs:__imp_OpenThreadToken
0x10042b824  test    eax, eax
0x10042b826  jnz     loc_10046F739
0x10042b82c  call    cs:__imp_GetLastError
0x10042b832  mov     [rsp+108h+TokenHandle], rsi
0x10042b83a  cmp     eax, 3F0h
0x10042b83f  jnz     loc_10046F5FB
0x10042b845  mov     ecx, 2; ImpersonationLevel
0x10042b84a  call    cs:__imp_ImpersonateSelf
0x10042b850  test    eax, eax
0x10042b852  jz      loc_10046F7C2
0x10042b858  call    cs:__imp_RevertToSelf
0x10042b85e  test    eax, eax
0x10042b860  jz      loc_10046F787
0x10042b866  mov     r14d, esi
0x10042b869  jmp     short loc_10042B86C
0x10042b86c  mov     dword ptr [rsp+108h+arg_10], r14d
0x10042b874  test    r14d, r14d
0x10042b877  jnz     loc_10046F60F
0x10042b87d  cmp     qword ptr [rdi+128h], 0
0x10042b885  jz      loc_10046F7CE
0x10042b88b  mov     rax, [r12+118h]
0x10042b893  movzx   r9d, word ptr [rax+0A0h]
0x10042b89b  mov     ecx, esi
0x10042b89d  mov     eax, cs:?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10042b8a3  test    eax, eax
0x10042b8a5  jz      short loc_10042B8D9
0x10042b8a7  nop
0x10042b8a8  nop     dword ptr [rax+rax+00000000h]
0x10042b8b0  mov     edx, ecx
0x10042b8b2  mov     eax, ecx
0x10042b8b4  shl     rax, 5
0x10042b8b8  mov     r8, cs:?sm_CPUInfo@SOS_PublicGlobals@@2PEAVSOS_CPUInfo@@EA; SOS_CPUInfo * SOS_PublicGlobals::sm_CPUInfo
0x10042b8bf  cmp     [rax+r8], r9w
0x10042b8c4  jz      loc_10042BA3F
0x10042b8ca  inc     ecx
0x10042b8cc  mov     eax, cs:?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10042b8d2  cmp     ecx, eax
0x10042b8d4  jb      short loc_10042B8B0
0x10042b8d6  jmp     short loc_10042B8D9
0x10042b8d9  mov     rcx, [r12+118h]
0x10042b8e1  add     rcx, 40h ; '@'
0x10042b8e5  mov     rdx, rdi
0x10042b8e8  call    ?AppendElem@?$TList@VSOS_Node@@VSystemThread@@$0LI@UTListSLock@@@@QEAAXPEAVSystemThread@@@Z; TList<SOS_Node,SystemThread,184,TListSLock>::AppendElem(SystemThread *)
0x10042b8ed  nop
0x10042b8ee  xor     edx, edx; unsigned __int16
0x10042b8f0  mov     [rsp+108h+var_E0], rsi; struct Worker *
0x10042b8f5  lea     rax, ?ReportAndBackoutHandler@@YAHHHHHPEAD@Z; ReportAndBackoutHandler(int,int,int,int,char *)
0x10042b8fc  mov     [rsp+108h+var_E8], rax; int (*)(int, int, int, int, char *)
0x10042b901  xor     r9d, r9d; unsigned __int8
0x10042b904  xor     r8d, r8d; unsigned __int8
0x10042b907  lea     rcx, [rsp+108h+var_60]; this
0x10042b90f  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10042b914  nop
0x10042b915  lea     rcx, [r12+0C0h]; this
0x10042b91d  mov     rdx, rdi; struct SystemThread *
0x10042b920  call    ?ProcessWorker@SystemThreadDispatcher@@QEAAXPEAVSystemThread@@@Z; SystemThreadDispatcher::ProcessWorker(SystemThread *)
0x10042b925  nop
0x10042b926  nop     word ptr [rax+rax+00000000h]
0x10042b930  lea     rcx, [rsp+108h+var_60]; this
0x10042b938  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10042b93d  nop
0x10042b93e  jmp     short loc_10042B941
0x10042b941  mov     rcx, gs:58h
0x10042b94a  mov     eax, cs:_tls_index
0x10042b950  mov     ebx, cs:SystemThread_TlsOffset
0x10042b956  add     rbx, [rcx+rax*8]
0x10042b95a  mov     rcx, [rbx+100h]; void *
0x10042b961  test    rcx, rcx
0x10042b964  jnz     short loc_10042B972
0x10042b966  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042b96b  mov     rcx, [rbx+100h]; struct Worker *
0x10042b972  cmp     dword ptr [rcx+22Ch], 0
0x10042b979  jz      short loc_10042B980
0x10042b97b  call    ?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10042b980  mov     eax, 0FFFFFFFFh
0x10042b985  lock xadd [r13+0D0h], eax
0x10042b98e  cmp     eax, 1
0x10042b991  jnz     loc_10046F834
0x10042b997  cmp     qword ptr [r13+0C0h], 0
0x10042b99f  jz      loc_10046F802
0x10042b9a5  mov     rcx, [r13+0C8h]
0x10042b9ac  add     rcx, 40h ; '@'
0x10042b9b0  mov     r15, [rsp+108h+var_D8]
0x10042b9b5  mov     rdx, r15
0x10042b9b8  call    ?RemoveElem@?$TList@VSOS_Node@@VSystemThread@@$0LI@UTListSLock@@@@QEAAXPEAVSystemThread@@@Z; TList<SOS_Node,SystemThread,184,TListSLock>::RemoveElem(SystemThread *)
0x10042b9bd  mov     rdx, gs:58h
0x10042b9c6  mov     eax, cs:_tls_index
0x10042b9cc  mov     ecx, cs:SystemThread_TlsOffset
0x10042b9d2  add     rcx, [rdx+rax*8]
0x10042b9d6  mov     rax, r15
0x10042b9d9  mov     [rax+0F8h], rcx
0x10042b9e0  mov     rcx, [rax+140h]; hEvent
0x10042b9e7  call    cs:__imp_SetEvent
0x10042b9ed  jmp     short loc_10042B9F0
0x10042b9f0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x10042b9f5  mov     rcx, [rdi+140h]; hHandle
0x10042b9fc  call    cs:__imp_WaitForSingleObject
0x10042ba02  mov     ebx, eax
0x10042ba04  cmp     qword ptr [rdi+0F8h], 0
0x10042ba0c  jnz     short loc_10042BA1A
0x10042ba0e  cmp     eax, 0C0h
0x10042ba13  mov     edx, 1
0x10042ba18  jnz     short loc_10042BA1C
0x10042ba1a  mov     edx, esi; int
0x10042ba1c  mov     r8d, ebx; unsigned int
0x10042ba1f  mov     rcx, rdi; this
0x10042ba22  call    ?LogSpuriousEvent@SystemThread@@AEAAXHK@Z; SystemThread::LogSpuriousEvent(int,ulong)
0x10042ba27  cmp     qword ptr [rdi+0F8h], 0
0x10042ba2f  jnz     loc_10046F61D
0x10042ba35  test    ebx, ebx
0x10042ba37  jz      short loc_10042B9F0
0x10042ba39  jmp     loc_10046F61D
0x10042ba3f  shl     rdx, 5
0x10042ba43  mov     eax, [rdx+r8+4]
0x10042ba48  mov     [rdi+0D8h], eax
0x10042ba4e  jmp     loc_10042B8D9
0x10046f48e  mov     ebx, esi
0x10046f490  mov     eax, gs:48h
0x10046f498  mov     r15d, eax
0x10046f49b  mov     eax, dword ptr cs:qword_1007143D8
0x10046f4a1  test    eax, eax
0x10046f4a3  jnz     short loc_10046F4BD
0x10046f4a5  xor     eax, eax
0x10046f4a7  lock cmpxchg cs:qword_1007143D8, r15
0x10046f4b0  mov     eax, esi
0x10046f4b2  setz    al
0x10046f4b5  test    eax, eax
0x10046f4b7  jnz     loc_10046F56B
0x10046f4bd  mov     eax, cs:?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10046f4c3  and     eax, 84h
0x10046f4c8  mov     r14, rsi
0x10046f4cb  cmp     al, 84h
0x10046f4cd  jnz     short loc_10046F521
0x10046f4cf  mov     rcx, gs:58h
0x10046f4d8  mov     eax, cs:_tls_index
0x10046f4de  mov     edx, cs:SystemThread_TlsOffset
0x10046f4e4  add     rdx, [rcx+rax*8]
0x10046f4e8  jz      short loc_10046F4FA
0x10046f4ea  cmp     [rdx+110h], rdx
0x10046f4f1  jnz     short loc_10046F4FA
0x10046f4f3  mov     r14, [rdx+100h]
0x10046f4fa  test    r14, r14
0x10046f4fd  jz      short loc_10046F51A
0x10046f4ff  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ebx; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046f505  jz      short loc_10046F579
0x10046f507  lea     rcx, [rsp+108h+PerformanceCount]; lpPerformanceCount
0x10046f50c  call    cs:__imp_QueryPerformanceCounter
0x10046f512  mov     rbx, qword ptr [rsp+108h+PerformanceCount]
0x10046f517  jmp     short loc_10046F51A
0x10046f51a  lea     rcx, qword_1007143D8; this
0x10046f521  test    byte ptr cs:qword_1007149B5+2, 80h
0x10046f528  jz      short loc_10046F584
0x10046f52a  mov     r8, r15
0x10046f52d  mov     rdx, r14
0x10046f530  call    ?SpinToAcquireOptimistic@?$Spinlock@$0P@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<15,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x10046f535  jmp     short loc_10046F538
0x10046f538  test    r14, r14
0x10046f53b  jz      short loc_10046F56B
0x10046f53d  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10046f544  jz      short loc_10046F590
0x10046f546  lea     rcx, [rsp+108h+var_B0]; lpPerformanceCount
0x10046f54b  call    cs:__imp_QueryPerformanceCounter
0x10046f551  mov     rax, qword ptr [rsp+108h+var_B0]
0x10046f556  jmp     short loc_10046F559
0x10046f559  cmp     rax, rbx
0x10046f55c  jb      short loc_10046F59B
0x10046f55e  sub     rax, rbx
0x10046f561  jmp     short loc_10046F564
0x10046f564  add     [r14+0C78h], rax
0x10046f56b  mov     [rsp+108h+var_C0], 1
0x10046f573  jmp     loc_10042B76F
0x10046f579  mov     rbx, ds:7FFE0008h
0x10046f581  jmp     short loc_10046F51A
0x10046f584  mov     rdx, r15
0x10046f587  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0P@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<15,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10046f58c  nop
0x10046f58d  jmp     short loc_10046F538
0x10046f590  mov     rax, ds:7FFE0008h
0x10046f598  jmp     short loc_10046F559
0x10046f59b  mov     rax, rsi
0x10046f59e  jmp     short loc_10046F564
0x10046f5a1  xor     ecx, ecx; void *
0x10046f5a3  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10046f5a8  mov     rax, [rbx+100h]
0x10046f5af  jmp     loc_10042B798
0x10046f5b5  cmp     cs:?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA, 0; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x10046f5bc  jz      short loc_10046F5E5
0x10046f5be  call    cs:__imp_rand
0x10046f5c4  mov     r8d, eax
0x10046f5c7  mov     eax, 66666667h
0x10046f5cc  imul    r8d
0x10046f5cf  sar     edx, 1
0x10046f5d1  mov     ecx, edx
0x10046f5d3  shr     ecx, 1Fh
0x10046f5d6  add     edx, ecx
0x10046f5d8  lea     ecx, [rdx+rdx*4]
0x10046f5db  cmp     r8d, ecx
0x10046f5de  jnz     short loc_10046F5E5
0x10046f5e0  call    ?UpdateStatSnapshot@?$Spinlock@$0P@$00$0BAAAABAC@@@AEAAXXZ; Spinlock<15,1,268435714>::UpdateStatSnapshot(void)
0x10046f5e5  mov     cs:qword_1007143D8, rsi
0x10046f5ec  mov     [rsp+108h+var_C8], rsi
0x10046f5f1  mov     [rsp+108h+var_C0], esi
0x10046f5f5  jmp     loc_10042B7B4
0x10046f5fb  cmp     eax, 51Dh
0x10046f600  jz      loc_10042B845
0x10046f606  jmp     short loc_10046F609
0x10046f609  mov     r14d, 80000000h
0x10046f60f  lock dec dword ptr [r12+0C0h]
0x10046f618  mov     r15, [rsp+108h+var_D8]
0x10046f61d  mov     rcx, [rdi+100h]
0x10046f624  cmp     qword ptr [rcx+260h], 0
0x10046f62c  jnz     loc_10046F6D2
0x10046f632  mov     eax, cs:?SOS_OS_sm_osProcessStatus@@3KA; ulong SOS_OS_sm_osProcessStatus
0x10046f638  not     eax
0x10046f63a  test    al, 1
0x10046f63c  jz      short loc_10046F657
0x10046f63e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x10046f643  mov     rcx, cs:?SOS_OS_BootEvent@@3PEAXEA; hHandle
0x10046f64a  call    cs:__imp_WaitForSingleObject
0x10046f650  mov     rcx, [r15+100h]
0x10046f657  cmp     qword ptr [rcx+260h], 0
0x10046f65f  jnz     short loc_10046F6D2
0x10046f661  mov     r9, cs:qword_100714178
0x10046f668  test    r9, r9
0x10046f66b  jz      short loc_10046F6D2
0x10046f66d  test    byte ptr [r9+620h], 10h
0x10046f675  jnz     short loc_10046F6D2
0x10046f677  mov     r8, [r9+0B8h]
0x10046f67e  test    r8, r8
0x10046f681  jz      short loc_10046F6D2
0x10046f683  mov     rdx, [r8+0E70h]
0x10046f68a  mov     eax, [r8+0DD0h]
0x10046f691  mov     [rdi+0D8h], eax
0x10046f697  mov     [rcx+3E0h], r9
0x10046f69e  mov     [rcx+260h], r8
0x10046f6a5  mov     [rcx+3E8h], rdx
0x10046f6ac  mov     eax, [r8+0DD0h]
0x10046f6b3  mov     [rcx+4Ch], eax
0x10046f6b6  mov     rdx, [rcx+258h]
0x10046f6bd  mov     [rdx+0A0h], r8
0x10046f6c4  mov     rax, [r8+1448h]
0x10046f6cb  mov     [rdx+0A8h], rax
  ... truncated ...
```

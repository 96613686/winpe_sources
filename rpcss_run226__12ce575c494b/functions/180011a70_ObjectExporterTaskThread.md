# ObjectExporterTaskThread

- ea: `0x180011a70`
- end: `0x180011ebc`
- name: `ObjectExporterTaskThread`
- size: `1100`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180011a70`
- `0x180011ec4`
- `0x180011f78`
- `0x180012038`
- `0x18001219c`
- `0x1800121ec`
- `0x180017a2c`
- `0x180034368`
- `0x180053cf4`
- `0x18005ba08`
- `0x18005c11c`
- `0x1800a1570`
- `0x1800a1e98`
- `0x1800a228c`
- `0x1800a2c08`
- `0x1800b2bb0`
- `0x1800c039c`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011af0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011af0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011b28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011b14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011b56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011b56`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180011c3e`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180011c3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011de4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011de4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011ac4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011ac4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c07`

## string_xrefs

- `0x180011d56`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180011d97`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180011e1a`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180011eab`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180011d37`: `New task thread`
- `0x180011d4f`: `ObjectExporterTaskThread`
- `0x180011d90`: `ObjectExporterTaskThread`
- `0x180011e13`: `ObjectExporterTaskThread`
- `0x180011ea4`: `ObjectExporterTaskThread`
- `0x180011dfb`: `Task thread, new iteration`
- `0x180011d78`: `Task thread exiting`
- `0x180011e88`: `Task thread waiting until %#x`

## pseudocode

```c
__int64 __fastcall ObjectExporterTaskThread(PVOID Parameter)
{
  struct CTaskThreadState *v1; // rax
  CTaskThreadStateList *v2; // rcx
  struct CTaskThreadState *v3; // r15
  DWORD v4; // ebx
  unsigned int v5; // r14d
  char v6; // r13
  DWORD TickCount; // eax
  CPList *v8; // r14
  DWORD v9; // esi
  struct _RTL_CRITICAL_SECTION *v10; // r12
  DWORD v11; // edi
  int v12; // ebp
  CPList *v13; // r14
  struct _RTL_CRITICAL_SECTION *v14; // r12
  char v15; // r14
  unsigned __int16 v16; // dx
  DWORD v17; // edi
  unsigned __int16 v18; // ax
  void *v19; // rsi
  struct _TP_TIMER *v20; // rbp
  DWORD v21; // edi
  CTime *v22; // rcx
  unsigned __int16 CurrentThreadId; // ax
  CTaskThreadStateList *v24; // rcx
  CClientSet *v26; // r14
  struct CListElement *v27; // rax
  __int64 v28; // [rsp+28h] [rbp-50h]
  _BYTE v29[72]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v30; // [rsp+88h] [rbp+10h]
  DWORD v31; // [rsp+90h] [rbp+18h] BYREF
  PSRWLOCK SRWLock; // [rsp+98h] [rbp+20h] BYREF

  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    ComTraceMessageT<>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
      (unsigned int)"ObjectExporterTaskThread",
      826,
      3,
      (__int64)L"New task thread");
  v1 = InitializeTaskThreadState();
  v3 = v1;
  if ( v1 )
  {
    v4 = 0;
    CTaskThreadStateList::Insert(v2, v1);
    v5 = 0;
    v6 = 1;
    v30 = 0;
    while ( 1 )
    {
      if ( v6 )
      {
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          ComTraceMessageT<>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
            (unsigned int)"ObjectExporterTaskThread",
            860,
            3,
            (__int64)L"Task thread, new iteration");
        CurrentThreadId = GetCurrentThreadId();
        RpcssTestLog::Log((RpcssTestLog *)0x3EB, CurrentThreadId, v5);
        v6 = 0;
      }
      TickCount = GetTickCount();
      v8 = gpClientSetRemotePList;
      v9 = TickCount;
      v31 = TickCount;
      v10 = (struct _RTL_CRITICAL_SECTION *)((char *)gpClientSetRemotePList + 16);
      v11 = TickCount + 1000 * g_usBasePingInterval;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)gpClientSetRemotePList + 16));
      if ( *(_QWORD *)v8 )
      {
        v4 = *(_DWORD *)(*(_QWORD *)v8 + 24LL);
        LeaveCriticalSection(v10);
        if ( (int)(v9 - v4) >= 0 )
        {
          v12 = 2;
          v26 = 0;
          Microsoft::WRL::Wrappers::SRWLock::LockShared(v29, &gpClientLock);
          v27 = CPList::MaybeRemoveMin(gpClientSetRemotePList, (const struct CTime *)&v31);
          if ( v27 )
          {
            v26 = (struct CListElement *)((char *)v27 - 96);
            (*(void (__fastcall **)(__int64))(*((_QWORD *)v27 - 12) + 8LL))((__int64)v27 - 96);
          }
          Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v29);
          if ( v26 )
          {
            CClientSet::PingServer(v26);
            Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpClientLock);
            (*(void (__fastcall **)(CClientSet *))(*(_QWORD *)v26 + 16LL))(v26);
            if ( SRWLock )
            {
              ReleaseSRWLockExclusive(SRWLock);
              SRWLock = 0;
            }
          }
        }
        else
        {
          v12 = 1;
          v11 = v4;
        }
      }
      else
      {
        v12 = 0;
        LeaveCriticalSection(v10);
      }
      AcquireSRWLockShared(&gpServerLock);
      v13 = gpServerOidPList;
      v14 = (struct _RTL_CRITICAL_SECTION *)((char *)gpServerOidPList + 16);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)gpServerOidPList + 16));
      if ( *(_QWORD *)v13 )
      {
        v4 = *(_DWORD *)(*(_QWORD *)v13 + 24LL);
        LeaveCriticalSection(v14);
        v15 = 1;
      }
      else
      {
        LeaveCriticalSection(v14);
        v15 = 0;
      }
      ReleaseSRWLockShared(&gpServerLock);
      if ( v15 )
      {
        if ( !v12 )
          v12 = 1;
        if ( (int)(v9 - v4) < 0 )
        {
          if ( (int)(v4 - v11) < 0 )
            v11 = v4;
        }
        else if ( (unsigned int)RundownOidsHelper(&v31, 0, 0) )
        {
          v12 = 2;
        }
        else if ( v12 != 2 )
        {
          v12 = 1;
        }
      }
      if ( !v12 )
        break;
      v5 = v30;
      if ( v12 == 1 )
      {
        if ( (int)CInterlockedInteger::operator long(&dword_18014F0F0) > 2 )
          break;
        v5 = v30 + 1;
        v17 = v11 + 1000;
        v6 = 1;
        ++v30;
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          LODWORD(v28) = v17;
          ComTraceMessageT<int>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
            (unsigned int)"ObjectExporterTaskThread",
            986,
            3,
            (__int64)L"Task thread waiting until %#x",
            v28);
        }
        v18 = GetCurrentThreadId();
        RpcssTestLog::Log((RpcssTestLog *)0x3EE, v18, v17);
        v19 = (void *)*((_QWORD *)v3 + 4);
        v20 = (struct _TP_TIMER *)*((_QWORD *)v3 + 3);
        v21 = v17 - GetTickCount();
        v22 = (CTime *)(2000 * (unsigned int)g_usBaseTimeoutInterval);
        if ( v21 <= (unsigned int)v22 && CTime::Wait(v22, v21, v20, v19) == -1 )
          SleepEx(v21, 0);
      }
    }
    if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      ComTraceMessageT<>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
        (unsigned int)"ObjectExporterTaskThread",
        958,
        3,
        (__int64)L"Task thread exiting");
    RpcssTestLog::Log((RpcssTestLog *)0x3EC, v16);
    CTaskThreadStateList::Remove(v24, v3);
    CTaskThreadState::~CTaskThreadState(v3);
    operator delete(v3, 0x28u);
  }
  _InterlockedDecrement(&dword_18014F0F0);
  return 0;
}

```

## disassembly

```asm
0x180011a70  mov     [rsp+arg_0], rbx
0x180011a75  push    rbp
0x180011a76  push    rsi
0x180011a77  push    rdi
0x180011a78  push    r12
0x180011a7a  push    r13
0x180011a7c  push    r14
0x180011a7e  push    r15
0x180011a80  sub     rsp, 40h
0x180011a84  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180011a8b  jnz     loc_180011D26
0x180011a91  call    ?InitializeTaskThreadState@@YAPEAVCTaskThreadState@@XZ; InitializeTaskThreadState(void)
0x180011a96  mov     r15, rax
0x180011a99  test    rax, rax
0x180011a9c  jz      loc_180011CE8
0x180011aa2  mov     rdx, rax; struct CTaskThreadState *
0x180011aa5  xor     ebx, ebx
0x180011aa7  call    ?Insert@CTaskThreadStateList@@QEAAXPEAVCTaskThreadState@@@Z; CTaskThreadStateList::Insert(CTaskThreadState *)
0x180011aac  xor     r14d, r14d
0x180011aaf  lea     r13d, [rbx+1]
0x180011ab3  mov     [rsp+78h+arg_8], r14d
0x180011abb  test    r13b, r13b
0x180011abe  jnz     loc_180011C58
0x180011ac4  call    cs:__imp_GetTickCount
0x180011aca  mov     r14, cs:?gpClientSetRemotePList@@3PEAVCPList@@EA; CPList * gpClientSetRemotePList
0x180011ad1  mov     esi, eax
0x180011ad3  mov     [rsp+78h+arg_10], eax
0x180011ada  movzx   eax, cs:?g_usBasePingInterval@@3GA; ushort g_usBasePingInterval
0x180011ae1  imul    edi, eax, 3E8h
0x180011ae7  lea     r12, [r14+10h]
0x180011aeb  mov     rcx, r12; lpCriticalSection
0x180011aee  add     edi, esi
0x180011af0  call    cs:__imp_EnterCriticalSection
0x180011af6  mov     rax, [r14]
0x180011af9  mov     rcx, r12; lpCriticalSection
0x180011afc  test    rax, rax
0x180011aff  jnz     loc_180011D09
0x180011b05  xor     ebp, ebp
0x180011b07  call    cs:__imp_LeaveCriticalSection
0x180011b0d  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180011b14  call    cs:__imp_AcquireSRWLockShared
0x180011b1a  mov     r14, cs:?gpServerOidPList@@3PEAVCServerOidPList@@EA; CServerOidPList * gpServerOidPList
0x180011b21  lea     r12, [r14+10h]
0x180011b25  mov     rcx, r12; lpCriticalSection
0x180011b28  call    cs:__imp_EnterCriticalSection
0x180011b2e  mov     rax, [r14]
0x180011b31  mov     rcx, r12; lpCriticalSection
0x180011b34  test    rax, rax
0x180011b37  jz      loc_180011C8F
0x180011b3d  mov     ebx, [rax+18h]
0x180011b40  call    cs:__imp_LeaveCriticalSection
0x180011b46  mov     r12d, 1
0x180011b4c  mov     r14b, r12b
0x180011b4f  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180011b56  call    cs:__imp_ReleaseSRWLockShared
0x180011b5c  test    r14b, r14b
0x180011b5f  jz      short loc_180011B8E
0x180011b61  test    ebp, ebp
0x180011b63  cmovz   ebp, r12d
0x180011b67  cmp     esi, ebx
0x180011b69  js      loc_180011C49
0x180011b6f  xor     r8d, r8d
0x180011b72  lea     rcx, [rsp+78h+arg_10]
0x180011b7a  xor     edx, edx
0x180011b7c  call    ?RundownOidsHelper@@YAHPEAVCTime@@PEAVCServerOxid@@W4WhereIssuedRundown@@@Z; RundownOidsHelper(CTime *,CServerOxid *,WhereIssuedRundown)
0x180011b81  test    eax, eax
0x180011b83  jz      loc_180011CA3
0x180011b89  mov     ebp, 2
0x180011b8e  test    ebp, ebp
0x180011b90  jz      loc_180011CB4
0x180011b96  mov     r14d, [rsp+78h+arg_8]
0x180011b9e  cmp     ebp, r12d
0x180011ba1  jnz     loc_180011ABB
0x180011ba7  lea     rcx, dword_18014F0F0
0x180011bae  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x180011bb3  cmp     eax, 2
0x180011bb6  jg      loc_180011CB4
0x180011bbc  add     r14d, r12d
0x180011bbf  add     edi, 3E8h
0x180011bc5  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180011bcc  mov     r13b, r12b
0x180011bcf  mov     [rsp+78h+arg_8], r14d
0x180011bd7  jz      short loc_180011BEA
0x180011bd9  mov     rax, cs:WPP_GLOBAL_Control
0x180011be0  test    byte ptr [rax+1Ch], 8
0x180011be4  jnz     loc_180011E88
0x180011bea  call    cs:__imp_GetCurrentThreadId
0x180011bf0  mov     ecx, 3EEh; this
0x180011bf5  mov     r8d, edi
0x180011bf8  mov     edx, eax; unsigned __int16
0x180011bfa  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x180011bff  mov     rsi, [r15+20h]
0x180011c03  mov     rbp, [r15+18h]
0x180011c07  call    cs:__imp_GetTickCount
0x180011c0d  sub     edi, eax
0x180011c0f  movzx   eax, cs:?g_usBaseTimeoutInterval@@3GA; ushort g_usBaseTimeoutInterval
0x180011c16  imul    ecx, eax, 7D0h; this
0x180011c1c  cmp     edi, ecx
0x180011c1e  ja      loc_180011ABB
0x180011c24  mov     r9, rsi; void *
0x180011c27  mov     r8, rbp; struct _TP_TIMER *
0x180011c2a  mov     edx, edi; unsigned int
0x180011c2c  call    ?Wait@CTime@@QEBAKKPEAU_TP_TIMER@@PEAX@Z; CTime::Wait(ulong,_TP_TIMER *,void *)
0x180011c31  cmp     eax, 0FFFFFFFFh
0x180011c34  jnz     loc_180011ABB
0x180011c3a  xor     edx, edx; bAlertable
0x180011c3c  mov     ecx, edi; dwMilliseconds
0x180011c3e  call    cs:__imp_SleepEx
0x180011c44  jmp     loc_180011ABB
0x180011c49  cmp     ebx, edi
0x180011c4b  jns     loc_180011B8E
0x180011c51  mov     edi, ebx
0x180011c53  jmp     loc_180011B8E
0x180011c58  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180011c5f  jz      short loc_180011C72
0x180011c61  mov     rax, cs:WPP_GLOBAL_Control
0x180011c68  test    byte ptr [rax+1Ch], 8
0x180011c6c  jnz     loc_180011DFB
0x180011c72  call    cs:__imp_GetCurrentThreadId
0x180011c78  mov     ecx, 3EBh; this
0x180011c7d  mov     r8d, r14d
0x180011c80  mov     edx, eax; unsigned __int16
0x180011c82  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x180011c87  xor     r13b, r13b
0x180011c8a  jmp     loc_180011AC4
0x180011c8f  call    cs:__imp_LeaveCriticalSection
0x180011c95  xor     r14b, r14b
0x180011c98  mov     r12d, 1
0x180011c9e  jmp     loc_180011B4F
0x180011ca3  cmp     ebp, 2
0x180011ca6  jz      loc_180011B8E
0x180011cac  mov     ebp, r12d
0x180011caf  jmp     loc_180011B8E
0x180011cb4  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180011cbb  jnz     loc_180011D67
0x180011cc1  mov     ecx, 3ECh; this
0x180011cc6  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x180011ccb  mov     rdx, r15; struct CTaskThreadState *
0x180011cce  call    ?Remove@CTaskThreadStateList@@QEAAXPEAVCTaskThreadState@@@Z; CTaskThreadStateList::Remove(CTaskThreadState *)
0x180011cd3  mov     rcx, r15; this
0x180011cd6  call    ??1CTaskThreadState@@QEAA@XZ; CTaskThreadState::~CTaskThreadState(void)
0x180011cdb  mov     edx, 28h ; '('; unsigned __int64
0x180011ce0  mov     rcx, r15; void *
0x180011ce3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011ce8  lock dec cs:dword_18014F0F0
0x180011cef  mov     rbx, [rsp+78h+arg_0]
0x180011cf7  xor     eax, eax
0x180011cf9  add     rsp, 40h
0x180011cfd  pop     r15
0x180011cff  pop     r14
0x180011d01  pop     r13
0x180011d03  pop     r12
0x180011d05  pop     rdi
0x180011d06  pop     rsi
0x180011d07  pop     rbp
0x180011d08  retn
0x180011d09  mov     ebx, [rax+18h]
0x180011d0c  call    cs:__imp_LeaveCriticalSection
0x180011d12  cmp     esi, ebx
0x180011d14  jns     loc_180011E2B
0x180011d1a  mov     ebp, 1
0x180011d1f  mov     edi, ebx
0x180011d21  jmp     loc_180011B0D
0x180011d26  mov     rax, cs:WPP_GLOBAL_Control
0x180011d2d  test    byte ptr [rax+1Ch], 8
0x180011d31  jz      loc_180011A91
0x180011d37  lea     rax, aNewTaskThread; "New task thread"
0x180011d3e  mov     r9d, 3
0x180011d44  mov     r8d, 33Ah
0x180011d4a  mov     [rsp+78h+var_58], rax
0x180011d4f  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180011d56  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180011d5d  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180011d62  jmp     loc_180011A91
0x180011d67  mov     rax, cs:WPP_GLOBAL_Control
0x180011d6e  test    byte ptr [rax+1Ch], 8
0x180011d72  jz      loc_180011CC1
0x180011d78  lea     rax, aTaskThreadExit; "Task thread exiting"
0x180011d7f  mov     r9d, 3
0x180011d85  mov     r8d, 3BEh
0x180011d8b  mov     [rsp+78h+var_58], rax
0x180011d90  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180011d97  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180011d9e  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180011da3  jmp     loc_180011CC1
0x180011da8  mov     rcx, r14; this
0x180011dab  call    ?PingServer@CClientSet@@QEAAJXZ; CClientSet::PingServer(void)
0x180011db0  lea     rdx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180011db7  lea     rcx, [rsp+78h+SRWLock]
0x180011dbf  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180011dc4  mov     rax, [r14]
0x180011dc7  mov     rcx, r14
0x180011dca  mov     rax, [rax+10h]
0x180011dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dd3  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x180011ddb  test    rcx, rcx
0x180011dde  jz      loc_180011B0D
0x180011de4  call    cs:__imp_ReleaseSRWLockExclusive
0x180011dea  mov     [rsp+78h+SRWLock], 0
0x180011df6  jmp     loc_180011B0D
0x180011dfb  lea     rax, aTaskThreadNewI; "Task thread, new iteration"
0x180011e02  mov     r9d, 3
0x180011e08  mov     r8d, 35Ch
0x180011e0e  mov     [rsp+78h+var_58], rax
0x180011e13  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180011e1a  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180011e21  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180011e26  jmp     loc_180011C72
0x180011e2b  lea     rdx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180011e32  mov     ebp, 2
0x180011e37  lea     rcx, [rsp+78h+var_48]
0x180011e3c  xor     r14d, r14d
0x180011e3f  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180011e44  mov     rcx, cs:?gpClientSetRemotePList@@3PEAVCPList@@EA; this
0x180011e4b  lea     rdx, [rsp+78h+arg_10]; struct CTime *
0x180011e53  call    ?MaybeRemoveMin@CPList@@QEAAPEAVCListElement@@AEBVCTime@@@Z; CPList::MaybeRemoveMin(CTime const &)
0x180011e58  test    rax, rax
0x180011e5b  jz      short loc_180011E70
0x180011e5d  lea     r14, [rax-60h]
0x180011e61  mov     rax, [r14]
0x180011e64  mov     rcx, r14
0x180011e67  mov     rax, [rax+8]
0x180011e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e70  lea     rcx, [rsp+78h+var_48]; this
0x180011e75  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x180011e7a  test    r14, r14
0x180011e7d  jz      loc_180011B0D
0x180011e83  jmp     loc_180011DA8
0x180011e88  lea     rax, aTaskThreadWait; "Task thread waiting until %#x"
0x180011e8f  mov     dword ptr [rsp+78h+var_50], edi
0x180011e93  mov     r9d, 3
0x180011e99  mov     [rsp+78h+var_58], rax
0x180011e9e  mov     r8d, 3DAh
0x180011ea4  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180011eab  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180011eb2  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180011eb7  jmp     loc_180011BEA
```

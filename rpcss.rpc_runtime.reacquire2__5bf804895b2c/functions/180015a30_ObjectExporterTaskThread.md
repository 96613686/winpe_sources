# ObjectExporterTaskThread

- ea: `0x180015a30`
- end: `0x180015e98`
- name: `ObjectExporterTaskThread`
- size: `1128`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180015a30`
- `0x180015ea0`
- `0x180015eec`
- `0x180016030`
- `0x1800161bc`
- `0x180016218`
- `0x18001bcb4`
- `0x18002a89c`
- `0x180059020`
- `0x18006016c`
- `0x180060b04`
- `0x1800a6bec`
- `0x1800a7388`
- `0x1800a780c`
- `0x1800a8240`
- `0x1800b7e90`
- `0x1800c5e7c`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ab4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015afe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ab4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015afe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ad1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cdc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015ae4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015ae4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015b38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015dba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015dba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015a82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015a82`

## string_xrefs

- `0x180015d2c`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180015d6d`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180015df6`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180015e87`: `onecore\com\combase\rpcss\objex\worker.cxx`
- `0x180015d0d`: `New task thread`
- `0x180015d25`: `ObjectExporterTaskThread`
- `0x180015d66`: `ObjectExporterTaskThread`
- `0x180015def`: `ObjectExporterTaskThread`
- `0x180015e80`: `ObjectExporterTaskThread`
- `0x180015dd7`: `Task thread, new iteration`
- `0x180015d4e`: `Task thread exiting`
- `0x180015e64`: `Task thread waiting until %#x`

## pseudocode

```c
__int64 __fastcall ObjectExporterTaskThread(PVOID Parameter)
{
  struct CTaskThreadState *v1; // rax
  CTaskThreadStateList *v2; // rcx
  struct CTaskThreadState *v3; // r15
  DWORD v4; // edi
  unsigned int v5; // esi
  char v6; // r13
  DWORD TickCount; // eax
  CPList *v8; // r14
  DWORD v9; // esi
  struct _RTL_CRITICAL_SECTION *v10; // r12
  DWORD v11; // ebx
  int v12; // ebp
  CPList *v13; // r14
  struct _RTL_CRITICAL_SECTION *v14; // r12
  char v15; // r14
  unsigned __int16 v16; // dx
  DWORD v17; // ebx
  unsigned __int16 v18; // ax
  unsigned __int16 CurrentThreadId; // ax
  CTaskThreadStateList *v20; // rcx
  CClientSet *v22; // r14
  struct CListElement *v23; // rax
  __int64 v24; // [rsp+28h] [rbp-50h]
  _BYTE v25[72]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+88h] [rbp+10h]
  DWORD v27; // [rsp+90h] [rbp+18h] BYREF
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
    v26 = 0;
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
      v27 = TickCount;
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
          v22 = 0;
          Microsoft::WRL::Wrappers::SRWLock::LockShared(v25, &gpClientLock);
          v23 = CPList::MaybeRemoveMin(gpClientSetRemotePList, (const struct CTime *)&v27);
          if ( v23 )
          {
            v22 = (struct CListElement *)((char *)v23 - 96);
            (*(void (__fastcall **)(__int64))(*((_QWORD *)v23 - 12) + 8LL))((__int64)v23 - 96);
          }
          Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v25);
          if ( v22 )
          {
            CClientSet::PingServer(v22);
            Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpClientLock);
            (*(void (__fastcall **)(CClientSet *))(*(_QWORD *)v22 + 16LL))(v22);
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
        else if ( (unsigned int)RundownOidsHelper(&v27, 0, 0) )
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
      v5 = v26;
      if ( v12 == 1 )
      {
        if ( (int)CInterlockedInteger::operator long(&dword_1801581F0) > 2 )
          break;
        v5 = v26 + 1;
        v17 = v11 + 1000;
        v6 = 1;
        ++v26;
        v27 = v17;
        if ( gfEnableTracing )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            LODWORD(v24) = v17;
            ComTraceMessageT<int>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\worker.cxx",
              (unsigned int)"ObjectExporterTaskThread",
              986,
              3,
              (__int64)L"Task thread waiting until %#x",
              v24);
          }
        }
        v18 = GetCurrentThreadId();
        RpcssTestLog::Log((RpcssTestLog *)0x3EE, v18, v17);
        CTime::Sleep((CTime *)&v27, *((struct _TP_TIMER **)v3 + 3), *((void **)v3 + 4));
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
    CTaskThreadStateList::Remove(v20, v3);
    CTaskThreadState::~CTaskThreadState(v3);
    operator delete(v3, 0x28u);
  }
  _InterlockedDecrement(&dword_1801581F0);
  return 0;
}

```

## disassembly

```asm
0x180015a30  mov     [rsp+arg_0], rbx
0x180015a35  push    rbp
0x180015a36  push    rsi
0x180015a37  push    rdi
0x180015a38  push    r12
0x180015a3a  push    r13
0x180015a3c  push    r14
0x180015a3e  push    r15
0x180015a40  sub     rsp, 40h
0x180015a44  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180015a4b  jnz     loc_180015CFC
0x180015a51  call    ?InitializeTaskThreadState@@YAPEAVCTaskThreadState@@XZ; InitializeTaskThreadState(void)
0x180015a56  mov     r15, rax
0x180015a59  test    rax, rax
0x180015a5c  jz      loc_180015CB7
0x180015a62  mov     rdx, rax; struct CTaskThreadState *
0x180015a65  xor     edi, edi
0x180015a67  call    ?Insert@CTaskThreadStateList@@QEAAXPEAVCTaskThreadState@@@Z; CTaskThreadStateList::Insert(CTaskThreadState *)
0x180015a6c  xor     esi, esi
0x180015a6e  lea     r13d, [rdi+1]
0x180015a72  mov     [rsp+78h+arg_8], esi
0x180015a79  test    r13b, r13b
0x180015a7c  jnz     loc_180015C1B
0x180015a82  call    cs:__imp_GetTickCount
0x180015a89  nop     dword ptr [rax+rax+00h]
0x180015a8e  mov     r14, cs:?gpClientSetRemotePList@@3PEAVCPList@@EA; CPList * gpClientSetRemotePList
0x180015a95  mov     esi, eax
0x180015a97  mov     [rsp+78h+arg_10], eax
0x180015a9e  movzx   eax, cs:?g_usBasePingInterval@@3GA; ushort g_usBasePingInterval
0x180015aa5  imul    ebx, eax, 3E8h
0x180015aab  lea     r12, [r14+10h]
0x180015aaf  mov     rcx, r12; lpCriticalSection
0x180015ab2  add     ebx, esi
0x180015ab4  call    cs:__imp_EnterCriticalSection
0x180015abb  nop     dword ptr [rax+rax+00h]
0x180015ac0  mov     rax, [r14]
0x180015ac3  mov     rcx, r12; lpCriticalSection
0x180015ac6  test    rax, rax
0x180015ac9  jnz     loc_180015CD9
0x180015acf  xor     ebp, ebp
0x180015ad1  call    cs:__imp_LeaveCriticalSection
0x180015ad8  nop     dword ptr [rax+rax+00h]
0x180015add  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180015ae4  call    cs:__imp_AcquireSRWLockShared
0x180015aeb  nop     dword ptr [rax+rax+00h]
0x180015af0  mov     r14, cs:?gpServerOidPList@@3PEAVCServerOidPList@@EA; CServerOidPList * gpServerOidPList
0x180015af7  lea     r12, [r14+10h]
0x180015afb  mov     rcx, r12; lpCriticalSection
0x180015afe  call    cs:__imp_EnterCriticalSection
0x180015b05  nop     dword ptr [rax+rax+00h]
0x180015b0a  mov     rax, [r14]
0x180015b0d  mov     rcx, r12; lpCriticalSection
0x180015b10  test    rax, rax
0x180015b13  jz      loc_180015C58
0x180015b19  mov     edi, [rax+18h]
0x180015b1c  call    cs:__imp_LeaveCriticalSection
0x180015b23  nop     dword ptr [rax+rax+00h]
0x180015b28  mov     r12d, 1
0x180015b2e  mov     r14b, r12b
0x180015b31  lea     rcx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180015b38  call    cs:__imp_ReleaseSRWLockShared
0x180015b3f  nop     dword ptr [rax+rax+00h]
0x180015b44  test    r14b, r14b
0x180015b47  jz      short loc_180015B76
0x180015b49  test    ebp, ebp
0x180015b4b  cmovz   ebp, r12d
0x180015b4f  cmp     esi, edi
0x180015b51  js      loc_180015C0C
0x180015b57  xor     r8d, r8d
0x180015b5a  lea     rcx, [rsp+78h+arg_10]
0x180015b62  xor     edx, edx
0x180015b64  call    ?RundownOidsHelper@@YAHPEAVCTime@@PEAVCServerOxid@@W4WhereIssuedRundown@@@Z; RundownOidsHelper(CTime *,CServerOxid *,WhereIssuedRundown)
0x180015b69  test    eax, eax
0x180015b6b  jz      loc_180015C72
0x180015b71  mov     ebp, 2
0x180015b76  test    ebp, ebp
0x180015b78  jz      loc_180015C83
0x180015b7e  mov     esi, [rsp+78h+arg_8]
0x180015b85  cmp     ebp, r12d
0x180015b88  jnz     loc_180015A79
0x180015b8e  lea     rcx, dword_1801581F0
0x180015b95  call    ??BCInterlockedInteger@@QEAAJXZ; CInterlockedInteger::operator long(void)
0x180015b9a  cmp     eax, 2
0x180015b9d  jg      loc_180015C83
0x180015ba3  add     esi, r12d
0x180015ba6  add     ebx, 3E8h
0x180015bac  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180015bb3  mov     r13b, r12b
0x180015bb6  mov     [rsp+78h+arg_8], esi
0x180015bbd  mov     [rsp+78h+arg_10], ebx
0x180015bc4  jz      short loc_180015BD7
0x180015bc6  mov     rax, cs:WPP_GLOBAL_Control
0x180015bcd  test    byte ptr [rax+1Ch], 8
0x180015bd1  jnz     loc_180015E64
0x180015bd7  call    cs:__imp_GetCurrentThreadId
0x180015bde  nop     dword ptr [rax+rax+00h]
0x180015be3  mov     ecx, 3EEh; this
0x180015be8  mov     r8d, ebx
0x180015beb  mov     edx, eax; unsigned __int16
0x180015bed  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x180015bf2  mov     r8, [r15+20h]; void *
0x180015bf6  lea     rcx, [rsp+78h+arg_10]; this
0x180015bfe  mov     rdx, [r15+18h]; struct _TP_TIMER *
0x180015c02  call    ?Sleep@CTime@@QEBAXPEAU_TP_TIMER@@PEAX@Z; CTime::Sleep(_TP_TIMER *,void *)
0x180015c07  jmp     loc_180015A79
0x180015c0c  cmp     edi, ebx
0x180015c0e  jns     loc_180015B76
0x180015c14  mov     ebx, edi
0x180015c16  jmp     loc_180015B76
0x180015c1b  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180015c22  jz      short loc_180015C35
0x180015c24  mov     rax, cs:WPP_GLOBAL_Control
0x180015c2b  test    byte ptr [rax+1Ch], 8
0x180015c2f  jnz     loc_180015DD7
0x180015c35  call    cs:__imp_GetCurrentThreadId
0x180015c3c  nop     dword ptr [rax+rax+00h]
0x180015c41  mov     ecx, 3EBh; this
0x180015c46  mov     r8d, esi
0x180015c49  mov     edx, eax; unsigned __int16
0x180015c4b  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x180015c50  xor     r13b, r13b
0x180015c53  jmp     loc_180015A82
0x180015c58  call    cs:__imp_LeaveCriticalSection
0x180015c5f  nop     dword ptr [rax+rax+00h]
0x180015c64  xor     r14b, r14b
0x180015c67  mov     r12d, 1
0x180015c6d  jmp     loc_180015B31
0x180015c72  cmp     ebp, 2
0x180015c75  jz      loc_180015B76
0x180015c7b  mov     ebp, r12d
0x180015c7e  jmp     loc_180015B76
0x180015c83  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180015c8a  jnz     loc_180015D3D
0x180015c90  mov     ecx, 3ECh; this
0x180015c95  call    ?Log@RpcssTestLog@@YAXGZZ; RpcssTestLog::Log(ushort,...)
0x180015c9a  mov     rdx, r15; struct CTaskThreadState *
0x180015c9d  call    ?Remove@CTaskThreadStateList@@QEAAXPEAVCTaskThreadState@@@Z; CTaskThreadStateList::Remove(CTaskThreadState *)
0x180015ca2  mov     rcx, r15; this
0x180015ca5  call    ??1CTaskThreadState@@QEAA@XZ; CTaskThreadState::~CTaskThreadState(void)
0x180015caa  mov     edx, 28h ; '('; unsigned __int64
0x180015caf  mov     rcx, r15; void *
0x180015cb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015cb7  lock dec cs:dword_1801581F0
0x180015cbe  mov     rbx, [rsp+78h+arg_0]
0x180015cc6  xor     eax, eax
0x180015cc8  add     rsp, 40h
0x180015ccc  pop     r15
0x180015cce  pop     r14
0x180015cd0  pop     r13
0x180015cd2  pop     r12
0x180015cd4  pop     rdi
0x180015cd5  pop     rsi
0x180015cd6  pop     rbp
0x180015cd7  retn
0x180015cd9  mov     edi, [rax+18h]
0x180015cdc  call    cs:__imp_LeaveCriticalSection
0x180015ce3  nop     dword ptr [rax+rax+00h]
0x180015ce8  cmp     esi, edi
0x180015cea  jns     loc_180015E07
0x180015cf0  mov     ebp, 1
0x180015cf5  mov     ebx, edi
0x180015cf7  jmp     loc_180015ADD
0x180015cfc  mov     rax, cs:WPP_GLOBAL_Control
0x180015d03  test    byte ptr [rax+1Ch], 8
0x180015d07  jz      loc_180015A51
0x180015d0d  lea     rax, aNewTaskThread; "New task thread"
0x180015d14  mov     r9d, 3
0x180015d1a  mov     r8d, 33Ah
0x180015d20  mov     [rsp+78h+var_58], rax
0x180015d25  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180015d2c  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180015d33  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180015d38  jmp     loc_180015A51
0x180015d3d  mov     rax, cs:WPP_GLOBAL_Control
0x180015d44  test    byte ptr [rax+1Ch], 8
0x180015d48  jz      loc_180015C90
0x180015d4e  lea     rax, aTaskThreadExit; "Task thread exiting"
0x180015d55  mov     r9d, 3
0x180015d5b  mov     r8d, 3BEh
0x180015d61  mov     [rsp+78h+var_58], rax
0x180015d66  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180015d6d  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180015d74  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180015d79  jmp     loc_180015C90
0x180015d7e  mov     rcx, r14; this
0x180015d81  call    ?PingServer@CClientSet@@QEAAJXZ; CClientSet::PingServer(void)
0x180015d86  lea     rdx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180015d8d  lea     rcx, [rsp+78h+SRWLock]
0x180015d95  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180015d9a  mov     rax, [r14]
0x180015d9d  mov     rcx, r14
0x180015da0  mov     rax, [rax+10h]
0x180015da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015da9  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x180015db1  test    rcx, rcx
0x180015db4  jz      loc_180015ADD
0x180015dba  call    cs:__imp_ReleaseSRWLockExclusive
0x180015dc1  nop     dword ptr [rax+rax+00h]
0x180015dc6  mov     [rsp+78h+SRWLock], 0
0x180015dd2  jmp     loc_180015ADD
0x180015dd7  lea     rax, aTaskThreadNewI; "Task thread, new iteration"
0x180015dde  mov     r9d, 3
0x180015de4  mov     r8d, 35Ch
0x180015dea  mov     [rsp+78h+var_58], rax
0x180015def  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180015df6  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180015dfd  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x180015e02  jmp     loc_180015C35
0x180015e07  lea     rdx, ?gpClientLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpClientLock
0x180015e0e  mov     ebp, 2
0x180015e13  lea     rcx, [rsp+78h+var_48]
0x180015e18  xor     r14d, r14d
0x180015e1b  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180015e20  mov     rcx, cs:?gpClientSetRemotePList@@3PEAVCPList@@EA; this
0x180015e27  lea     rdx, [rsp+78h+arg_10]; struct CTime *
0x180015e2f  call    ?MaybeRemoveMin@CPList@@QEAAPEAVCListElement@@AEBVCTime@@@Z; CPList::MaybeRemoveMin(CTime const &)
0x180015e34  test    rax, rax
0x180015e37  jz      short loc_180015E4C
0x180015e39  lea     r14, [rax-60h]
0x180015e3d  mov     rax, [r14]
0x180015e40  mov     rcx, r14
0x180015e43  mov     rax, [rax+8]
0x180015e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e4c  lea     rcx, [rsp+78h+var_48]; this
0x180015e51  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x180015e56  test    r14, r14
0x180015e59  jz      loc_180015ADD
0x180015e5f  jmp     loc_180015D7E
0x180015e64  lea     rax, aTaskThreadWait; "Task thread waiting until %#x"
0x180015e6b  mov     dword ptr [rsp+78h+var_50], ebx
0x180015e6f  mov     r9d, 3
0x180015e75  mov     [rsp+78h+var_58], rax
0x180015e7a  mov     r8d, 3DAh
0x180015e80  lea     rdx, aObjectexporter_0; "ObjectExporterTaskThread"
0x180015e87  lea     rcx, aOnecoreComComb_113; "onecore\\com\\combase\\rpcss\\objex\\wo"...
0x180015e8e  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180015e93  jmp     loc_180015BD7
```

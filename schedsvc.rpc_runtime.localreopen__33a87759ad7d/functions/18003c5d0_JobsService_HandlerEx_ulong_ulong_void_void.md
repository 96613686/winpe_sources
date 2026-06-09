# JobsService::HandlerEx(ulong,ulong,void *,void *)

- ea: `0x18003c5d0`
- end: `0x18003ce1f`
- name: `?HandlerEx@JobsService@@UEAAKKKPEAX0@Z`
- size: `2127`
- prototype: `unsigned int __usercall@<eax>(JobsService *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, void *@<r9>, void *)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001a430`
- `0x180022600`
- `0x18003c460`
- `0x18003c5d0`
- `0x18003d280`
- `0x18003f600`
- `0x180040b70`
- `0x1800504f8`
- `0x180050a38`
- `0x1800515c0`
- `0x180051b1c`
- `0x180052150`
- `0x180054084`
- `0x180059780`
- `0x1800597e4`
- `0x18005a8ec`
- `0x18005b14c`
- `0x18005b4b4`
- `0x1800632bc`
- `0x180063708`
- `0x18006971c`
- `0x18006981c`
- `0x1800698d4`
- `0x180074130`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `UBPM!UbpmSessionStateChanged` at `0x18003c816`
- `UBPM!UbpmSessionStateChanged` at `0x18003c8e9`
- `UBPM!UbpmSessionStateChanged` at `0x18003c816`
- `UBPM!UbpmSessionStateChanged` at `0x18003c8e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ca4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003cabf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ccbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ca4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003cabf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003ccbf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c9e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003c9e2`
- `ntdll!NtSetThreadExecutionState` at `0x18003cd13`
- `ntdll!NtSetThreadExecutionState` at `0x18003cd13`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18003c920`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18003c920`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall JobsService::HandlerEx(JobsService *this, unsigned int a2, __int64 a3, unsigned int *a4, void *a5)
{
  unsigned int v6; // r14d
  unsigned int v9; // edi
  int v10; // edx
  __int64 v11; // r10
  char v12; // r11
  __int64 v13; // r8
  __int64 v14; // r8
  PseudoEventTrap *v15; // rcx
  Scheduler *v16; // rcx
  __int128 v18; // xmm6
  Scheduler *v19; // rcx
  Scheduler *v20; // rcx
  char v21; // al
  GUID *v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int32 v25[4]; // [rsp+50h] [rbp-138h] BYREF
  DWORD pBytesReturned[4]; // [rsp+60h] [rbp-128h] BYREF
  LPWSTR ppBuffer[2]; // [rsp+70h] [rbp-118h] BYREF
  int v28; // [rsp+80h] [rbp-108h]
  int v29; // [rsp+84h] [rbp-104h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+90h] [rbp-F8h] BYREF
  struct _FILETIME v31[2]; // [rsp+A0h] [rbp-E8h] BYREF
  struct _FILETIME v32[2]; // [rsp+B0h] [rbp-D8h] BYREF
  GUID iid; // [rsp+C0h] [rbp-C8h] BYREF
  GUID v34; // [rsp+E8h] [rbp-A0h] BYREF
  GUID v35; // [rsp+110h] [rbp-78h] BYREF

  v6 = a3;
  v28 = 0;
  v9 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    *(_QWORD *)pBytesReturned = 0;
    ppBuffer[0] = 0;
    ControlEventToStrings(a2, a3, (const char **)pBytesReturned, (const char **)ppBuffer);
    if ( *(_BYTE *)(v11 + 25) >= 4u )
      WPP_SF_DsDsqq(
        *(_QWORD *)(v11 + 16),
        v10,
        a3,
        a2,
        *(__int64 *)pBytesReturned,
        v6,
        (__int64)ppBuffer[0],
        (char)a4,
        v12);
  }
  if ( a2 != 13 )
  {
    switch ( a2 )
    {
      case 4u:
        goto LABEL_18;
      case 0xEu:
        v25[0] = 0;
        _InterlockedExchange(v25, 0);
        _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
        _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800BD53C, 0, 0) != 0);
        if ( !_InterlockedCompareExchange(v25, 0, 0) )
          goto LABEL_75;
        if ( *((_BYTE *)this + 128) )
        {
          UbpmSessionStateChanged(v6, a4[1], 0);
          pBytesReturned[0] = 0;
          ppBuffer[0] = 0;
          SystemTimeAsFileTime[0] = (struct _FILETIME)ppBuffer;
          if ( WTSQuerySessionInformationW(0, a4[1], WTSUserName, ppBuffer, pBytesReturned) )
          {
            if ( pBytesReturned[0] >= 2 )
            {
              if ( ppBuffer[0] )
              {
                if ( *ppBuffer[0] )
                {
                  v15 = g_pPseudoEventTrap;
                  if ( g_pPseudoEventTrap )
                  {
                    if ( v6 == 5 )
                    {
                      User::NotifyLogon(a4[1], ppBuffer[0]);
                      v15 = g_pPseudoEventTrap;
                    }
                    PseudoEventTrap::QueueOrProcessSessionChange(v15, v6, a4[1]);
                  }
                }
              }
            }
          }
          tsched::WTSFreeMe<int>::~WTSFreeMe<int>(SystemTimeAsFileTime);
          goto LABEL_75;
        }
        break;
      case 0x10u:
        v25[0] = 0;
        _InterlockedExchange(v25, 0);
        _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
        _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800BD53C, 0, 0) != 0);
        if ( !_InterlockedCompareExchange(v25, 0, 0) || !g_pScheduler )
          goto LABEL_75;
        if ( *((_BYTE *)this + 128) )
        {
          Scheduler::NotifyTimeChange(0);
          goto LABEL_75;
        }
        break;
      case 0x21u:
        v25[0] = 0;
        _InterlockedExchange(v25, 0);
        _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
        _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800BD53C, 0, 0) != 0);
        if ( !_InterlockedCompareExchange(v25, 0, 0) )
        {
LABEL_75:
          _InterlockedExchange(v25, 0);
          ShutdownMgr::Unguard();
          return v9;
        }
        if ( *((_BYTE *)this + 128) )
        {
          UbpmSessionStateChanged(v6, a4[1], *((_QWORD *)a4 + 1));
          goto LABEL_75;
        }
        break;
      default:
        switch ( a2 )
        {
          case 1u:
LABEL_17:
            CNtService::ReportStatusToSCMgr(this, 3, a3, 1, 0x7530u);
            (*(void (__fastcall **)(JobsService *, bool))(*(_QWORD *)this + 16LL))(this, a2 == 5);
            break;
          case 2u:
            CNtService::ReportStatusToSCMgr(this, 6, a3, 1, 0x7530u);
            (*(void (__fastcall **)(JobsService *))(*(_QWORD *)this + 40LL))(this);
            CNtService::ReportStatusToSCMgr(this, 7, v14, 0, 0);
            break;
          case 3u:
            CNtService::ReportStatusToSCMgr(this, 5, a3, 1, 0x7530u);
            (*(void (__fastcall **)(JobsService *))(*(_QWORD *)this + 48LL))(this);
            CNtService::ReportStatusToSCMgr(this, 4, v13, 0, 0);
            break;
          case 5u:
            goto LABEL_17;
          default:
            v9 = 120;
            v29 = 120;
            return v9;
        }
LABEL_18:
        v9 = 0;
        v29 = 0;
        return v9;
    }
LABEL_42:
    _InterlockedExchange(v25, 0);
    ShutdownMgr::Unguard();
    return 0;
  }
  v25[0] = 0;
  _InterlockedExchange(v25, 0);
  _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
  _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800BD53C, 0, 0) != 0);
  v16 = 0;
  if ( _InterlockedCompareExchange(v25, 0, 0) )
  {
    if ( *((_BYTE *)this + 128) )
    {
      switch ( v6 )
      {
        case 0u:
        case 4u:
          if ( byte_1800BD168 )
            goto LABEL_75;
          LOBYTE(SystemTimeAsFileTime[0].dwLowDateTime) = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
          v18 = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
          *(_OWORD *)&v32[0].dwLowDateTime = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
          *(_OWORD *)ppBuffer = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
          *(_OWORD *)pBytesReturned = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
          JobMoniker::JobMoniker(&iid, 0, 0);
          JobMoniker::JobMoniker(&v35, 0, 0);
          JobMoniker::JobMoniker(&v34, 0, 0);
          byte_1800BD168 = 1;
          LOBYTE(v31[0].dwLowDateTime) = 0;
          GetSystemTimeAsFileTime(&v31[1]);
          *(_OWORD *)((char *)this + 168) = *(_OWORD *)&v31[0].dwLowDateTime;
          Scheduler::NotifySleep(v19, byte_1800BD168);
          Scheduler::GetWakeupCall(v20, (struct TSTime *)ppBuffer, (struct JobMoniker *)&v34);
          if ( (unsigned __int8)TSTime::operator>(v32, SystemTimeAsFileTime)
            && (unsigned __int8)TSTime::operator>(ppBuffer, SystemTimeAsFileTime) )
          {
            v21 = TSTime::operator<(v32, ppBuffer);
            if ( !v21 )
              v18 = *(_OWORD *)ppBuffer;
            v22 = &v34;
            if ( v21 )
              v22 = &v35;
          }
          else if ( (unsigned __int8)TSTime::operator>(v32, SystemTimeAsFileTime) )
          {
            v22 = &v35;
          }
          else
          {
            if ( !(unsigned __int8)TSTime::operator>(ppBuffer, SystemTimeAsFileTime) )
              goto LABEL_56;
            v18 = *(_OWORD *)ppBuffer;
            v22 = &v34;
          }
          *(_OWORD *)pBytesReturned = v18;
          JobMoniker::operator=(&iid, v22);
LABEL_56:
          if ( (unsigned __int8)TSTime::operator>(pBytesReturned, SystemTimeAsFileTime) )
          {
            if ( (unsigned int)TSTime::operator-(pBytesReturned, SystemTimeAsFileTime) < 0x5A )
              v18 = *(_OWORD *)TSTime::operator+(SystemTimeAsFileTime, v31, 90);
            *(_OWORD *)&v31[0].dwLowDateTime = v18;
            JobsService::SetWakeupTimer(this, v31, &iid);
          }
          LOBYTE(v23) = 1;
          ItSrvNotifyResume(v23);
          JobMoniker::~JobMoniker((JobMoniker *)&v34);
          JobMoniker::~JobMoniker((JobMoniker *)&v35);
          JobMoniker::~JobMoniker((JobMoniker *)&iid);
          goto LABEL_75;
        case 2u:
          goto LABEL_73;
        case 6u:
        case 7u:
        case 0x12u:
          if ( !byte_1800BD168 )
            goto LABEL_75;
          pBytesReturned[0] = 0;
          _InterlockedExchange((volatile __int32 *)pBytesReturned, 0);
          _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
          _InterlockedExchange(
            (volatile __int32 *)pBytesReturned,
            _InterlockedCompareExchange(&dword_1800BD53C, 0, 0) != 0);
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)pBytesReturned, 0, 0) )
          {
            _InterlockedExchange((volatile __int32 *)pBytesReturned, 0);
            ShutdownMgr::Unguard();
            _InterlockedExchange(v25, 0);
            ShutdownMgr::Unguard();
            return 0;
          }
          LOBYTE(v32[0].dwLowDateTime) = 0;
          GetSystemTimeAsFileTime(&v32[1]);
          LOBYTE(v31[0].dwLowDateTime) = 0;
          v31[1] = 0;
          if ( (unsigned __int8)TSTime::operator!=((char *)this + 152, v31)
            && (unsigned __int8)TSTime::operator>=(v32, (char *)this + 152) )
          {
            LODWORD(ppBuffer[0]) = 0;
            NtSetThreadExecutionState(1u, (EXECUTION_STATE *)ppBuffer);
            *((_BYTE *)this + 152) = 0;
            *(_DWORD *)((char *)this + 153) = *(DWORD *)((char *)&v31[0].dwLowDateTime + 1);
            *(_WORD *)((char *)this + 157) = *(_WORD *)((char *)&v31[0].dwHighDateTime + 1);
            *((_BYTE *)this + 159) = HIBYTE(v31[0].dwHighDateTime);
            *((_QWORD *)this + 20) = 0;
          }
          v24 = Scheduler::EvaluateMissedRuns(g_pScheduler);
          v28 = v24;
          if ( v24 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids,
              (unsigned int)v24);
          }
          ItSrvNotifyResume(0);
          _InterlockedExchange((volatile __int32 *)pBytesReturned, 0);
          ShutdownMgr::Unguard();
LABEL_73:
          if ( byte_1800BD168 )
          {
            byte_1800BD168 = 0;
            Scheduler::NotifySleep(v16, 0);
          }
          break;
        default:
          goto LABEL_75;
      }
      goto LABEL_75;
    }
    goto LABEL_42;
  }
  _InterlockedExchange(v25, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
    SetEvent((HANDLE)_InterlockedCompareExchange64((volatile signed __int64 *)&ShutdownMgr::s_hEvent, -1, -1));
  return 0;
}

```

## disassembly

```asm
0x18003c5d0  push    rbx
0x18003c5d2  push    rsi
0x18003c5d3  push    rdi
0x18003c5d4  push    r12
0x18003c5d6  push    r13
0x18003c5d8  push    r14
0x18003c5da  push    r15
0x18003c5dc  sub     rsp, 150h
0x18003c5e3  movaps  [rsp+188h+var_48], xmm6
0x18003c5eb  mov     rax, cs:__security_cookie
0x18003c5f2  xor     rax, rsp
0x18003c5f5  mov     [rsp+188h+var_50], rax
0x18003c5fd  mov     rsi, r9
0x18003c600  mov     r14d, r8d
0x18003c603  mov     ebx, edx
0x18003c605  mov     r15, rcx
0x18003c608  mov     r11, [rsp+188h+arg_20]
0x18003c610  xor     r12d, r12d
0x18003c613  mov     [rsp+188h+var_108], r12d
0x18003c61b  mov     edi, r12d
0x18003c61e  mov     [rsp+188h+var_104], r12d
0x18003c626  lea     r13, WPP_GLOBAL_Control
0x18003c62d  mov     r10, cs:WPP_GLOBAL_Control
0x18003c634  cmp     r10, r13
0x18003c637  jz      short loc_18003C697
0x18003c639  test    dword ptr [r10+1Ch], 400h
0x18003c641  jz      short loc_18003C697
0x18003c643  mov     qword ptr [rsp+188h+var_128], r12
0x18003c648  mov     [rsp+188h+ppBuffer], r12
0x18003c64d  lea     r9, [rsp+188h+ppBuffer]; char **
0x18003c652  lea     r8, [rsp+188h+var_128]; char **
0x18003c657  mov     edx, r14d; unsigned int
0x18003c65a  mov     ecx, ebx; unsigned int
0x18003c65c  call    ?ControlEventToStrings@@YAXKKAEAPEBD0@Z; ControlEventToStrings(ulong,ulong,char const * &,char const * &)
0x18003c661  cmp     byte ptr [r10+19h], 4
0x18003c666  jb      short loc_18003C697
0x18003c668  mov     [rsp+188h+var_148], r11
0x18003c66d  mov     [rsp+188h+var_150], rsi
0x18003c672  mov     rax, [rsp+188h+ppBuffer]
0x18003c677  mov     [rsp+188h+var_158], rax
0x18003c67c  mov     [rsp+188h+var_160], r14d
0x18003c681  mov     rax, qword ptr [rsp+188h+var_128]
0x18003c686  mov     [rsp+188h+pBytesReturned], rax
0x18003c68b  mov     r9d, ebx
0x18003c68e  mov     rcx, [r10+10h]
0x18003c692  call    WPP_SF_DsDsqq
0x18003c697  cmp     ebx, 0Dh
0x18003c69a  jz      loc_18003C982
0x18003c6a0  cmp     ebx, 4
0x18003c6a3  jz      loc_18003C7A8
0x18003c6a9  cmp     ebx, 0Eh
0x18003c6ac  jz      loc_18003C88C
0x18003c6b2  cmp     ebx, 10h
0x18003c6b5  jz      loc_18003C821
0x18003c6bb  cmp     ebx, 21h ; '!'
0x18003c6be  jz      loc_18003C7B8
0x18003c6c4  mov     eax, ebx
0x18003c6c6  sub     eax, 1
0x18003c6c9  jz      loc_18003C775
0x18003c6cf  sub     eax, 1
0x18003c6d2  jz      short loc_18003C734
0x18003c6d4  sub     eax, 1
0x18003c6d7  jz      short loc_18003C6F3
0x18003c6d9  cmp     eax, 2
0x18003c6dc  jz      loc_18003C775
0x18003c6e2  mov     edi, 78h ; 'x'
0x18003c6e7  mov     [rsp+188h+var_104], edi
0x18003c6ee  jmp     loc_18003CDC4
0x18003c6f3  mov     dword ptr [rsp+188h+pBytesReturned], 7530h; unsigned int
0x18003c6fb  mov     edx, 5; unsigned int
0x18003c700  mov     r9d, 1; unsigned int
0x18003c706  mov     rcx, r15; this
0x18003c709  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003c70e  mov     rax, [r15]
0x18003c711  mov     rcx, r15
0x18003c714  mov     rax, [rax+30h]
0x18003c718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c71d  mov     dword ptr [rsp+188h+pBytesReturned], r12d; unsigned int
0x18003c722  xor     r9d, r9d; unsigned int
0x18003c725  mov     edx, 4; unsigned int
0x18003c72a  mov     rcx, r15; this
0x18003c72d  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003c732  jmp     short loc_18003C7A8
0x18003c734  mov     dword ptr [rsp+188h+pBytesReturned], 7530h; unsigned int
0x18003c73c  mov     edx, 6; unsigned int
0x18003c741  mov     r9d, 1; unsigned int
0x18003c747  mov     rcx, r15; this
0x18003c74a  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003c74f  mov     rax, [r15]
0x18003c752  mov     rcx, r15
0x18003c755  mov     rax, [rax+28h]
0x18003c759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c75e  mov     dword ptr [rsp+188h+pBytesReturned], r12d; unsigned int
0x18003c763  xor     r9d, r9d; unsigned int
0x18003c766  mov     edx, 7; unsigned int
0x18003c76b  mov     rcx, r15; this
0x18003c76e  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003c773  jmp     short loc_18003C7A8
0x18003c775  mov     dword ptr [rsp+188h+pBytesReturned], 7530h; unsigned int
0x18003c77d  mov     edx, 3; unsigned int
0x18003c782  mov     r9d, 1; unsigned int
0x18003c788  mov     rcx, r15; this
0x18003c78b  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003c790  mov     rax, [r15]
0x18003c793  mov     edx, r12d
0x18003c796  cmp     ebx, 5
0x18003c799  setz    dl
0x18003c79c  mov     rcx, r15
0x18003c79f  mov     rax, [rax+10h]
0x18003c7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7a8  mov     edi, r12d
0x18003c7ab  mov     [rsp+188h+var_104], r12d
0x18003c7b3  jmp     loc_18003CDC4
0x18003c7b8  mov     [rsp+188h+var_138], r12d
0x18003c7bd  mov     eax, r12d
0x18003c7c0  xchg    eax, [rsp+188h+var_138]
0x18003c7c4  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003c7cb  mov     ecx, r12d
0x18003c7ce  xor     eax, eax
0x18003c7d0  lock cmpxchg cs:dword_1800BD53C, ecx
0x18003c7d8  setnz   cl
0x18003c7db  xchg    ecx, [rsp+188h+var_138]
0x18003c7df  mov     ecx, r12d
0x18003c7e2  xor     eax, eax
0x18003c7e4  lock cmpxchg [rsp+188h+var_138], ecx
0x18003c7ea  jz      def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003c7f0  cmp     [r15+80h], cl
0x18003c7f7  jnz     short loc_18003C80C
0x18003c7f9  mov     eax, r12d
0x18003c7fc  xchg    eax, [rsp+188h+var_138]
0x18003c800  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003c805  xor     eax, eax
0x18003c807  jmp     loc_18003CDCF
0x18003c80c  mov     r8, [rsi+8]
0x18003c810  mov     edx, [rsi+4]
0x18003c813  mov     ecx, r14d
0x18003c816  call    cs:__imp_UbpmSessionStateChanged
0x18003c81c  jmp     def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003c821  mov     [rsp+188h+var_138], r12d
0x18003c826  mov     eax, r12d
0x18003c829  xchg    eax, [rsp+188h+var_138]
0x18003c82d  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003c834  mov     ecx, r12d
0x18003c837  xor     eax, eax
0x18003c839  lock cmpxchg cs:dword_1800BD53C, ecx
0x18003c841  setnz   cl
0x18003c844  xchg    ecx, [rsp+188h+var_138]
0x18003c848  mov     ecx, r12d; this
0x18003c84b  xor     eax, eax
0x18003c84d  lock cmpxchg [rsp+188h+var_138], ecx
0x18003c853  jz      def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003c859  cmp     cs:?g_pScheduler@@3PEAVScheduler@@EA, rcx; Scheduler * g_pScheduler
0x18003c860  jz      def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003c866  cmp     [r15+80h], cl
0x18003c86d  jnz     short loc_18003C882
0x18003c86f  mov     eax, r12d
0x18003c872  xchg    eax, [rsp+188h+var_138]
0x18003c876  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003c87b  xor     eax, eax
0x18003c87d  jmp     loc_18003CDCF
0x18003c882  call    ?NotifyTimeChange@Scheduler@@QEAAXXZ; Scheduler::NotifyTimeChange(void)
0x18003c887  jmp     def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003c88c  mov     [rsp+188h+var_138], r12d
0x18003c891  mov     eax, r12d
0x18003c894  xchg    eax, [rsp+188h+var_138]
0x18003c898  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003c89f  mov     ecx, r12d
0x18003c8a2  xor     eax, eax
0x18003c8a4  lock cmpxchg cs:dword_1800BD53C, ecx
0x18003c8ac  setnz   cl
0x18003c8af  xchg    ecx, [rsp+188h+var_138]
0x18003c8b3  mov     ecx, r12d
0x18003c8b6  xor     eax, eax
0x18003c8b8  lock cmpxchg [rsp+188h+var_138], ecx
0x18003c8be  jz      loc_18003C97D
0x18003c8c4  cmp     [r15+80h], cl
0x18003c8cb  jnz     short loc_18003C8E0
0x18003c8cd  mov     eax, r12d
0x18003c8d0  xchg    eax, [rsp+188h+var_138]
0x18003c8d4  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003c8d9  xor     eax, eax
0x18003c8db  jmp     loc_18003CDCF
0x18003c8e0  xor     r8d, r8d
0x18003c8e3  mov     edx, [rsi+4]
0x18003c8e6  mov     ecx, r14d
0x18003c8e9  call    cs:__imp_UbpmSessionStateChanged
0x18003c8ef  mov     [rsp+188h+var_128], r12d
0x18003c8f4  mov     [rsp+188h+ppBuffer], r12
0x18003c8f9  lea     rax, [rsp+188h+ppBuffer]
0x18003c8fe  mov     qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003c906  lea     rax, [rsp+188h+var_128]
0x18003c90b  mov     [rsp+188h+pBytesReturned], rax; pBytesReturned
0x18003c910  lea     r9, [rsp+188h+ppBuffer]; ppBuffer
0x18003c915  mov     r8d, 5; WTSInfoClass
0x18003c91b  mov     edx, [rsi+4]; SessionId
0x18003c91e  xor     ecx, ecx; hServer
0x18003c920  call    cs:__imp_WTSQuerySessionInformationW
0x18003c926  test    eax, eax
0x18003c928  jz      short loc_18003C96F
0x18003c92a  cmp     [rsp+188h+var_128], 2
0x18003c92f  jb      short loc_18003C96F
0x18003c931  mov     rdx, [rsp+188h+ppBuffer]; unsigned __int16 *
0x18003c936  test    rdx, rdx
0x18003c939  jz      short loc_18003C96F
0x18003c93b  cmp     r12w, [rdx]
0x18003c93f  jz      short loc_18003C96F
0x18003c941  mov     rcx, cs:?g_pPseudoEventTrap@@3PEAVPseudoEventTrap@@EA; PseudoEventTrap * g_pPseudoEventTrap
0x18003c948  test    rcx, rcx
0x18003c94b  jz      short loc_18003C96F
0x18003c94d  cmp     r14d, 5
0x18003c951  jnz     short loc_18003C962
0x18003c953  mov     ecx, [rsi+4]; SessionId
0x18003c956  call    ?NotifyLogon@User@@SAXKPEBG@Z; User::NotifyLogon(ulong,ushort const *)
0x18003c95b  mov     rcx, cs:?g_pPseudoEventTrap@@3PEAVPseudoEventTrap@@EA; this
0x18003c962  mov     r8d, [rsi+4]; unsigned int
0x18003c966  mov     edx, r14d; unsigned int
0x18003c969  call    ?QueueOrProcessSessionChange@PseudoEventTrap@@QEAAXKK@Z; PseudoEventTrap::QueueOrProcessSessionChange(ulong,ulong)
0x18003c96e  nop
0x18003c96f  lea     rcx, [rsp+188h+SystemTimeAsFileTime]
0x18003c977  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x18003c97c  nop
0x18003c97d  jmp     def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003c982  mov     [rsp+188h+var_138], r12d
0x18003c987  mov     eax, r12d
0x18003c98a  xchg    eax, [rsp+188h+var_138]
0x18003c98e  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003c995  mov     ecx, r12d
0x18003c998  xor     eax, eax
0x18003c99a  lock cmpxchg cs:dword_1800BD53C, ecx
0x18003c9a2  setnz   cl
0x18003c9a5  xchg    ecx, [rsp+188h+var_138]
0x18003c9a9  mov     ecx, r12d
0x18003c9ac  xor     eax, eax
0x18003c9ae  lock cmpxchg [rsp+188h+var_138], ecx
0x18003c9b4  jnz     short loc_18003C9EF
0x18003c9b6  mov     eax, r12d
0x18003c9b9  xchg    eax, [rsp+188h+var_138]
0x18003c9bd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c9c4  mov     eax, ecx
0x18003c9c6  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003c9ce  cmp     eax, 1
0x18003c9d1  jnz     short loc_18003C9E8
0x18003c9d3  mov     rax, rcx
0x18003c9d6  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x18003c9df  mov     rcx, rax; hEvent
0x18003c9e2  call    cs:__imp_SetEvent
0x18003c9e8  xor     eax, eax
0x18003c9ea  jmp     loc_18003CDCF
0x18003c9ef  cmp     [r15+80h], cl
0x18003c9f6  jnz     short loc_18003CA0B
0x18003c9f8  mov     eax, r12d
0x18003c9fb  xchg    eax, [rsp+188h+var_138]
0x18003c9ff  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003ca04  xor     eax, eax
0x18003ca06  jmp     loc_18003CDCF
0x18003ca0b  cmp     r14d, 12h; switch 19 cases
0x18003ca0f  ja      def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003ca15  lea     rdx, __ImageBase
0x18003ca1c  movzx   eax, ds:(byte_18003CE0C - 180000000h)[rdx+r14]
0x18003ca25  mov     ecx, ds:(jpt_18003CA2F - 180000000h)[rdx+rax*4]
0x18003ca2c  add     rcx, rdx
0x18003ca2f  jmp     rcx; switch jump
0x18003ca31  cmp     cs:byte_1800BD168, 0; jumptable 000000018003CA2F cases 0,4
0x18003ca38  jnz     def_18003CA2F; jumptable 000000018003CA2F default case, cases 1,3,5,8-17
0x18003ca3e  mov     byte ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003ca46  lea     rcx, [rsp+188h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18003ca4e  call    cs:__imp_GetSystemTimeAsFileTime
0x18003ca54  movaps  xmm6, xmmword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime]
0x18003ca5c  movaps  xmmword ptr [rsp+188h+var_D8.dwLowDateTime], xmm6
0x18003ca64  movdqa  xmmword ptr [rsp+188h+ppBuffer], xmm6
0x18003ca6a  movaps  xmmword ptr [rsp+188h+var_128], xmm6
0x18003ca6f  xor     r8d, r8d; unsigned __int16 *
0x18003ca72  xor     edx, edx; psz
0x18003ca74  lea     rcx, [rsp+188h+iid]; lpiid
0x18003ca7c  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18003ca81  nop
0x18003ca82  xor     r8d, r8d; unsigned __int16 *
0x18003ca85  xor     edx, edx; psz
0x18003ca87  lea     rcx, [rsp+188h+var_78]; lpiid
0x18003ca8f  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18003ca94  nop
0x18003ca95  xor     r8d, r8d; unsigned __int16 *
0x18003ca98  xor     edx, edx; psz
0x18003ca9a  lea     rcx, [rsp+188h+var_A0]; lpiid
0x18003caa2  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18003caa7  nop
0x18003caa8  mov     cs:byte_1800BD168, 1
0x18003caaf  mov     byte ptr [rsp+188h+var_E8.dwLowDateTime], 0
0x18003cab7  lea     rcx, [rsp+188h+var_E8.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18003cabf  call    cs:__imp_GetSystemTimeAsFileTime
0x18003cac5  movups  xmm0, xmmword ptr [rsp+188h+var_E8.dwLowDateTime]
0x18003cacd  movups  xmmword ptr [r15+0A8h], xmm0
0x18003cad5  movzx   edx, cs:byte_1800BD168; bool
0x18003cadc  call    ?NotifySleep@Scheduler@@QEAAX_N@Z; Scheduler::NotifySleep(bool)
0x18003cae1  lea     r8, [rsp+188h+var_A0]; struct JobMoniker *
0x18003cae9  lea     rdx, [rsp+188h+ppBuffer]; struct TSTime *
0x18003caee  call    ?GetWakeupCall@Scheduler@@QEAA_NAEAVTSTime@@AEAVJobMoniker@@@Z; Scheduler::GetWakeupCall(TSTime &,JobMoniker &)
0x18003caf3  lea     rdx, [rsp+188h+SystemTimeAsFileTime]
0x18003cafb  lea     rcx, [rsp+188h+var_D8]
0x18003cb03  call    ??OTSTime@@QEBA_NAEBV0@@Z; TSTime::operator>(TSTime const &)
  ... truncated ...
```

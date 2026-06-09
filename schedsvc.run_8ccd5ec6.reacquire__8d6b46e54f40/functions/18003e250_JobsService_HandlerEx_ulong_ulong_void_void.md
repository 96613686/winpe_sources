# JobsService::HandlerEx(ulong,ulong,void *,void *)

- ea: `0x18003e250`
- end: `0x18003ead3`
- name: `?HandlerEx@JobsService@@UEAAKKKPEAX0@Z`
- size: `2179`
- prototype: `unsigned int __usercall@<eax>(JobsService *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, void *@<r9>, void *)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180013a90`
- `0x18001ea40`
- `0x18003e030`
- `0x18003e250`
- `0x18003ebb0`
- `0x18004113c`
- `0x180043478`
- `0x180052a20`
- `0x180052f98`
- `0x180053b68`
- `0x180054108`
- `0x180054644`
- `0x180056954`
- `0x18005c17c`
- `0x18005c1e0`
- `0x18005d470`
- `0x18005dd04`
- `0x18005e0a8`
- `0x1800662cc`
- `0x180066738`
- `0x18006cb18`
- `0x18006cc2c`
- `0x18006ccec`
- `0x180077ea4`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `UBPM!UbpmSessionStateChanged` at `0x18003e496`
- `UBPM!UbpmSessionStateChanged` at `0x18003e56f`
- `UBPM!UbpmSessionStateChanged` at `0x18003e496`
- `UBPM!UbpmSessionStateChanged` at `0x18003e56f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e6ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e761`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e967`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e6ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e761`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e967`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e674`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e674`
- `ntdll!NtSetThreadExecutionState` at `0x18003e9c1`
- `ntdll!NtSetThreadExecutionState` at `0x18003e9c1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18003e5ac`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18003e5ac`

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
        _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800C163C, 0, 0) != 0);
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
        _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800C163C, 0, 0) != 0);
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
        _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800C163C, 0, 0) != 0);
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
  _InterlockedExchange(v25, _InterlockedCompareExchange(&dword_1800C163C, 0, 0) != 0);
  v16 = 0;
  if ( _InterlockedCompareExchange(v25, 0, 0) )
  {
    if ( *((_BYTE *)this + 128) )
    {
      switch ( v6 )
      {
        case 0u:
        case 4u:
          if ( byte_1800C1268 )
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
          byte_1800C1268 = 1;
          LOBYTE(v31[0].dwLowDateTime) = 0;
          GetSystemTimeAsFileTime(&v31[1]);
          *(_OWORD *)((char *)this + 168) = *(_OWORD *)&v31[0].dwLowDateTime;
          Scheduler::NotifySleep(v19, byte_1800C1268);
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
          if ( !byte_1800C1268 )
            goto LABEL_75;
          pBytesReturned[0] = 0;
          _InterlockedExchange((volatile __int32 *)pBytesReturned, 0);
          _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
          _InterlockedExchange(
            (volatile __int32 *)pBytesReturned,
            _InterlockedCompareExchange(&dword_1800C163C, 0, 0) != 0);
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
          if ( byte_1800C1268 )
          {
            byte_1800C1268 = 0;
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
0x18003e250  push    rbx
0x18003e252  push    rsi
0x18003e253  push    rdi
0x18003e254  push    r12
0x18003e256  push    r13
0x18003e258  push    r14
0x18003e25a  push    r15
0x18003e25c  sub     rsp, 150h
0x18003e263  movaps  [rsp+188h+var_48], xmm6
0x18003e26b  mov     rax, cs:__security_cookie
0x18003e272  xor     rax, rsp
0x18003e275  mov     [rsp+188h+var_50], rax
0x18003e27d  mov     rsi, r9
0x18003e280  mov     r14d, r8d
0x18003e283  mov     ebx, edx
0x18003e285  mov     r15, rcx
0x18003e288  mov     r11, [rsp+188h+arg_20]
0x18003e290  xor     r12d, r12d
0x18003e293  mov     [rsp+188h+var_108], r12d
0x18003e29b  mov     edi, r12d
0x18003e29e  mov     [rsp+188h+var_104], r12d
0x18003e2a6  lea     r13, WPP_GLOBAL_Control
0x18003e2ad  mov     r10, cs:WPP_GLOBAL_Control
0x18003e2b4  cmp     r10, r13
0x18003e2b7  jz      short loc_18003E317
0x18003e2b9  test    dword ptr [r10+1Ch], 400h
0x18003e2c1  jz      short loc_18003E317
0x18003e2c3  mov     qword ptr [rsp+188h+var_128], r12
0x18003e2c8  mov     [rsp+188h+ppBuffer], r12
0x18003e2cd  lea     r9, [rsp+188h+ppBuffer]; char **
0x18003e2d2  lea     r8, [rsp+188h+var_128]; char **
0x18003e2d7  mov     edx, r14d; unsigned int
0x18003e2da  mov     ecx, ebx; unsigned int
0x18003e2dc  call    ?ControlEventToStrings@@YAXKKAEAPEBD0@Z; ControlEventToStrings(ulong,ulong,char const * &,char const * &)
0x18003e2e1  cmp     byte ptr [r10+19h], 4
0x18003e2e6  jb      short loc_18003E317
0x18003e2e8  mov     [rsp+188h+var_148], r11
0x18003e2ed  mov     [rsp+188h+var_150], rsi
0x18003e2f2  mov     rax, [rsp+188h+ppBuffer]
0x18003e2f7  mov     [rsp+188h+var_158], rax
0x18003e2fc  mov     [rsp+188h+var_160], r14d
0x18003e301  mov     rax, qword ptr [rsp+188h+var_128]
0x18003e306  mov     [rsp+188h+pBytesReturned], rax
0x18003e30b  mov     r9d, ebx
0x18003e30e  mov     rcx, [r10+10h]
0x18003e312  call    WPP_SF_DsDsqq
0x18003e317  cmp     ebx, 0Dh
0x18003e31a  jz      loc_18003E614
0x18003e320  cmp     ebx, 4
0x18003e323  jz      loc_18003E428
0x18003e329  cmp     ebx, 0Eh
0x18003e32c  jz      loc_18003E512
0x18003e332  cmp     ebx, 10h
0x18003e335  jz      loc_18003E4A7
0x18003e33b  cmp     ebx, 21h ; '!'
0x18003e33e  jz      loc_18003E438
0x18003e344  mov     eax, ebx
0x18003e346  sub     eax, 1
0x18003e349  jz      loc_18003E3F5
0x18003e34f  sub     eax, 1
0x18003e352  jz      short loc_18003E3B4
0x18003e354  sub     eax, 1
0x18003e357  jz      short loc_18003E373
0x18003e359  cmp     eax, 2
0x18003e35c  jz      loc_18003E3F5
0x18003e362  mov     edi, 78h ; 'x'
0x18003e367  mov     [rsp+188h+var_104], edi
0x18003e36e  jmp     loc_18003EA78
0x18003e373  mov     dword ptr [rsp+188h+pBytesReturned], 7530h; unsigned int
0x18003e37b  mov     edx, 5; unsigned int
0x18003e380  mov     r9d, 1; unsigned int
0x18003e386  mov     rcx, r15; this
0x18003e389  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003e38e  mov     rax, [r15]
0x18003e391  mov     rcx, r15
0x18003e394  mov     rax, [rax+30h]
0x18003e398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e39d  mov     dword ptr [rsp+188h+pBytesReturned], r12d; unsigned int
0x18003e3a2  xor     r9d, r9d; unsigned int
0x18003e3a5  mov     edx, 4; unsigned int
0x18003e3aa  mov     rcx, r15; this
0x18003e3ad  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003e3b2  jmp     short loc_18003E428
0x18003e3b4  mov     dword ptr [rsp+188h+pBytesReturned], 7530h; unsigned int
0x18003e3bc  mov     edx, 6; unsigned int
0x18003e3c1  mov     r9d, 1; unsigned int
0x18003e3c7  mov     rcx, r15; this
0x18003e3ca  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003e3cf  mov     rax, [r15]
0x18003e3d2  mov     rcx, r15
0x18003e3d5  mov     rax, [rax+28h]
0x18003e3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3de  mov     dword ptr [rsp+188h+pBytesReturned], r12d; unsigned int
0x18003e3e3  xor     r9d, r9d; unsigned int
0x18003e3e6  mov     edx, 7; unsigned int
0x18003e3eb  mov     rcx, r15; this
0x18003e3ee  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003e3f3  jmp     short loc_18003E428
0x18003e3f5  mov     dword ptr [rsp+188h+pBytesReturned], 7530h; unsigned int
0x18003e3fd  mov     edx, 3; unsigned int
0x18003e402  mov     r9d, 1; unsigned int
0x18003e408  mov     rcx, r15; this
0x18003e40b  call    ?ReportStatusToSCMgr@CNtService@@IEAAHKKKK@Z; CNtService::ReportStatusToSCMgr(ulong,ulong,ulong,ulong)
0x18003e410  mov     rax, [r15]
0x18003e413  mov     edx, r12d
0x18003e416  cmp     ebx, 5
0x18003e419  setz    dl
0x18003e41c  mov     rcx, r15
0x18003e41f  mov     rax, [rax+10h]
0x18003e423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e428  mov     edi, r12d
0x18003e42b  mov     [rsp+188h+var_104], r12d
0x18003e433  jmp     loc_18003EA78
0x18003e438  mov     [rsp+188h+var_138], r12d
0x18003e43d  mov     eax, r12d
0x18003e440  xchg    eax, [rsp+188h+var_138]
0x18003e444  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003e44b  mov     ecx, r12d
0x18003e44e  xor     eax, eax
0x18003e450  lock cmpxchg cs:dword_1800C163C, ecx
0x18003e458  setnz   cl
0x18003e45b  xchg    ecx, [rsp+188h+var_138]
0x18003e45f  mov     ecx, r12d
0x18003e462  xor     eax, eax
0x18003e464  lock cmpxchg [rsp+188h+var_138], ecx
0x18003e46a  jz      def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e470  cmp     [r15+80h], cl
0x18003e477  jnz     short loc_18003E48C
0x18003e479  mov     eax, r12d
0x18003e47c  xchg    eax, [rsp+188h+var_138]
0x18003e480  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003e485  xor     eax, eax
0x18003e487  jmp     loc_18003EA83
0x18003e48c  mov     r8, [rsi+8]
0x18003e490  mov     edx, [rsi+4]
0x18003e493  mov     ecx, r14d
0x18003e496  call    cs:__imp_UbpmSessionStateChanged
0x18003e49d  nop     dword ptr [rax+rax+00h]
0x18003e4a2  jmp     def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e4a7  mov     [rsp+188h+var_138], r12d
0x18003e4ac  mov     eax, r12d
0x18003e4af  xchg    eax, [rsp+188h+var_138]
0x18003e4b3  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003e4ba  mov     ecx, r12d
0x18003e4bd  xor     eax, eax
0x18003e4bf  lock cmpxchg cs:dword_1800C163C, ecx
0x18003e4c7  setnz   cl
0x18003e4ca  xchg    ecx, [rsp+188h+var_138]
0x18003e4ce  mov     ecx, r12d; this
0x18003e4d1  xor     eax, eax
0x18003e4d3  lock cmpxchg [rsp+188h+var_138], ecx
0x18003e4d9  jz      def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e4df  cmp     cs:?g_pScheduler@@3PEAVScheduler@@EA, rcx; Scheduler * g_pScheduler
0x18003e4e6  jz      def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e4ec  cmp     [r15+80h], cl
0x18003e4f3  jnz     short loc_18003E508
0x18003e4f5  mov     eax, r12d
0x18003e4f8  xchg    eax, [rsp+188h+var_138]
0x18003e4fc  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003e501  xor     eax, eax
0x18003e503  jmp     loc_18003EA83
0x18003e508  call    ?NotifyTimeChange@Scheduler@@QEAAXXZ; Scheduler::NotifyTimeChange(void)
0x18003e50d  jmp     def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e512  mov     [rsp+188h+var_138], r12d
0x18003e517  mov     eax, r12d
0x18003e51a  xchg    eax, [rsp+188h+var_138]
0x18003e51e  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003e525  mov     ecx, r12d
0x18003e528  xor     eax, eax
0x18003e52a  lock cmpxchg cs:dword_1800C163C, ecx
0x18003e532  setnz   cl
0x18003e535  xchg    ecx, [rsp+188h+var_138]
0x18003e539  mov     ecx, r12d
0x18003e53c  xor     eax, eax
0x18003e53e  lock cmpxchg [rsp+188h+var_138], ecx
0x18003e544  jz      loc_18003E60F
0x18003e54a  cmp     [r15+80h], cl
0x18003e551  jnz     short loc_18003E566
0x18003e553  mov     eax, r12d
0x18003e556  xchg    eax, [rsp+188h+var_138]
0x18003e55a  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003e55f  xor     eax, eax
0x18003e561  jmp     loc_18003EA83
0x18003e566  xor     r8d, r8d
0x18003e569  mov     edx, [rsi+4]
0x18003e56c  mov     ecx, r14d
0x18003e56f  call    cs:__imp_UbpmSessionStateChanged
0x18003e576  nop     dword ptr [rax+rax+00h]
0x18003e57b  mov     [rsp+188h+var_128], r12d
0x18003e580  mov     [rsp+188h+ppBuffer], r12
0x18003e585  lea     rax, [rsp+188h+ppBuffer]
0x18003e58a  mov     qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003e592  lea     rax, [rsp+188h+var_128]
0x18003e597  mov     [rsp+188h+pBytesReturned], rax; pBytesReturned
0x18003e59c  lea     r9, [rsp+188h+ppBuffer]; ppBuffer
0x18003e5a1  mov     r8d, 5; WTSInfoClass
0x18003e5a7  mov     edx, [rsi+4]; SessionId
0x18003e5aa  xor     ecx, ecx; hServer
0x18003e5ac  call    cs:__imp_WTSQuerySessionInformationW
0x18003e5b3  nop     dword ptr [rax+rax+00h]
0x18003e5b8  test    eax, eax
0x18003e5ba  jz      short loc_18003E601
0x18003e5bc  cmp     [rsp+188h+var_128], 2
0x18003e5c1  jb      short loc_18003E601
0x18003e5c3  mov     rdx, [rsp+188h+ppBuffer]; unsigned __int16 *
0x18003e5c8  test    rdx, rdx
0x18003e5cb  jz      short loc_18003E601
0x18003e5cd  cmp     r12w, [rdx]
0x18003e5d1  jz      short loc_18003E601
0x18003e5d3  mov     rcx, cs:?g_pPseudoEventTrap@@3PEAVPseudoEventTrap@@EA; PseudoEventTrap * g_pPseudoEventTrap
0x18003e5da  test    rcx, rcx
0x18003e5dd  jz      short loc_18003E601
0x18003e5df  cmp     r14d, 5
0x18003e5e3  jnz     short loc_18003E5F4
0x18003e5e5  mov     ecx, [rsi+4]; SessionId
0x18003e5e8  call    ?NotifyLogon@User@@SAXKPEBG@Z; User::NotifyLogon(ulong,ushort const *)
0x18003e5ed  mov     rcx, cs:?g_pPseudoEventTrap@@3PEAVPseudoEventTrap@@EA; this
0x18003e5f4  mov     r8d, [rsi+4]; unsigned int
0x18003e5f8  mov     edx, r14d; unsigned int
0x18003e5fb  call    ?QueueOrProcessSessionChange@PseudoEventTrap@@QEAAXKK@Z; PseudoEventTrap::QueueOrProcessSessionChange(ulong,ulong)
0x18003e600  nop
0x18003e601  lea     rcx, [rsp+188h+SystemTimeAsFileTime]
0x18003e609  call    ??1?$WTSFreeMe@H@tsched@@QEAA@XZ; tsched::WTSFreeMe<int>::~WTSFreeMe<int>(void)
0x18003e60e  nop
0x18003e60f  jmp     def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e614  mov     [rsp+188h+var_138], r12d
0x18003e619  mov     eax, r12d
0x18003e61c  xchg    eax, [rsp+188h+var_138]
0x18003e620  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003e627  mov     ecx, r12d
0x18003e62a  xor     eax, eax
0x18003e62c  lock cmpxchg cs:dword_1800C163C, ecx
0x18003e634  setnz   cl
0x18003e637  xchg    ecx, [rsp+188h+var_138]
0x18003e63b  mov     ecx, r12d
0x18003e63e  xor     eax, eax
0x18003e640  lock cmpxchg [rsp+188h+var_138], ecx
0x18003e646  jnz     short loc_18003E687
0x18003e648  mov     eax, r12d
0x18003e64b  xchg    eax, [rsp+188h+var_138]
0x18003e64f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003e656  mov     eax, ecx
0x18003e658  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x18003e660  cmp     eax, 1
0x18003e663  jnz     short loc_18003E680
0x18003e665  mov     rax, rcx
0x18003e668  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rcx; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x18003e671  mov     rcx, rax; hEvent
0x18003e674  call    cs:__imp_SetEvent
0x18003e67b  nop     dword ptr [rax+rax+00h]
0x18003e680  xor     eax, eax
0x18003e682  jmp     loc_18003EA83
0x18003e687  cmp     [r15+80h], cl
0x18003e68e  jnz     short loc_18003E6A3
0x18003e690  mov     eax, r12d
0x18003e693  xchg    eax, [rsp+188h+var_138]
0x18003e697  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x18003e69c  xor     eax, eax
0x18003e69e  jmp     loc_18003EA83
0x18003e6a3  cmp     r14d, 12h; switch 19 cases
0x18003e6a7  ja      def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e6ad  lea     rdx, __ImageBase
0x18003e6b4  movzx   eax, ds:(byte_18003EAC0 - 180000000h)[rdx+r14]
0x18003e6bd  mov     ecx, ds:(jpt_18003E6C7 - 180000000h)[rdx+rax*4]
0x18003e6c4  add     rcx, rdx
0x18003e6c7  jmp     rcx; switch jump
0x18003e6cd  cmp     cs:byte_1800C1268, 0; jumptable 000000018003E6C7 cases 0,4
0x18003e6d4  jnz     def_18003E6C7; jumptable 000000018003E6C7 default case, cases 1,3,5,8-17
0x18003e6da  mov     byte ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003e6e2  lea     rcx, [rsp+188h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18003e6ea  call    cs:__imp_GetSystemTimeAsFileTime
0x18003e6f1  nop     dword ptr [rax+rax+00h]
0x18003e6f6  movaps  xmm6, xmmword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime]
0x18003e6fe  movaps  xmmword ptr [rsp+188h+var_D8.dwLowDateTime], xmm6
0x18003e706  movdqa  xmmword ptr [rsp+188h+ppBuffer], xmm6
0x18003e70c  movaps  xmmword ptr [rsp+188h+var_128], xmm6
0x18003e711  xor     r8d, r8d; unsigned __int16 *
0x18003e714  xor     edx, edx; psz
0x18003e716  lea     rcx, [rsp+188h+iid]; lpiid
0x18003e71e  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18003e723  nop
0x18003e724  xor     r8d, r8d; unsigned __int16 *
0x18003e727  xor     edx, edx; psz
0x18003e729  lea     rcx, [rsp+188h+var_78]; lpiid
0x18003e731  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18003e736  nop
0x18003e737  xor     r8d, r8d; unsigned __int16 *
0x18003e73a  xor     edx, edx; psz
0x18003e73c  lea     rcx, [rsp+188h+var_A0]; lpiid
0x18003e744  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18003e749  nop
0x18003e74a  mov     cs:byte_1800C1268, 1
0x18003e751  mov     byte ptr [rsp+188h+var_E8.dwLowDateTime], 0
0x18003e759  lea     rcx, [rsp+188h+var_E8.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18003e761  call    cs:__imp_GetSystemTimeAsFileTime
0x18003e768  nop     dword ptr [rax+rax+00h]
0x18003e76d  movups  xmm0, xmmword ptr [rsp+188h+var_E8.dwLowDateTime]
0x18003e775  movups  xmmword ptr [r15+0A8h], xmm0
0x18003e77d  movzx   edx, cs:byte_1800C1268; bool
0x18003e784  call    ?NotifySleep@Scheduler@@QEAAX_N@Z; Scheduler::NotifySleep(bool)
  ... truncated ...
```
